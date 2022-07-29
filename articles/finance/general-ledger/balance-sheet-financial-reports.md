---
title: 資產負債表財務報表
description: 本文介紹資產負債表的預設報表。 它還說明與本報表相關聯的建構元素。
author: jcart1106
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: FinanicalReports
audience: Application User
ms.reviewer: roschlom
ms.custom: 12274
ms.assetid: 52f78229-f531-4d16-b337-e2628994acb6
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b0fae7ccb216ced0cbcbdb69980b3bae754a4980ecaf9314893368ae89459fa0
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450342"
---
# <a name="balance-sheet-financial-reports"></a>資產負債表財務報表

[!include [banner](../includes/banner.md)]

本文介紹資產負債表的預設報表。 它還說明與本報表相關聯的建構元素。 

## <a name="default-balance-sheet-reports"></a>預設資產負債表報表

有兩個預設的資產負債表報表。 在一份報表中，這些區段是堆疊的。 在另一份報表中，這些區段是並排的。

| 預設報表                       | 它有什麼功能                                                                                                                           |
|--------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------|
| 資產負債表 - 預設              | 提供組織當年財務狀況的檢視表。                                                                 |
| 並排資產負債表 - 預設 | 提供組織當年財務狀況的檢視表。 資產和負債與股東權益並列。 |

## <a name="building-blocks"></a>建構元素
資產負債表財務報表使用以下建構元素。

| 預設報表                       | 列定義                       | 欄定義             |
|--------------------------------------|--------------------------------------|-------------------------------|
| 資產負債表 - 預設              | 資產負債表 - 預設              | YTD 和 差異- 預設    |
| 並排資產負債表 - 預設 | 並排資產負債表 - 預設 | 年初至今欄 - 預設 |

### <a name="row-definition"></a>列定義

兩個資產負債表報表的列定義都包含傳統資產負債表每個部分的區段。 並排報表包括分欄符，以便負債和擁有者權益顯示在資產旁邊。 主科目類別維度用來建構兩個列定義。 因此，任何人都能產生報表，不必進行任何修改。

### <a name="column-definition"></a>欄定義

欄位定義包含不同類型的欄位，提供不同等級的細節和財務資料。

-   **YTD 和差異 – 預設欄類型：**
    -   **DESC** – 列定義說明
    -   **FD** – 當年度的年初至今財務資料
    -   **FD** – 上一年度的年初至今財務資料
    -   **CALC** – 從今年減去去年所得的差異

<!-- -->

-   **年初至今欄 - 預設：**
    -   **DESC** – 列定義說明
    -   **FD** – 當年度的年初至今財務資料



## <a name="additional-resources"></a>其他資源

[財務報表概觀](financial-reporting-getting-started.md)

[檢視財務報表](view-financial-reports.md)

[Dynamics Financial Reporting 部落格](https://blogs.msdn.com/b/dynamics_financial_reporting/)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]