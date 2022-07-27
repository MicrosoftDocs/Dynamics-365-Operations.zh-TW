---
title: 從設定服務的全域存放庫下載 ER 設定
description: 本主題說明如何從設定服務的全域存放庫下載電子報表 (ER) 設定。
author: NickSelin
ms.date: 06/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionImport, ERWorkspace, ERSolutionRepositoryTable
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 105843
ms.assetid: dc44dea2-22ce-401e-98b9-d289e0e2825b
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 32eb5206fadefbd024f2dd2af888d166c81b950f
ms.sourcegitcommit: 25b3dd639e41d040c2714f56deadaa0906e4b493
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/06/2021
ms.locfileid: "8460498"
---
# <a name="download-er-configurations-from-the-global-repository-of-configuration-service"></a>從設定服務的全域存放庫下載 ER 設定

[!include [banner](../includes/banner.md)]

本主題說明如何從設定服務的全域存放庫下載[電子報表 (ER) 設定](general-electronic-reporting.md#Configuration)。 如需相關資訊，請參閱[Microsoft Dynamics 365 for Finance and Operations - Regulatory Services，設定服務](/business-applications-release-notes/october18/dynamics365-finance-operations/regulatory-service-configuration)。

## <a name="open-configurations-repository"></a>開啟設定存放庫

1. 使用以下角色之一登入 Dynamics 365 Finance 應用程式：

    - 電子報表開發人員
    - 電子報表函數
    - 系統管理員

2. 進入 **組織管理 > 工作區 > 電子報表**。
3. 在 **設定提供者** 區段，選取 **Microsoft** 圖格。
3. 在 **Microsoft** 圖格上，選取 **存放庫**。

    ![電子報表工作區](./media/er-download-configurations-global-repo-er-workspace.png)

4. 在 **設定存放庫** 頁面上，在格線中，選取 **全域** 類型的現有存放庫。 如果此存放庫未出現在格線中，請執行以下步驟：

    1. 選取 **新增** 以新增新存放庫。
    2. 選取 **全域** 作為存放庫類型，然後選取 **建立存放庫**。
    3. 如果出現提示，請按照授權說明進行操作。
    4. 輸入存放庫的名稱和說明，然後選取 **確定** 以確認新的存放庫條目。
    5. 在格線中，選取 **全域** 類型的新存放庫。

5. 選取 **開啟** 以查看所選存放庫的 ER 設定清單。

    ![設定存放庫頁面。](./media/er-download-configurations-global-repo-repositories-list.png)

## <a name="import-a-single-configuration"></a>匯入單一設定

1. 在 **設定存放庫** 頁面，在設定樹狀結構中，選取所需的 ER 設定。
2. 在 **版本** FastTab 上，選取所選 ER 設定的所需版本。
3. 選取 **匯入** 將所選版本從全域存放庫下載到現行 Finance 實體。

    > [!NOTE]
    > 對於現行 Finance 實體中已經存在的 ER 設定版本而言，**匯入** 按鈕不可用。

    ![設定存放庫頁面，設定 FastTab。](./media/er-download-configurations-global-repo-repository-content.png)

## <a name="import-filtered-configurations"></a>匯入過濾的設定

1. 在 **設定存放庫** 頁面，在設定樹狀結構中，展開 **過濾器** FastTab。
2. 在 **標籤** 格線中，新增任何需要的標籤。
3. 在 **國家/地區適用性** 欄位，選取適當的國家/地區代碼，然後選取 **套用過濾器**。

    > [!NOTE]
    > **設定** FastTab 顯示所有滿足指定選取條件的設定。

4. 在 **設定** FastTab，選取 **進口** 將過濾後的設定從全域存放庫下載到現行實體。
5. 在 **設定** FastTab，選取 **重設過濾器** 清理指定的選取條件。

    ![設定存放庫頁面、版本 FastTab、匯入按鈕。](./media/er-download-configurations-global-repo-filtered-configurations.png)

> [!NOTE]
> 根據 ER 設定，設定在匯入後進行驗證。 您可能會收到有關發現的任何不一致問題的通知。 您必須先解決問題，然後才能使用匯入的設定版本。 如需相關資訊，請參閱本主題的相關資源清單。

> [!NOTE]
> ER 設定可以設定為相依性於其他設定。 因此，連同選定的設定，可能會自動匯入其他設定。 如需設定相依性性的相關資訊，請參閱[定義 ER 設定對其他組件的相依性](tasks/er-define-dependency-er-configurations-from-other-components-july-2017.md)。

## <a name="additional-resources"></a>其他資源

[電子報表 (ER) 概觀](general-electronic-reporting.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
