---
title: 試算表財務報告
description: 本文介紹試算表的預設報表。 它還描述了與這些報告相關聯的構建元素，以及如何修改報告以滿足您的業務要求。
author: jinniew
ms.date: 05/26/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerTrialBalanceListPage
audience: Application User
ms.reviewer: roschlom
ms.custom: 12314
ms.assetid: 3b77d6f3-fd07-41a7-9ddb-1b22d1ae33fc
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9bb4977acde8b7a0b2cd6b44c518654fe4a6283b28dfd41216a0173c3aa8b61f
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450606"
---
# <a name="trial-balance-financial-reports"></a>試算表財務報告

[!include [banner](../includes/banner.md)]

本文介紹試算表的預設報表。 它還描述了與這些報告相關聯的構建元素，以及如何修改報告以滿足您的業務要求。 

## <a name="default-trial-balance-reports"></a>預設試算表報告

財務報告中提供了三個試算表報告。

| 預設報表                                 | 它能做什麼                                                                                                                                                                                        |
|------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 預設試算表 - 預設               | 提供所有帳戶的餘額資訊，包括借方和貸方餘額，以及這些餘額的淨值，加上交易日期、憑證和日記帳描述。                  |
| 彙總試算表 - 預設                | 提供所有帳戶的餘額資訊，包括期初和期末餘額、借方和貸方餘額及其淨差額。                                        |
| 彙總年度試算表 - 預設 | 提供所有帳戶的餘額資訊，包括期初和期末餘額、借方和貸方餘額及其現年度與過去年度的淨差額。 |

## <a name="building-blocks"></a>建構元素
試算表財務報告使用以下建構元素。

| 預設報表                                 | 列定義          | 欄定義                              |
|------------------------------------------------|-------------------------|------------------------------------------------|
| 預設試算表 - 預設               | 試算表 - 預設 | 預設試算表 - 預設               |
| 彙總試算表 - 預設                | 試算表 - 預設 | 彙總試算表 - 預設                |
| 彙總年度試算表 - 預設 | 試算表 - 預設 | 彙總年度試算表 - 預設 |

> [!NOTE] 
> 在運行財務報告中的 **試算表** 時，請務必選取 **設定** 索引標籤中 **顯示沒有金額的列** 和 **顯示沒有有效列的報告** 的核取方塊。

### <a name="row-definition"></a>列定義

列定義，試算表 - 預設，包含拉入所有主科目的單列。 因此，任何人都能產生報表，不必進行任何修改。 在檢視報告時，您可以切入到單列以查看每個帳戶的相關詳情。 您可以修改列定義，使其包含更多詳情。 若要修改試算表 - 預設列定義好讓其包含所有科目的列，請執行以下步驟。

1.  按一下 **編輯**，然後按一下 **從維度插入列**。 **從維度插入列** 命令允許您選擇要在列定義中包含的維度。 如需此列定義，您將使用 **主科目**。
2.  確保 **主科目** 包含所有 & 符號，然後按一下 **好的**。

列定義現在包含預設法律實體的所有主科目。

### <a name="column-definition"></a>欄定義

每個試算表報告使用不同的欄定義。 這些欄定義包含不同類型的欄，以提供不同級別的詳情和財務資料。

-   **預設試算表 - 預設欄類型：**
    -   **DESC** – 列定義說明
    -   **ACCT - 科目代碼**
    -   **ATTR (3)** – 屬性：
        -   交易日期
        -   憑證
        -   日記帳描述
    -   **FD** – 僅包含借方的財務資料
    -   **FD** – 僅包含貸方的財務資料
    -   **CALC** – 淨差
-   **彙總試算表 - 預設欄類型：**
    -   **ACCT - 科目代碼**
    -   **DESC** – 列定義說明
    -   **ATTR** – 屬性：
        -   憑證
    -   **FD** – 期初餘額財務資料
    -   **FD** – 僅包含借方的財務資料
    -   **FD** – 僅包含貸方的財務資料
    -   **CALC** – 淨差
    -   **CALC** – 期末餘額
-   **彙總年度試算表 - 預設：**
    -   **ACCT - 科目代碼**
    -   **DESC** – 列定義說明
    -   **ATTR** – 屬性
        -   憑證
    -   **FD** – 本年期初餘額財務資料
    -   **FD** – 僅包含當年借方的財務資料
    -   **FD** – 僅包含當年貸方的財務資料
    -   **CALC** – 淨差
    -   **CALC** – 期末餘額
    -   **FD** – 僅包含去年借方的財務資料
    -   **FD** – 僅包含去年貸方的財務資料

## <a name="additional-resources"></a>其他資源

[財務報告概述](financial-reporting-getting-started.md)

[檢視財務報告](view-financial-reports.md)

[Dynamics Financial Reporting 部落格](https://blogs.msdn.com/b/dynamics_financial_reporting/)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
