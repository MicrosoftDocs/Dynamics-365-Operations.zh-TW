---
title: 資產計量
description: 本主題說明如何在資產計量管理中建立資產類型。
author: johanhoffmann
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetObjectCounterPart, EntAssetObjectCounterLookup, EntAssetCounterType, EntAssetObjectCounterTotals
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: fc515615afaa172e1832508d79e202b166f134a9171a0a35ea4f372f9d19b7e2
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446727"
---
# <a name="counters"></a>計數器

[!include [banner](../../includes/banner.md)]

本主題說明如何在資產計量管理中建立計數器類型。 計數器類型是用於對資產進行計數器註冊，例如，關於生產小時數或資產生產的數量。 資產類型與計數器類型相關。 這代表只有在資產上使用的資產類型上設定了計數器時，才能在資產上使用計數器。

在您可以對資產進行計數器註冊之前，您會先建立要在 **計數器** 中使用的計數器類型。 接下來，您可以在 **計數器** 中的資產上建立計數器註冊。 

計數器可用於維護計劃。 維護計劃明細可以是「計數器」類型，例如，與生產小時數或生產數量有關。 

計數器註冊可以根據生產時間或生產數量手動或自動更新。 可以將計數器設定為使用三種更新方法之一 (在 **計數器** 的 **更新** 欄位中選擇)：
  
- 手動 - 您必須手動註冊計數器值。  
- 生產小時數 - 計數器會根據生產小時數自動更新。  
- 生產數量 - 計數器會根據生產數量自動更新。  

>[!NOTE]
>如果使用生產數量，*所有* 已註冊的項目都包括在計數器註冊中，良好數量以及錯誤數量。 如果需要，永遠都可以進行手動計數器註冊。

## <a name="create-counter-types-for-asset-counter-registrations"></a>為資產計數器註冊建立計數器類型

1. 選擇 **資產管理** > **設定** > **資產類型** > **計數器**。
2. 選擇 **新增** 建立新的計數器類型。
3. 將 ID 插入 **計數器** 欄位，並在 **名稱** 欄位插入計數器名稱。
4. 在 **一般** FastTab 的 **單位** 欄位，選擇計數器單位。
5. 在 **更新** 欄位中，選擇要用於計數器的更新方法。
6. 如果資產結構中的子系資產應自動繼承在父系資產上進行的計數器註冊，請在 **繼承計數器值** 切換按鈕上選擇是。
7. 在 **總彙總** 欄位中，選擇用於使用此計數器類型的計數器的求和方法。 「Sum」是用於將註冊值連續新增到總值的標準選擇。 如果設定了一個計數器來監控閾值，例如關於溫度、振動或資產的磨損，則可以使用「Average」。 
8. 在 **偏差上** 欄位中，插入上層百分比以驗證手動計數器註冊是否在預期範圍內。 該驗證是以現有計數器註冊的線性增長為根據。
9. 在 **偏差下** 欄位中，插入下層百分比以驗證手動計數器註冊是否在預期範圍內。 該驗證是以現有計數器註冊的線性減少為根據。
10. 在 **類型** 欄位中，在您進行手動計數器註冊，並出現超出定義範圍的偏差時，選擇要顯示的訊息類型 (訊息、警示、錯誤)。
11. 在 **資產類型** FastTab 上，新增應該能夠使用計數器的資產類型。
12. 在 **相關資產計數器** FastTab 上，新增您想在更新此計數器時自動更新的計數器。


>[!NOTE]
>僅在相關計數器在計數器設定中具有與其相關的資產類型時，才會自動更新相關計數器。 例如：您為「生產小時數」設定了一個計數器，並新增了資產類型「Truck Engine」。 當該計數器更新時，相關的計數器「Oil」也會被更新為相同的計數器值。 **計數器** 中的設定包括「小時」的設定。 此外，在「Oil」計數器上，應將資產類型「Truck Engine」新增到 **資產類型** FastTab 以確保計數器關係。 有關小時和油量計數器的設置範例，請參見下面的螢幕擷取畫面。

當資產類型新增到 **計數器** 中的計數器類型時，該計數器會自動新增到 [資產類型](../setup-for-objects/object-types.md)中的 **計數器** FastTab 上的資產類型中。

![圖 1。](media/071-setup-for-objects.png)



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]