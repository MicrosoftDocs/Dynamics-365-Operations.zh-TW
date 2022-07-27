---
title: 在採購訂單上記錄收貨
description: 本主題說明如何直接在採購訂單上記錄收貨。
author: Henrikan
ms.date: 07/09/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart, PurchCreateOrder, InventItemIdLookupPurchase, PurchEditLines
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5ec37082ffa7816d1b07cadc595eec6e8373920a
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8447810"
---
# <a name="record-the-receipt-of-goods-on-the-purchase-order"></a>在採購訂單上記錄收貨

[!include [banner](../../includes/banner.md)]

本主題說明如何直接在採購訂單上記錄收貨。 也可以在倉庫登記產品收貨，之後再記錄到採購訂單中。 此任務通常由採購代理人或應付帳款協調員完成。 此指南中的範例說明，可用於 USMF 示範資料公司。 此範例包括建立簡單採購訂單的步驟，以便您將此程序作為任務指南執行。 如果您將此程序用在自己的資料中，則可以從 **記錄收貨** 子任務開始著手。


## <a name="prepare-a-new-purchase-order-for-receipt-of-goods"></a>準備新的採購訂單以收貨
1. 移至前往 **功能窗格 > 模組 > 採購及開源 > 採購訂單 > 所有採購訂單**。
2. 選取 **新增**。
3. 在 **廠商帳戶** 欄位中輸入 `US-101`。
4. 選取 **確定**。
5. 在 **品項編號** 欄位中輸入 `M0001`。
6. 在 **數量** 欄位中，輸入 `5`。
7. 在動作窗格中選取 **購買**。
8. 選取 **確認**。

## <a name="record-receipt-of-goods"></a>記錄收貨
1. 在動作窗格中選取 **接收**。
2. 選擇 **產品收貨**。 **數量** 欄位用於為要接收的數量選擇不同的選項。 例如，如果某個數量以前在倉庫中已登記，可以選擇 **登記數量**。 對於此範例，請使用 **訂購數量** 的值。
3. 展開 **概覽** 區段。
4. 在 **產品收貨** 欄位，輸入任意值。 此欄位用於輸入將用作產品收貨日記帳憑證的參考。  
5. 展開 **明細** 區段。
6. 將 **數量** 設為「4」。 您可以在此處手動指定訂單中各明細將收到的數量。  
7. 選取 **確定**。 貨物現在已在購買退貨單上記錄為已收穫，並已建立產品收貨日記帳以反映此資訊。 您可以使用產品收貨操作，來查看使用訂購單建立的日記帳，並查看收到的內容以及時間。  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]