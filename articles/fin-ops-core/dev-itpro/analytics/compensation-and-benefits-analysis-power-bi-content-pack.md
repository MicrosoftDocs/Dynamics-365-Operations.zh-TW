---
title: 薪酬與福利 Power BI 內容
description: 本主題介紹薪酬與福利 Power BI 內容。
author: jcart1106
ms.date: 12/19/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 263914
ms.assetid: 18634bb5-3341-42f2-9cc9-7b04708b506b
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 13f084ba49baa01eea99822baa6960136725140a80c9d29a4104aabc5d7d5dca
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460285"
---
# <a name="compensation-and-benefits-power-bi-content"></a>薪酬與福利 Power BI 內容

[!include [banner](../includes/banner.md)]

本主題介紹薪酬與福利 Power BI 內容。 

## <a name="reports-that-are-included-in-the-content-pack"></a>內容套件中包含的報表
將內容套件與資料連線後，報表會顯示您組織的資料。 如果您以前從未使用過 Microsoft Power BI，可以在[Power BI 引導學習頁面](https://powerbi.microsoft.com/guided-learning/?WT.mc_id=PBIService_GetData)上了解更多資訊。 內容套件中包含的報表具有包含附加資訊的圖表和表格。 下表描述了這些報表。

| 報告                     | 內容                                                                                                                              |
|----------------------------|---------------------------------------------------------------------------------------------------------------------------------------|
| 薪酬和福利分析 | 按公司劃分的時薪和受薪員工、平均時薪、平均薪金、按就業類型劃分的員工和方案登記 |
| 員工福利          | 按選定福利劃分的員工提撥                                                                                               |

您可以過濾這些報表上的圖表和圖格，並將圖表和圖格固定到儀表板。 如需如何在 Power BI 中篩選和釘選的相關資訊，請參閱[建立和設定儀表板](https://powerbi.microsoft.com/guided-learning/powerbi-learning-4-2-create-configure-dashboards)。

## <a name="understanding-the-data-model-and-entities"></a>了解資料模型和實體
應用程式資料用於填入薪酬和福利內容套件中的報表。 下表顯示了內容套件所基於的實體。

| 實體                            | 內容                                                                                                   | 與其他實體的關係 |
|-----------------------------------|------------------------------------------------------------------------------------------------------------|-----------------------------------|
| Workforce\_CalendarOffset         | 交叉分析報表的排程偏移                                                                          | Workforce\_PastPositionAssignment，Workforce\_PositionTrend，Workforce\_WorkerTrend，Workforce\_TerminatedWorker |
| Workforce\_Company                | 過濾報表的公司                                                                             | Workforce\_CurrentCompensation，Workforce\_CurrentWorker，Workforce\_TerminatedWorker，Workforce\_WorkerTrend |
| Workforce\_Compensation           | 隨時間變化的薪酬率和頻率                                                                           | Workforce\_CurrentCompensation，Workforce\_CurrentWorker，Workforce\_TerminatedWorker，Workforce\_WorkerTrend |
| Workforce\_CurrentCompensation    | 截至現行日期的薪酬率和頻率                                                              | Workforce\_Company，Workforce\_Compensation，Workforce\_Demographics，Workforce\_Job，Workforce\_Position |
| Workforce\_CurrentPosition        | 截至現行日期的職位、全職等效 (FTE)、空缺職位和空缺職位 | Workforce\_Job，Workforce\_Position |
| Workforce\_CurrentWorker          | 截至現行日期、年齡和人數的員工                                                         | Workforce\_Company，Workforce\_Compensation，Workforce\_GeographicLocation，Workforce\_Performance，Workforce\_WorkerName，Workforce\_ReportsToWorkerName，Workforce\_WorkerTitle，Workforce\_Demographics，Workforce\_Job，Workforce\_Employment，Workforce\_Position，Workforce\_WorkerBenefit |
| Workforce\_Date                   | 日、週、月和年                                                                             | Workforce\_PastPositionAssignment，Workforce\_PositionTrend，Workforce\_TerminatedWorker，Workforce\_WorkerTrend |
| Workforce\_Demographics           | 出生日期、性別、種族、婚姻狀況                                                   | Workforce\_CurrentWorker，Workforce\_TerminatedWorker，Workforce\_WorkerTrend |
| Workforce\_Employment             | 開始日期、結束日期和過渡日期                                                                  | Workforce\_CurrentWorker，Workforce\_TerminatedWorker，Workforce\_WorkerTrend |
| Workforce\_GeographicLocation     | 市、縣、郵政編碼和州或省                                                           | Workforce\_CurrentWorker，Workforce\_TerminatedWorker，Workforce\_WorkerTrend |
| Workforce\_Job                    | 職能、類型和職稱                                                                                  | Workforce\_CurrentPosition，Workforce\_CurrentWorker |
| Workforce\_PastPositionAssignment | 指派原因、開始日期、結束日期和工作                                                           | Workforce\_CalendarOffset，Workforce\_Date，Workforce\_Job，Workforce\_Position |
| Workforce\_Performance            | 評級、描述和評級模型                                                                      | Workforce\_CurrentWorker，Workforce\_TerminatedWorker，Workforce\_WorkerTrend |
| Workforce\_Position               | 部門、FTE、職位、職位類型和職稱                                                        | Workforce\_CurrentPosition，Workforce\_CurrentWorker |
| Workforce\_PositionTrend          | 職位隨時間、FTE 和工作的變化                                                                          | Workforce\_CalendarOffset，Workforce\_Date，Workforce\_Job，Workforce\_Position |
| Workforce\_ReportsToWorkerName    | 名字、姓氏和全名                                                                       | Workforce\_CurrentWorker，Workforce\_TerminatedWorker，Workforce\_WorkerTrend |
| Workforce\_Skill                  | 技能、技能類型和評級                                                                              | |
| Workforce\_TerminatedWorker       | 被解僱的員工、解僱日期、職稱、職位和工作                                             | Workforce\_Company，Workforce\_Compensation，Workforce\_GeographicLocation，Workforce\_Performance，Workforce\_WorkerName，Workforce\_ReportsToWorkerName，Workforce\_CalendarOffset，Workforces\_Date，Workforce\_WorkerTitle，Workforce\_Demographics，Workforce\_Employment，Workforce\_Job，Workforce\_Position，Workforce\_WorkerBenefit |
| Workforce\_WorkerBenefit          | 生效日期、福利選項、福利方案和福利類型                                             | Workforce\_CurrentWorker，Workforce\_TerminatedWorker，Workforce\_WorkerTrend |
| Workforce\_WorkerName             | 名字、姓氏和全名                                                                       | Workforce\_CurrentWorker，Workforce\_TerminatedWorker，Workforce\_WorkerTrend |
| Workforce\_WorkerTitle            | 職稱和資曆日期                                                                                   | Workforce\_CurrentWorker，Workforce\_TerminatedWorker，Workforce\_WorkerTrend |
| Workforce\_WorkerTrend            | 員工隨著時間、人數、公司和職位的變化                                                        | Workforce\_Company，Workforce\_Compensation，Workforce\_GeographicLocation，Workforce\_Performance，Workforce\_WorkerName，Workforce\_ReportsToWorkerName，Workforce\_CalendarOffset，Workforces\_Date，Workforce\_WorkerTitle，Workforce\_Demographics，Workforce\_Employment，Workforce\_Job，Workforce\_WorkerBenefit |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]