---
title: 管理生產中的分包工作
description: 本主題說明如何在 Dynamics 365 Supply Chain Management 中管理分包作業。 換句話說，它說明廠商如何管理分配給資源的生產作業。
author: johanhoffmann
ms.date: 11/03/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeanDocumentServiceCreation, PlanActivity, ProdBOMVendorListPage, ProdRoute, ProdTable, ProdTableListPage, PurchAgreementSubcontractorLookup, RouteTable, WrkCtrResourceGroup, ProdBOMVendorListPagePreviewPane, ProdBOMVendor
audience: Application User
ms.reviewer: kamaybac
ms.custom: 268174
ms.assetid: fe47c498-4f48-42a2-a0cf-5436c19ab3ea
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7e80efc751ccf9243163d23ed48fd17923326f89
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449211"
---
# <a name="manage-subcontracting-work-in-production"></a>管理生產中的分包工作

[!include [banner](../includes/banner.md)]

本主題說明如何在 Dynamics 365 Supply Chain Management 中管理分包作業。 換句話說，它說明廠商如何管理分配給資源的生產作業。

在[生產流程](production-process-overview.md)中，作業可以由廠商擁有或管理的資源完成。 一般而言，廠商資源會用於平衡超過公司自身資源可用容量的周期性過剩需求。 廠商也可以低價提供特定的[資源能力](resource-capabilities.md)或資源。  

根據生產流程中使用的廠商資源，一個[路線](routes-operations.md)通常會有額外的物流要求，因為材料和半成品必須首先運輸到廠商的站點。 然後，分包作業的結果必須傳輸到分配給下一個作業的位置或成品倉庫。  

在使用分包作業或活動時，它們會影響從生產、成本計算、預測、計劃和排程所需的作業定義，到材料、半成品和完成品物流管理的所有作業階段。 最後，這些資源會需要自己的會計和成本控制流程。  

對於內部資源，通常會為一段時間分配固定成本率。 相比之下，分包資源的成本根據是依相關服務的購買價格。 該服務被定義為另一種產品，用於驅動給定分包作業的採購和購買流程。  

目前，Supply Chain Management 中還沒有明確的半成品概念。 對於需要多個作業才能將原物料轉換為成品的生產訂單，成品僅在最後一道作業中過帳回庫存。 早期作業生產的半成品會計入在製品 (WIP)，但不會在庫存中進行過帳或追蹤。 儘管您可以將途程和物料清單 (BOM) 分割為多個較小的單元，但這種方法會增加必須管理的產品、BOM 和途程的數量。  

有兩種方法可以對生產作業的分包工作建模。 這些方法的不同之處在於分包流程的建模方式、半成品在流程中的表示方式，以及成本控制的管理方式。

-   生產訂單或批次訂單中的途程作業分包
    -   服務產品必須是庫存產品，並且必須是 BOM 的一部分。
    -   此方法支持先進先出 (FIFO) 或標準成本。
    -   半成品以流程中的服務產品為代表。
    -   成本控制會把與分包作業相關的成本分配給材料成本。
-   精實生產流程中的生產流程活動分包
    -   該服務是一種非庫存服務產品，而且不是 BOM 的一部分。
    -   此方法使用採購合約作為服務合約。
    -   此方法使用倒推成本法。
    -   此方法允許彙總和非同步採購。 (物料流程獨立於採購流程。)
    -   成本控制會在其自己的成本分解區塊中分配分包工作。

## <a name="subcontracting-of-route-operations"></a>途程作業分包
若要將途程作業分包用於生產或批次訂單，則用於服務採購的服務產品必須定義為 **服務** 類型產品。 此外，它必須具有將 **庫存原則** 下的 **庫存產品** 選項設為 **是** 的品項模型群組。 此選項定義了產品是否在產品收貨時被記為庫存 (**庫存產品** = **是**)，或者該產品是否計入損益賬戶 (**庫存產品** = **否**)。 儘管這種行為可能看起來自相矛盾，但它是根據此一事實，即只有具此原則的產品才會建立可用於成本控制的庫存交易記錄，以計算計劃成本並在生產訂單結束時決定實際成本。  

如要在計劃和成本計算中進行考量，則必須將服務新增到 BOM。 BOM 明細必須是 **廠商** 類型，並且必須分配給分配服務的途程作業。 此途程作業必須具有指向 **廠商** 類型資源的成本計算資源和資源需求，該廠商類型會將作業和相關服務連接到對應的廠商帳戶。  

使用此設定時，訂購單會根據生產訂單的估計為相關服務產品而建立。 服務的訂購單會用作分包作業的錨點。 分包工作可以透過生產控制中的 **分包工作** 清單頁面進行管理。 分包工作會用於向廠商運送原物料，最終將半成品運送給廠商，以為作業做準備。 它也用於在品項到達時接收分包作業的結果產品，其中服務產品會用於識別半成品的抵達。 收到訂購單明細後，生產作業將更新為已完成。  

一個生產訂單可以有很多作業，每個作業可以分配給不同的廠商。 因此，一個端到端的生產訂單可能會觸發多個訂購單。

