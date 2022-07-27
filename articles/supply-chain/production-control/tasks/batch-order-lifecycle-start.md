---
title: 從建立到開始批次訂單生命週期
description: 此過程將引領您完成批次訂單生命週期的第一部分。
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ProdTableListPage, ProdTableCreate, ProdBOM, PmfProdCoBy, ProdParmCostEstimation, ProdCalcTrans, ProdParmRelease, ProdSchedule, ProdRouteJob, ProdParmStartUp, ProdJournalTransBOM, ProdJournalTransRoute
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a7ca259ca8f176cd5bc76081836adcb7d272972b
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449196"
---
# <a name="batch-order-lifecycle-from-create-to-start"></a>從建立到開始批次訂單生命週期

[!include [banner](../../includes/banner.md)]

此過程將引領您完成批次訂單生命週期的第一部分。

從建立、成本估算和過剩生產作業排程到實際開始批次訂單。



建立此程序的示範資料公司為 USMF。 



使用另一個資料集執行此過程的先決條件，是具有有效配方和途程版本的已發布產品。


## <a name="create-a-batch-order"></a>建立批次訂單
1. 前往所有生產訂單。
2. 按一下新增批次訂單。
3. 在品項編號欄位中，輸入或選擇一個值。
4. 按一下建立。
5. 使用快速篩選來篩選出具有 'b' 值的生產欄位。

## <a name="view-production-formula-and-expected-co-products"></a>查看生產配方和預期的聯產品
1. 在 [動作窗格] 上按一下 [產品訂單]。
2. 按一下配方。
3. 關閉頁面。
4. 按一下聯產品。
5. 關閉頁面。

## <a name="estimate-the-batch-order"></a>預估批次訂單
1. 按一下預估。
2. 按一下確定。
3. 在動作窗格上，按一下「管理成本」。
4. 按一下查看計算詳細資訊。
5. 關閉頁面。

## <a name="release-the-batch-order"></a>發佈批次訂單
1. 在 [動作窗格] 上按一下 [產品訂單]。
2. 按一下發佈。
3. 按一下確定。

## <a name="schedule-production-jobs"></a>排程生產作業
1. 在 [動作窗格] 上按一下 [排程]。
2. 按一下排程作業。
3. 在有限產能欄位中選擇否。
4. 在有限材料欄位中選擇否。
5. 按一下確定。
6. 在 [動作窗格] 上按一下 [產品訂單]。
7. 按一下「所有作業」。
8. 關閉頁面。

## <a name="start-the-batch-order"></a>開始批次訂單
1. 按一下啟動。
2. 按一下「一般」索引標籤。
3. 在立即過帳揀料單欄位選取「否」。
4. 按一下確定。
5. 在「動作窗格」上按一下 [檢視]。
6. 按一下「揀料單」。
7. 在列表中，按一下所選行中的連結。
8. 關閉頁面。
9. 關閉頁面。
10. 按一下途程卡。
11. 在列表中，按一下所選行中的連結。
12. 關閉頁面。
13. 關閉頁面。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]