---
title: 將設定上傳到 Lifecycle Services
description: 本主題說明如何建立新的電子報表 (ER) 設定並將其上傳到 Microsoft Dynamics Lifecycle Services (LCS)。
author: NickSelin
ms.date: 06/17/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionCreateDropDialog, ERDataModelDesigner, ERDataModelContentsItemCreationDialog, ERSolutionRepositoryTable, ERSolutionRepositoryCreateDropDialog, ERSolutionImport
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b480351875c7d300db790a68d61a402218f8ee36d8247188b912762f21d035b3
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460514"
---
# <a name="upload-a-configuration-into-lifecycle-services"></a>將設定上傳到 Lifecycle Services

[!include [banner](../../includes/banner.md)]

本主題說明系統管理員或電子報表開發人員角色的使用者如何建立新的[電子報表 (ER) 設定](../general-electronic-reporting.md#Configuration)並將其上傳到 Microsoft Dynamics Lifecycle Services (LCS) 中的[專案級資產庫](../../lifecycle-services/asset-library.md)。

> [!IMPORTANT]
> 已[棄用](../../../../finance/get-started/removed-deprecated-features-finance.md#features-removed-or-deprecated-in-the-finance-10017-release) LCS 作為 ER 設定的存放庫。 如需相關資訊，請參閱[Regulatory Configuration Service (RCS) - Lifecycle Services (LCS) 儲存棄用](../../../../finance/localizations/rcs-lcs-repo-dep-faq.md)。

在此範例中，您將為名為 Litware, Inc 的樣本公司建立設定並將其上傳到 LCS。這些步驟可以在任何公司中完成，因為 ER 設定在公司之間共用。 若要完成這些步驟，您必須先完成[建立設定提供者並將它們標記為作用中](er-configuration-provider-mark-it-active-2016-11.md)中的步驟。 還需要存取 LCS。

1. 使用以下角色之一登入應用程式：

    - 電子報表開發人員
    - 系統管理員

2. 進入 **組織管理**\>**工作區**\>**電子報表**。
3. 選取 **Litware, Inc.**，並將其標記為 **作用中**。
4. 選取 **設定**。

<a name="accessconditions"></a>
> [!NOTE]
> 確保目前 Dynamics 365 Finance 使用者是 LCS 專案的成員，該專案包含用於匯入 ER 設定的[資產庫](../../lifecycle-services/asset-library.md#asset-library-support)。
>
> 您不能從代表與 Finance 使用領域不同的 ER 資源庫存取 LCS 專案。 如果您嘗試，將顯示 LCS 專案的空白清單，並且您將無法從 LCS 中的專案級資產庫匯入 ER 設定。 若要從用於匯入 ER 設定的 ER 存放庫存取專案級資產庫，請使用屬於為其設定目前 Finance 實體的租使用者 (領域) 的使用者的憑據登入到 Finance。

## <a name="create-a-new-data-model-configuration"></a>建立新的資料模型設定

1. 進入 **組織管理\>電子報表\>設定**。
2. 在 **設定** 頁面上，選取 **建立設定** 以打開下拉式對話方塊。

    在此範例中，您將建立一個設定，其中包含電子文件的樣本資料模型。 此資料模型設定稍後將上傳到 LCS。

3. 在 **名稱** 欄位中，輸入 **Sample model configuration**。
4. 在 **描述** 欄位中，輸入 **Sample model configuration**。
5. 選取 **建立設定**。
6. 選取 **模型設計工具**。
7. 選取 **新增**。
8. 在 **名稱** 欄位中，輸入 **Entry point**。
9. 選取 **新增**。
10. 選取 **儲存**。
11. 關閉頁面。
12. 選取 **更改狀態**。
13. 選取 **完成**。
14. 選取 **確定**。
15. 關閉頁面。

## <a name="register-a-new-repository"></a>註冊新的存放庫

1. 進入 **組織管理\>工作區\>電子報表**。

2. 在 **設定提供者** 區段，選取 **Litware, Inc.** 圖格。

3. 在 **Litware, Inc.** 圖格上，選取 **存放庫**。

    您現在可以打開 Litware, Inc. 設定提供者的存放庫清單。

4. 選取 **新增** 打開下拉式對話方塊。

    您現在可以新增新存放庫。

5. 在 **設定存放庫輸入** 中，選取 **LCS**。
6. 選取 **建立存放庫**。
7. 在 **專案** 欄位中，輸入或選取一個值。

    對於此範例，選取所需的 LCS 專案。 您必須已經[存取](#accessconditions)該專案。

8. 選取 **確定**。

    完成一個新的存放庫分錄。

9. 在清單中，標示選取的列。

    在此範例中，選取 **LCS** 存放庫記錄。

    請注意，已註冊的存放庫由目前提供者標記。 換句話說，只有該提供者擁有的設定才能放入此存放庫中，並因此上傳到選定的 LCS 專案中。

10. 請選取 **打開**。

    您打開存放庫以查看 ER 設定清單。 如果所選專案尚未用於 ER 設定分享，則清單將為空白。

11. 關閉頁面。
12. 關閉頁面。

## <a name="upload-a-configuration-into-lcs"></a>將設定上傳到 LCS

1. 進入 **組織管理\>電子報表\>設定**。
2. 在 **設定** 頁面上，在設定樹狀結構中，選取 **樣本模型設定**。

    您必須選取一個已經完成的建立設定。

3. 在清單中，尋找並選取所需的記錄。

    對於此範例，請選取狀態為 **已完成** 的已選取設定版本。

4. 選取 **更改狀態**。
5. 選取 **分享**。

    當設定在 LCS 中發佈時，設定的狀態會從 **已完成** 更改為 **共用**。

6. 選取 **確定**。
7. 在清單中，尋找並選取所需的記錄。

    對於此範例，請選取狀態為 **共用** 的設定版本。

    請注意，所選版本的狀態已從 **已完成** 到 **共用**。

8. 關閉頁面。
9. 選取 **存放庫**。

    您現在可以打開 Litware, Inc. 設定提供者的存放庫清單。

10. 請選取 **打開**。

    在此範例中，選取 **LCS** 存放庫，並將它開啟。

    請注意，所選設定顯示為所選 LCS 專案的資產。

11. 前往<https://lcs.dynamics.com>即可開啟 LCS。
12. 打開之前用於存放庫註冊的專案。
13. 打開專案的資源庫。
14. 選取 **GER 設定** 資產類型。

    應列出您上傳的 ER 設定。

    請注意，如果廠商有權存取此 LCS 專案，則可以將上傳的 LCS 設定匯入另一個實體。


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
