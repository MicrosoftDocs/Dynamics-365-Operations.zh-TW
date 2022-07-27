---
title: 使用工序和作業排程安排生產訂單
description: 本主題重點介紹使用工序排程和作業排程來安排生產訂單。
author: johanhoffmann
ms.date: 08/19/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ProdTableListPage, ProdTableCreate, InventItemIdLookupPurchase, ProdSchedule, ProdTable, ProdRouteJob
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bc91fe5aa398cd94e38beea017d6d60ecb44f17e
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448716"
---
# <a name="schedule-a-production-order-with-operations-and-job-scheduling"></a>使用工序和作業排程安排生產訂單

[!include [banner](../../includes/banner.md)]

本主題重點介紹使用工序排程和作業排程來安排生產訂單。 不使用工序排程建立作業，而使用作業排程建立。 用於創建此工作的示範資料公司是 USMF。 此程序適用於在離散製造環境中工作的生產經理、生產規劃員或工廠主管。


## <a name="create-a-production-order"></a>建立生產訂單
1. 在瀏覽窗格中，移至 **模組 > 生產控制 > 生產訂單 > 所有生產訂單**。
2. 選取 **新生產訂單**。
3. 在 **項目號碼** 欄位中，輸入或選擇一個值。 選擇品項編號 **D0001**。  
4. 選取 **建立**。

## <a name="schedule-operations-for-the-production-order"></a>為生產訂單排程工序
1. 標記新建立的列。      
2. 在 [動作窗格] 上，選取 **排程**。
3. 選取 **排程作業**。
4. 在 **排程方向** 欄位中，選取 **從排程日期正推**。
5. 在 **排程日期** 欄位中，輸入日期。 選擇一個未來的日期，例如今天加上一週。 使用選定的 [排程方向]，安排生產訂單將從該日期正推。  
6. 選擇 **確定**。
7. 在清單中，標記所選資料列。 請注意，狀態變更為 **已排程**。 
8. 選取 **所有作業**。 請注意，沒有使用工序排程建立作業。  
9. 關閉頁面。

## <a name="schedule-jobs-for-the-production-order"></a>為生產訂單排程作業
1. 在 [動作窗格] 上，選取 **排程**。
2. 選取 **排程作業**。
3. 在 **排程方向** 欄位中，選取 **從排程日期正推**。
4. 在 **排程日期** 欄位中，輸入日期。 選擇一個未來的日期，例如今天加上一週。 使用選定的 [排程方向]，安排生產訂單將從該日期正推。  
5. 選擇 **確定**。
6. 在動作窗格上，選擇 **生產訂單**。
7. 選取 **所有作業**。 請注意，根據使用中的途程，透過作業排程建立 5 個作業。  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]