---
title: 成本元素維度
description: 作為成本會計的核心支柱之一，成本元素維度用於分類和追蹤成本流向。
author: AndersGirke
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CAMDimension
audience: Application User
ms.reviewer: roschlom
ms.custom: 223204
ms.assetid: 1eda0e62-760b-4737-9dfd-3c3c38d80c1a
ms.search.region: global
ms.author: roschlom
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 667fb81a2c1c8f564c09fe8fb7921c7aff75920bfa4326e82078583df61576e0
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450285"
---
# <a name="cost-element-dimensions"></a>成本元素維度

[!include [banner](../includes/banner.md)]

作為成本會計的核心支柱之一，成本元素維度用於分類和追蹤成本流向。 

成本元素對應於會計科目表中與成本相關的項目。 基本上，它可以是成本可以流向的業務中最低等級的任何類型的元素。 成本元素的概念範圍從分類帳科目到所有與成本相關的資源。 目前，成本會計支援分類帳科目。

## <a name="two-types-of-cost-elements"></a>成本元素的兩種類型
有兩種類型的成本元素：主要成本元素和次要成本元素。 下表說明了這兩種類型之間的區別。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><strong>主要成本元素</strong></td>
<td><strong>次要成本元素</strong></td>
</tr>
<tr class="even">
<td>主要成本元素代表從財務會計到成本會計的成本流。 成本元素結構對應於總帳中的損益科目結構，其中一個成本元素可以對應一個主科目。 根據業務需要，並非所有主要科目都必須表示為成本元素。 主要成本元素的範例包括：
<ul>
<li>銷貨成本成本 (COG)</li>
<li>間接物料成本</li>
<li>人事費</li>
<li>能源成本</li>
</ul></td>
<td>次要成本元素代表內部成本流，因為這些成本僅在成本會計中建立和使用。 它們用於確保成本來源可以追蹤。 這些成本元素用於成本分攤和間接費用計算。 次要成本元素的範例包括：
<ul>
<li>生產成本</li>
<li>生產、物料和行銷費用</li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="cost-element-dimensions-and-cost-element-dimension-members"></a>成本要素維度和成本要素維度成員
成本元素稱為 *成本元素維度*。 各個維度值稱為 *成本元素維度成員*。 例如，您將美國會計科目表結構 (COA) 做為法定申報的基礎。 此 COA 會當作成本元素維度。 作為主要成本元素的科目在成本會計中表示為成本元素維度成員。 以下螢幕擷取畫面舉例說明了作為成本元素維度的主科目，及其作為成本元素維度成員的實際主科目。 

[![作為成本元素維度的主科目螢幕擷取畫面。](./media/cost-element-dimensions.png)](./media/cost-element-dimensions.png)

## <a name="import-cost-element-dimension-members-through-data-connectors"></a>透過資料連接器匯入成本元素維度成員
為了簡化成本會計中成本元素維度成員的設定，您可以使用預先構建或自訂構建的資料連接器，從一個或多個來源系統中擷取主要成本元素。

## <a name="implementation-considerations"></a>執行注意事項
由於成本元素代表最低等級的成本詳細資料，因此您應確保在實施成本元素結構時包含製作管理報表所需的所有成本元素。 為成本控制找到適當數量的成本元素可能是一項挑戰。 擁有數千個成本元素，則難以控制每個成本元素。 作為替代方案，您可以將成本元素分組，並在彙總等級管理成本控制。





[!INCLUDE[footer-include](../../includes/footer-banner.md)]