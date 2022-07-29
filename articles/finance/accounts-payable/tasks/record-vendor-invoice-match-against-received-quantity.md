---
title: 記錄廠商發票並且比對收到的數量
description: 當您從廠商處收到訂購單上的貨物或服務的發票時，業務流程可能要求先接收貨物或服務，然後才能核准發票以進行付款。
author: ShivamPandey-msft
ms.date: 02/11/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PurchTable, PurchCreateOrder, PurchEditLines, VendEditInvoice, VendEditInvoiceDefaultQuantityForLinesDropDialog,  VendJournalMatch_PackingSlip, VendInvoiceMatchingDetails
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8a3f1463821a43af0d8d5f15225944b080414e4c
ms.sourcegitcommit: 3105642fca2392edef574b60b4748a82cda0a386
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/12/2022
ms.locfileid: "8451554"
---
# <a name="record-vendor-invoice-and-match-against-received-quantity"></a>記錄廠商發票並且比對收到的數量

[!include [banner](../../includes/banner.md)]

當您從廠商處收到訂購單上的貨物或服務的發票時，業務流程可能要求先接收貨物或服務，然後才能核准發票以進行付款。 在開始之前，請確保已選取發票比對組態金鑰。 

確保選取 **應付帳款參數** 頁的 **啟用發票比對驗證** 選項、**過帳差額發票** 欄位設定為 **需要核准** 及 **明細比對政策** 欄位設定為 **三向比對**。

此程序使用的是 USMF 示範公司。 應付帳款經理或會計經理角色將執行這些步驟。


## <a name="create-a-purchase-order"></a>建立採購訂單
1. 前往所有訂購單。
2. 點選 **新增**。
3. 在 **廠商科目** 欄位，點選下拉式按鈕打開查閱功能。
4. 在 **廠商帳戶** 欄位中，輸入一個值。
5. 點選 **確定**。
6. 點選 **新增行項**。
7. 在 **品項編號** 欄位中，輸入一個值。
8. 在「動作窗格」上，按一下 **採購**。
9. 點選 **確認**。

## <a name="post-a-product-receipt"></a>過帳產品收據
1. 在動作窗格上，點選 **收件**。
2. 點選 **產品收據**。
3. 在清單中，標示選取的列。
4. 在 **產品收據** 欄位，輸入一個值。
5. 點選 **確定**。

## <a name="record-and-match-a-vendor-invoice-to-a-product-receipt"></a>記錄廠商發票並將其與產品收據比對
1. 請在動作窗格上點選 **發票** 。
2. 點選 **發票**。
3. 在 **編號** 欄位，輸入一值。
4. 按一下 **預設：訂購數量** 以打開拖曳對話方塊。
5. 在 **預設行數量** 欄位中，選取一個選項。
6. 點選 **確定**。
7. 點選 **是**。
8. 按一下 **比對產品收據**。
9. 點選 **確定**。
10. 在動作窗格上，按一下 **審核**。
11. 點選 **比對細節**。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
