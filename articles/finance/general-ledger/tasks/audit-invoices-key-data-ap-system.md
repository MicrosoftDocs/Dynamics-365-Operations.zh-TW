---
title: 稽核應付帳款中的發票和關鍵資料
description: 本主題介紹如何稽核應付帳款中的發票和關鍵資料。
author: kweekley
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PurchTable, PurchCreateOrder, PurchEditLines, VendEditInvoice, VendEditInvoiceDefaultQuantityForLinesDropDialog,  VendJournalMatch_PackingSlip, VendInvoiceMatchingDetails
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f49f8c87f628d68f2c7f355b93cdf5e0a9403251
ms.sourcegitcommit: 62ca651c94e61aaa69cfa59e861f263f89d01c4a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/03/2021
ms.locfileid: "8451260"
---
# <a name="audit-invoices-and-key-data-in-accounts-payable"></a>稽核應付帳款中的發票和關鍵資料

[!include [banner](../../includes/banner.md)]

當您從廠商處收到訂購單上的貨物或服務的發票時，業務流程可能要求先接收貨物或服務，然後才能核准發票以進行付款。 在開始之前，請確保已選取發票比對組態金鑰。 

在 **應付帳款參數** 頁面，請確定選取「啟用發票比對驗證」選項，將 **過帳發票差異** 欄位設為 **需要核准**，**行比對原則** 欄位設為 **三向比對**。

此程序使用的是 USMF 示範公司。 應付帳款經理或會計經理角色將執行這些步驟。


## <a name="create-a-purchase-order"></a>建立採購訂單
1. 前往 **所有訂購單**。
2. 按一下 **新增**。
3. 在 **廠商帳戶** 欄位中，輸入一個值。
4. 按一下 **確定**。
5. 按一下 **新增行**。
6. 在 **品項編號** 欄位中，輸入一個值。
7. 在「動作窗格」上，按一下 **採購**。
8. 按一下 **確認**。

## <a name="post-a-product-receipt"></a>過帳產品收據
1. 在動作窗格上，點選 **收件**。
2. 按一下 **產品收據**。
3. 在 **產品收據** 欄位，輸入一個值。
4. 按一下 **確定**。

## <a name="record-and-match-a-vendor-invoice-to-a-product-receipt"></a>記錄廠商發票並將其與產品收據比對
1. 在動作窗格上，點選 **發票 > 發票**。
2. 在 **編號** 欄位，輸入一值。
3. 按一下 **預設：訂購數量** 以打開拖曳對話方塊。
4. 在 **預設行數量** 欄位中，選取一個選項。
5. 按一下 **確定**。
6. 按一下 **是**。
7. 按一下 **比對產品收據**。
8. 按一下 **確定**。
9. 在動作窗格上，按一下 **審核**。
10. 按一下 **比對詳細資料**。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
