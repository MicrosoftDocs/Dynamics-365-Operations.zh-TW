---
title: 應收帳款中的收帳
description: 應付帳款收帳資訊使用 Microsoft Dynamics 365 Finance 收帳頁面在一個中央檢視表中進行管理。 信用和收帳經理可以使用這個集中檢視表來管理收帳。 收帳代理人可以從使用預先定義收帳標準產生的客戶清單或從客戶頁面開始收帳流程。
author: ShivamPandey-msft
ms.date: 10/26/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustAgingSnapshot, CustBankAccounts, CustCollections, CustCollectionsActivitiesListPage, CustCollectionsAgent, CustCollectionsCaseListPage, CustCollectionsPool, CustCollectionsPoolsListPage, CustTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 3061
ms.assetid: fd851520-8d93-434b-845b-be127d6ac3a6
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b143ebead89804af57e7d2dbfa6f7d366c1ae664573776d78bff44763ddeb819
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450225"
---
# <a name="collections-in-accounts-receivable"></a>應收帳款中的收帳

[!include [banner](../includes/banner.md)]

應付帳款收帳資訊使用 Microsoft Dynamics 365 Finance 收帳頁面在一個中央檢視表中進行管理。 信用和收帳經理可以使用這個集中檢視表來管理收帳。 收帳代理人可以從使用預先定義收帳標準產生的客戶清單或從客戶頁面開始收帳流程。

在開始設定或使用收款之前，您應該了解以下概念：
-   客戶帳齡快照集包含某個時間點的帳齡餘額資訊
-   收帳客戶群可幫助您組織工作
-   收帳代理人可以擁有自己的客戶群
-   清單頁面組織收帳客戶、活動和案例
-   客戶的所有收帳資訊都在一個頁面上，您可以從該頁面採取行動
-   可以在一個步驟中免除、恢復或沖銷利息和費用
-   可以在一個步驟中建立核銷交易
-   可以在一個步驟中處理資金不足 (NSF) 付款

以下章節描述了每個概念。

## <a name="customer-aging-snapshots"></a>客戶帳齡快照集
帳齡快照包集包含特客戶在某個時間點計算的帳齡餘額。 此資訊會顯示在帳齡餘額清單頁面和收帳頁面上。 必須先建立帳齡快照集，然後才能查看收帳清單頁面上的資訊。 

對於每個客戶，帳齡快照集包含對應於帳齡期間定義的每個帳齡期間的帳齡快照集標題和記錄詳細資料。 

帳齡快照集標題包含客戶帳戶的應付款總金額、信用額度、裝箱單金額、銷售訂單金額、爭議交易編號和爭議交易總額。 客戶的所有交易都包括在這些金額的計算中。 應付款總金額、信用額度、裝箱單金額和銷售訂單金額將顯示在收帳頁面的信用資訊 FactBox 上。 

對於帳齡期間定義中的每個帳齡期間，都會建立帳齡快照集詳細記錄。 每個帳齡快照都詳細記錄都包含帳齡期間識別碼和日期在帳齡期間內的交易總額。 交易會分配到某個帳齡期間，例如 30 天前已到期。 該日期與建立帳齡快照集時指定的帳齡截止日期值相關。 此資訊會顯示在帳齡餘額清單頁面和收帳頁面上的帳齡餘額 FactBox 中。

## <a name="collections-customer-pools"></a>收帳客戶群
客戶群是定義為可用於展示和管理收帳或帳齡流程之客戶記錄群組的查詢。 使用客戶群篩選帳齡餘額、收帳活動和收帳案例清單頁面上的資訊。 如果已建立帳齡快照，也可以使用客戶群篩選包含在該帳齡快照中的客戶帳戶。

## <a name="collections-agents"></a>收帳代理人
根據預設，使用者可以查看收帳清單頁面上的所有客戶資訊。 您可以使用收帳代理人記錄確定可用於篩選收帳清單頁面上的資訊和收帳頁面中的客戶群。 

收款代理是處理客戶工作以確保按時收到付款的人員。 收帳代理人是使用者設定頁面上分配給使用者的工作人員。

## <a name="collections-list-pages"></a>收帳清單頁面
以下清單頁面可幫助您組織收帳資訊。
-   帳齡餘額 – 該清單頁面上的欄按帳齡顯示客戶餘額和帳齡金額。 此資料儲存在帳齡快照中。 帳齡期間由所用的帳齡期間定義決定。 如果為群查詢指定了某個客戶，則帳齡期間定義從自客戶群中提取。 如果客戶群裡沒有帳齡期間定義，則使用應收帳款參數頁面中設定的預設帳齡期間定義。 如果未指定預設帳齡期間定義，則在帳齡期間定義頁面中使用第一個帳齡期間定義。
-   收帳活動 – 該清單頁面上的欄顯示標識為收帳活動的活動。 這些活動是使用收帳頁面建立的。 使用這些活動來追蹤您使其與收帳相關的工作。
-   收帳案例 – 該清單頁面上的欄顯示具有包含收帳案例類型之案例類別的資訊。

