---
title: 招聘 Power BI 內容
description: 本主題介紹招聘 Power BI 內容。
author: jcart1106
ms.date: 12/19/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmRecruitmentWorkspace
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 263934
ms.assetid: 38e6827b-0819-473c-bc47-821a1ec482b8
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 36ea9f204b50b3d7a6c8e33e69a9c3fd7d82cd79d466e2b9547c6733aa294aea
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460372"
---
# <a name="recruiting-power-bi-content"></a>招聘 Power BI 內容

[!include [banner](../includes/banner.md)]

本主題介紹 **招聘** Microsoft Power BI 內容。 它解釋了如何存取 Power BI 報表，並提供有關用於構建內容的資料模型和實體的資訊。

## <a name="accessing-the-power-bi-content"></a>存取 Power BI 內容
**招聘** Power BI 內容顯示在 **招聘管理** 工作區。

## <a name="reports-and-visuals-in-the-recruitment-management-workspace"></a>招聘管理工作區中的報表和視覺效果
**招聘管理** 工作區包含 **分析** 索引標籤。此索引標籤包含招聘的內嵌 Power BI 內容。 內容由概述索引標籤和包含詳情的附加索引標籤組成。 下表說明每個索引標籤的報表。

| 報告               | 內容 |
|----------------------|----------|
| 招聘概述 | 總結其他報表 |
| 申請者分析   | 申請者總數、按職位劃分的申請者、申請者來源、女性對男性申請者、按地區劃分的申請者 |
| 申請者狀態     | 按類型和狀態劃分的申請者以及申請者狀態 |
| 招聘分析  | 淨僱用比率、平均僱用天數、不良僱用百分比、招聘成本、招聘專案數量、僱用與申請，以及招聘項目的申請者與職缺 |

## <a name="understanding-the-data-model-and-entities"></a>了解資料模型和實體
您可以過濾這些報表上的圖表和圖格，並將圖表和圖格固定到儀表板。 如需如何在 Power BI 中篩選和釘選的相關資訊，請參閱[建立和設定儀表板](https://powerbi.microsoft.com/guided-learning/powerbi-learning-4-2-create-configure-dashboards)。

下表顯示了 **招聘** Power BI 內容所基於的實體。

| 實體               | 內容                                                         | 與其他實體的關係 |
|----------------------|------------------------------------------------------------------|-----------------------------------|
| 申請者            | 申請者、被雇用的申請者、淨僱用率和成本          | 申請者姓名、公司、日曆偏移量、日期、地理位置、人口統計、工作、媒體、招聘專案 |
| 申請者姓名       | 申請者的名字、姓氏和全名                   | 申請者，受僱申請者，終止申請者 |
| 排程偏移      | 交叉分析報表的排程偏移                                | 申請者，受僱申請者，終止申請者 |
| 公司              | 過濾報表的公司                                   | 申請者，受僱申請者，終止申請者 |
| 日期                 | 日、週、月和年                                   | 申請者，受僱申請者，終止申請者 |
| 人口統計         | 出生日期、性別、種族、婚姻狀況         | 申請者，受僱申請者，終止申請者 |
| 受僱申請者   | 申請者、績效、開始日期和申請者類型           | 公司、日曆偏移量、日期、地理位置、申請者姓名、就業、績效、工作、媒體、招聘專案 |
| 雇用           | 開始日期、結束日期和過渡日期                        | 申請者，受僱申請者，終止申請者 |
| 地理位置  | 市、縣、郵政編碼和州或省                 | 申請者，受僱申請者，終止申請者 |
| 工作                  | 職能、類型和職稱                                        | 申請者，受僱申請者，終止申請者 |
| 媒體                | 申請者來源                                             | 申請者，受僱申請者，終止申請者 |
| 效能          | 評級、描述和評級模型                            | 申請者，受僱申請者，終止申請者 |
| 招聘專案  | 專案描述、專案狀態和職缺                | 申請者，受僱申請者，終止申請者 |
| 終止申請者 | 終止申請者、原因、績效和終止日期 | 公司、日曆偏移量、日期、地理位置、績效、人口統計、就業、媒體、招聘專案、申請者姓名 |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]