## <a name="subcontracting-of-production-flow-activities"></a>生產流程活動分包
[精益製造](lean-manufacturing-overview.md)解決方案會將分包工作建模為與[生產流程](tasks/create-production-flow-version.md)活動相關的服務 (工作指南主題)。 因此，這種類型的分包也被稱為[活動型分包](activity-based-subcontracting.md)。 一種特別的成本群組類型 (**直接外包**) 已經引入，並且分包服務不是成品 BOM 的一部分。 在您使用精益製造時，所有活動都由可以與一或多項生產流程活動相關的看板定義。 到目前為止，這種說明聽起來就像是對生產訂單的說明。 但是，雖然生產訂單必須一律以成品結束，但您可以建立看板來供應半成品。 您不必導入新產品和 BOM 等級。  

因為看板規則可以是非常動態的，所以您可以對生產流程中相同產品的不同供應變體進行建模。 在您使用精益分包時，物料流程和財務流程是嚴格分開的。 所有的物料流程都由看板活動來表示。 根據生產流程中看板工作的狀態，服務產品的訂購單和這些服務的收貨過帳都可以自動化。 看板工作甚至可以在訂購單建立之前開始並完成。 分包文件 (訂購單和服務採購收據) 可以按期間和服務進行彙總。 因此，即使在廠商以單件流程提供分包服務的高度重複性作業中，採購文件和明細數量也可以保持較小。

### <a name="modeling-subcontracting-in-a-production-flow"></a>在生產流程中建模分包

在[精益生產流程](lean-manufacturing-modeling-lean-organization.md)中，當流程活動被分配到具有單一廠商資源的工作單元 (資源群組) 時，流程活動便可以定義為分包。 分包工作單元時，相關流程活動必須連結到包含服務項目和服務價格的有效採購合約明細。 活動的服務合約也定義了看板工作的產品數量與產生的服務數量的計算比例。 您可以選擇要根據作業數量、作業上報告的合格產品數量，還是產品總數量 (包括報廢產品) 來計算服務數量。  

轉移活動也可以定義為分包。 當您在轉移活動中選擇運輸責任方時，此定義會以隱含方式出現。 在您選擇 **托運人** 或 **收件者** 時，如果相應的來源倉庫或目標倉庫是廠商管理的倉庫，則該活動被視為分包。 在您選擇 **承運業者** 時，活動一律是分包的。 與分包流程活動一樣，分包轉移活動必須先連線到服務合約，然後才能啟用生產流程。

### <a name="backflush-costing"></a>倒推成本法

分包工作的成本會計會完全整合到精益製造解決方案 (倒推成本法) 的成本核算中。 服務訂購單收據過帳或發票開立時，服務成本會分配到生產流程。 對於倒推成本法，透過將已收到產品的標準成本分包區塊，與實際已收到且已開立發票的服務數量相抵銷，以計算分包服務的差異。

## <a name="material-supply-for-subcontracted-operations"></a>分包作業的物料供應
半成品和其他相關物料必須轉移到實際進行工作的地點。 在您使用分包作業和活動時，這種轉移通常與到廠商營運站點的額外運輸有關。 透過將 BOM 中的物料分配給分包作業，您宣告了材料必須暫存到已分配資源的資源群組輸入位置。 然後主計劃或精益補貨會將物料供應到該位置。  

若要對位於廠商站點的庫存進行建模，業界的最佳做法是定義廠商管理的倉庫。 您可以透過建立新倉庫並指派廠商帳戶，以輕鬆定義廠商管理的倉庫。 如要記錄該物料必須在執行作業之前轉移給廠商，您應該將廠商管理的倉庫分配到擁有該資源的資源群組輸入倉庫。  

如要在此倉庫補充物料，您可以使用多種策略：

-   轉移單
-   轉移日記帳
-   提取看板
-   直接購買到廠商位置

半成品是此規則的例外。 如要轉移半成品，您只能使用以下選項：

-   對於生產訂單與批次訂單，半成品只能透過使用揀料單日記帳合理轉移。**分包工作** 清單頁面。 此日記帳將建立可用於將半成品和原物料轉移給廠商的交貨單文件。
-   對於生產流程中的分包作業，半成品的轉移會透過廠商位置的提貨或生產看板收據進行記錄。 若要對顯式轉移活動建模，您可以使用附加轉移活動來結束生產看板。

**注意：** 單一生產訂單的生產途程不能跨越多個站點。 此規則也適用於分包工作。 因此，代表廠商管理的物料位置倉庫，必須定義在與途程中使用的內部資源相同站點中。 即使生產流程可以跨站點，但它們不能將半成品從一個站點運輸到另一個站點，因為該作業代表成本環境的變化。  

一般而言，分包資源群組的輸出倉庫和位置，會直接分配到途程或生產流程中下一步作業的倉庫和位置。 此設定有助於減少發生的工作報告量，或必須建模的其他傳輸作業數量。





[!INCLUDE[footer-include](../../includes/footer-banner.md)]