---
title: 計劃您的區域會計科目表
description: 本主題提供將在貴組織明文要求遵守法定/當地要求時，為貴組織計劃會計科目表的資訊。
author: VeselinaE
ms.date: 10/07/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DimensionConfigureAccountStructure, LedgerChartOfAccounts, LedgerConsolidateAccountGroup, MainAccountConsolidateAccount, DimensionDetails, MainAccountDetails
ROBOTS: ''
audience: Application User
ms.devlang: ''
ms.reviewer: roschlom
ms.tgt_pltfrm: ''
ms.custom: 14051
ms.assetid: 10edb129-33f0-4cf9-b2a7-4b7ffa09b229
ms.search.region: Global
ms.search.industry: ''
ms.author: veneva
ms.search.validFrom: 10/07/2021
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e224a2e24b4ba293c953c6c883307038128e2f04
ms.sourcegitcommit: ba10ba2cd4fb4267afb5aacae4f6a52aa2456e7e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/11/2021
ms.locfileid: "8451188"
---
# <a name="plan-your-local-chart-of-accounts"></a>計劃您的區域會計科目表

[!include [banner](../includes/banner.md)]

當貴組織包括必須符合生意往來特定區域要求的法人實體時，本主題提供將幫助您計劃會計科目表的資訊。 本主題使用下列術語說明會計科目表：

- **全球性** – 組織在全球使用的會計科目表。 絕大多數情況下，您將合併到此會計科目表。
- **區域** – 特定國家或地區的法人實體使用的會計科目表。
- **共用** – 供多間法人實體使用的會計科目表。 全球性會計科目表和區域會計科目表可以共用。

您可以建立和共用多份會計科目表。 共用的會計科目表可由多間法人實體使用，但每間法人實體只能指派到一份會計科目表。 法人實體使用的會計科目表在 **分類帳** 頁定義。

當他們設計會計科目表時，許多組織的目標是全球會計科目表。 共用的會計科目表功能允許建立全球性會計科目表。 建立和使用單份會計科目表有多項好處。 例如，治理和控制、維護和編製報表更容易。

大多數組織更傾向於全球會計科目表，這是最容易落實的類型。 然而，一些法人實體需要區域會計科目表，原因如下：

- 區域規管要求
- 區域會計準則要求
- 產業要求
- 公司特定報表編製和分析要求

如果貴組織要求法人實體使用區域會計科目表，目前開放兩個選項供人落實：

- 指派全球會計科目表，並定義符合區域要求的其他方式。
- 將區域會計科目表指派給法人實體，並定義與全球會計科目表的關係。

組織結構和報表編製結構判定使用的選項。

[![顯示組織結構如何判定使用全球或區域會計科目表的示意圖](./media/local-chart-of-accounts-diagram.png)](./media/local-chart-of-accounts-diagram.png)

如果全球會計科目表指派給法人實體，則開放使用下列選項符合區域報表編製要求：

- 進行區域合併。
- 使用財務維度追蹤區域會計科目表。
- 在全球會計科目表建立區域主科目。
- 對區域會計科目表進行外部測繪。

如果區域會計科目表指派給法人實體，則只有目前開放使用的選項符合全球報表編製要求，即全球合併。

## <a name="global-chart-of-accounts-assigned-to-a-legal-entity"></a>指派給法人實體的全球會計科目表

如果您必須指派全球會計科目表分配給法人實體，目前開放四個選項用來配置系統，如前所述。 以所有四個選項而言，皆已配置一份會計科目表並連結 **分類帳** 頁面上的每間法人實體。 於是每個選項都使用不同辦法符合在地化要求。 下列章節概述配置系統符合在地化要求的高等級步驟。 他們也說明每個選項的優點和缺點。

### <a name="do-local-consolidation"></a>進行區域合併

區域合併是符合區域科目表要求，及善用專為此目的設計的系統功能的推薦辦法。

#### <a name="set-up-consolidation-for-a-local-chart-of-accounts"></a>針對區域會計科目表設定合併

