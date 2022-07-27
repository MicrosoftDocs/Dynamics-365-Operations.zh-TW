---
title: 成本項目
description: 本文提供有關成本項目及其建立時間的資訊。 成本條目是記錄特定事件的數量和成本的記錄。
author: AndersGirke
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventCostOnhandItem
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19131
ms.assetid: dd2663d8-bcc0-47b1-b36d-57433143487c
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 53e2dd7375daf0d33ff61b870fecfdaa44dd0838
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448857"
---
# <a name="cost-entries"></a>成本項目

[!include [banner](../includes/banner.md)]

本文提供有關成本項目及其建立時間的資訊。 成本條目是記錄特定事件的數量和成本的記錄。

成本項目是記錄在活動財務庫存維度上之庫存交易的彙總。

## <a name="examples"></a>範例
### <a name="example-1-no-cost-entries-are-created"></a>範例 1：不建立成本項目

已登記轉移日記帳事件。 該事件將一件物料 A 從位置 A 轉移到位置 B。位置庫存維度不被視為成本物件的一部分。 因此，該事件會建立兩個庫存交易並且沒有成本項目。

### <a name="example-2-cost-entries-are-created"></a>範例 2：建立成本項目

已登記轉移日記帳事件。 該事件將一件物料 A 從站點 1 轉移到站點 2。 站點庫存維度被視為成本物件的一部分。 因此，該事件會建立兩個庫存交易以及兩個成本項目。

### <a name="example-3-one-cost-entry-is-created"></a>範例 3：建立一個成本項目

為訂購單登記了產品接收事件。 該事件以 10.00 美元 (USD) 的單價登記 100 件物料 A。 因為物料 A 使用序號來追蹤庫存管理的目的，所以為每個收到的物料建立一個唯一的序號。 因此，該事件會建立 100 個庫存交易和一個成本項目。

## <a name="cost-entries-page"></a>成本項目頁面
新的 **成本項目** 頁面可讓您查看和控制數量和成本的登記。 本頁面補充了 **庫存交易** 和 **庫存結算** 頁面。 記錄按事件的時間順序登記。 因此，您可以快速查找和控制與特定事件 (或與文件相關之所有事件) 的累積成本。 範例如下：

-   為項目 A 記錄產品接收事件。以 10.00 美元的單位成本接收一百件。
-   發票事件登記幾天後，成本增加到 11.00 美元。 因此，總金額為 1,100 美元。 建立第二個憑單以說明 100 美元的差異。
-   幾天後，用於支付運輸成本的雜項收費 15.00 美元在採購單上登記。

| 憑單 | 日期       | 參考      | 號碼 | 批次識別碼  | 數量 | 金額  |
|---------|------------|----------------|--------|---------|---------------|----|
| 00001   | 01-01-2015 | 訂購單 | 100001 | 0000101 | 100.00   | 1000.00 |
| 00002   | 20-01-2015 | 訂購單 | 100001 | 0000101 |          | 100.00  |
| 00003   | 31-01-2015 | 調整     | 100001 | 0000101 |          | 15.00   |

**成本項目** 頁面可文件識別碼和文件日期進行篩選。 

> [!NOTE]
> 成本項目僅適用於[成本物件](cost-object.md)或已發佈的產品。

## <a name="additional-resources"></a>其他資源

[成本物件](cost-object.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]