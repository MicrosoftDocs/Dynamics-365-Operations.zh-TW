---
title: 如何設定平衡財務維度？
description: 本主題介紹設定和使用平衡財務維度功能的選項。
author: kweekley
ms.date: 08/25/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DimensionDetails
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2021-08-17
ms.dyn365.ops.version: 10.0.210
ms.openlocfilehash: 188c15c4cb0c295a9fcbb08273ddb391fbc29e24
ms.sourcegitcommit: b4c78655f2ab4b0e7ead96dfb9cf087a18014253
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/02/2021
ms.locfileid: "8450963"
---
# <a name="how-do-i-set-up-balancing-financial-dimensions"></a>如何設定平衡財務維度？

[!include [banner](../includes/banner.md)]

本主題介紹設定和使用平衡財務維度功能的選項。

## <a name="symptom"></a>問題

設定平衡財務維度有兩個選項。 第一個選項是使用 **分類帳** 頁面 (**總帳 \> 分類帳設定 \> 分類帳**) 中的 **平衡財務維度** 欄位。 第二個選項是使用 **財務維度** 頁面 (**總帳 > 會計科目表 \> 維度 \> 財務維度**) 中的 **要求維度平衡** 欄位。 本主題說明這兩個選項之間的區別。

## <a name="resolution"></a>解決方法

組織通常使用平衡維度來產生在財務維度等級處於平衡狀態的資產負債表。 啟用這些功能不會將已過帳的未平衡維度導入餘額中。 在啟用任一功能之前，必須先手動輸入調整分錄，以使資產負債表導入餘額中。

這兩個選項無法一起使用。 應該根據業務要求，選擇組織使用的選項。 我們經常聽到客戶同時在分類帳設定和財務維度設定中定義平衡維度，然後完成所需部分或全部額外設定。 但是因為財務維度等級不平衡，他們仍然無法過帳。

以下部分介紹這兩個選項並說明如何設定它們。

### <a name="ledger--balancing-financial-dimension"></a>分類帳 – 平衡財務維度

**分類帳** 設定頁面中的平衡維度用於啟用單位間會計。 若要開啟該功能，則按照以下步驟執行。

1. 確定哪個財務維度將作為平衡維度。

    - 此功能允許您僅選擇一個財務維度作為平衡維度。
    - 尚未在 **分類帳** 設定頁面中選擇維度。
    - 確保所選財務維度的資產負債表已平衡。

2. 更新平衡財務維度的科目結構。

    - 指派給分類帳的所有科目結構中都必須包含此平衡財務維度。
    - 財務維度在科目結構中不得有空白。 此項限制可以確保過帳到總帳的每個會計分錄中都包含財務維度值。 如果使用平衡維度，則空白維度無效。

3. 在 **自動交易科目** 頁面 (**總帳 \> 過帳設定 \> 自動交易科目**)，定義單位間借方和貸方主科目。
4. 在 **分類帳** 設定頁面 (**總帳 \> 分類帳設置 \> 分類帳**) 的 **平衡財務維度** 欄位中，選擇用於平衡的財務維度。

如果因為輸入和過帳交易，導致所選財務維度不平衡，系統將自動加入在過帳期間用於平衡會計分錄的借方或貸方分錄。 總帳的已過帳憑單中會顯示單位間交易的借方和貸方分類帳科目。 但是，它們不會顯示在過帳會計分錄的日記帳或原始單據中。

### <a name="financial-dimensions--require-the-dimension-to-be-balanced"></a>財務維度 – 需要維度平衡

雖然 **財務維度** 頁面中的平衡維度通常由公共部門公司使用，此功能卻不連接到任何公共部門組態金鑰。 由於系統中無限制，因此即使您的組織不是公共部門實體，也可以使用此功能。

此功能通常使用在公共部門客戶群組中，因為它要求使用過帳定義自動平衡每個交易。 其不使用在 **自動交易科目** 頁面中定義的單位間借方和貸方科目自動平衡會計分錄。 如果套用過帳定義之後，某個會計分錄在維度等級不平衡，將不過帳交易，即使已定義單位間借方和貸方科目。

我們經常聽到客戶同時在日記帳設定和財務維度設定中定義平衡維度。 在這種情況下，系統將使用財務維度功能。 過帳期間，優先設定財務維度等級的平衡維度。 如果過帳定義不建立財務維度等級的平衡會計條目，過帳將失敗。

若要開啟財務維度等級的平衡維度使用，請執行以下步驟。

1. 確定哪個財務維度將作為平衡維度。

    - 可以將多個財務維度設定為平衡維度。
    - 尚未在 **財務維度** 頁面中設定平衡交易所需財務維度。

2. 定義組織所用各種日記帳或原始單據的過帳定義。 過帳定義使用未過帳日記帳或原始單據中的會計科目作為「比對條件」。 然後，過帳定義傳回成為會計分錄的「已產生分錄」。 如果已正確設定過帳定義，則已產生分錄中將包含比對條件分類帳科目，以及用於在維度等級平衡會計分錄的其他科目。 如需詳細資料，請參閱[過帳定義](posting-definitions.md)。 
   
   並非每種交易類型都支援過帳定義。 例如，不能為透過總帳或固定資產日記帳輸入的任何交易定義過帳定義。 如果不能為日記帳或原始單據定義過帳定義，則必須在財務維度值處手動平衡交易。 例如，如果已建立總帳分錄，並且「部門」維度為平衡維度，則必須確保每個部門值都平衡。  如果每個部門值的維度不平衡，則在透過在憑單手動加入單位間借方或貸方更正不平衡之前，不會過帳憑單。 

    > [!IMPORTANT]
    > 如果必須手動平衡過多的交易，則 **不** 應在 **財務維度** 頁面中使用平衡維度功能。 請改為在 **分類帳** 設定頁面中使用平衡維度功能。

3. 定義過帳定義之後，可以將財務維度標記為平衡必需。

在輸入和過帳交易時，過帳期間將呼叫過帳定義以確定會計分錄。 如果財務維度已平衡，則會在已確定會計分錄之後進行驗證。 如果財務維度不平衡，則不會過帳交易，並且您將收到一條訊息，說明特定維度的借項與貸項不相等。
