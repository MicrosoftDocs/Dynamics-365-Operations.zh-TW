---
title: 為一次性供應商創建採購訂單
description: 此程序說明如何為一次性供應商創建訂購單。
author: Henrikan
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart, PurchCreateOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e89a9d1b382efa3b90b8d70e84777321e9595f4a
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449226"
---
# <a name="create-a-purchase-order-for-a-one-time-supplier"></a>為一次性供應商創建採購訂單

[!include [banner](../../includes/banner.md)]

此程序說明如何為一次性供應商創建訂購單。 供應商會隨訂購單自動創建，無須手動創建廠商帳戶。 訂購單通常由採購代理人創建。 此指南中的範例說明，可用於 USMF 示範資料公司。 先決條件是在付款帳戶參數頁面中，設置一次性廠商帳戶。


## <a name="create-a-purchase-order-for-a-one-time-supplier"></a>為一次性供應商創建採購訂單
1. 前往採購和開源 > 訂購單 > 所有訂購單。
2. 按一下新增。
3. 在一次性供應商字段中選擇是。
    * 會自動創建廠商帳務，然後指派至訂購單。 廠商帳戶會根據付款帳戶參數頁面中，一般索引標籤指定的範本創建。  
4. 在名稱欄位中，鍵入供應商名稱。
5. 按一下確定。
    * 現在，可以像其他訂單一樣，完成和處理訂購單。 如何完成之間沒有特殊字元。 發票會計算與訂單一起創建的廠商帳戶中的到期交易，然後處理付款。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]