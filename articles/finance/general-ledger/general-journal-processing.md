---
title: 普通日記帳處理
description: 本主題說明 Microsoft Dynamics 365 Finance 的功能可以幫助簡化普通日記帳的處理作業，也可以幫助確保擷取正確資料且不損害內部控制。
author: kweekley
ms.date: 02/28/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalSetup, LedgerJournalTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7096d8576cf124e5e1d814c360d96639f66a742a
ms.sourcegitcommit: 753714ac0dabc4b7ce91509757cd19f7be4a4793
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/01/2022
ms.locfileid: "8451659"
---
# <a name="general-journal-processing"></a>普通日記帳處理

[!include [banner](../includes/banner.md)]

本主題說明各項功能有助於讓普通日記帳的處理作業更加簡單輕鬆，也能確保擷取正確資料且不損害內部控制。  

## <a name="journal-names"></a>日記帳名稱

要設定的其中一個最重要部份是日記帳名稱。 為每個目的定義特定的日記帳名稱是個好主意，例如公司間、累計調整和錯誤更正。 您可以制訂每個日記帳名稱，有助於讓每種用途的資料分錄簡單、安全。 

請在 **日記帳名稱** 頁上設定下列元素：

-   **工作流程核准**– 為了加強內部控制，定義日記帳工作流程，根據借方總額等標準基礎建立審查與核准步驟的重大限制。 您在 **總帳工作流程** 頁針對普通日記帳設定工作流程。
-   **預設值**– 為抵銷科目、貨幣和財務維度選取預設值。
-   **日記帳控制**– 您可以為公司和科目類型設限，也可以為區段值設限。 

**範例**

日記帳名稱只能用於調整。 此時您可以指明只有 **總帳** 科目類型對所有公司有效。 

[![日記帳控制科目類型](./media/journal-control-account-types1.png)](./media/journal-control-account-types1.png)

日記帳名稱只能用於特定區段或主科目範圍。 

[![日記帳控制區段。](./media/journal-control-segment1.png)](./media/journal-control-segment1.png)

**自動沖銷** 選項可在普通日記帳中使用。 例如，您有實際文件尚未處理的累計調整，圖示說明如下。
[![普通日記帳沖銷。](./media/general-journal-reversing1.png)](./media/general-journal-reversing1.png) 

Microsoft Excel 日記帳分錄增益集提供額外自動化層級，讓資料分錄工作變得更容易。 **在 Excel 打開行項資料** 動作可在 **普通日記帳** 和 **日記帳憑證** 頁執行。 

您可以在 **定期日記帳** 頁設定定期日記帳自動處理日記帳。 

您可以隨時使用憑證範本。 **普通日記帳** 頁面上，**儲存** 和 **選取憑單範本** 動作可在憑單行項 **功能** 下方的  **日記帳憑單** 頁面上找到。

## <a name="related-setup"></a>相關設定
下列設定並非普通日記帳的特定部份，但將有助於確保資料分錄正確和簡單。

### <a name="main-account"></a>主科戶

主科目設定為普通日記帳處理提供許多選項：

-   **DC/CR 要求** – 如果主科目僅限於借記或貸記交易，請使用此選項。 驗證或過帳日記帳時會驗證設定。

-   **預設抵銷科目**
-   **已暫停** – 暫停所有公司或特定公司/法人實體的資料分錄主科目。
-   **不允許人工分錄** – 防止用戶在日記帳以人工方式輸入科目的數值。
-   **預設/驗證貨幣**
-   **法人實體覆寫** – 此設定特定於定義的公司/法人實體：
    -   **預設/驗證銷售稅**
    -   **預設維度** – **非固定** 或 **固定值**。 **固定值** 將有助於確保此主科目的所有過帳始終使用設定為 **固定** 的任何維度值。
-   **過帳驗證**
    -   **用戶驗證** – 此選項控制被允許過帳到主科目的用戶。
    -   **過帳類型驗證** – 此選項控制主科目允許的過帳類型。

### <a name="accounting-structures-and-advanced-rules-structures"></a>會計結構和進階規則結構

會計結構和進階規則結構對於確保普通日記帳處理和任何文件記錄期間擷取財務報表和績效追蹤所需的資料非常重要。 會計結構和進階規則結構讓您制訂資料分錄體驗。 您可以只允許資料分錄用於每種財務維度相關情況，也可以強制要求始終擷取必要的準確資料。

有關詳細資訊，請參閱下列主題：
- [計劃您的會計科目表](plan-chart-of-accounts.md) 
- [為日記帳建立進階規則](tasks/create-advanced-rules-journals.md)
- [使用範本建立日記帳分錄](tasks/create-journal-entry-template.md)
- [建立和驗證日記帳](tasks/create-validate-journals.md)
- [過帳定期日記帳](tasks/post-periodic-journals.md)
- [流程總帳分配日記帳](tasks/process-ledger-allocation-journal.md)

## <a name="simulate-posting"></a>模擬過帳
您可以在大多數日記帳的 **驗證** 選單上找到 **模擬過帳**。 當您使用 **驗證** 功能驗證日記帳時，系統會測試日記帳的特定錯誤條件。 如果您使用 **模擬過帳** 功能，系統會執行過帳期間執行的所有相同流程，不會實際過帳日記帳。 您可以回顧顯示的過帳訊息，修正您發現的任何錯誤，然後打開 **過帳** 選單進行日記帳的過帳。 

批次處理無法使用 **模擬過帳** 功能。 然而可以使用代碼進行批次過帳，開發人員會擴展代碼以新增該功能。  

## <a name="journal-unlock"></a>日記帳解鎖
日記帳頁面上有按鈕解鎖“被系統鎖定”狀態設定為“是”的日記帳。 此解鎖按鈕可由已經分析任何正在執行的批次工作，並且確認此日記帳不再由批次工作主動處理的系統管理員執行。 此按鈕由 **功能管理** 頁上，名為 **日記帳解鎖按鈕** 的功能啟用。 

## <a name="workflow-recall"></a>工作流程重新叫用 
在狀態是 "不可恢復" 的 **工作流程** 中重新叫用日記帳的能力可藉由日記帳上的按鈕和 **工作流程歷程記錄** 頁上的按鈕啟用。 這是由 **功能管理** 頁上，名為 **重設日記帳的工作流程狀態** 的功能啟用。

## <a name="delete-journal-lines"></a>刪除日記帳行項
快速刪除所有日記帳行項的功能是在 **功能** > **刪除日記帳行項** 下方的日記帳中啟用。 若要啟用此功能，請在 **功能管理** 上選取 **刪除日記帳效能優化**。 此功能會影響 **LedgerJournalTrans** 表格上的擴充功能，它的 **刪除** 方法因為行項集合已被移除，因此不調用每一行項的 **刪除** 方法。 


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
