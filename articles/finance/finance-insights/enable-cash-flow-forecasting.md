---
title: 啟用現金流量預測
description: 本主題說明如何在 Finance Insights 中打開現金流量預測功能。
author: ShivamPandey-msft
ms.date: 02/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-07-24
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 763818f70095964d77ff82cf02178367d05eaf23
ms.sourcegitcommit: 3105642fca2392edef574b60b4748a82cda0a386
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/12/2022
ms.locfileid: "8451533"
---
# <a name="enable-cash-flow-forecasting"></a>啟用現金流量預測

[!include [banner](../includes/banner.md)]

本主題說明如何在 Finance Insights 中打開現金流量預測功能。

> [!NOTE]
> 要在現金流中使用付款預測，您必須按照中所述設置客戶付款預測功能[啟用客戶付款預測 ](enable-cust-paymnt-prediction.md)。
  
1. 打開 **功能管理** 工作區，然後按照以下步驟操作：

    1. 選擇 **檢查更新**。
    2. 在 **全部** 標籤，搜尋 **現金流量預測**。 如果您沒有找到該功能，請搜尋 **(預覽) 現金流量預測**。 
    3. 開啟功能。

2. 去 **現金和銀行管理\>現金流量預測設置**，並新增應包含在預測中的流動性帳戶。 還設置流動資金帳戶用於支付 **應收帳款** 和 **應付帳款** 標籤。 一定要重新計算現金流量預測。

    > [!NOTE]
    > 如果沒有設置流動資金帳戶，就無法產生現金流。
    >
    > 有關如何設定現金流量預測的更多資訊，請參閱[現金流量預測](../cash-bank-management/cash-flow-forecasting.md)。

3. 去 **現金和銀行管理\>設置\>Finance Insights (預覽)\>現金流量預測 (預覽)**，然後按照以下步驟操作：

    1. 在 **現金流量預測** 索引標籤，選擇 **啟用功能**。
    2. 選擇 **建立預測模型**。

> [!NOTE]
> 這 **現金流量預測** 模型訓練需要超過一年的 100 個或更多交易的資料。 我們建議您擁有至少兩年的超過 1,000 筆交易的數據。

有關現金流量預測功能的更多資訊，請參閱[現金流量預測](cash-flow-forecast-intro.md)。

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
