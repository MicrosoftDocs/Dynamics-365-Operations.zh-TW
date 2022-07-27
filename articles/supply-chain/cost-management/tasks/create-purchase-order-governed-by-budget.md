---
title: 創建受預算控制的訂購單
description: 使用此程序來創建可用於預算檢查的訂購單。
author: AndersGirke
ms.date: 06/20/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2e2bfec4d7d38ef95d1f0ce3bd89938337ecf731
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448476"
---
# <a name="create-a-purchase-order-governed-by-budget"></a>創建受預算控制的訂購單

[!include [banner](../../includes/banner.md)]

使用此程序來創建可用於預算檢查的訂購單。 此錄製內容使用 USMF 示範資料公司。


## <a name="review-the-budget-control-configuration"></a>查看預算控制設定
1. 前往預算 > 設定 > 預算控制 > 預算控制設定。
2. 按一下預算基金可用索引標籤。
3. 按一下文件和日記錄索引標籤。
4. 按一下定義預算控制規則索引標籤。
5. 按一下定義預算控制群組索引標籤。
6. 關閉頁面。

## <a name="create-the-purchase-order-header"></a>創建訂購單標題
1. 前往採購和開源 > 訂購單 > 所有訂購單。
2. 按一下新增。
3. 在廠商帳戶欄位中，輸入或選擇一個值。
4. 展開一般區段。
5. 在帳戶日期欄位中，將日期設定為「2016-01-01」。
6. 按一下確定。

## <a name="add-a-purchase-order-line"></a>新增訂購單明細
1. 在採購類別欄位中，輸入或選擇一個值。
2. 將數量設為「2」。
3. 在單位欄位中，輸入或選擇一個值。
4. 將單價設為「10000」。
5. 按一下財務。
6. 按一下經銷商金額。
7. 在分類帳科目欄位中，指定值為「601300-001-023--」。
8. 關閉頁面。

## <a name="perform-budget-checking"></a>執行預算檢查
1. 按一下財務。
2. 按一下執行預算檢查。
3. 按一下財務。
4. 按一下預算檢查錯誤或警告。
5. 按一下關閉。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]