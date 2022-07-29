---
title: 按分類帳交易報告的銷售稅明細報表
description: 此主題說明如何使用「按分類帳交易報告的銷售稅明細」報表查看和列印有關為其計算銷售稅的分類帳交易資料。
author: ericwang
ms.date: 08/19/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2019-08-19
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: f835f06c190f1d174fbde6b68f189b0484a7b39610bc2edc0676a3e2fa320268
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450198"
---
# <a name="sales-tax-specification-by-ledger-transaction-report"></a>按分類帳交易報告的銷售稅明細報表
[!include [banner](../includes/banner.md)]

此主題說明如何使用 **按分類帳交易報告的銷售稅明細** 報表查看和列印有關為其計算銷售稅的分類帳交易資料。

## <a name="tax-accounts-vs-non-tax-accounts"></a>納稅科目與非納稅科目

**按分類帳交易報告的銷售稅明細** 報表顯示納稅科目與非納稅科目的稅務交易。 這些科目按以下方法分類：

- **納稅科目**：在過帳稅務交易時，科目被視為納稅科目，並且 **銷售稅** 日記帳明細中的主科目也是納稅科目，例如：應納銷售稅科目或應收銷售稅科目。
- **非納稅科目**：在過帳稅務交易時，科目被視為納稅科目，並且原始交易中的主科目也是非納稅科目，例如：收入科目或費用科目。

對於納稅科目，報表中的 **原始金額**、**應收銷售稅** 和 **應納銷售稅** 列顯示 **0** (零)。 對於非納稅科目，這些列顯示金額。

## <a name="filtering-the-data-on-the-report"></a>篩選報表中的資料

產生此報告時，以下預設欄位可用。 可使用這些欄位篩選此報表中顯示的資料。

| 欄位                      | 描述 |
|----------------------------|-------------|
| 日期                       | 使用 **開始** 和 **結束** 區段中的欄位為稅務交易定義日期範圍。 |
| 主科目               | 使用 **開始** 和 **結束** 區段中的欄位定義主科目範圍。 |
| 銷售稅代碼             | 使用 **開始** 和 **結束** 區段中的欄位定義銷售稅代碼範圍。 |
| 分組                   | 選擇是否應該按會計科目還是銷售稅代碼分組報表。 |
| 按銷售稅代碼小計 | 如果將此選項設定為 **是**，則按銷售稅代碼顯示小計。 |
| 僅總計                | 如果將此選項設定為 **是**，則僅顯示總計。 |
| 僅主科目         | 如果將此選項設置為 **是**，則報表中僅包含主科目。 |

## <a name="showing-only-non-tax-accounts-on-the-report"></a>報表中僅顯示非納稅科目

若僅要在報表中顯示非納稅科目，則設定篩選條件，如星號(\*)，如下圖所示。

![顯示非納稅科目的報表。](media/taxspecperledgertrans.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]