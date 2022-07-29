---
title: 應計項目概觀
description: 本文介紹應計項目，並提供有關如何設定和建立交易的資訊。
author: aprilolson
ms.date: 01/11/2018
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerAccuralTable
audience: Application User
ms.reviewer: roschlom
ms.custom:
- "14131"
- intro-internal
ms.assetid: 0489b59a-37a7-4a78-87bf-4b597e9efad9
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: dc3234c1a64155e1d0ad53cb7008d91847f7af7d
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/15/2022
ms.locfileid: "8451446"
---
# <a name="accruals-overview"></a>應計項目概觀

[!include [banner](../includes/banner.md)]

本文介紹應計項目，並提供有關如何設定和建立交易的資訊。

應計項目用於在應計制會計中追蹤在賺取收入期間而不是在收到付款時認列的收入，並追蹤在發生時而不是在付款時認列的費用 (成本)。

## <a name="accrual-schemes"></a>應計項目架構
應計項目架構用於設定遞延收入和成本，相同的應計項目結構可用於收入和成本。 分類帳應計項目重新分配日記帳行的成本或收入，以便在適當的期間認列成本和收入。 在 **應計項目結構** 頁面中，指定在套用應計項目結構時將使用的借方和貸方科目。

-   **借方** – 您定義的主科目將替換日記帳憑證行上的借方主科目。 該帳戶還將用於根據分類帳應計項目交易撤銷延期。
-   **貸方** – 您定義的主科目將替換日記帳憑證行上的貸方主科目。 該帳戶還將用於根據分類帳應計項目交易撤銷延期。

在確定要使用的科目後，您可以指定在建立應計項目交易時如何建立憑證編號。 您還可以指定交易發生的頻率、建立交易的次數以及過帳交易的時間。 建立應計項目結構後，您可以透過分類帳應計項目功能在某些日記帳中使用它。

## <a name="ledger-accruals"></a>分類帳應計項目
輸入日記帳時，您可以點擊 **功能** 功能表的 **分類帳應計項目**。 然後，當您選擇應計項目結構時，將看到由應計項目結構確定的分攤在該期間的日記帳的基本金額。 例如，如果您在一月份為員工支付了全年的保險，金額為 12,000，則您必須每月認列該費用。 您可以選取開始日期。 您還可以指定應計金額是根據此科目或沖銷科目。 做出選擇後，點擊 **交易** 查看根據應計項目結構建立的所有交易。 例如，如果您將 12,000 的保險費用分攤到一年中，則每個月將看到 1,000。 過帳日記帳後，您可以使用 **憑證交易** 查詢頁面查看交易。 如果無法套用應計項目結構 (例如，當涉及銷售訂單發票或訂購單發票時)，您可以貸記預付金額並借記費用金額。 然後您可以在套用應計項目結構時選擇 **沖銷**。


有關詳細資訊，請參閱[建立應計項目結構](tasks/create-accrual-schemes.md)和[建立分類帳應計項目交易](tasks/create-ledger-accrual-transactions.md)。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]