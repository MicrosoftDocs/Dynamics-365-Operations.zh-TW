---
title: 零售商店交易的少量多次訂單建立
description: 本文章描述 Microsoft Dynamics 365 Commerce 中適用於商店交易的少量多次訂單建立。
author: analpert
ms.date: 01/11/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: ''
ms.openlocfilehash: 0f0ee361df8c565761e79f5b0ecf519c149f2ec0
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/03/2022
ms.locfileid: "8873242"
---
# <a name="trickle-feed-based-order-creation-for-retail-store-transactions"></a>零售商店交易的少量多次訂單建立

[!include [banner](includes/banner.md)]

在 Microsoft Dynamics 365 Commerce 10.0.5 版及更新版本中，我們建議您將所有對帳單過帳過程轉換為涓流饋給式的對帳單過帳過程。 使用涓流饋給功能可帶來顯著的績效與業務優勢。 銷售交易會全天處理。 投標和現金管理交易在一天結束時於財務報表中處理。 涓流饋給功能可實現連續處理銷售訂單、發票和付款。 因此，庫存、營收和付款都會以近乎即時的時間更新及確認。

## <a name="use-trickle-feed-based-posting"></a>使用涓流饋給式過帳

> [!IMPORTANT]
> 啟用涓流饋給式過帳前，您必須確保沒有任何經過計算及未過帳的對帳單。 請在啟用功能前將所有對帳單過帳。 您可以在 **商店財務** 工作區中查看開啟的對帳單。

若要啟用零售交易的涓流饋給式過帳，請在 **功能管理** 工作區中啟用 **零售對帳單 - 涓流饋給** 功能。 對帳單將分為兩種類型：交易對帳單與財務報表。

### <a name="transactional-statements"></a>交易對帳單

交易對帳單處理的目標是整天以高頻率執行，以便交易上傳至 Commerce Headquarters 時會建立好文件。 當您執行 **P-Job** 時，交易會從商店載入 Commerce Headquarters。 您也必須執行 **驗證商店交易** 工作來驗證交易，以便交易對帳單加以接收。

排程以下工作以高頻率執行：

- 若要計算交易對帳單，請執行 **以批次計算交易對帳單** 工作 (**Retail 和 Commerce \> Retail 和 Commerce IT \> POS 過帳 \> 以批次計算交易對帳單**)。 這項工作會接收所有未過帳與經驗證的交易，並將它們新增至新的交易對帳單。
- 若要以批次將交易對帳單過帳，請執行 **以批次將交易對帳單過帳** 工作 (**Retail 和 Commerce \> Retail 和 Commerce IT \> POS 過帳 \> 以批次將交易對帳單過帳**)。 這項工作會執行過帳程序並建立銷售訂單、銷售發票、付款日記帳、折扣日記帳，以及不包含任何錯誤之未過帳對帳單的收支交易。 

### <a name="financial-statements"></a>財務報表

財務報表處理目標是做為一天的結束程序。 這種類型的對帳單處理只支援 **轉移** 關帳方法，且只會接收已關閉的轉移。 對帳單受限於財務對帳。 它們將只會針對投標之計算金額與交易金額之間的差異金額建立日記帳，以及對其他現金管理交易建立日記帳。

財務報表還可以實現以下交易的審核：投標申報交易、付款交易、銀行投標交易以及安全投標交易。 只有在選取財務報表時，投標詳細資料頁面才會顯示。

![只有當您選取財務報表時，才會出現顯示已過帳對帳單表單之投標詳細資料區段的影像。](./media/Trickle-feed-posted-statements-transaction-view.png)

根據一天的預期結束時間，排程以下財務報表工作的開始與結束時間：

- 若要計算財務報表，請執行 **以批次計算財務報表** 工作 (**Retail 和 Commerce \> Retail 和 Commerce IT \> POS 過帳 \> 以批次計算財務報表**)。 這項工作會收集所有未過帳的財務交易，並將它們新增至新的財務報表。
- 若要以批次將財務報表過帳，請執行 **以批次將財務報表過帳** 工作 (**Retail 和 Commerce \> Retail 和 Commerce IT \> POS 過帳 \> 以批次將財務報表過帳**)。

### <a name="manually-create-statements"></a>手動建立對帳單

您也可以手動建立交易與財務報表類型。 

1. 移至 **Retail 和 Commerce \> 通路 \> 商店**，然後選取 **對帳單**。 
2. 選取 **新增**，然後選取要建立的對帳單類型。 **對帳單** 頁面上的欄位會顯示與所選對帳單類型相關的資料，而 **對帳單群組** 下的動作則會顯示相關動作。

[!INCLUDE[footer-include](../includes/footer-banner.md)]
