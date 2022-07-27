---
title: 更新製造環境中的標準成本
description: 本文提供有關如何在製造環境中更新標準成本的指南。
author: AndersGirke
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CostingVersion, InventStdCostConv
audience: Application User
ms.reviewer: kamaybac
ms.custom: 79663
ms.assetid: 3a7c3d13-8dbc-442d-a281-ac0ebe99ec83
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f0c8cae65ef95e299f9b774c4fa18dbdc615dd169138835f1852ee21a54cba69
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446835"
---
# <a name="update-standard-costs-in-a-manufacturing-environment"></a>更新製造環境中的標準成本

[!include [banner](../includes/banner.md)]

本文提供有關如何在製造環境中更新標準成本的指南。 

更新可以反映新品項、成本類別或間接成本計算公式。 它們還可以反映更正和成本變化。 此類型的更新會影響更新標準成本必須完成的的步驟，如以下情況所示：

-   為採購品項輸入預期的標準成本變化，然後將相應日期上的品項成本記錄狀態變更為 **使用中**。 但是，不要重新計算使用採購品項的製造品項的成本。
-   輸入新採購品項的標準成本，但不要重新計算具有包含新採購物料作為組件的物料清單 (BOM) 版本的製造品項的成本。
-   更正或更改採購物料的成本，或變更指派給採購品項的成本群組，並計算具有包含採購物料作為組件的 BOM 版本的所有製造品項的成本。
-   變更某成本類別的成本，並計算具有包含使用該成本類別的途程工序的途程版本的所有製造品項的成本。
-   變更指派給途程工序的成本類別或指派給成本類別的成本群組。 計算具有包含使用成本類別的途程工序的途程版本的所有製造品項的成本。
-   變更間接成本計算公式，並且為該變更影響的所有製造品項計算成本。
-   變更或新增製造品項的製造站點，並計算該站點的品項製造成本。
-   計算 (或重新計算) 某製造品項的成本，並重新計算具有包含製造品項作為組件的 BOM 版本的所有製造品項的成本。
-   根據已定義、已核准和有效的 BOM 和途程資訊計算新製造品項的成本。

每個案例都需要仔細考慮如何更新標準成本。





[!INCLUDE[footer-include](../../includes/footer-banner.md)]