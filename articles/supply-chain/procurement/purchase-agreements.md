---
title: 採購合約
description: 本文提供採購合約的相關資訊。 採購合約是一種契約，用於承諾組織在一段時間內使用多個訂購單購買指定的產品數量或金額。 作為承諾回饋，買方可能會獲得特價和折扣優惠。
author: Henrikan
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AgreementClassification, AgreementLine, AgreementLinePrompt, PurchAgreement, PurchAgreementCreate, PurchAgreementGenerateReleaseOrder, PurchAgreementHistory, PurchAgreementInvoiceJournal, PurchLine, AgreementLines
audience: Application User
ms.reviewer: kamaybac
ms.custom: 11634
ms.assetid: 8ac20adf-7412-4929-be8c-aaedf23a76ad
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d8084ebed80a509d543053867bb1f4d483b3f8eb
ms.sourcegitcommit: fcb8a3419e3597fe855cae9eb21333698518c2c7
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/09/2022
ms.locfileid: "8450027"
---
# <a name="purchase-agreements"></a>採購合約

[!include [banner](../includes/banner.md)]

本文提供採購合約的相關資訊。 採購合約是一種契約，用於承諾組織在一段時間內使用多個訂購單購買指定的產品數量或金額。 作為承諾回饋，買方可能會獲得特價和折扣優惠。 

採購協議可適用於產品的特定數量、產品的特定貨幣金額或採購類別中產品的特定貨幣金額。 採購合約的價格和折扣推翻現有貿易合約中指定的價格和折扣。  

在 **採購合約** 頁面，您可以建立、套用和追蹤您的組織與供應商之間已建立的採購合約。 例如，建立採購合約後，您可以直接根據合約訂購。 每個採購合約都有一個由建立採購合約者定義的有效期。 購買的交貨日期必須在此有效期的生效日期內。  

建立採購合約後，您必須啟用合約才能生效。 若要啟用採購協議，請將 **將合約標記為有效選項** 設為 **是**。 

為防止您的採購合約受到使用和確認，請將合約狀態標記為 **已關閉**。 您在進行更改後，仍可以隨時將狀態更新為 **生效**。

## <a name="responsible-workers-on-purchase-agreements"></a>負責採購合約的工作人員

您可以在採購合約分類中識別主要責任工作人員和次要負責的工作人員。 這些值將由產生的購買合約繼承。 您不需要將負責的工作人員新增到採購合約中，並且可以根據採購合約本身逐案直接修改工作人員。 您不能在缺少主要負責人的情況下指定次要負責人，而且次要負責工作人員不是必要項目。 您不能將同一個工作人員指定為主要負責工作人員和次要負責工作人員。

> [!IMPORTANT]
> 若要使用責任方功能，您必須先在系統中開啟此功能。 從 Supply Chain Management 版本 10.0.25 起，此功能預設為開啟。 管理員可以透過搜尋來開啟或關閉 *採購合約責任方* 功能，其位在[功能管理](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)工作區。

## <a name="commitment-types"></a>承諾類型
採購合約中的每一行都表達了購買某物的承諾。 您可以使用多個訂購單 (PO) 的明細來履行承諾。 有四種類型的承諾：

-   **產品數量承諾**– 您購買特定數量的產品。
-   **產品價值承諾**– 您購買特定貨幣金額的產品。
-   **產品類別價值承諾**– 您在採購類別中購買特定貨幣金額。 金額可以來自目錄品項或非目錄品項。
-   **價值承諾**– 您在採購類別中購買特定貨幣金額的任何單一或多個產品。

## <a name="pricing-terms-for-purchase-agreements"></a>採購合約的價格條款
價格條款可能會有所不同，具體取決於承諾的類型。 採購合約中的定價條款優先於為貿易合約設定的任何其他定價條款。 下表描述受每種承諾類型影響的價格相關欄位。 包含 **是** 的欄位可以在訂單行上更新。

| 承諾類型                   | 單價 | 計價單位 | 折扣率 | 現金折扣金額 |
|-----------------------------------|------------|------------|------------------|----------------------|
| 產品數量承諾       | 是        | 是        | 是              | 是                  |
| 產品價值承諾          |            |            | 是              |                      |
| 產品類別價值承諾 |            |            | 是              |                      |
| 價值承諾                  |            |            | 是              |                      |

