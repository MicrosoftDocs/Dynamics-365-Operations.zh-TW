---
title: 尋找過時的產品變體
description: 此程序會顯示如何尋找過時的已發佈產品或產品變體，以及如何將產品生命週期狀態與過時產品相關聯。
author: t-benebo
ms.date: 12/05/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 13db6620575b4c97b3f8079ac94f5231a2fd9c1b
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448989"
---
# <a name="find-obsolete-product-variants"></a>尋找過時的產品變體 

[!include [banner](../../includes/banner.md)]

此程序會顯示如何尋找過時的已發佈產品或產品變體，以及如何將產品生命週期狀態與過時產品相關聯。 前提條件：您必須先定義至少一個不供規劃的產品生命週期狀態，才能執行此任務指南。


## <a name="run-a-simulation"></a>執行模擬
1. 移至產品資訊管理 > 定期任務 > 變更過時產品的生命週期狀態。
2. 在 [新產品生命週期狀態] 欄位中，輸入或選取一個值。
3. 在 [執行模擬] 中選取 [是]，且不更新產品資料欄位。
4. 在 [排除在此天數內建立的產品] 欄位中，輸入一個數字。
5. 在 [排除在交易中使用的產品 (天數)] 欄位中，輸入一個數字。
6. 展開記錄以包含區段。
7. 按一下 [篩選]。
8. 在清單中，標記所選資料列。
9. 在 [條件] 欄位中，輸入一個值。
10. 按一下 [確定]。
11. 按一下 [確定]。

> [!NOTE]
> 如果您想要搜尋大量產品，建議您批次執行模擬。 此外，請確保不在公司最活躍的工作時間內執行模擬。  

## <a name="review-the-simulation-results"></a>檢閱模擬結果
1. 移至 [產品資訊管理] > [查詢與報告] > [產品生命週期狀態維護歷程]。
   
> [!NOTE]
> 在此頁面上，您可以檢閱模擬結果，並評估若在沒有模擬的情況下執行更新時，將有多少產品和產品變體與新產品生命週期狀態相關聯。  

## <a name="run-the-update-of-the-product-lifecycle-state-for-obsolete-products"></a>執行過時產品的產品生命週期狀態更新
1. 關閉頁面。
2. 移至產品資訊管理 > 定期任務 > 變更過時產品的生命週期狀態。
3. 展開記錄以包含區段。

> [!NOTE]
> 請注意，已儲存最後的選擇。  

4. 在 [執行模擬] 中選取 [否]，且不更新產品資料欄位。
5. 展開 [在背景執行] 區段。

> [!NOTE]
> 根據受影響的產品和產品變體數量，考慮批次執行此作業。 確保您不會在公司最活躍的工作時間內執行大型更新作業。  

6. 按一下 [確定]。
7. 移至 [產品資訊管理] > [查詢與報告] > [產品生命週期狀態維護歷程]。

> [!NOTE]
> 檢閱變更的已發佈產品和產品變體。  

8. 在清單中，尋找並選擇所需紀錄。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]