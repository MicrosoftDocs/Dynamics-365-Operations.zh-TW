---
title: 產生受限方案
description: 本主題說明如何建立同時考慮材料和產能限制的方案。
author: ChristianRytt
ms.date: 08/02/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, ReqCreatePlanWorkspace, ReqTransPlanCard, ReqPlanSched
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5fea315d41d01cb578d7d60c9eb7006e4b6c3362
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449100"
---
# <a name="generate-a-constrained-plan"></a>產生受限方案

[!include [banner](../../includes/banner.md)]

本主題說明如何建立同時考慮材料和產能限制的方案。 方案能確保在有材料且資源沒有超額預訂之前，不會開始製造。 

建立此程序的示範資料公司為 USMF。 此程序適用於生產規劃員。


## <a name="set-up-a-constrained-plan"></a>設定受限方案
1. 在首頁中，選擇 **主計劃** 工作區。
2. 選擇工作區最右側連結列表中的 **總規劃**。
3. 在清單中，尋找並選擇所需紀錄。 範例：**StaticPlan**  
4. 在 **有限產能** 欄位中選擇 **是**。
5. 在 **有限產能時界** 欄位中，輸入 `30`。
6. 展開 **時間範圍 (天)** 區段。
7. 在 **產能** 欄位中選擇 **是**。
8. 在 **產能排程時間範圍 (天)** 欄位裡輸入一個數字。 範例: `60`  
9. 在 **已計算延遲** 欄位中選擇 **是**。
10. 在 **計算延遲時界 (天)** 欄位裡輸入一個數字。 範例: `60` 
11. 展開 **已計算延遲** 區段。
12. 在所有 **將已計算延遲新增至需求日期** 欄位選擇 **是**。
13. 關閉頁面。

## <a name="create-a-constrained-plan"></a>建立受限方案
1. 選擇 **執行**。
2. 在 **主計劃** 欄位裡，輸入或選擇您已設定限制的方案。  
3. 選擇 **確定**。
4. 選擇 **已規劃訂單**。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]