1. 建立一份包括所有必要主科目的單份全球會計科目表。
2. 每間法人實體在 **分類帳** 頁面上指派全球會計科目表。
3. 必須針對每次的在地化建立合併法人實體。
4. 請執行以下其中一個步驟：

    - 如果只需要一次在地化動作，請在 **主科目** 頁面，或使用 **合併群組** 和 **額外合併科目** 頁配置合併科。
    - 如果需要進行多次在地化，或者如果科目編號和科戶名稱需要翻譯，請使用 **合併群組** 和 **額外合併科目** 代表在地化要求的頁面。

5. 執行合併流程以將使用全球會計科目表的來源法人實體值轉換為使用區域會計科目表的合併公司。

#### <a name="advantages"></a>優點

- 這項辦法提供整個組織工作的一致方式。
- 區域位置的一次性翻譯已完成。
- 此項辦法支援主科目識別碼和每個主科目名稱的翻譯。
- 它支援多次在地化。

#### <a name="disadvantages"></a>缺點

- 已建立額外合併公司。
- 已完成額外合併流程。
- 只有在合併流程完成後，在地化圖表上才能納入這套辧法。

### <a name="use-a-financial-dimension-to-track-the-local-chart-of-accounts"></a>使用財務維度追蹤區域會計科目表。

此方法使用財務維度，其中財務維度值代表在地化所需的區域主科目。 如果只需要在地化一次，它呈現不錯的效果。 不過隨著您新增更多次在地化和財務維度，它會逐漸變得不管用。

#### <a name="set-up-a-financial-dimension-for-a-local-chart-of-accounts"></a>設定財務維度給區域會計科目表

1. 建立一份包括所有必要主科目的單份全球會計科目表。
2. 每間法人實體在 **分類帳** 頁面上指派全球會計科目表。
3. 建立財務維度代表區域會計科目表。
4. 建立財務維度值代表區域會計科目表中的主科目。
5. 更新科目結構，使其包括 "區域會計科目表" 財務維度。
6. 確保 "區域會計科目表" 財務維度始終有數值，並且不允許出現空白值。 考慮使用衍生維度或固定維度。
7. 建立財務維度集合，其中 "區域會計科目表" 財務維度是第一個選取的財務維度。 試算表產生時可以使用財務維度集合。

#### <a name="advantages"></a>優點

- 全球和區域會計科目表的主科目都存在於交易等級。 主科目是全球性，而財務維度值是區域性。
- 這套辦法提供全球財務部位和區域財務部位的即時報表和視圖。

#### <a name="disadvantages"></a>缺點

- 以總帳參數而言，如果 **彙總科目使用值** 欄位設定為 **會計分配**，則代表費用/資產/營收主科目的財務維度將會誤用於應收帳款和應付帳款彙總科目。 我們建議您改成設定此欄位為來源文件，確保使用正確的財務維度值。
- 如果需要許多區域會計科目表，並且只能使用一個財務維度，則使用的財務維度值清單會變得冗長難以處理。
- 如果需要許多區域會計科目表，並且使用分開的財務維度代表，則新增財務維度和財務維度集合時，系統的可用性和效能會受到影響。
- 我們建議您仔細思考需要的財務維度數量、每個維度裡的值數量以及財務維度集合數量，因為所有這些因素都會影響系統效能。

### <a name="create-local-main-accounts-in-the-global-chart-of-accounts"></a>在全球會計科目表建立區域主科目。

*複製編輯器詢問的內容：* 這套辦法中，全球會計科目表的區域主科目包括全球會計科目表中，區域會計科目表的主科目。

*原始版本：* 全球 CoA 辦法的區域主科目是區域 CoA 主科目納入全球 CoA。

*倘若它說：* 這套辦法中，區域會計科目表的區域主科目納入全球會計科目表。


#### <a name="set-up-local-main-accounts-in-the-global-chart-of-accounts"></a>在全球會計科目表設定區域主科目。

1. 建立單一會計科目表包括全球會計科目表和區域會計科目表的主科目。
2. 每間法人實體在 **分類帳** 頁面上指派全球會計科目表。
3. 在會計科目表建立總計科目以便加總代表相同用途的主科目。
4. 建立每個區域科目的優先法人實體可防止非專屬設計的區域科目遭到其他法人實體交易。
5. 建立每個全球科目優先的法人實體，防止在地化法人實體交易。

