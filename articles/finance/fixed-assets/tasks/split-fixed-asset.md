---
title: 分割固定資產
description: 本主題說明如何將一個資產帳冊按百分比分割至新的資產帳冊。
author: moaamer
ms.date: 08/06/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: AssetTable, AssetBook, AssetSplit, AssetBookLookup, LedgerJournalTable, LedgerJournalTransAsset
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a2fbca50342196dd9f5acb53027fb9c0052a81de
ms.sourcegitcommit: 62ca651c94e61aaa69cfa59e861f263f89d01c4a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/03/2021
ms.locfileid: "8451245"
---
# <a name="split-a-fixed-asset"></a>分割固定資產

[!include [banner](../../includes/banner.md)]

本主題說明如何將一個資產帳冊按百分比分割至新的資產帳冊。 

## <a name="create-a-new-fixed-asset"></a>建立新的固定資產

1. 在瀏覽窗格中，前往 **模組 \> 固定資產 \> 固定資產 \> 固定資產**。
2. 選取 **新增**。
3. 在 **固定資產群組** 欄位中，輸入或選取一個值。 記下固定資產編號以於日後用於分割流程中。
4. 在 **名稱** 欄位中，輸入一個值。
5. 關閉表單。

## <a name="split-a-fixed-asset"></a>分割固定資產

在完全折舊的資產被分割之前，應手動將資產帳冊狀態從 **已結** 變更為 **未結**。 如果您必須過帳資產的交易 (例如，處置出售)，則此步驟是必要的，因為帳冊狀態必須為 **未結**。 您也必須在 **總分類帳參數** 頁面的 **一般** 索引標籤上開啟 **允許一張憑單有多筆交易** 參數。 資產帳冊狀態變更且已允許一張憑單內有多筆交易後，請完成以下步驟分割資產。

1. 在清單中，尋找並選取要分割的固定資產連結。
2. 選擇 **帳簿**。 選擇要分割給新資產的帳冊。
3. 選取 **功能**。
4. 選取 **分割固定資產**。
5. 在 **至固定資產** 欄位中，輸入或選取一個值。
6. 在 **至帳冊** 欄位中，選取下拉式按鈕以開啟查閱功能。
7. 在 **交易日期** 欄位，輸入日期。
8. 在 **百分比** 欄位中，輸入一個數字。
9. 在 **日記帳名稱** 欄位，輸入或選取一個值。
10. 選取 **確定**。

## <a name="post-the-journal-transaction"></a>過帳日記帳交易

1. 在瀏覽窗格中，前往 **模組 \> 固定資產 \> 日記帳分錄 \> 固定資產日記帳**。
2. 在清單中，選取使用分割流程建立的日記帳。
3. 選取 **明細**。

    - 驗證建立的日記帳明細行。
    - 系統會為原始資產建立收購調整交易，以按照分割流程期間指定的百分比來減少值。
    - 系統會為新資產建立金額相同的收購交易。

4. 選取 **過帳**。


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
