---
title: 正確的庫存追蹤資訊
description: 本程序將引導您完成建立和過帳庫存轉移日記帳以庫存追蹤資訊的過程。
author: yufeihuang
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventJournalTransfer, InventJournalCreate, InventItemIdLookupSimple, InventBatchIdLookup, InventLocationIdLookup, InventDimTracking, InventTrans
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 69921651ecd0969e9cdd3cdd3740db212a1953e1
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448656"
---
# <a name="correct-inventory-tracking-information"></a>正確的庫存追蹤資訊

[!include [banner](../../includes/banner.md)]

本程序將引導您完成建立和過帳庫存轉移日記帳以庫存追蹤資訊的過程。 在此範例中，我們將登記錯誤的批次更改為另一個批次來更新批次控管項目的資訊。 您能以示範資料公司 USPI 或自己的資料，逐步瞭解此程序。 如果您使用自己的資料，需要有一個啟用批次的項目，並且不能是由位置控制。 在開始之前，您也需要為庫存轉移設定庫存日記帳名稱。 這些工作通常由倉庫員工執行。


## <a name="create-an-inventory-transfer-journal"></a>建立庫存轉移日記帳
1. 前往轉移。
2. 按一下新增。
3. 在名稱欄位中，輸入或選擇一個值。
4. 按一下確定。

## <a name="create-journal-lines"></a>建立日記帳明細
1. 按一下新增。
2. 在品項編號欄位中，輸入或選擇一個值。
    * 如果您使用的是 USPI，請選擇項目 M5003。  
3. 在數量欄位中，輸入一個數字。
4. 按一下庫存維度索引標籤。
5. 在批號欄位中，輸入或選擇一個值。
6. 在站點欄位中，輸入或選擇一個值。
7. 在倉庫欄位中，輸入或選擇一個值。
8. 在批號欄位中，輸入或選擇一個值。

## <a name="post-the-journal"></a>過帳日記帳
1. 按一下過帳。
2. 按一下確定。

## <a name="check-tracing-information"></a>檢查追蹤資訊
1. 按一下庫存。
2. 按一下追蹤。
3. 按一下確定。
    * 使用此追蹤資訊，您可以追溯您從哪個批次更正了庫存。  您也可以使用項目追蹤頁面查看此資訊。  
4. 關閉頁面。

## <a name="check-inventory-transactions"></a>檢查庫存交易
1. 按一下庫存。
2. 按一下交易。
    * 在這裡，您可以查看日記帳過帳時建立的交易。   



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]