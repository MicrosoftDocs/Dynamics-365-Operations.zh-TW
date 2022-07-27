---
title: 從 Lifecycle Services 匯入設定
description: 本主題介紹如何從 Microsoft Dynamics Lifecycle Services (LCS) 匯入新版本的電子報表 (ER) 設定。
author: NickSelin
ms.date: 06/17/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionRepositoryTable, ERSolutionImport
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 05a8ad127df177c54e67ff1f2ddcd8b3a3f51ea12b6e11d087105bd74b6bdb3f
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460462"
---
# <a name="import-a-configuration-from-lifecycle-services"></a>從 Lifecycle Services 匯入設定

[!include [banner](../../includes/banner.md)]

本主題說明系統管理員或電子報表開發人員角色的使用者如何從 Microsoft Dynamics Lifecycle Services (LCS) 中的[專案級資產庫](../../lifecycle-services/asset-library.md)匯入新版本的[電子報表 (ER) 設定](../general-electronic-reporting.md#Configuration)。

> [!IMPORTANT]
> 已[棄用](../../../../finance/get-started/removed-deprecated-features-finance.md#features-removed-or-deprecated-in-the-finance-10017-release) LCS 作為 ER 設定的存放庫。 如需相關資訊，請參閱[Regulatory Configuration Service (RCS) - Lifecycle Services (LCS) 儲存棄用](../../../../finance/localizations/rcs-lcs-repo-dep-faq.md)。

在此範例中，您將選取所需版本的 ER 設定並將其匯入名為 Litware, Inc 的樣本公司。這些步驟可以在任何公司中完成，因為 ER 設定在公司之間共用。 若要完成這些步驟，您必須先完成[將設定上傳到 Lifecycle Services](er-upload-configuration-into-lifecycle-services.md) 中的步驟。 還需要存取 LCS。

1. 使用以下角色之一登入應用程式：

    - 電子報表開發人員
    - 系統管理員

2. 進入 **組織管理**\>**工作區**\>**電子報表**。
3. 選取 **設定**。

<a name="accessconditions"></a>
> [!NOTE]
> 確保現行 Dynamics 365 Finance 使用者是 LCS 專案的成員，該項目包含使用者想要[存取](../../lifecycle-services/asset-library.md#asset-library-support)以匯入 ER 設定的資產庫。
>
> 您不能從代表與 Finance 使用領域不同的 ER 資源庫存取 LCS 專案。 如果您嘗試，將顯示 LCS 專案的空白清單，並且您將無法從 LCS 中的專案級資產庫匯入 ER 設定。 若要從用於匯入 ER 設定的 ER 存放庫存取專案級資產庫，請使用屬於為其設定目前 Finance 實體的租使用者 (領域) 的使用者的憑據登入到 Finance。

## <a name="delete-a-shared-version-of-a-data-model-configuration"></a>刪除資料模型設定的共用版本

1. 在 **設定** 頁面上，在設定樹狀結構中，選取 **樣本模型設定**。

    在完成[將設定上傳到 Lifecycle Services](er-upload-configuration-into-lifecycle-services.md)中的步驟後，您建立了樣本資料模型設定的第一個版本並將其發佈到 LCS。 在此程序中，您將刪除該版本的 ER 設定。 然後，您將在本主題後面部分從 LCS 匯入該版本。

2. 在清單中，尋找並選取所需的記錄。

    對於此範例，請選取狀態為 **共用** 的設定版本。 此狀態表示設定已發佈到 LCS。

3. 選取 **更改狀態**。
4. 選取 **中止**。

    透過將所選版本的狀態從 **共用** 更改為 **中止**，您可以使該版本可供刪除。

5. 選取 **確定**。
6. 在清單中，尋找並選取所需的記錄。

    對於此範例，請選取狀態為 **中止** 的設定版本。

7. 選取 **刪除**。
8. 選取 **是**。

    請注意，所選資料模型設定的唯一草稿版本 2 現在可用。

9. 關閉頁面。

## <a name="import-a-shared-version-of-a-data-model-configuration-from-lcs"></a>從 LCS 匯入資料模型設定的共用版本

1. 進入 **組織管理\>工作區\>電子報表**。

2. 在 **設定提供者** 區段，選取 **Litware, Inc.** 圖格。

3. 在 **Litware, Inc.** 圖格上，選取 **存放庫**。

    您現在可以打開 Litware, Inc. 設定提供者的存放庫清單。

4. 請選取 **打開**。

    在此範例中，選取 **LCS** 存放庫，並將它開啟。 您必須有權[存取](#accessconditions) LCS 專案和所選 ER 存放庫可存取的資產庫。

5. 在清單中，標示選取的列。

    對於本範例，在版本清單中選取 **樣本模型設定** 的第一個版本。

6. 選取 **匯入**。
7. 選取 **是** 以確認從 LCS 匯入所選版本。

    一條資訊性訊息確認所選版本已成功匯入。

8. 關閉頁面。
9. 關閉頁面。
10. 選取 **設定**。
11. 在樹狀結構中，選取 **樣本資料模型**。
12. 在清單中，尋找並選取所需的記錄。

    對於此範例，請選取狀態為 **共用** 的設定版本。

    請注意，所選資料模型設定的共享版本 1 現在也可用。


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
