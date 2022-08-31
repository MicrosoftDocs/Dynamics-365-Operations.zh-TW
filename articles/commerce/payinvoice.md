---
title: 建立付款發票情境
description: 本文章描述如何設定 Dynamics 365 Commerce 以支援發票付款相關的各種情境。
author: josaw1
ms.date: 11/14/2018
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: ''
ms.openlocfilehash: 78af54fec771e5012aca095d07fd772988a56029
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/03/2022
ms.locfileid: "8885366"
---
# <a name="set-up-pay-invoice-scenarios"></a>建立付款發票情境

[!include [banner](includes/banner.md)]

Dynamics 365 Commerce 已擴充支援發票付款功能：

- 在單一 POS 交易中支付多張銷售訂單發票。
- 支付各種客戶發票類型，包括手寫發票、專案發票和貸項通知單。

若要啟用這些案例，您必須依照如下所述設定商店的功能設定檔。

1. 移至 **Retail 和 Commerce \> 管道設定 \> POS 設定 \> POS 設定檔 \> 功能設定檔**，並選取連結到要為其進行變更的目標商店設定檔。
2. 在 **功能** 索引標籤上，根據需要設定以下參數。

    - **銷售訂單發票** - 選取 **是**，允許使用者在單一 POS 交易中支付一或多張銷售訂單發票。
    - **手寫發票** - 選取 **是**，允許使用者在單一 POS 交易中支付一或多張手寫發票。
    - **專案發票** - 選取 **是** 允許使用者在單一 POS 交易中支付一或多張專案發票。
    - **銷售訂單貸項通知單** - 選取 **是**，允許使用者根據未結發票結算多筆銷售訂單貸項通知單，或為客戶處理未結貸項通知單的退款。

> [!NOTE]
> 尚不支援支付或結算部分付款金額。


[!INCLUDE[footer-include](../includes/footer-banner.md)]