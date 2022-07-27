---
title: 標準成本概觀的先決條件
description: 本主題介紹使用標準成本的基本步驟。
author: AndersGirke
ms.date: 07/25/2019
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: InventStdCostConv, CostingVersion
audience: Application User
ms.reviewer: kamaybac
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7c25f2109522c7ba549ef7c3ea429873d0e1f06e
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/15/2022
ms.locfileid: "8449778"
---
# <a name="prerequisites-for-standard-costs-overview"></a>標準成本概觀的先決條件

[!include [banner](../includes/banner.md)]

本主題介紹使用標準成本的基本步驟。 後續步驟取決於公司的營運。 例如，非製造環境、不使用路由的製造環境和使用路由的製造環境的步驟不同。 

要設定標準成本，請按照以下步驟操作。

**1. 為標準成本建立一個項目模型群組。**

使用 **項目模型群組** 頁面為標準成本建立一個新群組，並指派一個 **標準成本** 的庫存模型。 該項目模型群組的識別碼應該是有意義的，例如 **標準成本**。 選取核取方塊以表示該群組應允許財務負庫存，並且應過帳實際庫存和財務庫存。 此標準成本群組將指派給項目。

**2. 定義與標準成本差異相關的分類帳科目。** 

使用 **會計科目表** 頁面來定義與標準成本差異相關的分類帳科目。 必須先定義這些分類帳科目，它們才能在 **過帳** 頁面上被分配。 分類帳科目可以反映項目群組和成本群組。

**3. 將分類帳科目分配給與標準成本差異相關的項目過帳。** 

使用 **過帳** 頁面，指派與標準成本差異相關的分類帳科目。 您可以按項目（或項目群組）和成本群組（或成本群組類型）指定差異的分類帳科目，也可以指定分類帳科目適用於所有項目和所有成本群組。 這些選項對應到表、群組和所有的成本關係。 

在您定義項目過帳規則之前，使用 **交易組合** 頁面啟用成本關係（用於表、群組和所有）。

**4. 定義與標準成本相關的庫存參數。** 

-  使用 **庫存會計原則設定>參數** 頁面上的 **庫存會計** 索引標籤來定義與標準成本相關的兩個成本控制參數。

    -  在 **成本明細** 欄位中，選擇 **否** 或 **子分類帳**。 如果您選擇 **子分類帳**，則該成本明細為 *執行中* 成本明細。 執行中成本明細對於標準成本項目跨多層級產品結構的計算、保留和檢視成本群組細分非常重要。 當成本明細處於執行中時，您能以單一層級、多層級或總計格式報告和分析每個成本群組的庫存、在製品 (WIP) 和銷貨成本 (COGS)。 當執行中成本明細正在執行中時，如果您啟用製造品項的成本，則成本群組細分將會儲存在品項成本記錄中。 

    -  如果您選擇 **無**，則成本群組細分將不會為標準成本項目被維護。 換言之，製造品項的標準成本將作為一個單一金額進行計算和維護，無需成本群組細分。 製造組件的成本貢獻將彙總到該單一金額內。

-  在 **與標準的差異** 欄位中，選擇 **彙總** 或 **每個成本群組**。 若您選擇 **每個成本群組**，您便能按成本群組識別採購價格差異和生產差異。 您也能識別四種類型的生產差異：批量、數量、價格和替代差異。 如果您選擇 **彙總**，您則無法按成本群組識別差異，也無法識別四種類型的生產差異。 您只能檢視彙總的生產差異。

-  關於與標準的差異的原則獨立於成本明細原則。 換句話說，您可以選擇 **無** 成本明細原則，並選擇每個成本群組的差異，那麼按成本群組的生產差異將仍能被擷取。

**5. 為標準成本建立成本計算版本。** 

使用 **成本計算版本設定** 頁面，為標準成本建立一個或多個成本計算版本。 每個成本計算版本必須由一個 **標準成本** 的成本計算類型指定，並且必須允許內容包含成本資料。

**6. 準備現有客戶使用標準成本。** 

想要將現有項目更改為標準成本庫存模型的客戶必須使用 **標準成本轉換** 頁面。


## <a name="related-topics"></a>相關主題

[標準成本轉換概觀](standard-cost-conversion-overview.md)

### <a name="blogs"></a>部落格

#### <a name="community-blogs"></a>社群部落格

- [如何在Dynamics 365 for Finance and Operations中設定直接材料的標準成本](https://financefunction.tech/2018/06/07/how-to-set-up-standard-costs-for-direct-materials-in-dynamics-365-for-finance-and-operations)
- [在Dynamics 365 for Finance and Operations中的標準直接人工成本](https://financefunction.tech/2018/07/16/standard-direct-labor-cost-in-dynamics-365-for-finance-and-operations)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]