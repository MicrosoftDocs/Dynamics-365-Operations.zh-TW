---
title: 動作訊息
description: 動作訊息是系統生成的建議，通知更改現有計劃或確定訂單。
author: ChristianRytt
ms.date: 10/14/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqGroup, MCRSalesOrderMessages, MCRSalesTableDetailedStatus, TAMItemVendRebateGroup, TAMVendRebate, TAMVendRebateAgreementLineInfoPart, TAMVendRebateGroup, TAMVendRebateTable, TAMVendRebateTrans, ReqTransActionListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19411
ms.assetid: 52b46d93-7d02-46b5-aad1-9fd08206bf9d
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bb208d390d3b5d2091f5b0f112532794a4d78d8adcf947291a4183c3b3fd3f9c
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447210"
---
# <a name="action-messages"></a>動作訊息

[!include [banner](../includes/banner.md)]

動作訊息是系統生成的建議，通知更改現有計劃或確定訂單。

## <a name="introduction"></a>簡介

動作訊息由主計劃計算生成，反應更改需求。 例如，銷售訂單的發貨日期或數量可能變動，而之前為滿足其需求，已建立採購訂單。 在這種情況下，主計劃計算會生成一個以上的動作訊息，通知更新採購訂單。 由您決定是否進行建議的更改動作。

您可以設定如何計算動作訊息，指派其涵蓋群組到品項。

## <a name="select-action-messages"></a>選取動作訊息

在 **涵蓋群組** 頁面，您可以選擇您希望系統生成的動作訊息，以及訊息套用的涵蓋群組或品項。 您可以選取以下的動作訊息。

| 訊息             | 描述                                                                                                                                                                                                                                              |
|---------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **進階**         | 如果您選取此訊息，系統將在需要時生成動作訊息，通知將訂單移至更早的日期。 在 **提前寬限** 欄位，您也可以指定收貨和發貨之間，無需提前動作的最大天數。 |
| **推遲**        | 如果您選取此訊息，系統將在需要時生成動作訊息，通知將訂單移至更晚的日期。 在 **延遲寬限** 欄位，您也可以指定收貨和發貨之間，無需延遲動作的最大天數。       |
| **減少**        | 如果您選擇此訊息，則應減少生產訂單、採購訂單和其他收貨交易以防止庫存量過高。                                                                                                   |
| **增加**        | 如果您選擇此訊息，則應增加生產訂單、採購訂單和其他收貨交易以防止庫存量過低。                                                                                                    |
| **衍伸動作** | 如果您選擇此訊息，則會為衍伸需求建立動作訊息，例如，生產滿足部件訂單的動作。                                                                                                   |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]