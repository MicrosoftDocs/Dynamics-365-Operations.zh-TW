---
title: 內建總規劃和規劃最佳化之間的差異
description: 本主題列出了規劃最佳化尚不支援且未在規劃最佳化適合度分析頁面上列出的功能。
author: ChristianRytt
ms.date: 07/30/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-07-30
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 575aef709a0ac3b0cf8150f1e816dac04c069814
ms.sourcegitcommit: ddcab9726e9dbcf3296cb0988b97a3ae7ccb3dfb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/08/2022
ms.locfileid: "8450108"
---
# <a name="differences-between-built-in-master-planning-and-planning-optimization"></a>內建總規劃和規劃最佳化之間的差異

[!include [banner](../../includes/banner.md)]

規劃最佳化結果可能與內建總規劃引擎的結果不同。 其差異可能是由待決功能所引起。 本主題列出了規劃最佳化尚不支援且未在 **[規劃最佳化適合度分析](planning-optimization-fit-analysis.md)** 頁面上列出的功能]。

| 功能 | 規劃最佳化中的當前行為 |
|---|---|
| 實秤重量產品 | 實秤重量產品被認為是一般產品。|
| 可擴充維度 | 即使選取 **儲存維度群組** 或 **追蹤維度群組** 頁面上的 **依維度劃分的覆蓋範圍計劃** 核取方塊，計劃訂單上的可擴充維度是空的。 |
| 已篩選生產執行 | 有關詳細資訊，請參閱[生產計劃 - 篩選器](production-planning.md#filters)。 |
| 預測規劃 | 不支援預測規劃。 我們建議您使用將預測模型指派給總規劃的總規劃。 |
| 計劃訂單的編號序列 | 不支援計劃訂單的編號序列。 計劃訂單編號在服務端產生。 計劃訂單號通常以 10 位數顯示，但序列實際上是建立在 20 個字元上，其中 10 位分配給規劃執行計數，另外 10 位分配給計劃訂單計數。 |
| 計劃複製、刪除計劃和計劃版本清理 | <p>導覽窗格中的 **總規劃\>總規劃\>維護計劃** 以下的項目被停用：</p><ul><li>計劃複製</li><li>刪除計劃</li><li>計劃版本清理</li></ul> |
| 退貨單 | 不考慮退貨單。 |
| 排程相關功能 | 有關詳細資訊，請參閱[無限產能排程](infinite-capacity-planning.md#limitations)。 |
| 安全庫存履行 | 規劃最佳化一律使用 **品項涵蓋範圍** 頁面上 **滿足最小值** 欄位的 *今天日期+採購時間* 選項。 這有助於避免不需要的計劃訂單和其他問題，因為如果不包括安全庫存的採購時間，為低現有庫存建立的計劃訂單會一直因為前置時間而延遲。 |
| 安全庫存需求追蹤和淨需求 | 此 *安全庫存* 需求類型不包括在內，也不會顯示在 **淨需求** 頁面上。 安全庫存不代表需求，也沒有與其相關的需求日期。 相反地，它限制了必須始終存在多少庫存。 然而在總規劃期間計算計劃訂單時，仍會考慮該 **下限** 欄位值。 我們建議您檢查 **淨需求** 頁面上的 **累積數量** 欄，查看是否考慮了此值。 |
| 運輸行事曆 | **交貨模式** 頁面上的 **運輸行事曆** 列的值被忽略。 |
| 沒有值的最小值/最大值涵蓋範圍代碼| 當您使用未設置最小值或最大值的最小值/最大值涵蓋範圍代碼時，使用內建規劃引擎，該規劃引擎會將涵蓋範圍代碼視為一項需求並為每個需求建立一個訂單。 使用規劃最佳化，系統將每天建立一個訂單以支付當天的全部金額。  |

## <a name="additional-resources"></a>其他資源

- [規劃最佳化適合度分析](planning-optimization-fit-analysis.md)
- [規劃最佳化未使用的參數](not-used-parameters.md)
- [規劃最佳化使用的日期與時間參數](date-time-used.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
