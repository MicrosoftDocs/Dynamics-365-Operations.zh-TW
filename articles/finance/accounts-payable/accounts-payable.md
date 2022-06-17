---
title: 應付帳款首頁
description: 本主題提供應付帳款的概觀。
author: sunfzam
ms.date: 02/15/2019
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: VendInvoiceWorkspace
audience: Application User
ms.reviewer: roschlom
ms.custom:
- "21901"
- intro-internal
ms.assetid: 1e4c2ac4-077b-4678-8733-5cec8f6ff659
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: ce768ecaa668f2c69d6753401eaa145b6fddc5ec
ms.sourcegitcommit: e40a9fac5bac9f57a6dcfe73a1f21856eab9b6a9
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/02/2021
ms.locfileid: "8452898"
---
# <a name="accounts-payable-home-page"></a>應付帳款首頁

[!include [banner](../includes/banner.md)]

本主題提供應付帳款的概觀。 

您可以手動輸入廠商發票或透過資料實體以電子方式接收發票。 輸入或接收發票後，您可以使用發票審核日記帳或 **廠商發票** 頁面來審閱和核准發票。 您可以使用發票比對、廠商發票政策和工作流程將審閱流程自動化，使符合特定條件的發票能夠自動獲得核准，並標記剩餘的發票以供授權使用者進行審閱。

**商務程序**

[![商務程序圖。](./media/AP-process.PNG)](./media/AP-process.PNG)

## <a name="set-up-accounts-payable"></a>設定應付帳款

設定廠商群組、廠商、過帳設定檔、各種付款選項以及有關廠商、費用、交貨和目的地、本票和其他類型的應付帳款資訊的參數。 

[設定應付帳款概觀](accounts-payable-overview.md)

[廠商發票的會計分配和子分類帳日記帳分錄](accounting-distributions-subledger-journal-entries-vendor-invoices.md) 

[應付帳款和應收帳款的外幣重估](../cash-bank-management/foreign-currency-revaluation-accounts-payable-accounts-receivable.md)

## <a name="configure-vendor-invoices"></a>設定廠商發票

使用應付帳款來追蹤發票和支付給廠商的支出。

[應付帳款發票比對概觀](accounts-payable-invoice-matching.md)

[廠商過帳設定檔](vendor-posting-profiles.md)

[設定應付帳款發票比對驗證](tasks/set-up-accounts-payable-invoice-matching-validation.md)

[三向比對原則](three-way-matching-policies.md)

[發票比對和公司內部訂購單](invoice-matching-intercompany-purchase-orders.md)

[解析發票總額比對時的差異](resolve-invoice-totals-invoice-matching-discrepancies.md)

[廠商發票日記帳和發票審核日記帳的預設沖銷帳戶](default-offset-accounts-vendor-invoice-journals.md)

[行動發票審核](mobile-invoice-approvals.md)

[廠商集合開立發票工作區](vendor-portal-invoicing-workspace.md)

[廠商發票自動化](vendor-invoice-automation.md)

## <a name="configure-vendor-payments"></a>設定供應商付款 

將系統定義的付款類型 (例如支票、電子付款或本票) 指派至任何使用者定義的付款方式。 付款類型是選擇性的，但它們在您驗證電子付款並希望能夠快速確定付款使用的付款類型時很有用。 

[廠商付款工作區](vendor-payments-workspace.md)

[定義廠商的付款費用](tasks/define-vendor-payment-fees.md)

[定義廠商的付款條款](tasks/define-vendor-payment-terms.md)

[票據審核概觀](positive-pay-overview.md)

[設定並產生票據審核檔案](set-up-generate-positive-pay-files.md)

[使用付款提案建立廠商付款方式](create-vendor-payments-payment-proposal.md)

[廠商支付部分付款金額](vendor-payments-partial-amount.md)

[廠商付款取得比已計算折扣更多的折扣](take-discount-more-calculated-discount-vendor-payment.md)

[非現金折扣期間取得現金折扣](take-cash-discount-outside-cash-discount-timeframe.md)

[電子報表廠商支票樣本](electronic-reporting-sample-vendor-checks.md)

[還原廠商的付款](reverse-vendor-payment.md)

[預付款發票與預付款](prepayments-invoices-vs-prepayments.md)

[應付帳款的集中付款](centralized-payments-accounts-payable.md)

## <a name="settlements"></a>結算

以下主題提供有關結算的資訊。 結算是用發票結算付款的過程。 

[設定結算方式](../cash-bank-management/configure-settlement.md)

[在折扣日期前結算部分廠商付款並在折扣日期後支付尾款](settle-partial-vendor-payment-before-discount-or-final-payment-after.md)

[結算在貸項通知單上有折扣的部分廠商付款](settle-partial-vendor-payment-discounts-vendor-credit-notes.md)

[結算有多個折扣期間的部分廠商付款](settle-partial-vendor-payment-multiple-discount-periods.md)

[結算部分廠商付款並在折扣日期前付清尾款](settle-partial-vendor-payment-or-final-payment-before-discount.md)

[具有多個客戶或廠商記錄的單一憑單](single-voucher-multiple-customer-vendor-records.md)



### <a name="additional-resources"></a>其他資源

#### <a name="whats-new-and-in-development"></a>新增功能和開發中的功能

前往 [Microsoft Dynamics 365 發行計劃](/dynamics365/release-plans/)查看規劃的新功能。 

#### <a name="blogs"></a>部落格

您可以在 [Microsoft Dynamics 365 部落格](https://community.dynamics.com/b/msftdynamicsblog?c=Enterprise)和 [Microsoft Dynamics 365 Finance- 財務部落格](https://community.dynamics.com/365/financeandoperations/b/financials)上尋找有關應付帳款和其他解決方案的意見、新聞和其他資訊。

[Microsoft Dynamics Operations 合作夥伴社群部落格](https://community.dynamics.com/partner/b/operationspartnercommunityblog)為 Microsoft Dynamics 合作夥伴提供可從中了解 Dynamics 365 中的新功能和趨勢的單一資源。

#### <a name="community-blogs"></a>社群部落格

[如何在 Dynamics 365 Finance 中管理應付帳款](https://financefunction.tech/2019/02/15/how-to-manage-payables-in-dynamics-365-for-finance-and-operations)

#### <a name="task-guides"></a>工作指南
應用程式內有以工作指南提供的額外協助。 要存取工作指南，請按一下任何頁面上的說明按鈕。

#### <a name="videos"></a>影片

瞧瞧在 [Microsoft Dynamics 365 YouTube 頻道](https://www.youtube.com/channel/UCJGCg4rB3QSs8y_1FquelBQ)上現在推出的操作影片。






[!INCLUDE[footer-include](../../includes/footer-banner.md)]
