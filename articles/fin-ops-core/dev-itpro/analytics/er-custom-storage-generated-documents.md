---
title: 為產生的文件指定自訂儲存位置
description: 本主題說明如何擴展電子報表 (ER) 格式產生的文件的儲存位置清單。
author: NickSelin
ms.date: 02/22/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-3-31
ms.dyn365.ops.version: 10
ms.openlocfilehash: 61a1e46497d650e2c063a5fe7537d17cf7aa1828a5a4504bb781e84aeb88f04a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460417"
---
# <a name="specify-a-custom-storage-location-for-generated-documents"></a>為產生的文件指定自訂儲存位置

[!include[banner](../includes/banner.md)]

電子報告 (ER) 架構的應用程式程式編寫介面 (API) 允許您擴展 ER 格式產生的文件的儲存位置清單。 本主題概述了新增自訂儲存位置必須完成的主要工作。

## <a name="prerequisites"></a>先決條件

您必須部署支援持續構建的拓撲。 (如需相關資訊，請參閱[部署支援持續構建和測試自動化的拓撲](/dynamics365/unified-operations/dev-itpro/perf-test/continuous-build-test-automation)。) 您必須有權存取此拓撲以獲得以下角色之一：

- 電子報表開發人員
- 電子報表函數
- 系統管理員

您還必須有權存取此拓撲的開發環境。

## <a name="create-or-import-an-er-format-configuration"></a>建立或匯入 ER 格式設定

在現行拓撲中，[建立新的 ER 格式](tasks/er-format-configuration-2016-11.md)以產生您計畫為其新增自訂儲存位置的文件。 或者，[將現有的 ER 格式匯入此拓撲](general-electronic-reporting-manage-configuration-lifecycle.md)。

![格式設計工具頁面。](media/er-extend-file-storages-format.png)

> [!IMPORTANT]
> 您建立或匯入的 ER 格式必須至少包含以下格式元素之一：
>
> - 檔案
> - 資料夾
> - 合併
> - 附件

## <a name="create-a-new-document-type"></a>建立新的文件類型

若要指定如何路由 ER 格式產生的文件，您必須設定[電子報表 (ER) 目的地](electronic-reporting-destinations.md)。 在設定為將產生的文件儲存為檔案的每個 ER 目標中，您必須指定文件管理架構的文件類型。 不同的文件類型可用於路由不同 ER 格式產生的文件。

1. 為您之前建立或匯入的 ER 格式新增新的[文件類型](../../fin-ops/organization-administration/configure-document-management.md)。 在下圖中，文件類型為 **FileX**。
2. 若要將此文件類型與其他文件類型區分開來，請在其名稱中包含特定關鍵字。 例如，在下圖中，名稱為 **(LOCAL) folder**。
3. 在 **類別** 欄位中，指定 **附加檔案**。
4. 在 **分組** 欄位中，指定 **檔案**。

![檔案類型頁面。](media/er-extend-file-storages-document-type.png)

> [!NOTE]
> 文件類型為公司專用。 若要在多個公司中使用具有已設定目標的 ER 格式，您必須在每個公司中設定單獨的文件類型。

## <a name="review-source-code"></a>查看原始程式碼

查看 **ERDocuManagement** 類的 **insertFile()** 方法的代碼。 請注意，在產生的檔案附加到記錄時會引發 **AttachingFile()** 事件。


```xpp
/// <summary>
/// Inserts file as attachment in Document Management.
/// </summary>
/// <param name = "_owner">A record as the attachment owner.</param>
/// <param name = "_stream">The file stream.</param>
/// <param name = "_filePath">The file path with name.</param>
/// <param name = "_attachmentName">The name of file attachment.</param>
/// <returns>The reference to inserted file.</returns>
[Hookable(false)]
public DocuRef insertFile(
    Common _owner, 
    System.IO.Stream _stream, 
    str _filePath, 
    str _attachmentName, 
    DocuTypeId _docuTypeId)
{
    DocuRef docuRef;
    if (_stream)
    {
        DocuType::createDefaults();
        if (!this.isDocuTypeValid(_docuTypeId))
        {
            throw error(strFmt("@ElectronicReporting:DocuTypeIsNotValid", _docuTypeId));
        }
        var args = ERDocuManagementAttachingFileEventArgs::construct(_owner, _stream, _filePath, _attachmentName, _docuTypeId);
        ERDocuManagementEvents::onAttachingFile(args);
        if (args.isHandled())
        {
            docuRef = args.getDocuRef();
        }
        else
        {
            docuRef = this.attachFile(_owner, _stream, _filePath, _attachmentName, _docuTypeId);
        }
    }
    return docuRef;
}
```

