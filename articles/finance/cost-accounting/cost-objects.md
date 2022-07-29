---
title: 成本物件維度
description: 分析成本時，使用成本元素維度來確定成本流向何處。 您可以使用成本物件維度來確定應在何處分配成本。 本主題提供有關成本物件維度的資訊。
author: AndersGirke
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CAMDimensionMember, CAMCostObject
audience: Application User
ms.reviewer: roschlom
ms.custom: 223174
ms.assetid: 2a1cdd35-30cb-41e7-9506-67fd04a537c5
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roschlom
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: e266a9ee2f47b819a4074291ad4a52d8df46ce1abe4f16308a3645375cd2dd80
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450267"
---
# <a name="cost-object-dimensions"></a>成本物件維度

[!include [banner](../includes/banner.md)]

分析成本時，使用成本元素維度來確定成本流向何處。 您可以使用成本物件維度來確定應在何處分配成本。 本主題提供有關成本物件維度的資訊。

成本物件可以是您要估計、分配成本或直接測量的任何類型物件。 典型的成本物件包括產品、專案、資源、部門、成本中心和地理區域。 管理層使用成本物件來量化成本並推動盈利能力分析。

## <a name="cost-object-dimensions-and-cost-object-dimension-members"></a>成本物件維度和成本物件維度成員
成本物件稱為 *成本物件維度*。 在您決定成本物件維度應該引用哪個實體之後，必須指定各個維度值或將它們從其他來源系統匯入成本會計。 這些單獨的維度值稱為 *成本元素維度成員*。 例如，您要使用名為「成本中心」的財務維度作為成本物件維度。 要查看成本如何流向各個成本中心，必須匯入成本物件維度成員。 在這種情況下，成本物件維度成員是實際成本中心，例如銷售、生產、管理和地理位置。 以下螢幕擷取畫面舉例說明了作為成本物件維度的成本中心及其做為成本物件維度成員的實際成本中心。 

[![成本中心做為成本物件維度的螢幕擷取畫面。](./media/cost-object-dimensions.png)](./media/cost-object-dimensions.png)

## <a name="import-cost-object-dimension-members-through-data-connectors"></a>透過資料連接器匯入成本物件維度成員
為了更輕鬆地匯入成本物件維度成員，您可以使用資料連接器從要做為成本物件維度的實體中擷取值。 您可以使用預先建立的資料連接器或您建立的自訂資料連接器。





[!INCLUDE[footer-include](../../includes/footer-banner.md)]