---
title: 計劃您的會計科目表
description: 本主題提供將幫助您為貴組織規劃會計科目表的資訊。
author: aprilolson
ms.date: 04/02/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DimensionConfigureAccountStructure, LedgerChartOfAccounts
audience: Application User
ms.reviewer: roschlom
ms.custom: 14051
ms.assetid: 10edb129-33f0-4cf9-b2a7-4b7ffa09b229
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0c4a5c0d758ecacce6433b13a2b2044d2417d018
ms.sourcegitcommit: 7aa7d756e1e98a53da62e03c608a9597ef9893ea
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/20/2021
ms.locfileid: "8450948"
---
# <a name="plan-your-chart-of-accounts"></a>計劃您的會計科目表

[!include [banner](../includes/banner.md)]

本主題提供將幫助您為貴組織規劃會計科目表的資訊。

若要追蹤和維護組織的財務資訊，您可以設定會計科目表。 會計科目表是定義財務框架的科目集合。 若要進一步追蹤這些科目的交易，您可以新增區隔。 這些區隔稱為財務維度。 例如，開銷科目可能包括名為部門、成本中心和用途的財務維度。 使用者定義的規則負責判定財務維度附接到主科目和其他財務維度及交易輸入的方式。 這些使用者定義規則即為所知的科目結構和進階規則。

會計科目表是法人實體總帳科目的結構化清單。 此清單用來為機關和負責人準備財務報表。 科目會先分成幾組科目類型，接著進一步彙總為更大類別。 從最籠統的等級來看，帳戶分成營收組和成本組 (營運帳戶) 及資產和負債 (餘額帳戶)。

會計科目表可由組織中的任何法人實體共用和使用。 法人實體使用的會計科目表在 **帳本** 頁定義。

以下是您在為貴組織規劃會計科目表結構時必須考慮的一些因素：

- 貴組織所在國家或地區的報表編製要求
- 您的法人實體的報表編製要求
- 外部組織和貴組織所需的規範程度

您在 **會計科目表** 頁面上建立會計科目表。 您可以從 **會計科目表** 頁或 **主科目** 頁建立主科。 您的主科目不應使用任何當成會計科目表分隔符號的特殊字元。 否則您可能會經歷不穩定，或者您在輸入帳戶和維度組合時可能一直必須使用查閱功能或對話方塊。 更多資訊，請參閱[建立主科目](tasks/create-main-account.md)。

> [!NOTE]
> 在 Dynamics 365 for Finance and Operations 8.0 版 (2018 年四月)，您可以從 **總帳參數** 頁修改會計科目表分隔符號。

連結主科目到主科目類別是很好的構想，如此您便能充分運用預設財務報告，不必進行任何修改。 因此，您可以更快速、更輕鬆地設計和維護報表。

您在 **配置帳戶結構** 頁面建立帳戶結構。 帳戶結構定義有效的組合。 這些組合連同主科目一起形成會計科目表。 更多資訊，請參閱[建立科目結構](tasks/create-account-structures.md)。

**法人實體覆寫**

並非所有主科目對所有法人實體都有效，某些主科目可能只與特定期間相關。 這種情況下，您可以使用 **法人實體覆寫** 專區辨別主科目應暫停的公司、負責人及維度有效的期間。 共用等級覆寫的限制程度比法人實體等級覆寫的程度低。

有關詳細資訊，請參閱下列主題：

- [財務維度](financial-dimensions.md)
- [建立和指派進階規則結構](tasks/create-assign-advanced-rule-structures.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