#### <a name="advantages"></a>優點

- 全球財務部位和區域財務部位的即時視圖現在開放特定報表和系統的特定視圖使用，例如資產負債表財務報告。 它同時也可藉由總計科目上的 **期間** 按鈕存取。
- 您在總帳科目中沒有額外區段。

#### <a name="disadvantages"></a>缺點

- 總計科戶的使用和能見度有限。 例如，**試算表** 清單頁看不見總計科目。
- 維護需要額外的努力。
- 建立財務報告需要額外的人工心力。

### <a name="do-external-mapping-to-the-local-chart-of-accounts"></a>對區域會計科目表進行外部測繪。

採用全球會計科目表假定您在系統外管理測繪和在地化。 使用這套辧法時，您只要在 Microsoft Dynamics 365 Finance 建立單一全球會計科目表處理系統外需求即可。

#### <a name="set-up-external-mapping-to-a-local-chart-of-accounts"></a>對區域會計科目表設定外部測繪。

1. 建立一份包括所有必要主科目的單份全球會計科目表。
2. 每間法人實體在 **分類帳** 頁面上指派全球會計科目表。
3. 對 Finance 以外的區域會計科目表進行測繪。

#### <a name="advantages"></a>優點

- 這套辦法提供整個組織統一的工作方式。

#### <a name="disadvantages"></a>缺點

- 系統尚未開放使用區域報表編製功能。
- 這套辦法在建立財務報告時容易出錯。

## <a name="local-chart-of-accounts-assigned-to-legal-entity"></a>指派給法人實體的區域會計科目表

如果貴組織決定不跨法人實體使用全球會計科目表，則會針對各個唯一的區域會計科目表建立分開的會計科目表。 接著每間法人實體連結到 **分類帳** 頁面對應的會計科目表。

### <a name="do-global-consolidation"></a>進行全球合併

這套辦法中的合併公司用來將每間來源區域公司的餘額加總且併入合併公司的全球組合式會計科目表。 此套辦法要求您維護每份區域會計科目表測繪合併公司的全球會計科目表。

#### <a name="set-up-global-consolidation"></a>設定全球合併

1. 針對區域會計科目表不同的每間法人實體建立分開的會計科目表。 如果任何法人實體有相同的區域會計科目表，則只需要一份區域會計科目表並可共用。
2. 每間法人實體在 **分類帳** 頁面上指派適當的會計科目表。
3. 選擇性：針對全球會計科目表不同的每間合併公司，建立適用全球會計科目表的會計科目表。
4. 針對需要的每個合併等級建立合併法人實體，並在 **分類帳** 頁面上指派適當的會計表。
5. 請執行以下其中一個步驟：

    - 如果只需要一次合併，請在 **主科目** 頁面上配置合併科目。
    - 如果需要多次合併，或者如果科目編號和科戶名稱需要翻譯，請使用 **合併群組** 和 **額外合併科目** 代表全球會計科目表的要求。

6. 執行合併流程將區域法人實體的餘額轉移到合併的法人實體。 此合併法人實體使用您在步驟 5 定義的合併科目。

#### <a name="advantages"></a>優點

- 區域會計準則格式須當地套用。
- 這套辦法給區域財務團隊一種更輕鬆的工作方式。

#### <a name="disadvantages"></a>缺點

- 尚未開放全球部位的即時視圖。
- 合併流程的執行次數可能更加頻繁。

## <a name="additional-resources"></a>其他資源

- [計劃您的會計科目表](plan-chart-of-accounts.md)
- [配置分類帳](configure-ledger.md)
- [財務維度和過帳](Default-dimensions.md#balancing-dimension)
- [財務維度集合](financial-dimension-sets.md)
- [合併和消除概觀](../budgeting/consolidation-elimination-overview.md)
- [合併科目群組和額外合併科目](../budgeting/consolidation-account-groups-consolidation-accounts.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]