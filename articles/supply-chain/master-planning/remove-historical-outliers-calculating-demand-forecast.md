---
title: 計算需求預測時，從歷史交易資料中刪除極端值
description: 本文介紹如何從用於計算需求預測的歷史資料中排除極端值。 透過排除極端值，您可以提高預測準確性。
author: ChristianRytt
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqDemPlanForecastParameters, ReqDemPlanOutlierQuerySetup, ReqDemPlanOutlierQueryPreview
audience: Application User
ms.reviewer: kamaybac
ms.custom: 72621
ms.assetid: 88a964af-14eb-4c5c-945b-388e5908362c
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bc0826d3a0dd8ded19590867e9a8138bb772c89a
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448131"
---
# <a name="remove-outliers-from-historical-transaction-data-when-calculating-a-demand-forecast"></a>計算需求預測時，從歷史交易資料中刪除極端值

[!include [banner](../includes/banner.md)]

本文介紹如何從用於計算需求預測的歷史資料中排除極端值。 透過排除極端值，您可以提高預測準確性。

可以排除極端值以提高預測的精確度。 這是一個選擇性任務。 以下是流程總覽：

1.  按一下 **總體規劃** &gt; **設定** &gt; **需求預測** &gt; **極端值移除** 以開啟 **極端值移除** 頁面，從中可以使用查詢選擇要排除的交易。
2.  選擇要套用查詢的公司，然後輸入名稱和描述。 **查詢日期** 欄位自動設定為目前日期。
3.  選擇 **啟用** 核取方塊可以從歷史資料中排除由查詢找到的交易。 在您建立基準預測時，此設定將生效。
4.  在 **極端值移除查詢** 頁面，您可以新增、刪除和選擇用於定義在計算基準預測時將排除哪些交易的條件。 例如，選擇要排除的特定品項或訂單交易。
5.  按一下 **顯示交易**。 **極端值交易** 頁面列出符合查詢中定義條件的交易，並且在計算需求預測時，將從歷史資料中排除此交易。

**附註：** 您還可以建立基於現有查詢的查詢。 選擇要複製的查詢，然後按一下 **複製**。 **查詢日期** 欄位識別版本。 您可以按原樣使用查詢，也可以按一下 **編輯查詢** 修改條件。 您可以選擇性地修改新查詢的名稱和描述。

## <a name="additional-resources"></a>其他資源

[需求預測概觀](introduction-demand-forecasting.md)

[監控預測準確性](monitor-forecast-accuracy.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]