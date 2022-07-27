---
title: 在運輸管理中對帳運費
description: 本主題說明運費對帳流程。
author: Henrikan
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TMSAuditMaster, TMSFreightBillInvoiceReconcile, TMSFreightBillSummary, TMSFreightBillType, TMSFreightMatchReason, TMSFBDetailReconcile, TMSInvoiceTable,TMSInvoiceLineReconcile,TMSReconcileInvoice, TMSFreightBillDetail, TMSFreightBillTypeAssignment, TMSRejectInvoiceLine, TMSMiscellaneousCharge
audience: Application User
ms.reviewer: kamaybac
ms.custom: 89983
ms.assetid: bc34a9b1-0c11-4797-b463-25409cf98ca8
ms.search.region: Global
ms.search.industry: Distribution
ms.author: henrikan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a63bfd34860c6a7c34cbc526c6a621cbc9666efc
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448767"
---
# <a name="reconcile-freight-in-transportation-management"></a>在運輸管理中對帳運費

[!include [banner](../includes/banner.md)]

本主題說明運費對帳流程。

貨運對帳可以手動完成，也可以設定為自動進行。 若要使用自動運費對帳，您必須設定一個審核主檔案，在其中可以定義確定自動比對哪些運費單的條件。

## <a name="the-freight-reconciliation-process"></a>運費對帳流程

運費費率由與相關承運業者相關聯的費率引擎來計算。 確認負載後，會產生運費帳單，運費費率將被轉移到該帳單。 根據用於常規請款程序的設定，運費費率作為雜項費用分攤到相關的來源文件 (訂購單、銷售訂單和/或移轉訂單)。 從承運業者收到運費發票後，就立即可以開始運費對帳流程 (這也稱為比對流程)。 可以透過電子方式或紙本形式接收發票。 如果收到紙本發票，可以使用運費帳單作為範本產生電子發票。

[![運費對帳流程。](./media/freight-reconcilation-process.jpg)](./media/freight-reconcilation-process.jpg)

## <a name="manual-reconciliation"></a>手動對帳

如果要手動對帳運費，必須將每個發票明細與一個或多個已開票負載的運費帳單明細進行比對。 您在 **運費帳單和發票比對** 頁面進行此比對。 如果發票明細上的金額與運費帳單金額不相符，則必須為差異選擇對帳原因。 如果有多個對帳原因，您可以將不相符的金額拆分到它們之中。 對帳原因決定如何在總分類帳中過帳差異金額。 當對整個發票金額進行對帳時，提交金額以供核准，然後過帳日記帳。 下圖顯示如何產生運費發票和執行運費對帳。

[![運費對帳任務。](./media/processflowforfreightreconciliation.jpg)](./media/processflowforfreightreconciliation.jpg)

## <a name="automatic-reconciliation"></a>自動對帳

若要使用自動對帳，您必須指定對帳計劃和發票，以及要使用的裝運承運業者。 發票明細和運費帳單的比對是根據審核主檔案和運費帳單類型的設定而進行完成的。 執行自動對帳後，必須處理所有系統不能比對的發票。 然後，您必須手動處理這些發票，然後才能過帳所有付款發票。

## <a name="match-freight-bills-with-freight-invoices-using-automatic-or-manual-reconciliation"></a>使用自動或手動對帳將比對運費帳單與運費發票

*比對* 是查找與每張運費發票對應的運費帳單之流程。 這可以透過逐一比對發票明細 (手動比對) 或一次比對所有可用發票 (自動比對) 來完成。

### <a name="auto-matching"></a>自動比對

比對多個運費發票與同一運費帳單時，自動比對的流程如下：

1. 所有未比對的運費發票按金額排序，最上方為金額最大的。
1. 逐一比對運費發票，直到運費帳單上沒有剩餘的正數金額。
1. 根據審核主檔案的設定和運費發票上的剩餘金額，設定剩餘金額。

### <a name="manual-matching"></a>手動比對

所有金額為正的運費帳單都可用於比對。 與自動比對類似，使用者只能將負金額的運費發票與未完全比對的運費帳單進行比對。

### <a name="example"></a>範例

假設您有一個金額為 1500 的運費帳單 (FB)，並且已為該運費帳單建立三個運費發票，每個發票有一個發票明細，並進行以下設定：

- 原始運費帳單 (FB)：金額 1500
- 發票 1 (Inv1)：金額 1000
- 發票 2 (Inv2)：金額 600
- 發票 3 (Inv3)：金額 -100

#### <a name="automatic-matching-result"></a>自動比對結果

自動比對將按以下順序執行：

1. 按金額降序排列所有運費發票：Inv1 -> Inv2 -> Inv3。
1. 比對 Inv1 與 FB。 Inv1 已比對了 1000，FB 還剩餘 500，所以狀態設定為 *已部分比對*。
1. 比對 Inv2 與 FB。 Inv2 已比對了 500，FB 還剩餘 0，所以狀態設定為 *已全部比對*。
1. 因為 FB 現在完全比對，所以不會處理 Inv3。

#### <a name="manual-matching-result"></a>手動比對結果

對於手動比對，結果會根據比對的順序而有所不同，如以下範例所示。

##### <a name="manual-matching-case-1"></a>手動比對案例 1

一種手動比對本範例的方法如下：

1. 比對 FB 與 Inv1。 FB 還剩餘 500，所以狀態設定為 *已部分比對*。
1. 比對 Inv2 與 FB。 Inv2 已比對了 500，FB 還剩餘 0，所以狀態設定為 *已全部比對*。
1. 手動比對 Inv3 時，您將找不到任何未比對的運費帳單。

這種情況與自動比對基本相同

##### <a name="manual-matching-case-2"></a>手動比對案例 2

另一種手動比對本範例的方法如下：

1. 比對 Inv3 與 FB。 現在 FB 有剩餘 1600 的金額，這與在 1500 的基礎上減去負 100 相同。 FB 和 Inv3 的已比對數量均為 -100。
1. 依次將 Inv1 和 Inv 2 與 FB 比對。 FB 已完全比對。

如本範例所示，具有負金額的運費發票僅應手動比對。 這樣能確保始終可以將具有負金額的運費發票與未完全比對的運費帳單進行匹配，因為這讓您可以控制比對順序。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]