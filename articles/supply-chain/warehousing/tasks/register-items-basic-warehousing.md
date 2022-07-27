---
title: 使用品項到貨日記帳為基本倉儲啟用的品項登記品項
description: 此程序說明在庫存管理模組中使用「基本倉儲」時如何使用品項到貨日記帳登記物料。
author: Mirzaab
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart, PurchCreateOrder, WMSJournalTable, WMSJournalCreate, PurchEditLines
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 76dd2bfd57db7dfd5c2baf59a864e59a509a64e0
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449043"
---
# <a name="register-items-for-a-basic-warehousing-enabled-item-using-an-item-an-item-arrival-journal"></a>使用品項到貨日記帳為基本倉儲啟用的品項登記品項

[!include [banner](../../includes/banner.md)]

此程序說明在庫存管理模組中使用「基本倉儲」時如何使用品項到貨日記帳登記物料。 這通常由收貨員執行完成。 您可以使用所示的範例值執行 USMF 公司示範資料的程序。  如果您不使用 USMF，則在開始本指南前，您需要有一個已確認的訂購單，其中包含未結訂購單明細。 明細中的品項必須有庫存。 而且品項需與儲存維度群組相關聯，其中站點和倉庫都是有效的。


## <a name="create-item-arrival-journal-header"></a>建立品項到貨日記帳標頭
1. 前往庫存管理 > 日記帳分錄 > 品項到貨 > 品項到貨。
2. 按一下 [新增]。
3. 在名稱欄位中，輸入一個值。
    * 如果您使用 USMF，則可以輸入 WHS。 如果您使用其他資料，您選擇的日記帳名稱必須具有以下屬性：檢查揀料地點必須設定為「否」，以及「隔離管理」必須設定為「否」。  
4. 在「裝箱單」欄位中，輸入一個值。
    * 這是廠商簽發裝箱單中的裝箱單識別碼。 新增唯一編號。  
5. 在「編號」欄位中，在「編號」欄位中，選擇採購單。
6. 按一下 [確定]。

## <a name="add-lines-to-item-arrival-journal"></a>在品項到貨日記帳中新增明細
1. 按一下 [功能]。
2. 按一下 [建立明細]。
    * 可以在此日記帳中手動輸入明細，也可以自動建立明細。 這將展示如何自動建立明細。  
3. 勾選或取消勾選「初始化數量」核取方塊。
    * 這將用採購單明細未登記的數量初始化日記帳明細上的數量。  
4. 按一下 [確定]。

## <a name="post-the-journal"></a>過帳日記帳
1. 按一下 [過帳]。
2. 按一下 [確定]。

## <a name="generate-the-product-receipt"></a>產生產品收貨
1. 按一下 [功能]。
2. 按一下 [產品收貨]。
3. 按一下 [確定]。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]