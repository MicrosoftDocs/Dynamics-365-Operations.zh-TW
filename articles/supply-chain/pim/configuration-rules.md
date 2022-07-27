---
title: 設定規則
description: 本文說明關於設定規則的資訊。 對於使用維度式設定技術的產品，設定規則定義物料清單 (BOM) 中的品項之間的關係。
author: t-benebo
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BOMConfigRule
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19761
ms.assetid: e4c6622d-1e2d-4a4d-8047-c553a25d4f87
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1ddc74777ae0cde5367667f93eb29ffb21531e02
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448344"
---
# <a name="configuration-rules"></a>設定規則

[!include [banner](../includes/banner.md)]

本文說明關於設定規則的資訊。 對於使用維度式設定技術的產品，設定規則定義物料清單 (BOM) 中的品項之間的關係。

定義維度式設定模型時，設定規則可以使用。 設定規則用於強制或禁止物料清單 (BOM) 中的特定品項組合。 在建立 BOM 並將相關品項指派到各自的設定群組後，可以定義一個或多個設定規則。 如果兩個品項要在一起，則 **選取** 運算子用於確保包含。 如果兩個項目互斥，則 **取消選擇** 運算子用於確保排除。  

**注意：** 此資訊僅適用於使用維度式設定技術的基準產品。  

現有設定不受設定規則的後續變更影響。 但是，重要的是在定義新設定之前設定規則，以及如果您認為規則已變更，請檢查規則。  

**注意：** 在 **選取** 方法，衍生的設定群組、品項編號和設定會被自動選取。 注意：在 **取消選取** 方法，衍生的設定群組、品項編號和設定無法被選取。

## <a name="additional-resources"></a>其他資源

[維度式產品設定概觀](dimension-based-product-configuration.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]