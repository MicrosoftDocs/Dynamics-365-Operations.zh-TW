---
title: 啟用客戶付款預測
description: 本主題說明如何在 Finance Insights 中打開和配置客戶付款預測功能。
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
ms.search.validFrom: 2020-05-29
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: b83d1230c94462ca722ad7ceb7b2185afd636aae
ms.sourcegitcommit: 3105642fca2392edef574b60b4748a82cda0a386
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/12/2022
ms.locfileid: "8451539"
---
# <a name="enable-customer-payment-predictions"></a>啟用客戶付款預測

[!include [banner](../includes/banner.md)]

本主題說明如何在 Finance Insights 中打開和配置客戶付款預測功能。 您在 **特徵管理** 工作區並在 **Finance Insights 配置** 頁面。 本主題還包括可幫助您有效使用該功能的資訊。

> [!NOTE]
> 在完成以下步驟之前，請務必完成[配置 Finance Insights](configure-for-fin-insites.md)話題。

1. 打開客戶付款預測功能：

    1. 打開 **功能管理** 工作區。
    2. 選擇 **檢查更新**。
    3. 在 **全部** 標籤，搜尋 **客戶付款預測**。 如果您沒有找到該功能，請搜尋 **(預覽) 客戶付款預測**。 
    4. 開啟功能。

    客戶付款預測功能現在已打開並準備好進行配置。

2. 配置客戶付款洞察功能：

    1. 去 **信貸和收款\>設置\>Finance Insights\>客戶付款預測**。
    2. 在 **Finance Insights 配置** 頁，在 **客戶付款預測** 索引標籤，選擇 **查看預測模型中使用的資料欄位** 打開 **預測模型的資料欄位** 頁。 在那裡，您可以查看用於為客戶付款預測創建人工智能 (AI) 預測模型的默認欄位列表。

        要使用默認欄位列表創建預測模型，請關閉 **預測模型的資料欄位** 頁，然後在 **Finance Insights 配置** 頁，設置 **啟用功能** 選項 **是的**。
        
   > [!NOTE]
   > 這 **客戶付款預測** 該功能需要在過去六到九個月內完成 100 多筆交易。 交易可以包括普通發票、銷售訂單和客戶付款。 這些資料必須分佈在 **準時**、**晚了** 和 **非常晚** 的設定。    
     

    3. 指定「非常晚」的交易期來定義什麼 **非常晚** 預測桶對您的業務代表什麼。

        對於每張未結髮票，系統會在三個桶中預測付款機率：**準時**、**晚了** 和 **非常晚**。

        - **準時** - 此貯體包括在交易到期日或之前支付的款項。
        - **晚了** – 此貯體包括預計在交易到期日之後但在「非常晚」交易期開始之前支付的款項。
        - **非常晚** – 此貯體包括預計將在「非常晚」交易期開始後支付的款項。

        > [!NOTE]
        > 如果您更改「非常晚」交易期限並選擇 **更改延遲閾值** 客戶支付的 AI 預測模型創建完成後，刪除現有的預測模型，創建一個新的模型。 新的預測模型將根據為定義它而輸入的設置將交易移至「非常晚」時期。

    4. 完成定義「非常晚」交易期間後，選擇 **創建預測模型** 創建預測模型。 這 **預測模型** 部分 **Finance Insights 配置** 頁面顯示預測模型的狀態。

        > [!NOTE]
        > 在創建預測模型時，您可以隨時選擇 **重置模型創建** 重新啟動該過程。

    該功能現在已經配置好，可以使用了。

開啟和配置該功能、創建預測模型並開始工作後，**預測模型** 的部分 **Finance Insights 參數** 頁面顯示模型的準確性。

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
