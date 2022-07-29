---
title: 子分類帳轉移至總分類帳
description: 本主題說明與總分類帳中子分類帳轉移流程相關的功能。
author: rcarlson
ms.date: 12/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalSetup, LedgerJournalTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2020-01-18
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: 213bbc2541c614aa26b0c830431818fb99c7682d
ms.sourcegitcommit: f5885999e008a49fe072d95f15e239905c24918a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/08/2021
ms.locfileid: "8451296"
---
# <a name="subledger-transfer-to-the-general-ledger"></a>子分類帳轉移至總分類帳

[!include [banner](../includes/banner.md)]

本主題說明與批次轉移子分類帳日記帳分錄相關的功能。

在 8.1 版中進行了一些變更，以允許使用轉移規則，這棄用了 **同步** 選項。 如需詳細資訊，請參閱[財務與營運的已移除或棄用功能](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md?toc=%2fdynamics365%2ffinance%2ftoc.json#finance-and-operations-81-with-platform-update-20)

以下選項可用於批次轉移子分類帳: 

- **異步** – 立即排程將子分類帳會計分錄轉移至總分類帳。 一旦有資源可用於處理伺服器上的要求，就會記錄總分類帳憑單。
- **排程批次** – 將必須轉移的子分類帳會計分錄新增至總分類帳中的處理佇列。 佇列中的分錄將按照收到的順序進行處理。 如果有資源可用於處理伺服器上的批次工作，則每個總分類帳憑單將在排程的時間更新帳戶。

在 10.0.8 版本中進行了一些改進，以增強 **異步** 選項的效能。 此功能在 **子分類帳轉移至總分類帳效能最佳化** 功能名稱下啟用。

子分類帳批次異步轉移功能有助於改進從子分類帳到總分類帳的資料轉移。 該功能透過將數組較小的交易加以分組，並將交易分組轉移，而能夠更有效地處理交易。 當交易被分組時，能夠更有效率地使用批次伺服器的資源。

若要異步轉移子分類帳批次，則批次伺服器必須設定完成、上線並運作，因為批次工作是為了能在批次伺服器上立即執行而建立的。 當 **子分類帳轉移至總分類帳效能最佳化** 功能啟用時，則必須也啟用名為 **流程自動化輪詢系統作業** 的 **流程自動化** 系統批次作業。 更多資訊，請參閱[流程自動化](../../fin-ops-core/dev-itpro/sysadmin/process-automation.md)。

批次層級的效率變更會為系統中所有的法律實體使用單一週期性批次作業。 在執行階段，將建立一個新的批次作業來處理尚未轉移的必要記錄。 從系統管理中的 **流程自動化** 頁面可控制更多設定。 在該頁面上，您可以修改背景流程、變更頻率，以及定義睡眠期間。

更多有關流程自動化設定的資訊，請參閱[流程自動化](../../fin-ops-core/dev-itpro/sysadmin/process-automation.md)。

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
