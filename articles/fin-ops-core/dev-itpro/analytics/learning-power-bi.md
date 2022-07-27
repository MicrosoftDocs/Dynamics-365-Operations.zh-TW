---
title: 學習 Power BI 內容
description: 本主題介紹學習 Power BI 內容。
author: jcart1106
ms.date: 12/19/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 6236868dca26be8cf54ad3cf73e846f2e689af8635e212c493b65a5d1aaa62ed
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460206"
---
# <a name="learning-power-bi-content"></a>學習 Power BI 內容

[!include [banner](../includes/banner.md)]

本主題介紹 **學習** Microsoft Power BI 內容。

## <a name="reports-that-are-included-in-the-power-bi-content"></a>Power BI 內容中包含的報表

**學習** Power BI 內容中包含的報表具有包含附加資訊的圖表和表格。 下表描述了這些報表。

| 報告                | 內容 |
|-----------------------|----------|
| 學習概述     | 其他報表摘要 |
| 課程分析       | 按地點註冊，按狀態參加者，按公司類型按課程，按工作按課程參加 |
| 註冊分析 | 註冊清單 |
| 課程類型          | 依技能區分的課程類型 |
| 講師分析   | 課程與講師的比例、講師人數、講師的課程、每位講師的課程以及講師的課程議程 |
| 提供的課程       | 課程清單 |
| 課程設計        | 課程議程 |

您可以過濾這些報表上的圖表和圖格，並將圖表和圖格固定到儀表板。 如需如何在 Power BI 中篩選和釘選的相關資訊，請參閱[建立和設定儀表板](https://powerbi.microsoft.com/guided-learning/powerbi-learning-4-2-create-configure-dashboards)。

## <a name="understanding-the-data-model-and-entities"></a>了解資料模型和實體

以下資料用於填入 **學習** Power BI 內容中的報表。 此表顯示內容所基於的實體。

| 實體           | 內容                                                         | 與其他實體的關係 |
|------------------|------------------------------------------------------------------|-----------------------------------|
| 排程偏移  | 交叉分析報表的排程偏移                                | 課程議程，課程參加者 |
| 公司          | 過濾報表的公司                                   | 課程議程，課程參加者 |
| 課程           | 課程、描述、講師姓名、位置、房間和狀態 | 課程議程，課程參加者，課程技能 |
| 課程議程    | 議程、課程以及開始和結束時間                          | 公司、日曆偏移量、日期、課程 |
| 課程參加者 | 姓名、狀態、工作和註冊日期                         | 公司、日曆偏移量、日期、課程、人口統計、就業、課程、員工姓名、員工頭銜、工作、職位 |
| 課程技能     | 技能、技能類型和等級                                     | 課程 |
| 日期             | 日、週、月和年                                   | 課程議程，課程參加者 |
| 人口統計     | 出生日期、性別、種族、婚姻狀況         | 課程議程，課程參加者 |
| 雇用       | 開始日期、結束日期和過渡日期                        | 課程議程，課程參加者 |
| 工作              | 職能、類型和職稱                                        | 課程議程，課程參加者 |
| 職位         | 職位、頭銜和全時約當數 (FTE)                  | 課程議程，課程參加者 |
| 員工姓名    | 名字、姓氏和全名                             | 課程參加者 |
| 員工頭銜   | 職稱和資曆日期                                         | 課程參加者 |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]