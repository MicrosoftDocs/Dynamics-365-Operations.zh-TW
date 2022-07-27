---
title: 標準成本的成本計算版本限制
description: 本主題介紹適用於標準成本的成本計算版本限制。
author: AndersGirke
ms.date: 01/17/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CostingVersion
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2028cdabde3d01de16050b38893ec9e42353ae542be7a0cd7362cf62e9315170
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446964"
---
#  <a name="restrictions-on-costing-versions-for-standard-costs"></a>標準成本的成本計算版本限制

[!include [banner](../includes/banner.md)]

本主題介紹適用於標準成本的成本計算版本限制。 

以下限制有助於保證遵守標準成本計算原則：

-  費用必須包含在某品項的成本中。 製造品項的費用代表物料清單 (BOM) 和途程資訊中的攤銷固定成本。 因此，單位成本必須包含這些費用。 採購品項的費用也包含在品項的單位成本中。

-  製造品項的標準成本計算必須根據標準成本的成本計算版本中的成本記錄。 成本資料的替代來源只能用於計劃成本的成本計算版本，例如採購品項的採購價格貿易合約。 成本資料的替代來源由 BOM 計算群組定義。

-  BOM 計算必須在單級分解模式下進行。

可以將標準成本的品項成本資料複製到其他包含標準成本或計劃成本的成本計算版本。 但是，無法將計劃成本的品項成本資料複製到包含標準成本的成本版本中，因為本主題前述的限制不適用於計劃成本。

## <a name="related-topics"></a>相關主題

[成本計算版本概觀](costing-versions.md)

[更新非製造環境中的標準成本](update-standard-costs-non-manufacturing-environment.md)

[準備維護製造品項的標準成本](update-standard-costs-manufacturing-environment.md)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]