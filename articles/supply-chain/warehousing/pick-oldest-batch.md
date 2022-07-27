---
title: 在行動裝置上挑選最舊的批次
description: 本主題說明如何設定與套用選項，以從行動裝置中挑選最舊的批次。
author: Mirzaab
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSRFMenuItem
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d96221ae14610057cceed304efa01261eb01aef134e4bdad10ccd0386bd52cf9
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446949"
---
# <a name="pick-oldest-batch-on-a-mobile-device"></a>在行動裝置上挑選最舊的批次

[!include [banner](../includes/banner.md)]

您可以透過行動裝置功能表存取 **挑選最舊的批次** 組態，它允許您強制或警告倉庫員工挑選其目前位置中最舊的批次。  

## <a name="where-it-applies"></a>適用處
[挑選最舊的批次] 是在行動裝置功能表項目設定的，會影響項目之下的批次選擇。

## <a name="how-to-set-up-the-configuration-for-pick-oldest-batch"></a>如何設定挑選最舊批次組態 
對於設定使用現有工作的項目，可從行動裝置功能表將 **挑選最舊的批次** 設定為 **無**、**警告** 或 **強制**。

**無**：員工不會收到任何訊息，且允許他們挑選其位置中的任何批次。

**警告** 和 **強制**：當員工選擇批次時，到期日最舊的批次清單將顯示在批次控制項上方。 如果位置是由牌照控制，則具有最舊批次的牌照清單將顯示在牌照控制項上方。 
-   **警告**：如果員工選擇的牌照或批次未在顯示的清單中，則控制項將變為空白，並會顯示一則警告，表示有一個更舊的批次可供選擇。 若要允許員工繼續工作，員工可以再次選擇相同的牌照或批次。  
-   **強制**：員工將繼續收到有更舊批次可供選擇的訊息。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]