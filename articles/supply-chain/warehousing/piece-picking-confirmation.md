---
title: 分揀確認
description: 分揀可讓您透過在行動裝置上進行揀貨或盤點工作，來確認每件庫存。
author: Mirzaab
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSRFAutoConfirm, WHSRFMenuItem
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a925685b80c635cf036f19748e16d415953ed5fdda7b81498baeade35ccbfcab
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447156"
---
# <a name="piece-picking-confirmation"></a>分揀確認

[!include [banner](../includes/banner.md)]

分揀可讓您透過在行動裝置上進行揀貨或盤點工作，來確認每件庫存。 對於分揀，您可以確認待處理的工作數量，最多可達在待揀貨的工作上指定的數量。 對於盤點工作，您可以掃描正在盤點的庫存並追蹤總數量。

當您啟用分揀時，會自動選擇產品確認。 對於工作類型揀貨，您可以設定件數上限。 這允許您設定在工作流程期間必須確認的件數上限。 數量上限是以正在處理的目前工作單元為基礎。 盤點工作類型不允許上限。

您還可以使用與掃描的條碼相關聯的數量和測量單位 (UOM)。 這將適用於在入庫流程的收貨，包括混合牌照接收、採購訂單品項、轉移訂單品項及裝載品項。 它也適用於分揀，其中在掃描條碼時會將數量新增至在條碼上的 UOM 與工作單元之間轉換的已確認件數總數。 在對條碼上的 UOM 進行盤點時，如果確認允許對序列群組盤點數量，則會該數量新增至總計數。

## <a name="where-it-applies"></a>適用處

分揀適用於所有的盤點工作及任何類型工作的初始揀貨。 如果該品項是由序號控制的，或者是來自牌照 (LP) 位置的生產或看板揀貨，且該品項設為暫存，則不適用分揀。

## <a name="set-up-piece-picking"></a>設定分揀

1.  在行動裝置功能表項目上，開啟設定表單以確認工作：倉庫管理 > **倉庫管理** > **設定** > **行動裝置** > **行動裝置功能表項目**。 
2. 從行動裝置功能表項目中，開啟工作確認設定。

當工作類型為揀貨或盤點時，以下選項可供選擇。


|           選項           |                                                                            描述                                                                            |
|----------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 分揀確認 | 可用於揀貨和盤點工作類型。 系統自動選擇產品確認。 允許您從行動裝置確認每件庫存。 |
|  件數上限  |                   如果已啟用分揀確認，則可用於揀貨工作。 設定您必須確認的件數限制。                   |



[!INCLUDE[footer-include](../../includes/footer-banner.md)]