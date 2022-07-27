---
title: 混合模式規劃 - 結合分散式、流程和精益式採購
description: 本主題提供有關混合模式規劃的資訊。
author: johanhoffmann
ms.date: 11/03/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResStorageDimensionGroup, InventItemOrderSetup, ReqItemTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 52931
ms.assetid: 2e8b5fd1-cee9-45da-a3ae-6961fb020b89
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a199d5ac7633aba894ffbc17db015100ae93d895
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8447945"
---
# <a name="mixed-mode-planning---combine-discrete-process-and-lean-sourcing"></a>混合模式規劃 - 結合分散式、流程和精益式採購

[!include [banner](../includes/banner.md)]

本主題提供有關混合模式規劃的資訊。 在混合模式規劃中，您可以根據材料流程對供應鏈進行建模。 Dynamics 365 Supply Chain Management 確保材料流程遵循您的模型，無論選擇何種供應原則 (看板、生產訂單、訂購單、批次訂單或轉移訂單)。 

無論產品結構如何，您都可以選擇供應產品的整體策略。  

例如，您可以在裝配中進行看板控制，透過生產訂單、看板、轉移、批次訂單或適合您供應鏈特性的任何組合為裝配區域採購材料，但您仍然可以擁有全面的供應可見性。 此功能可最佳化供應鏈流程並增強對供應鏈的可見性。  

總排程中使用的供應原則細微性，取決於作為涵蓋範圍維度的儲存維度。 為了使總排程能夠控制不同位置類型的補貨和供應 (例如，將不同生產單元的生產車間分開，或將不同類型的材料和成品倉庫分開)，我們建議您啟用場地和倉庫作為涵蓋範圍維度。 或者，可以省略倉庫作為涵蓋範圍維度。 在這種情況下，您使用進階倉庫管理時，倉庫內的所有移動都由倉庫工作控制，而跨倉庫的所有移動都可以由提貨看板控制。

## <a name="supply-policies"></a>供應原則
混合模式規劃控制產品的供應方式，以及如何依據供應發佈衍生需求 (物料清單中的品項消耗\[物料清單\])。 根據訂單類型，系統會自動採購符合要求的材料。  

可以在產品層級或支援您要求的任何細微性定義供應原則。 您可在 **預設訂單設定** 頁面定義供應原則的細微性。  

供應原則可透過產品、品項維度 (設定、顏色和尺寸)、場地和倉庫來控制。 此設定在 **品項涵蓋範圍** 頁面進行。  

預設訂單類型控制訂單總體規劃產生的內容。  

無論如何建模供應鏈，Supply Chain Management 都支援您的供應原則組合。 您可以擁有源自看板的生產訂單。 或者，您可以有一個批次訂單，該訂單需要透過轉移或看板提供的產品。  

Supply Chain Management 會確保材料流程遵循模型。  

在定義供應原則後，執行時會動態指派用於揀料的倉庫。  

通常不會為將來的日期建立看板，因為看板的生命週期很短。 為了保持對供應鏈的全面可見性，我們引入了「計劃看板」的新規劃概念，用於計算衍生需求，並有助於確保作為需求來源依據的邏輯，與實際看板建立時使用的邏輯相同。  

其他所有供應原則都存在相同的邏輯。 因此，長期材料規劃所依據的邏輯，與您預期在核准生產和供應後執行實際訂單的邏輯相同。

## <a name="materials-allocation-cross-supply-policy--resource-consumption-on-boms"></a>材料分配交叉供應原則 – 物料清單上的資源消耗
資源消耗是一個重要的功能。 資源消耗使倉庫能夠根據供應原則 (訂單類型) 動態選擇揀選材料，也使基礎資料的維護更加容易。  

資源消耗要求根據產品的供應方式指派從中揀料的倉庫。 換句話說，執行時系統會找到應該用於製造的資源。 然後，系統會根據這些資源找到揀料倉庫。  

對於不受供應原則影響的工作，如果供應發生變化，您不必變更物料清單的資訊。 對於臨時變更，Supply Chain Management 確保材料源自正確的倉庫。

## <a name="process-manufacturing--the-production-type"></a>製程製造 - 生產類型
為了在混合模式下獲得充分的靈活性，我們建議您對所有產品使用生產類型物料清單。 然後，您可以使用生產訂單、看板、轉移訂單或訂購單來供應產品。 對於製程製造，您必須使用 **公式**、**副產品**、**副產品** 或 **規劃品項** 的生產類型。 看板和生產訂單不能用於這些生產類型。





[!INCLUDE[footer-include](../../includes/footer-banner.md)]