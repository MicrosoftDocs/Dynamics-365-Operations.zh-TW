---
title: 為站點建立排程
description: 此程序說明如何排程站點尚未開始處理的生產訂單。
author: ChristianRytt
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ProdTableListPage, ProdSchedule, ProdRouteJob
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 146531217f7f596a5cb98e271b0356ffeb3d5547
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8447996"
---
# <a name="create-a-schedule-for-a-site"></a>為站點建立排程

[!include [banner](../../includes/banner.md)]

此程序說明如何排程站點尚未開始處理的生產訂單。  示範資料公司 USMF 會用於完成此程序。


## <a name="identify-production-orders-that-are-not-started"></a>識別尚未開始的生產訂單
1. 移至 [生產控制] > [生產訂單] > [所有生產訂單]。
2. 使用快速篩選器尋找記錄。 例如，以「1」這個值來篩選站點欄位。
    * 1 代表 USMF 的一個站點。 若您使用的不是 USMF，請從自己的公司中選擇一個站點。  
3. 開啟狀態欄的篩選器。
4. 使用「完全符合」篩選運算子，以「已排程」這個值對「狀態」欄位進行篩選。

## <a name="create-a-schedule"></a>建立排程
1. 在清單中，標記或取消標記所有列。
2. 在 [動作窗格] 上按一下 [排程]。
3. 按一下排程作業。
4. 在排程方向欄位中，選擇「從交貨日期向後」。
5. 在有限產能欄位中選擇否。
6. 在有限材料欄位中選擇否。
7. 按一下確定。
    * 這可能需要一些時間。  

## <a name="view-the-result-of-scheduled-production-orders"></a>檢視排程生產訂單的結果
1. 在清單中，標記所選資料列。
    * 您可標記任何列。  
2. 在 [動作窗格] 上按一下 [產品訂單]。
3. 按一下所有作業。
    * 此頁面會呈現作業清單。 在排程索引標籤上，您可檢視作業的開始日期和結束日期。  
4. 按一下材料。
    * 在此頁面上，您可查看生產訂單上的作業的預估材料消耗和目前可用庫存。  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]