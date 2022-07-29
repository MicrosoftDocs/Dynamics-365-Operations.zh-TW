---
title: 設定子公司法律實體進行合併
description: 本主題說明如何處理合併公司的會計科目表。
author: jinniew
ms.date: 10/30/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2020-10-31
ms.dyn365.ops.version: 8.0.1
ms.openlocfilehash: fbec5ad8fa5e17b75859c07ee64a66c9568c97d3d18b6a7616a64303d3a33f10
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450270"
---
# <a name="set-up-a-subsidiary-legal-entity-for-consolidation"></a>設定子公司法律實體進行合併

[!include [banner](../includes/banner.md)]

您用於準備子公司科目以進行合併的方法，部分取決於子公司法律實體中會計科目表結構能夠反映已合併法律實體中會計科目表的程度。

在您開始進行合併以作為期末結算的一部分之前，請先完成期末結算的準備活動，但在合併完成之前請勿關閉子公司科目。 如需期末結算的詳細資訊，請參閱[在期末結算總帳](close-general-ledger-at-period-end.md)和[結算會計年度](tasks/close-fiscal-year.md)。

> [!NOTE]
>  我們建議您使用 Management Reporter for Microsoft Dynamics 365 Finance，以合併格式結合多個法人實體的財務結果。 Management Reporter 讓您建立跨法人實體的合併財務報表、使用 Excel 從其他來源匯入合併數據，並將金額轉換為報表貨幣的任何數字，無需在 Dynamics 365 Finance 執行合併流程。

## <a name="map-subsidiary-main-accounts-to-consolidated-main-accounts"></a>將子公司主科目對應至合併的主科目

如果子公司法律實體中的會計科目表與合併後法律實體中的會計科目表不一致，您可以將子公司的主科目對應至合併後法律實體的主科目。

1. 在 *子公司法律實體* 中，移至 **總帳 \> 設定** \> **會計科目表 \> 會計科目表**。
2. 選取會計科目表。 在 **主科目** FastTab 上，選取一個主科目，然後選取 **編輯**。
3. 選取必須對應至合併後主科目的每個子公司主科目。 在 **一般** FastTab 上的 **合併科目** 欄位中，輸入所選子公司主科目的餘額或交易必須轉移至合併後法律實體中的科目。 您可以為數個子公司科目輸入相同的合併主科目。

    > [!NOTE]
    > 如果對應的子公司科目其主科目類型與合併法律實體中科目的主科目類型不同，則在合併期間會覆寫具有 **總計** 其主科目類型的科目值。

4. 為合併法律實體準備以財務維度為基礎的報告和財務報表。 按照以下步驟將子公司科目中使用的財務維度對應至合併法律實體中的財務維度: 

    1. 在 *子公司法律實體* 中，移至 **總帳 \> 設定 \> 財務維度 \> 財務維度**，選取一個財務維度，然後選取 **財務維度值**。
    2. 選擇財務維度值以對應到合併法律實體中不同的財務維度值。
    3. 在 **一般** FastTab 上的 **群組維度** 欄位中，在合併法律實體中輸入財務維度。 在合併期間，此財務維度將指派給在子公司法律實體中使用所選財務維度的交易和餘額。 您在此處輸入的財務維度必須用於合併法律實體中。 您可以將用作群組財務維度的財務維度指派給數個子公司財務維度。

5. 如果您正在進行線上合併，請按照以下步驟確保轉移依您的意願進行: 

    1. 在 *合併法律實體* 中，移至 **總帳 \> 定期 \> 合併 \> 合併 \[匯出至\]**，以開啟 **合併 \[線上\]** 頁面。
    2. 在 **準則** 索引標籤上，選取 **使用合併科目** 核取方塊。
    3. 在 **財務維度** 索引標籤上卡，選取適當的財務維度。
    4. 對於您選取的每個財務維度，在 **區段順序** 欄位中輸入數字，以指出維度應出現的順序。

## <a name="maintain-the-same-chart-of-accounts-in-the-subsidiary-and-consolidated-legal-entities"></a>在子公司和合併法律實體中保持相同的會計科目表

子公司法律實體中的主科目可能具有與合併法律實體中的主帳戶相同的科目編號和相同的會計科目表結構。 在這種情況下，您不必手動將子公司中的主科目對應至合併法律實體中的主科目。

在開始合併之前，請執行以下步驟。

1. 在 *合併法律實體* 中，移至 **總帳 \> 定期 \> 合併 \> 合併 \[匯出至\]**，以開啟 **合併 \[線上\]** 頁面。
2. 選取 **使用合併科目** 核取方塊。 合併期間，交易和餘額將自動轉移到正確的科目。

> [!NOTE]
> 如果科目未對應，合併將停止，您會收到一則訊息。

## <a name="create-a-chart-of-accounts-for-the-consolidated-legal-entity-based-on-an-existing-chart-of-accounts"></a>根據現有的會計科目表為合併法律實體建立會計科目表

即使尚未在合併法律實體中建立會計科目表，您也可以進行合併。

- 如果您已規劃要在合併法律實體中使用的科目結構，則可以將子公司科目對應到此結構。
- 如果您未對應任何子公司科目，則當子公司資料轉移至合併法律實體時，會自動建立合併法律實體中的科目。 這些科目以主科目為基礎。 後續資料會累積在合併法律實體的科目中，這些科目的科目編號與子公司科目相同。

無論您是否已對應科目，請先清除合併法律實體中 **合併** 頁面上的 **使用合併科目** 核取方塊，再執行此類型的合併。

> [!NOTE]
> 您可以使用此方法從其中一個子公司法律實體的會計科目表，在合併法律實體中立會計科目表。 (如需詳細資訊，請參閱[合併科目群組和額外合併科目](../budgeting/consolidation-account-groups-consolidation-accounts.md)。) 然後將適當的合併轉換原則指派給每個合併主科目，再為所有的子公司法律實體執行合併。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]