## <a name="policies-for-purchase-agreements"></a>採購合約原則
以下原則會影響採購合約承諾與相應訂購單行之間連結的運作方式：

-   **強制為最大** – 所有訂單行的總數量或金額不能超過相關承諾中指定的數量或金額。
-   **價格和折扣是固定的** – 訂單行的價格和相關承諾的價格必須相同。 如果訂單行上的價格發生變化，則指向承諾的連結將中斷。 如果連結中斷，則訂單行無助於履行承諾。
-   **最小發放金額和最大發放金額** – 如果指定了金額，如果對訂單行進行任何變更導致訂單行與相關承諾不同，您會收到一則訊息。

## <a name="fulfillment-calculations-for-purchase-agreements"></a>採購合約的履行計算
**採購合約** 頁面的 **行詳細資料** FastTab 的 **履行** 索引標籤會顯示履行數量和金額。  

**履行** 區域顯示履行承諾所需的剩餘金額或數量。  

**合約** 區域顯示銷售合約行有效的總數量或總金額。  

您可以透過選擇 **相關資訊** 在採購合約的行或標題上採取行動。

## <a name="confirmations-and-version-history-for-purchase-agreements"></a>採購合約的確認和版本歷程記錄
當您確認採購合約時，採購合約的目前版本儲存在歷程記錄資料表中。 如果變更了採購合約，您可以在歷程記錄中再次確認以儲存其他版本的採購合約。 如果未確認採購合約，您仍可以使用它來建立訂購單。 但是，不會儲存採購合約的歷程記錄資訊。 您可以預覽或列印合約的所有版本。 然後，您可以與您的供應商共用修訂以獲得核准。

## <a name="applying-purchase-agreements-in-the-ordering-process"></a>在訂購程序中套用採購合約
建立訂購單時，您可以對訂購單套用採購合約。 然後將合約條款中的資訊 (例如付款條款、交貨條款和交貨地址) 複製到訂購單的標題中。 如果訂購單包含合約涵蓋的產品或類別的一個或多個行，則採購合約中的價格和折扣會套用至這些明細。 訂單明細上的金額或數量有助於履行採購合約中的承諾。 同一個訂購單可以包括與採購合約無關的行和具有採購合約承諾的行。  

您只能在建立訂購單時選擇採購合約。 建立訂購單後，您就無法選擇採購合約。  
在某些間接建立訂購單的情況下，您可以控制 Supply Chain Management 是否自動搜尋適用的採購合約。 例如，當您自動確定規劃的訂購單，或建立以銷售訂單為依據的訂購單時，您可以按照以下方式進行。

## <a name="matching-policy-on-purchase-agreements"></a>採購合約比對原則
您可以在採購合約的標題上定義明細比對原則。 當 **應付帳款參數** 頁面的 **允許覆寫比對原則** 欄位 (在 **價格和數量比對** FastTab 上) 設定為 **高於公司原則** 時，這行比對原則會尊重應付帳款參數比對原則。 除非在相應的材料、物料和供應商或類別採購政策上另有定義，否則引用採購合約的單據將使用採購合約標題上定義的比對原則。

## <a name="purchase-agreements-and-intercompany-trade"></a>採購合約和公司間貿易
可以在位於不同法律實體中的供應商帳戶和客戶帳戶之間建立公司間貿易關係。 為其中一方建立銷售訂單或訂購單時，會建立公司間訂單鏈。 在訂單鏈中，銷售訂單和採購訂單在相應的法律實體中建立。  

您可以為公司間貿易方之一建立採購合約或銷售合約。 然後，您可以為其他法律實體中的其他公司間貿易方產生相應的銷售協議或採購協議。  

如果您在一個法律實體中建立使用公司間採購合約的公司間採購訂單，則相應的公司間銷售訂單將使用另一法律實體中的相應公司間銷售合約。 銷售協議合約的履行和採購合約的履行是同步的，就像公司間銷售訂單和公司間採購訂單是同步的一樣。

## <a name="financial-dimensions-on-purchase-agreements"></a>採購合約的財務維度
您可以將財務維度複製到文件標題或採購合約的各個行。 如果您更改合約標題或合約行中的維度，則更改不會影響任何已下達的訂單，但會反映在任何新訂單上。

## <a name="additional-resources"></a>其他資源

- [建立購買合約。](tasks/create-purchase-agreement.md)
- [建立採購訂單時套用採購合約](tasks/create-purchase-release-order-purchase-agreement.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]