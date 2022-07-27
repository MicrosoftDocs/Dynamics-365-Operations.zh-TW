---
title: 採購申請
description: 本主題介紹如何在規劃最佳化中支援採購申請。
author: ChristianRytt
ms.date: 01/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqPlanSched, ReqGroup
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2021-01-04
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 1d6fd4be0ee1913264c4a565234cfdf711365792
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448353"
---
# <a name="purchase-requisitions"></a>採購申請

[!include [banner](../../includes/banner.md)]

總規劃可以補充已批准的採購申請。 因此，為了處理採購申請，使用者不必使用工作流程來建立採購訂單。 相反，採購申請可以包含在總規劃中。 由於此功能，採購申請可以產生採購訂單、轉移訂單或生產訂單，具體取決於 **計劃訂單類型** 為相關產品設定的值。

## <a name="enable-master-plans-to-include-requisitions"></a>啟用總規劃以包括申請

要在總規劃的覆蓋率計算過程中包含申請，請執行以下步驟。

1. 前往 **總規劃**\> **設定**\>**規劃**\>**總規劃**。
1. 建立或選擇總規劃。
1. 在 **一般** FastTab 上，將 **包括申請** 選項設為 *是*。
1. 對要包含申請的每個其他總規劃重複步驟 2 和 3。

## <a name="approved-requisitions-time-fence"></a>核准的申請時界

*已核准的申請時間範圍* 會確定總規劃將在多長時間內 (以天計) 包括來自已批准補貨申請的需求。 您可以在覆蓋群組層級和總規劃層級設定已批准的申請時間範圍。

### <a name="set-the-approved-requisitions-time-fence-for-a-coverage-group"></a>為涵蓋範圍群組設定已核准申請時間範圍。

1. 前往 **總規劃** \>**設定** \> **涵蓋範圍**\> **涵蓋範圍群組**。
1. 建立或選取一個覆蓋群組。
1. 在 **其他** FastTab 上，將 **已核准的申請時間範圍 (天)** 欄位的天數設成包含在時間範圍中的天數。
1. 對要設定已核准申請時間範圍的每個其他覆蓋範圍群組重複步驟 2 和 3。

### <a name="set-the-approved-requisitions-time-fence-for-individual-master-plans"></a>為個別總規劃設定已核准申請時間範圍

當您為單個總規劃設定已批准的申請時間範圍時，該設定將覆寫任何適用覆蓋範圍群組的時間範圍設定。

1. 前往 **總規劃**\> **設定**\>**規劃**\>**總規劃**。
1. 建立或選擇總規劃。
1. 在 **時間範圍 (天)** FastTab 上，將 **已核准的申請時間範圍 (天)** 欄位的天數設成包含在時間範圍中的天數。
1. 對要設定已核准申請時間範圍的每個其他總規劃重複步驟 2 和 3。

> [!IMPORTANT]
> **即將推出：** 規劃最佳化尚未支援已核准的申請時間範圍。 在它們獲得支援之前，您在 **已核准的申請時間範圍 (天)** 欄位會遭到忽略。

## <a name="independent-supply-regardless-of-coverage-code"></a>獨立供應，不考慮覆蓋代碼

無論覆蓋代碼如何，採購申請始終由獨立的計劃訂單覆蓋。 這種行為確保了採購申請和補貨訂單之間的清晰可追溯性和工作流程。

### <a name="example-1"></a>範例 1

設定產品，使其具有值為 *最小/最大* 的 **覆蓋代碼**。它具有以下庫存和申請狀態：

- 庫存現有數量 = 10。
- 庫存下限數量 = 15。
- 庫存上限數量 = 20。
- 存在單件的採購申請。 其請求日期是今天。

總規劃執行時，會建立兩個計劃訂單：一個用於將庫存補充到最大數量的 10 件，另一個用於補充採購申請。

### <a name="example-2"></a>範例 2

設定產品，使其具有值為 *最小/最大* 的 **覆蓋代碼**。它具有以下庫存和申請狀態：

- 庫存現有數量 = 17。
- 庫存下限數量 = 15。
- 庫存上限數量 = 20。
- 存在單件的採購申請。 其請求日期是今天。

當總規劃執行時，會為一件建立一個計劃訂單來補充採購申請。

### <a name="example-3"></a>範例 3

設定產品，使其具有值為 *時期* **的覆蓋代碼** 以及為期 7 天的期限。 它具有以下庫存、銷售訂單和申請狀態：

- 庫存現有數量 = 0。
- 存在五件的銷售訂單。 其預計發貨日期為今天加上一天。
- 存在三件的採購申請。 其要求日期是今天加三天。

總規劃執行時，會建立兩個計劃訂單：一個用於將採購申請補充到三件，另一個用於將銷售訂單需求補充到五件。

> [!NOTE]
> 在確定與採購申請掛鉤的計劃訂單後，計劃引擎會保持與採購申請的掛鉤。 如果稍後發現確定的訂單缺少滿足採購申請所需的一些數量，系統將為差異建立一個新的計劃訂單。

若需更多採購申請的相關資訊，請參閱[採購申請概覽](../../procurement/purchase-requisitions-overview.md)。


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]