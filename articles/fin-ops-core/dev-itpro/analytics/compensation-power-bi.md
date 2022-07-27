---
title: 薪酬 Power BI 內容
description: 本主題介紹薪酬 Power BI 內容。 它解釋了如何存取報表並提供有關所用資料模型的資訊。
author: jcart1106
ms.date: 12/19/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmCompensationWorkspace
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 549111dab1b6d3b66567801ae787a680a04b18e20e286e1a59d1ab388bf2a4f7
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460287"
---
# <a name="compensation-power-bi-content"></a>薪酬 Power BI 內容

[!include [banner](../includes/banner.md)]

本主題介紹 **薪酬** Microsoft Power BI 內容。 它解釋了如何存取報表，並提供有關用於構建內容的資料模型和實體的資訊。

## <a name="accessing-the-power-bi-content"></a>存取 Power BI 內容
如果您使用以下產品之一，則 **薪酬** Power BI 內容會顯示在 **薪酬管理** 工作區中：

- 財務和營運應用程式
- Microsoft Dynamics 365 Human Resources

## <a name="reports-that-are-included-in-the-power-bi-content"></a>Power BI 內容中包含的報表
**薪酬** Power BI 內容中包含的報表具有包含附加資訊的圖表和表格。 下表描述了這些報表。

| 報告                     | 內容 |
|----------------------------|----------|
| 薪酬概覽      | 其他報表摘要 |
| 薪酬分析      | 按公司劃分的時薪和受薪員工、按薪酬方案劃分的員工總數、按薪酬方案劃分的男性和女性員工、按部門劃分的員工薪酬 |
| 職位薪酬分析      | 最高和最低的時薪和薪水，最高和最低薪的職位，以及全職和兼職職位 |
| 薪酬方案分析 | 按選定福利劃分的員工提撥 |

您可以過濾這些報表上的圖表和圖格，並將圖表和圖格固定到儀表板。 如需如何在 Power BI 中篩選和釘選的相關資訊，請參閱[建立和設定儀表板](https://powerbi.microsoft.com/guided-learning/powerbi-learning-4-2-create-configure-dashboards)。

## <a name="understanding-the-data-model-and-entities"></a>了解資料模型和實體
以下資料用於填入 **薪酬** Power BI 內容中的報表。 此表顯示內容所基於的實體。

| 實體                   | 內容                                                                                                   | 與其他實體的關係 |
|--------------------------|------------------------------------------------------------------------------------------------------------|-----------------------------------|
| 排程偏移          | 交叉分析報表的排程偏移                                                                          | 過去的職位指派、職位趨勢、員工趨勢、被解僱的員工 |
| 公司                  | 過濾報表的公司                                                                             | 現行薪酬、現行員工、被解僱的員工、員工趨勢 |
| 薪酬             | 隨時間變化的薪酬率和頻率                                                                           | 現行薪酬、現行員工、被解僱的員工、員工趨勢 |
| 現行薪酬     | 截至現行日期的薪酬率和頻率                                                              | 公司、薪酬、人口統計、工作、職位 |
| 現行職位         | 截至現行日期的職位、全職等效 (FTE)、空缺職位和空缺職位 | 工作，職位 |
| 現任員工         | 截至現行日期、年齡和人數的員工                                                         | 公司、薪酬、地理位置、員工姓名、匯報對象、員工職稱、人口統計、工作、就業、職位、福利 |
| 日期                     | 日、週、月和年                                                                             | 過去的職位指派、職位趨勢、被解僱的員工、員工趨勢 |
| 人口統計             | 出生日期、性別、種族、婚姻狀況                                                   | 現行員工、被解僱的員工、員工趨勢 |
| 雇用               | 開始日期、結束日期和過渡日期                                                                  | 現行員工、被解僱的員工、員工趨勢 |
| 地理位置      | 市、縣、郵政編碼和州或省                                                           | 現行員工、被解僱的員工、員工趨勢 |
| 工作                      | 職能、類型和職稱                                                                                  | 現行職位，現行員工 |
| 過去職位指派 | 指派原因、開始日期、結束日期和工作                                                           | 排程偏移、日期、工作、職位 |
| 職位                 | 部門、FTE、職位、職位類型和職稱                                                        | 現行職位，現行員工 |
| 職位趨勢           | 職位隨時間、FTE 和工作的變化                                                                          | 排程偏移、日期、工作、職位 |
| 主管               | 名字、姓氏和全名                                                                       | 現行員工、被解僱的員工、員工趨勢 |
| 被解僱的員工      | 被解僱的員工、解僱日期、職稱、職位和工作                                           | 公司、薪酬、地理位置、員工姓名、匯報對象、排程偏移、日期、員工職稱、人口統計、就業、工作、職位、福利 |
| 福利                 | 生效日期、福利選項、福利方案和福利類型                                             | 現行名稱、被解雇的員工、員工趨勢 |
| 員工姓名            | 名字、姓氏和全名                                                                       | 現行員工、被解僱的員工、員工趨勢 |
| 員工職稱           | 職稱和資曆日期                                                                                   | 現行員工、被解僱的員工、員工趨勢 |
| 員工趨勢           | 員工隨著時間、人數、公司和職位的變化                                                        | 公司、薪酬、地理位置、員工姓名、匯報對象、排程偏移、日期、員工職稱、人口統計、就業、工作、福利 |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]