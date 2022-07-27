---
title: 公司間計劃
description: 本主題說明公司間計劃，並說明如何使用 Microsoft Dynamics 365 Supply Chain Management 中的 Planning Optimization 設定公司間計劃。
author: ChristianRytt
ms.date: 12/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-12-02
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 2bf69a5d0d6e070374277e2d82d5fbf6eb4b8704895ffe31aa7e2d2d3546bb16
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447291"
---
# <a name="intercompany-planning"></a>公司間計劃

[!include [banner](../../includes/banner.md)]

對於部分組織，物流作業依賴於組織中的其他法律實體 (公司)。 這些操作需要透過公司間的銷售和訂購進行處理，因為每個法律實體，都有其獨立的會計科目表。

本主題說明公司間計劃，並說明如何使用 Microsoft Dynamics 365 Supply Chain Management 中的 Planning Optimization 設定公司間計劃。

本主題使用下列重要的公司間條款：

- **上游** – 對於公司或供應鏈來說，一個相對的參考。 表示向原材料供應商的方向移動。
- **下游** – 對於公司或供應鏈來說，一個相對的參考。 表示向客戶的方向移動。
- **公司間需求計劃** – 根據下游公司對產品的需求計劃，制訂公司的產品需求計劃。

在主計劃中，一間公司的計劃，可以包括公司間的需求計劃，該需求計劃與另一間公司的訂單計劃相關。 此功能非常實用，因為能夠看見跨公司間完整的訂單計劃。 還可以確保，所需的計劃都是根據滿足訂單而建立，不是因為公司間需求而計劃訂單。

如果，您是從包含下游需求的已制訂計劃執行主計劃，則相關的公司間廠商資訊計劃訂購單，會自動包括在所需的計劃當中。

## <a name="required-setup"></a>所需的設定

若要使用公司間計劃，您必須按下列方式準備好系統：

1. 相關的產品，必須發佈至所有相關的公司。 如需詳細資訊，請參閱[Microsoft Learn 上 Dynamics 365 Supply Chain Management中設定和使用公司間交易](/learn/modules/configure-use-intercompany-trade-dyn365-supply-chain-mgmt/)。
1. 下游需求必須透過與上游公司間建立關係的廠商，以及客戶相關的預設詳細目錄維度 (網站和倉庫) 才能滿足。 如需詳細資訊，請參閱[Microsoft Learn 上 Dynamics 365 Supply Chain Management中設定和使用公司間交易](/learn/modules/configure-use-intercompany-trade-dyn365-supply-chain-mgmt/)。
1. 主計劃中的上游公司，必須包括下游的需求計劃，並且下游計劃中，必須指定相關的公司和主計劃。

## <a name="include-planned-downstream-demand"></a>包括已計劃的下游需求

按照下列步驟，設定主計劃，以包括已計劃的下游需求。

1. 前往 **主計劃 \> 設定 \> 計劃 \> 主計劃**。
1. 選擇或建立主計劃。
1. 在 **公司間計劃** FastTab 上，設定以下欄位：

    - **包括下游的已計劃需求** – 將此選項設定為 *是*，以啟用主計劃的公司間計劃。
    - **下游計劃** – 如果您將 **包括下游的已計劃需求** 選項設定為 *是*，則可以使用工具列和格線，將其他公司的主計劃新增至所需的主計劃。

## <a name="peg-across-companies-by-using-multilevel-pegging"></a>使用多層次需求追蹤，以追蹤跨公司間的需求

在多層次需求追蹤中，您可以檢視跨公司間的需求追蹤，以查看供應商所涵蓋的初始需求來源。

若要檢視多層次需求追蹤資訊，請按照下列步驟進行。

1. 移至 **主要計劃 \> 主計劃 \> 計劃訂單**。
1. 選擇或打開計劃訂單。
1. 在動作窗格的 **檢視** 索引標籤上，在 **需求** 群組中選取 **多層次需求追蹤**。

### <a name="intercompany-example-that-involves-two-companies"></a>公司間範例，涉及兩間公司

在此範例中，USMF 公司生產訂單的計劃，涵蓋 DEMF 公司的銷售訂單。 USMF 公司中，直接需求是公司間需求的計劃。 若要將此需求顯示於 USMF 中，主計劃需要先執行 DEMF，然後在執行 USMF。

下列圖示，說明在此範例中，可能出現在 **多層次需求追蹤** 頁面上的已計劃生產訂單。

![公司間範例，涉及兩間公司。](media/IntercompanyPlanning1.png)

### <a name="intercompany-example-that-involves-three-companies"></a>公司間範例，涉及三間公司

在此範例中，USMF 公司的計劃訂購單，涵蓋 FRRT 公司的銷售訂單。 DEMF 和 USMF 公司中，直接需求是公司間需求的計劃。 若要將此需求顯示於 USMF 中，主計劃需要先執行 FRRT，然後在執行 DEMF，最後再執行 USMF。

下列圖示，說明在此範例中，可能出現在 **多層次需求追蹤** 頁面上的已計劃生產訂單。

![公司間範例，涉及三間公司。](media/IntercompanyPlanning2.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]