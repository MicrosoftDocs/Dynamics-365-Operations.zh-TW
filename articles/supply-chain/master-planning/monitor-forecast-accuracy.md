---
title: 監控預測準確性
description: 本主題說明 Dynamics 365 Supply Chain Management 計算的預測正確性類型，並解釋如何檢視正確性值。
author: ChristianRytt
ms.date: 01/07/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqDemPlanForecastDetails
audience: Application User
ms.reviewer: kamaybac
ms.custom: 72863
ms.assetid: 810a0d63-f4c6-4167-b2b3-a178b74ead89
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4246a277aa5d88193c18336cb1de69916ec2a3c2
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8447855"
---
# <a name="monitor-forecast-accuracy"></a>監控預測準確性

[!include [banner](../includes/banner.md)]

本主題說明 Microsoft Dynamics 365 Supply Chain Management 計算的預測正確性類型，並解釋如何檢視正確性值。

Supply Chain Management 計算以下類型的預測正確性：

-   歷史預測正確性，將總體規劃使用的歷史預測與歷史需求進行比較。 若要查看歷史預測正確性的值 (絕對值和百分比值)，請按一下 **需求預測詳細資料** 頁面中的 **顯示正確性**。
-   用於產生預測的預測模型估計正確性。 您可以在 **需求預測詳細資料** 頁面的 **模型詳細資料 - MAPE** 下檢視正確性百分比。 

> [!NOTE]
> 如果您使用需求預測 Microsoft Azure Machine Learning，會根據測試資料集計算內部模型正確性。 若要指定測試資料集的大小，請在 **需求預測參數** 頁面中設定 **TEST\_SET\_SIZE\_PERCENT** 參數。 例如，如果您將值設置為 **20**，最後 20% 的歷史資料將用於計算內部模型正確性。


## <a name="additional-resources"></a>其他資源

[授權已調整預測](authorize-adjusted-forecast.md)

[計算需求預測時，從歷史交易資料中刪除異常值](remove-historical-outliers-calculating-demand-forecast.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]