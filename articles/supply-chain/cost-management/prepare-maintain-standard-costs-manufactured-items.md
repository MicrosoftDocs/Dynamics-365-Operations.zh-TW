---
title: 準備維護製造品項的標準成本
description: 本主題描述準備維護製造品項的成本的步驟。
author: AndersGirke
ms.date: 01/17/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventStdCostConv
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ec68e1efc261920dc8f08ed602836b1939511dfce01008c093af7916ecd71618
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446823"
---
# <a name="prepare-to-maintain-standard-costs-for-manufactured-items"></a>準備維護製造品項的標準成本

[!include [banner](../includes/banner.md)]

本主題描述準備維護製造品項的成本的步驟。 製造品項的步驟與購買項目的步驟略有不同。

指派給製造品項的原則會影響父系製造品項的成本計算。 要準備維護製造品項的標準成本，請按照以下步驟操作。

1. 將項目模型群組指派給該製造品項。 

   此項目模型群組確定將會使用標準成本。

2. 將項目群組指派給該製造品項。 

   此項目群組包含套用在該製造品項的分類帳科目。 具有標準成本庫存模型的製造品項的分類帳科目包括數個生產差異、成本變更差異和庫存成本重估。

3. 將庫存測量單位指派給該品項。 

   該品項的成本一律以其庫存測量單位表示。

4. 不要將成本群組指派給該製造品項，除非該品項將被視為採購項目。

5. 將物料清單 (BOM) 計算群組指派給該製造品項。 

   該品項的 BOM 計算群組定義使用的警告條件。 那麼，當 BOM 計算完成時，可以產生有關計算錯誤的可能來源的警告訊息。 例如，警告訊息可以識別現用的 BOM 或路由何時不存在。 BOM 計算群組包含一個停止展開原則，該原則指出何時應將製造品項視為採購項目。

6. 如果該製造品項具有恆定成本，則為其分配標準訂單數量。 

   標準訂單數量是用於攤銷恆定成本的會計批量。 恆定成本的範例包括路由操作中的設定時間和 BOM 中的恆定組件數量。

7. 定義該製造品項的 BOM。 

   可以為該製造品項定義一個或多個 BOM 版本。 驗證您想要的版本已標記為已核准和使用中，而且它們具有您想要的生效日期。 該 BOM 版本可以是全公司的或特定於站點的。

8. 定義該製造品項的路由。 

   可以為該製造品項定義一個或多個路由版本。 驗證您想要的版本已標記為已核准和使用中，而且它們具有您想要的生效日期。 此路由版本必須特定於站點的。

如果您想將路由資訊用於成本計算，則需要另外的準備步驟。 例如，指派給路由操作的成本類別必須正確且完整。

## <a name="related-topics"></a>相關主題

[攤銷製造品項的恆定成本](amortize-constant-costs-manufactured-item.md)

[設定可以生產或採購的產品](manufactured-items-treated-as-purchased-items.md)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]