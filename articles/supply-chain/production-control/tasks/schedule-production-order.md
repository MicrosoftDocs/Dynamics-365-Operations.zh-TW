---
title: 排程生產訂單
description: 此程序說明如何排程生產訂單。
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ProdTableListPage, ProdSchedule, ProdRouteJob, WrkCtrCapResSum, ProdRouteJobSched, ProductionOrderScheduleDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 43d183764def1b1bea7bbe140c25e0eec0b692b1
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449325"
---
# <a name="schedule-a-production-order"></a>排程生產訂單

[!include [banner](../../includes/banner.md)]

此程序說明如何排程生產訂單。 建立此程序的示範資料公司為 USMF。 這是解釋生產訂單生命週期的第三個程序 (共七個程序)。


## <a name="schedule-a-production-order"></a>排程生產訂單
1. 移至 [生產控制] > [生產訂單] > [所有生產訂單]。
    * 選取具有 [預估] 狀態的生產訂單。  
2. 在 [動作窗格] 上按一下 [排程]。
3. 按一下 [排程] 作業。
    * 在此頁面上設定排程參數。 您可以為特定使用者或所有使用者設定參數。  
4. 在 [排程方向] 欄位中，選取 [從今天開始]。
5. 在 [排程日期] 欄位中，輸入日期。
6. 選取或清除 [有限產能] 核取方塊。
7. 選取或清除 [有限物料] 核取方塊。
8. 點選 [確定]。

## <a name="view-the-scheduling-results"></a>查看排程結果
1. 在 [動作窗格] 上按一下 [產品訂單]。
2. 按一下 [所有作業]。
    * 此頁面顯示您剛剛產生的排程作業。  
3. 展開或摺疊 [排程] 區段。
    * 在 [排程] FastTab上可以查看排程的日期和時間。  
4. 點選 [查詢]。
5. 點選 [產能負載]。
    * [產能負載] 頁面顯示作業排程預留的產能、目前可用的預留總小時數，以及排程作業仍可用小時數。  
6. 關閉頁面。
7. 關閉頁面。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]