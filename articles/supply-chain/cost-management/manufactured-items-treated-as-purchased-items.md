---
title: 設定可以生產或採購的產品
description: 產品來源有多種方式 - 可以是生產 (製造) 或採購 (購買)。 本文章說明設定多重供應來源產品時，通常需要考慮的要點。
author: AndersGirke
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqGroup, ReqItemTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 21841
ms.assetid: acc608b7-2cad-4fba-afee-9b7cc93761ec
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 344a022561fa425747e7674bd600c65d70229557
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448092"
---
# <a name="set-up-products-that-can-be-produced-or-procured"></a>設定可以生產或採購的產品

[!include [banner](../includes/banner.md)]

產品來源有多種方式 - 可以是生產 (製造) 或採購 (購買)。 本文章說明設定多重供應來源產品時，通常需要考慮的要點。 

多重供應來源通常用於採購偶爾製造的品項，或是當主要製造的品項發生變更，導致該品項變為採購品項時。 品項首先被指定為製造品項，以定義支援該品項的生產訂單的物料清單 (BOM) 和路徑資訊。 生產類型應設定為 **BOM** (或者，對於過程製造來說，為 **公式** 或 **副產品**)。

當您使用標準成本時，可以計算用於製造品項的成本記錄。 但是，品項成本記錄，無法配對您要採購的標準成本。 在這種情況下，必須手動輸入標準成本，並將其使用於品項成本記錄。 對於成本計算，可以考慮使用一個特殊的 BOM 和路徑，用於代表產品在會計期間的供應組合，以盡可能減少因時間變化造成的差異。 此外，製造的品項可以從一個位置轉移至另一個位置。 因此，物料的成本必須手動輸入，並將其使用於要轉移的位置。 當您將製造的品項作為元件，用於更高等級的產品時，元件的成本應視為採購品項。 無論元件的成本是通過計算或手動輸入，都適用於本指南。 換句話說，BOM 計算應將品項成本視為採購的元件，而不是使用 BOM 和路徑資訊來計算成本。 

為了避免計算，請選取嵌入在品項指派的 BOM 計算群組中的 **停止展開** 標幟。 為了避免總排程計算品項展開的需求，請在品項涵蓋範圍或涵蓋範圍群組中將展開範圍設定為 0 (零) 天。 然後，主計劃計算會將品項視為採購品項，並且不會對品項的 BOM 和路徑資訊執行更多計算。







[!INCLUDE[footer-include](../../includes/footer-banner.md)]