---
title: 處理配比
description: 本主題提供有關配比的資訊、在 Microsoft Dynamics 365 Finance 中處理它們的選項，以及在預算規劃的用法。 配比用來橫跨多個分類帳科目組合配比金額。 它們有助於確保將費用或營收計入正確的會計對象。
author: kweekley
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AccountingDistribution, LedgerAllocationRule, MainAccount
audience: Application User
ms.reviewer: roschlom
ms.custom: 17361
ms.assetid: 04c8548a-0af9-492b-954b-946b4f8ca023
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0b79282abd0edf86f1a9f39fd869cf1fab28b9a4
ms.sourcegitcommit: 4f8465729d7ae0bf5150a2785a6140c984c7030e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2021
ms.locfileid: "8451134"
---
# <a name="process-allocations"></a>處理配比

[!include [banner](../includes/banner.md)]

本主題提供有關配比的資訊、處理選項以及在預算規劃的用法。 配比用來橫跨多個分類帳科目組合配比金額。 它們有助於確保將費用或營收計入正確的會計對象。

下列功能支持這段流程：

-   使用會計配比的拆分動作，或套用財務維度預設範本到文件的方式，手動配比交易金額。 更多資訊，請參閱[會計分配](../accounts-payable/accounting-distributions.md)。
-   根據個人主科目定義的配比條款自動配比交易金額。 只要會計分錄符合來源分類帳科目定義的標準，就會根據佔比和目的地分類帳科目為每份日記帳產生配比科目分錄。 更多資訊，請參閱[主科目配比條款](../general-ledger/main-account-allocation-terms.md)
-   自動根據分類帳配比規則自動配比分類帳餘額或固定金額。 分類帳分配規則是依照定期使用的配比日記帳基礎處理。 更多資訊，請參閱[配比規則](../general-ledger/ledger-allocation-rules.md)。

###  <a name="allocations-in-budget-planning"></a>預算計劃中的配比

分類帳配比規則可用於預算計劃。 在預算計劃中使用分類帳配比規則時，配比規則的運作方式與分類帳的相同，但來源資料和目的地資料則來自預算計劃。 您可以手動選取分類帳配比規則用於預算計劃。 或者，您可以使用以工作流程一部分環節執行的配比期程表。

> [!NOTE]
> 您不能將公司間分類帳的配比規則用於預算計劃。



[!INCLUDE[footer-include](../../includes/footer-banner.md)]
