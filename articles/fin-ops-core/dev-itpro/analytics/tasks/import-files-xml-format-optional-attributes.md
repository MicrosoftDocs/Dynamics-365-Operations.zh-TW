---
title: (RCS) 使用可選屬性匯入 XML 格式的檔案
description: 本主題提供有關使用者如何設計 ER 格式設定以匯入包含可選屬性的 XML 格式檔案的資訊。
author: NickSelin
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-07-28
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b9447c827a02acb616bbfdcb2c7305e8bdd013c9811e28bb25256db056d85d6a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460459"
---
# <a name="rcs-import-files-in-xml-format-with-optional-attributes"></a>(RCS) 使用可選屬性匯入 XML 格式的檔案

[!include [banner](../../includes/banner.md)]

以下步驟說明了系統管理員或電子報表開發人員角色的使用者如何設計 ER 格式設定以匯出包含可選屬性的 XML 格式的檔案。 若要完成這些步驟，您必須先完成「建立設定提供者並將其標記為有效」程序中的步驟。 在開始之前，從 [Microsoft 下載中心](https://go.microsoft.com/fwlink/?linkid=874684)下載 IncomingDocumentToLearnHowToHandleOptionalAttributes.xml 檔案並將其儲存到本機。

1.    進入 **所有工作區** > **電子報表**。
2.    確保樣本公司 Litware, Inc. 的設定提供者可用並標記為 **作用中**。 如果您沒有看到此設定供應商，請完成程序中的步驟[建立設定供應商並將其標記為有效](er-configuration-provider-mark-it-active-2016-11.md)。
3.    點選 **報表設定**。

## <a name="create-a-new-data-model-configuration"></a>建立新的資料模型設定
1.    點選 **建立設定** 即可打開下拉式對話方塊。
2.    在 **名稱** 欄位，輸入「Model to import xml file」。
3.    點選 **建立設定**。
4.    點選 **設計工具**。
5.    點選 **新增** 打開下拉式對話方塊。
6.    在 **名稱** 欄位，輸入「Root」。
7.    選點 **新增**。
8.    點選 **新增** 打開下拉式對話方塊。
9.    在 **名稱** 欄位，輸入「List」。
10.    在 **項目類型** 欄位中，選取 **記錄清單**。
11.    選點 **新增**。
12.    點選 **新增** 打開下拉式對話方塊。
13.    在 **名稱** 欄位，輸入「Code」。
14.    在 **項目類型** 欄位中，選取 **字串**。
15.    選點 **新增**。
16.    選取 **儲存**。
17.    關閉頁面。
18.    點選 **更改狀態**。
19.    點選 **完成**。
20.    點選 **確定**。

## <a name="create-a-format-for-data-import"></a>建立資料匯出格式
1.    點選 **建立設定** 即可打開下拉式對話方塊。
2.    在 **新建** 欄位中，輸入「Format based on data model Model to import xml file」。
3.    在 **名稱** 欄位，輸入「Format to import xml file」。
4.    在 **支援資料匯出** 欄位中選取 **是**。
5.    點選 **建立設定**。

## <a name="design-a-format-to-parse-incoming-file-in-xml-format"></a>設計一種格式來解析 xml 格式的傳入檔案
1.    點選 **設計工具**。
2.    點選 **新增根** 以開啟下拉式對話方塊。
3.    在樹狀結構中，選取 **XML\元素**。
4.    在 **名稱** 欄位，輸入「root」。
5.    點選 **確定**。
6.    點選 **新增** 以開啟下拉式對話方塊。
7.    在樹狀結構中，選取 **XML\元素**。
8.    在 **名稱** 欄位，輸入「document」。
9.    在 **多重性** 欄位，選取 **一對多**。
10.    點選 **確定**。
11.    在樹狀結構中，選取 **根\文件**。
12.    點選 **新增** 以開啟下拉式對話方塊。
13.    在樹狀結構中，選取 **XML\屬性**。
14.    在 **名稱** 欄位，輸入「ID」。
15.    點選 **確定**。
16.    選取 **儲存**。

## <a name="design-a-format-mapping-to-save-parsed-information-to-data-model"></a>設計格式對應以將解析的資訊儲存到資料模型
1. 點選 **將格式對應到模型**。
2. 點選 **新增**。
3. 在 **定義** 欄位中，輸入或選取值。
4. 在清單中，點選所選資料列中的連結。
5. 在 **名稱** 欄位中，輸入「對應」。
6. 選取 **儲存**。
7. 點選 **設計工具**。
8. 在樹狀結構中，展開 **格式**。
9. 在樹狀結構中，展開 **格式\根：XML 元素(根)**。
10.    在樹狀結構中，選取**格式\根：XML 元素 (根)\文件：XML 元素 1..* (文件)**。
11.    點選 **繫結**。
12.    在樹狀結構中，展開**格式\根：XML 元素 (根)\文件：XML 元素 1..* (文件)**。
13.    在樹狀結構中，選取**格式\根：XML 元素 (根)\文件：XML 元素 1..* (文件)\識別碼**。
14.    在樹狀結構中，展開 **清單 = 格式.根.文件**。
15.    在樹狀結構中，選取 **清單 = 格式.根.文件\代碼**。
16.    點選 **繫結**。
17.    選取 **儲存**。
18.    關閉頁面。
 
## <a name="run-format-mapping"></a>執行格式對應
1. 點選 **執行**。
2. 點選 **瀏覽** 並選取 **IncomingDocumentToLearnHowToHandleOptionalAttributes.xml**。
3. 點選 **確定**。

> [!NOTE]
> 所選檔案尚未匯出，因為格式設計假定「文件」元素存在「識別碼」屬性，但匯出的檔案不包含此類屬性。

## <a name="modify-format-structure-to-handle-xml-attribute-as-optional"></a>修改格式結構以將 xml 屬性作為可選處理
1. 關閉頁面。
2. 在樹狀結構中，展開 **根\文件**。
3. 在樹狀結構中，選取 **根\文件\識別碼**。
4. 在 **遺失屬性的空白字串** 欄位中選取 **是**。
5. 選取 **儲存**。
 
## <a name="run-format-mapping-to-test-changes"></a>執行格式對應以測試更改
1. 點選 **將格式對應到模型**。
2. 點選 **執行**。
3. 點選 **瀏覽** 並選取 **IncomingDocumentToLearnHowToHandleOptionalAttributes.xml** 檔案。
4. 點選 **確定**。
5. 查看產生的檔案。 

> [!NOTE]
> 已匯入相同的檔案，因為格式設計現在將「文件」元素的「id」屬性視為可選。


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]