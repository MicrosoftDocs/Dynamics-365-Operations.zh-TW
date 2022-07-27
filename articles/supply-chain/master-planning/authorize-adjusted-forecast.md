---
title: 授權已調整預測
description: 不是所有預測數據都必須立即獲得授權。 本文介紹如何為授權預測指定期間。 本文也說明若是對特定公司和預測模型，如何授權預測。
author: ChristianRytt
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqDemPlanImportForecastDialog
audience: Application User
ms.reviewer: kamaybac
ms.custom: 72734
ms.assetid: cb8fd809-605a-4a8b-a390-636edfec21f9
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1f9ceeb01675a44388862e1dede11551d3a60bdc
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448137"
---
# <a name="authorize-an-adjusted-forecast"></a>授權已調整預測

[!include [banner](../includes/banner.md)]

不是所有預測數據都必須立即獲得授權。 本文介紹如何為授權預測指定期間。 本文也說明若是對特定公司和預測模型，如何授權預測。

不是所有預測數據都必須立即獲得授權。 對於預測的授權期間，您可以指定開始日期和結束日期。 此功能可讓您凍結特定的貯體。 

您指定的預測開始日期和結束日期，必須對應其生成貯體的開始日期和結束日期。 系統會強制執行此限制，如果需要調整，則會自動調整日期。 

在 **授權** 頁面上的 **詳細資料** 索引標籤，有新近生成預測的詳細資料，您可以查看。 

請選取公司和預測模型以授權預測使用。 預設情況下，網格包括為其建立預測需求的所有公司。 對於每個公司，設定在主計劃參數中並對應當前預測計劃的預測模型是預先填寫的。 但是，您可以將此預測模型更改為屬於該公司的任何預測模型。 如果沒有為選定公司生成預測需求數據，匯入時會收到警告訊息。 

知道 **儲存對基準需求預測進行的手動調整** 核取方塊如何運作非常重要。 如果您對統計基線預測進行了手動調整，則即使清除此核取方塊，調整後的值也會被授權使用。 但是，更改會在授權後被拋棄。 因此，下次生成預測時，該預測只是統計預測，沒有任何手動覆寫，即使選取了 **將手動調整轉移到需求預測**。 因此，您可以認為 **儲存對基準需求預測進行的手動調整** 核取方塊是一種允許您保留或放棄所有手動更改的機制。

## <a name="additional-resources"></a>其他資源

[對基線預測進行手動調整](manual-adjustments-baseline-forecast.md)

[監控預測準確性](monitor-forecast-accuracy.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]