---
title: 將財務維度新增到 CFO 工作區
description: 本主題說明如何將財務維度新增到 CFO 工作區，以便其可用於分類帳和預算報表。
author: aprilolson
ms.date: 08/01/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14091
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 3acff8a0cf36ee6958effd9c5384895df20c180499437c43feddce31c884dbbf
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450303"
---
# <a name="add-financial-dimensions-to-the-cfo-workspace"></a>將財務維度新增到 CFO 工作區

[!include [banner](../includes/banner.md)]

本主題說明如何將財務維度新增到財務長 CFO 工作區，以便將其用於分類帳和預算報表。 CFO 工作區具有 **概觀** 索引標籤和 **財務** 所以標籤。這兩個索引標籤上的報表由以下兩個測量值支援：LedgerActivityMeasure 和 BudgetActivityMeasure。 這兩個測量與 DimensionCombinationEntity 實體之間存在關係。 因此，您可以選擇維度。

1. 在 Finance 的 **實體店** 頁面中，更新 **LedgerActivityMeasure** 和 **BudgetActivityMeasure** 測量。
2. 在 Microsoft Visual Studio 中打開 Application Explorer，然後搜尋 **LedgerCFO**。
3. 在 **資源** 下，打開 **LedgerCFOWorkspacePBIX**。
4. 資源在 Microsoft Power BI Desktop 中打開時，依次選擇 **取得資料**、**SQL Server 資料庫** 和 **連線**。
5. 輸入伺服器名稱，然後輸入 **AxDW** 作為資料庫。 選擇 **DirectQuery**，然後選擇 **確定**。
6. 搜尋並選擇 **LedgerActivityMeasure\_DimensionCombination**，然後選擇 **載入**。

    > [!TIP]
    > 在 **欄位** 清單，重新命名 **財務維度** 資料表，以便於識別。

7. 選擇 **管理關係**，然後選擇 **新增**。
8. 在第一個欄位中，選擇 **總帳活動**，然後選擇 **LedgerDimension**。
9. 在第二個欄位中，選擇 **LedgerActivityMeasure\_DimensionCombination** (如果重新命名了資料表，則選擇 **財務維度**)。 選擇 **DimensionCombinationRECID** 標題。
10. 在 **基數** 欄位，選擇 **多對一**。
11. 將 **跨篩選方向** 值變更為 **單一**。
12. 同時選擇 **使此關係可用** 和 **假設參考完整性**，選擇 **確定**，然後選擇 **關閉**。

    [![建立關係。](./media/Create-relationship.png)](./media/Create-relationship.png)

13. 在 **欄位** 清單中，應該可以看到資料表和可用的財務維度。 將所需的財務維度拖曳到報表級篩選。
14. 儲存您的變更。
15. 在應用程式物件樹 (AOT) 中，對專案按滑鼠右鍵，然後選擇 **同步**。
16. 組建您的專案，然後打開應用程式以查看結果。

    [![完整的工作區。](./media/workspace.png)](./media/workspace.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]