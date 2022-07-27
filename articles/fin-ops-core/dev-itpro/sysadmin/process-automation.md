---
title: 流程自動化
description: 本主題提供有關流程自動化如何允許對將由批次處理伺服器執行的流程進行簡單調度的詳情。
author: RyanCCarlson2
ms.date: 04/20/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ProcessScheduleSeries
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: rcarlson
ms.search.validFrom: 2020-06-30
ms.dyn365.ops.version: AX 10.0.11
ms.openlocfilehash: b69fa378539e39053b6f7066ba4b6ae9984157c9bdc4f38b78de4c062c04ad09
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460458"
---
# <a name="process-automation"></a>流程自動化

[!include[banner](../includes/banner.md)]

流程自動化允許對將由批次處理伺服器執行的流程進行簡單調度。 計劃工作的更新日曆檢視表允許最終使用者查看計劃和已完成的工作並採取行動。

## <a name="administration"></a>管理

所有流程自動化的中央管理頁面位於 **設定** 選單下的系統管理模組中。 此頁面將列出系統中設定的所有自動化流程 (系列)。 它還允許您直接從此頁面新增新的流程自動化。 設定系列後，您可以從此清單管理每個系列。 您可以選取編輯整個系列、刪除它、在清單檢視表中查看所有事件，或者如果您想暫停計劃的工作一段時間，則停用該系列。 

功能管理中停用的任何流程都不會在停用該功能時顯示。 此外，流程自動化調度引擎不會為停用的功能調度任何事件或後台流程。 重新啟用該功能將導致過去任何計劃的事件或後台流程立即執行。 流程自動化調度引擎依靠系統批次處理作業 **流程自動化輪詢系統作業** 來執行。 任何時候都不應更改或篡改作業。 

## <a name="calendar-view"></a>行事曆檢視

流程自動化的主要優勢之一是能夠在簡單的日曆檢視表中查看已安排的工作。  此檢視表允許您一次查看一週的工作。 您將在 **流程自動化** 頁面的右側看到此檢視表。 它將填入所選系列的預定工作。 

[![流程自動化行事曆。](./media/CalendarView2.png)](./media/CalendarView2.png)

## <a name="occurrence-changes"></a>發生變化

可以修改每個事件，而不會影響由它們產生的系列定義的其他事件。 透過選取 **查看/編輯** 按鈕並選取 **發生**，可以從日曆檢視表中編輯計劃工作的發生。 此頁面允許您存取最初在系列安裝精靈中顯示的所有設定，並提供對選定事件進行一次性更改的能力。 還可以透過從日曆檢視表中選取 **停用** 按鈕來關閉計劃工作的發生。

## <a name="developer-documentation"></a>開發人員文件

流程自動化架構允許開發人員擴展流程自動化架構。 [流程自動化架構](../process-automation/process-automation-framework.md)文件提供了如何建立自訂流程的相關資訊，這些流程需要由使用流程自動化精靈安排的批次處理伺服器執行並自動顯示在日曆檢視表中。


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