> [!NOTE]
> 必須先建立帳齡快照集，然後才能查看這些清單頁面上的資訊。 僅為已建立帳齡快照集的客戶顯示資料。 在清單頁面上顯示可附加篩選的記錄，如下所示：
> <li>根據預設，財務和營運應用程式使用者可以存取所有擁有帳齡快照集的客戶。</li>
> <li>如果存在客戶群，則必須將使用者設定為收帳代理人，以使用這些客戶群來篩選收帳清單頁面上的資訊。 資訊僅限於包含在所選客戶群中的客戶。</li>
> <li>如果將使用者設定為收帳代理人，則只有為該收帳代理人選擇的客戶群在清單頁面上可用。 如果在收帳代理人的收帳代理人頁面中選取了允許代理人查看所有客戶群開關，則該代理人可使用所有客戶群。</li>


## <a name="collections-page"></a>收帳頁面
使用收帳頁面查看、管理客戶的收帳資訊、活動和案例，並對其採取行動。 

上方窗格顯示所選客戶的案例。 中間窗格顯示客戶的交易。 下方窗格顯示客戶的活動。 您可以建立收帳案例來追蹤一項或多項交易和活動的收帳資訊。 上下兩個窗格的資訊可以按案例篩選。 

FactBoxes 顯示所選客戶的帳齡餘額和信用額度資訊。 此資訊儲存在帳齡快照中。 如有需要，您可以使用目前資訊更新帳齡快照。 

動作窗格包含顯示所選客戶、案例、交易或活動的相關資訊的按鈕。 您還可以執行常用動作，例如變更交易的收帳狀態、透過與電子郵件提供者的整合傳送電子郵件通信、償還客戶、處理 NSF 付款以及註銷無法收回的餘額。

## <a name="waive-reinstate-or-reverse-interest-and-fees"></a>免除、恢復或沖銷利息和費用
您可以免除、恢復或沖銷完整利息單，或利息單中包含的費用和交易利息。 您可以透過選擇利息單、交易利息或費用，從「所有客戶清單」頁面動作窗格的收帳索引標籤上執行此動作。 

這些調整僅影響利息單，以及其中包含的利息和費用。 使用「一步建立沖銷交易」區段中的步驟沖銷客戶所欠的所有費用。

有關更多資訊，請參閱[建立具有範圍的利息代碼](tasks/create-interest-code-range.md)和[處理利息](tasks/process-interest.md)。 

## <a name="create-writeoff-transactions"></a>建立沖銷交易
您可以透過點擊收帳表單中的沖銷以及帳齡餘額、客戶和未結客戶發票清單頁面來沖銷壞帳。 

當您沖銷客戶的交易時，該客戶的所有交易都會自動標記為結算。 已沖銷的金額取決於標記交易的淨額。 沖銷交易在一般日記帳中建立，最多可包含三種類型的日記帳行。

-   第一種日記帳行包含客戶沖銷分錄。 如果標記的交易記錄包含貨幣代碼、維度和過帳設定檔的多個組合，則會為每個組合建立單獨的日記帳行。
-   第二種日記帳行包含總帳沖銷分錄。 如果標記的交易記錄包含貨幣代碼、維度和過帳設定檔的多個組合，則會為每個組合建立單獨的日記帳行。
-   第三種日記帳行包含銷售稅的總帳沖銷資訊。 只有在應收帳款參數頁面中選擇單獨的銷售稅開關後，才會建立此日記帳行。 如果已標記的交易記錄包含銷售稅應付科目、維度和銷售稅代碼的多個組合，則會為每個組合建立單獨的日記帳行。

沖銷交易以交易貨幣建立。

有關詳細資訊，請參閱[建立客戶的沖銷日記帳](tasks/create-write-off-journal-customer.md)。

## <a name="process-not-sufficient-funds-nsf-payments"></a>處理資金不足 (NSF) 付款 

您可以在收帳頁面上點選 NSF 付款來處理 NSF 付款。 當您點選此按鈕時，會取消付款。 如果客戶需要繳納 NSF 費用，則會在付款日記帳中建立費用交易。 該費用金額取決於自動費用的設定。 適用於 NSF 付款的自動費用由受影響銀行帳戶的在銀行帳戶頁面中選擇的費用組指定。







[!INCLUDE[footer-include](../../includes/footer-banner.md)]