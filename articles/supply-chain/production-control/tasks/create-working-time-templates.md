---
title: 建立工作時間範本
description: 工作時間範本定義了一週的工作時數，用於產生一段時間的工作時間。
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: OpResLifeCycleManagementWorkspace, WorkTimeTable, WorkTimeCopyDayDialog, WorkPeriodTemplate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 130a21d08e4e720f8bf803a5d4b03d315cefc26f
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449337"
---
# <a name="create-working-time-templates"></a>建立工作時間範本

[!include [banner](../../includes/banner.md)]

工作時間範本定義了一週的工作時數，用於產生一段時間的工作時間。 本程序將顯示如何使用分類工作時間間隔的工作時間排程屬性定義工作時間範本。 您能以示範資料公司 USMF 或自己的資料走完這段程序。

1. 前往 **工作區 > 資源生命週期管理**。
1. 選擇 **工作時間範本**。

## <a name="create-working-time-template"></a>建立工作時間範本

1. 選擇 **新增**。
1. 在 **工作時間範本** 欄位輸入值。
1. 在 **名稱** 欄位中，輸入一個值。
1. 展開 **週一** 區段。
1. 選擇 **新增**。
1. 在 **從** 欄位輸入時間。
    * 指定早上開始工作的時間。  
1. 在 **到** 欄位輸入時間。
    * 指定工作人員休息吃午飯的時間。  
1. 選擇 **新增**。
1. 在 **從** 欄位輸入時間。
    * 指定午餐後恢復工作的時間。  
1. 在 **到** 欄位輸入時間。
    * 指定工作日的結束時間。  

## <a name="replicate-working-times-to-all-week-days"></a>將工作時間複製到所有工作日

1. 選擇 **複製日**。
    * 複製週一到週二的工作時間定義。  
1. 選擇 **確定**。
1. 選擇 **複製日**。
    * 複製週一到週三的工作時間定義。  
1. 在 **到工作日** 欄位選擇選項。
1. 選擇 **確定**。
1. 選擇 **複製日**。
    * 複製週一到週四的工作時間定義。  
1. 在 **到工作日** 欄位選擇選項。
1. 選擇 **確定**。
1. 選擇 **複製日**。
    * 複製週一到週五的工作時間定義。  
1. 在 **到工作日** 欄位選擇選項。
1. 選擇 **確定**。

## <a name="define-time-slots-for-special-operations"></a>定義特殊作業時段

1. 展開 **週五** 區段。
1. 在清單中，尋找並選擇所需紀錄。
1. 在 **屬性** 欄位輸入或選擇值。
1. 在清單中，尋找並選擇所需紀錄。
1. 在 **屬性** 欄位輸入或選擇值。

## <a name="mark-weekend-days-as-closed-for-pickup"></a>將週末標記為不開放取貨

1. 展開 **週六** 區段。
1. 在 **不開放取貨** 欄位選擇 *是*。
1. 展開 **週日** 區段。
1. 在 **不開放取貨** 欄位選擇 *是*。


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]