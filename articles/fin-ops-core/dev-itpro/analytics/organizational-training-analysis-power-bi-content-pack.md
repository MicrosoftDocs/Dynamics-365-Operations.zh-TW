---
title: 組織訓練 Power BI 內容
description: 本主題介紹財務和營運應用程式- 組織訊聯 Power BI 內容。
author: jcart1106
ms.date: 12/19/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 263874
ms.assetid: 45dbba14-aba6-4571-be0d-5d1aba3515d9
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: cd48c12ea3ea31904c437f678888a51e5381cfcfbeef0e1c709858b0c6cb857d
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460442"
---
# <a name="organizational-training-power-bi-content"></a>組織訓練 Power BI 內容

[!include [banner](../includes/banner.md)]

本主題介紹財務和營運應用程式- 組織訊聯 Power BI 內容。

## <a name="reports-that-are-included-in-the-content-pack"></a>內容套件中包含的報表
將內容套件與資料連線後，報表會顯示您組織的資料。 如果您以前從未使用過 Microsoft Power BI，可以在[Power BI 引導學習頁面](https://powerbi.microsoft.com/guided-learning/?WT.mc_id=PBIService_GetData)上了解更多資訊。 內容套件中包含的報表具有包含附加資訊的圖表和表格。 下表描述了這些報表。

| 報告          | 內容                                                                    |
|-----------------|-----------------------------------------------------------------------------|
| 課程分析 | 按位置註冊，按狀態參加課程的人，以及註冊清單 |
| 課程類型    | 依技能區分的課程類型                                                       |

您可以過濾這些報表上的圖表和圖格，並將圖表和圖格固定到儀表板。 如需如何在 Power BI 中篩選和釘選的相關資訊，請參閱[建立和設定儀表板](https://powerbi.microsoft.com/guided-learning/powerbi-learning-4-2-create-configure-dashboards)。

## <a name="understanding-the-data-model-and-entities"></a>了解資料模型和實體
應用程式資料用於填入組織訓練內容包中的報表。 下表顯示了內容套件所基於的實體。

| 實體                    | 內容                                                         | 與其他實體的關係 |
|---------------------------|------------------------------------------------------------------|-----------------------------------|
| Training\_CalendarOffset  | 交叉分析報表的排程偏移                                | Training\_CourseAgenda、Training\_CourseAttendees |
| Training\_Company         | 過濾報表的公司                                   | Training\_CourseAgenda、Training\_CourseAttendees |
| Training\_Course          | 課程、描述、講師姓名、位置、房間和狀態 | Training\_CourseAgenda、Training\_CourseAttendees、Training\_CourseSkill |
| Training\_CourseAgenda    | 議程、課程以及開始和結束時間                          | Training\_Company、Training\_CalendarOffset、Training\_Date、Training\_Course |
| Training\_CourseAttendees | 姓名、狀態、工作和註冊日期                         | Training\_Company、Training\_CalendarOffset、Training\_Date、Training\_Demographics、Training\_Employment、Training\_Course、Training\_WorkerName、Training\_WorkerTitle、Training\_Job、Training\_Position |
| Training\_CourseSkill     | 技能、技能類型和等級                                     | Training\_Course |
| Training\_Date            | 日、週、月和年                                   | Training\_CourseAgenda、Training\_CourseAttendees |
| Training\_Demographics    | 出生日期、性別、種族、婚姻狀況         | Training\_CourseAgenda、Training\_CourseAttendees |
| Training\_Employment      | 開始日期、結束日期和過渡日期                        | Training\_CourseAgenda、Training\_CourseAttendees |
| Training\_Job             | 職能、類型和職稱                                        | Training\_CourseAgenda、Training\_CourseAttendees |
| Training\_Position        | 職位、頭銜和全時約當數 (FTE)                  | Training\_CourseAgenda、Training\_CourseAttendees |
| Training\_WorkerName      | 名字、姓氏和全名                             | Training\_CourseAttendees |
| Training\_WorkerTitle     | 職稱和資曆日期                                         | Training\_CourseAttendees |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]