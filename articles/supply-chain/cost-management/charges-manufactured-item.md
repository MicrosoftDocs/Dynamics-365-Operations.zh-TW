---
title: 顯示製造品項的費用
description: 製造品項的固定成本反映了作業設定時間以及具有固定數量或固定報廢量的組件。
author: AndersGirke
ms.date: 04/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CostingVersion, InventItemPrice
audience: Application User
ms.reviewer: kamaybac
ms.custom: 274483
ms.assetid: 6f5b851b-c5a7-43ef-b380-0d316667c1ef
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.dyn365.ops.version: AX 7.0.0
ms.search.validFrom: 2016-02-28
ms.openlocfilehash: dbce06f554a5c2cf3a52d1a508c1391882af44b8
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448860"
---
# <a name="display-charges-for-a-manufactured-item"></a>顯示製造品項的費用

[!include [banner](../includes/banner.md)]

製造品項的固定成本反映了作業設定時間以及具有固定數量或固定報廢量的組件。

品項費用的計算總額可以與品項的單位成本一起顯示。 但是，費用有時會顯示為單獨的欄位，並且不包含在品項的單位成本中。 當費用顯示為單獨的欄位時，一個欄位顯示費用總額，另一個欄位顯示用於攤銷金額的成本核算批量的大小。 例如，品項價格頁面將費用顯示為兩個單獨的欄位。 但是，「完成」頁面顯示品項每單位總成本，並且攤銷成本包含在單位成本中。

用於標準成本時，製造品項的費用始終包含在物料的單位成本中。 用於計劃成本，則可以選擇是否將它們包括在內。 成本核算版本中的原則，強制將費用包含在製造品項的成本中。 當您啟用品項的成本記錄時，您會為品項基本成本資訊更新費用，該資訊顯示在品項價格頁面中。 費用會顯示為兩個單獨的欄位，並且不包含在品項的單位成本中。 每次啟用都會更新項品項的基本成本資訊，即使啟用反映了不同的站點。 因此，您應該將基本成本資訊視為參考資訊。







[!INCLUDE[footer-include](../../includes/footer-banner.md)]