處理以下 ER 目的地時會引發 **AttachingFile()** 事件：

- **封存** – 使用此目的地時，將在 ERFormatMappingRunJobTable 表中建立正在執行的 ER 格式的新記錄。 此記錄中的 **已封存** 欄位設定為 **False**。 如果 ER 格式成功執行，產生的文件將附加到該記錄，並引發 **AttachingFile()** 事件。 在此 ER 目標中選取的文件類型決定了附件的儲存位置 (Microsoft Azure儲存體或微軟 SharePoint 資料夾)。
- **作業封存** – 使用此目的地時，將在 ERFormatMappingRunJobTable 表中建立正在執行的格式的新記錄。 此記錄中的 **已封存** 欄位設定為 **True**。 如果 ER 格式成功執行，產生的文件將附加到該記錄，並引發 **AttachingFile()** 事件。 在 ER 參數中設定的文件類型決定了附加檔案的儲存位置 (Azure 儲存體或 SharePoint 資料夾)。

![電子報表參數頁面。](media/er-extend-file-storages-parameters.png)

## <a name="configure-an-er-destination"></a>設定 ER 目的地

1. 為您建立或匯入的 ER 格式的上述元素 (檔案、資料夾、合併或附件) 之一設定存檔目的地。 如需相關指導，請參閱[ER 設定目的地](/dynamics365/unified-operations/dev-itpro/analytics/tasks/er-destinations-2016-11)。
2. 使用您之前為設定的目標新增的文件類型。 (對於本主題中的範例，文件類型為 **FileX**。)

![目的地設定對話方塊。](media/er-extend-file-storages-destination.png)

## <a name="modify-source-code"></a>修改原始程式碼

1. 向您的 Microsoft Visual Studio 項目新增一個新類別，並編寫代碼來訂閱前面提到的 **AttachingFile()** 事件。 (如需所使用的可擴展性模式的相關資訊，請參閱[使用 EventHandlerResult 回應](/dynamics365/unified-operations/dev-itpro/extensibility/respond-event-handler-result)。) 例如，在新類別中，編寫執行以下操作的代碼：

    1. 將產生的檔案儲存在執行應用程式對象伺服器 (AOS) 服務的伺服器的本地檔案系統的資料夾中。
    2. 僅當新文件類型 (例如，**FileX** 名稱中包含「(LOCAL)」關鍵字的類型) 在將檔案附加到 ER 執行作業記錄中的記錄時使用。

    ```xpp
    class ERDocuSubscriptionSample
    {
        void new()
        {
        }
        [SubscribesTo(classStr(ERDocuManagementEvents), 
        staticDelegateStr(ERDocuManagementEvents, 
        attachingFile))]
        public static void ERDocuManagementEvents_attachingFile(ERDocuManagementAttachingFileEventArgs _args)
        {
            if (!_args.isHandled())
            {
                DocuType docuType = DocuType::find(_args.getDocuTypeId());
                if (strContains(docuType.Name, '(LOCAL)'))
                {
                    _args.markAsHandled();
                    var stream = _args.getStream();
                    if (stream.CanSeek)
                    {
                        stream.Seek(0, System.IO.SeekOrigin::Begin);
                    }
                    using (var localStream = System.IO.File::OpenWrite(@'c:\0\' + _args.getAttachmentName()))
                    {
                        stream.CopyTo(localStream);
                    }
                }
            }
        }
    }
    ```

2. 重建您的專案。

## <a name="run-the-er-format-that-you-created-or-imported"></a>執行您建立或匯入的 ER 格式

1. 執行您建立或匯入的 ER 格式
2. 進入 **組織管理\>電子報表\>電子報表作業**。 尋找為此執行作業建立的記錄，並且附加了產生的檔案。
3. 探索本地 **C:\\0** 資料夾以找到相同的產生檔案。

## <a name="additional-resources"></a>其他資源

- [電子報表 (ER) 目的地](electronic-reporting-destinations.md)
- [可擴展性首頁](../extensibility/extensibility-home-page.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]