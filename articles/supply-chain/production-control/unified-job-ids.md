---
title: 作業識別碼的統一編號序列
description: 此功能提供了一個統一的編號規則，可為生產控制、製造執行以及出勤模組產生作業識別碼。
author: johanhoffmann
ms.date: 03/25/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2021-03-05
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 8ff8fae0bb20b11b15c7520fbb14727ff0372ca0255adc82599c6680a64671af
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446961"
---
# <a name="unified-number-sequence-for-job-ids"></a>作業識別碼的統一編號序列

[!include [banner](../includes/banner.md)]

此功能提供了一個統一的編號規則，可為生產控制、製造執行以及出勤模組產生作業識別碼。 先前，您可以為每個模組選擇不同的編號規則，如果其中兩個或更多規則使用相同的格式，這可能會導致作業識別碼發生衝突。 這種衝突會導致資料損壞。

## <a name="turn-on-this-feature-for-your-system"></a>為您的系統啟用此功能

如果您的系統尚未包含本主題中說明的功能，請移至 [功能管理](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)，然後開啟 *統一作業識別碼編號規則* 功能。

## <a name="set-up-the-unified-number-sequence-for-job-ids"></a>為作業識別碼設置統一編號規則

啟用此功能後，生產控制、製造執行和出勤模組的參數頁面上的現有 **工作識別** 編號規則設定將被取代，並新增 **統一作業識別碼** 欄位。 **統一作業識別碼** 值由全部三個模組共用，從而確保所有模組引用相同的編號規則。 因此，作業識別碼在全部三個模組中都是唯一的，並且永遠不會發生衝突。

若要設定統一作業識別碼編號規則：

1. 按照上一節中的說明打開該功能。
1. 確定要用於統一作業識別碼的編號規則，或者建立一個新編號規則。 如需相關資訊，請參閱[編號規則概觀](../../fin-ops-core/fin-ops/organization-administration/number-sequence-overview.md)。
1. 移至 **生產控制參數**、**製造執行參數** 或 **出勤參數** 頁面。 選擇哪個都可以，因為在其中任何頁面上進行此設定時，所有其他頁面都會自動更新。
1. 在所選參數頁面上打開 **編號規則** 索引標籤。
1. 將先前標示的 **編號規則代碼** 指派到格線的 **統一作業識別碼**。
