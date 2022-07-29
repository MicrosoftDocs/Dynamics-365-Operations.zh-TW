---
title: 透過採購獲得資產
description: 本主題介紹如何設定固定資產和應付帳款之間的整合，以從訂購單或廠商發票自動建立固定資產，或自動過帳固定資產的購置和購置調整交易。
author: moaamer
ms.date: 03/05/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetParameters
audience: Application User
ms.reviewer: roschlom
ms.custom: 3481
ms.assetid: d4e73a3f-633b-48b2-b8db-7a4a59a4d7ec
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1c51abd3ce380f0cb1ad688ffab16b239460bc45
ms.sourcegitcommit: 1707cf45217db6801df260ff60f4648bd9a4bb68
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/23/2021
ms.locfileid: "8451071"
---
# <a name="acquire-assets-through-procurement"></a>透過採購獲得資產

[!include [banner](../includes/banner.md)]

本主題介紹如何設定固定資產和應付帳款之間的整合，以從訂購單或廠商發票自動建立固定資產，或自動過帳固定資產的購置和購置調整交易。 一個採購行建立一個資產，無論該採購行中的數量如何。 如果需要建立多個固定資產，則必須建立多個採購行。

 以下方法可用於將固定資產和應付帳款整合，所有固定資產必須使用相同的方法：
-   先手動建立固定資產，然後將固定資產編號新增到訂購單或廠商發票的行。 在過帳廠商發票時，會自動過帳資產的購置交易。 這是預設檢視方法。
-   先手動建立固定資產，然後將固定資產編號新增到訂購單或廠商發票的行。 在過帳廠商發票時，不過帳資產的購置交易。
-   在過帳選取 [建立新固定資產] 核取方塊的產品收貨或廠商發票時，將自動建立固定資產。 在過帳廠商發票時，會自動過帳資產的購置交易。
-   在過帳選取 [建立新固定資產] 核取方塊的產品收貨或廠商發票時，將自動建立固定資產。 在過帳廠商發票時，不過帳資產的購置交易。

如果您偏好手動建立固定資產，請選擇前兩種方法之一，然後將固定資產編號指派給訂購單或廠商發票。 如果您喜歡更靈活的方法，請選擇後兩種方法之一：有時您可能會手動建立固定資產，有時可能會根據行品項詳細資料中的固定資產資訊自動建立固定資產。 

無論您是手動建立固定資產還是使用更靈活的方法，您都必須決定是否只能在固定資產中過帳購置交易，或者在過帳廠商發票時是否進行過帳。 某些組織希望使用者使用手動日記帳分錄或提議在固定資產中手動建立購置和購置交易。 

本主題將詳細介紹上述各方法。

## <a name="methods-for-manually-creating-fixed-assets"></a>手動建立固定資產的方法
當您過帳在行中輸入了固定資產編號的廠商發票時，如果在固定資產參數頁面中選擇了允許從採購中購置資產選項，則會自動過帳購置，並且資產的狀態會變更為「未結」。 

如果無法過帳購置，您可以在固定資產中手動輸入購置交易，或使用固定資產日誌中的購置提議同時建立多個購置交易。

> [!NOTE]                                                                                                                              
> 如果將固定資產設定為將購置交易過帳限制到特定使用者群組，則您必須是該使用者群組的成員才能從發票過帳購置交易。

## <a name="methods-for-automatically-creating-fixed-assets"></a>自動建立固定資產的方法
當您過帳為行選擇了建立新固定資產選項的產品收貨時，將建立狀態為尚未獲得的新固定資產。 然後，當您過帳包含新固定資產的廠商發票時，如果將固定資產設定為允許從應付帳款採購資產，並且您是可以發布收購交易的使用者群組的成員，則將為這個新資產過帳購置交易，並且資產狀態將變更為「未結」。 

如果在您過帳產品收貨時在採購訂單行上未選取 [是否新增固定資產？] 選項，但在過帳廠商發票時選中了該核取方塊，並且固定資產設定為允許建立和購置，則新增固定資產，而且其購置狀態為「未結」。 如果在您過帳產品收貨時已經建立了附加資產，則在您過帳廠商發票時不會建立附加資產。

### <a name="capitalization-threshold"></a>資本化閾值

當您使用自動建立和購置資產的方法時，您可以設定系統來驗證固定資產的購買金額是否達到指定的資產折舊資本化閾值。 如果滿則，則從應付帳款建立資產時，將在帳簿中為資產選擇折舊選項。 

資本化閾值是確貨幣金額，確定資產達到指定金額時是否對資產進行折舊。 例如，如果您購買一項資產，且採購金額低於資本化閾值，則不指定該資產進行折舊；如果購買金額達到或超過閾值，則指定該資產進行折舊。 

您可以在固定資產群組頁面設定資本化閾值。

## <a name="scenario"></a>案例
以下案例說明固定資產和應付帳款整合的完整週期。 其中介紹了一個範例設定，並還描述如何使用購置提議。 

在此案例下，系統設定如下：

-   在產品收貨或廠商發票過帳期間自動建立資產，但設定固定資產以防止從應付帳款過帳購置交易。
-   在品項群組頁面的固定資產收貨和固定資產發貨科目類型的科目類型欄位中指定科目。
-   電腦群組 (COMP) 的資本閾值為 1,500。
-   您的工作是為員工將使用的新筆記型電腦輸入訂購單，過帳訂購單，驗證運輸員是否過帳產品收貨，過帳廠商發票，然後驗證會計是否將筆記型電腦資產更新為「未結」狀態。

首先，使用訂購單頁面輸入筆記型電腦的詳細資料，成本為 1,600。 在訂購單行的固定資產快速索引標籤上選擇 [是否新增固定資產？] 選項，選擇 COMP 作為固定資產群組，並儲存訂購單。 

收到筆記型電腦後，裝運人員將輸入並過帳產品收貨，以記錄收到該筆記型電腦。 已建立筆記型電腦資產，狀態為「尚未購置」。 該金額超過了資本化閾值。 因此，在帳簿中為筆記型電腦資產選擇 [折舊] 選項。 將出現以下交易。

| 描述                               | 客戶             | 借方    | 貸方   |
|-------------------------------------------|---------------------|----------|----------|
| 採購，產品收貨採購        | 未開票的收貨 | 1,600.00 |          |
| 採購，產品收貨採購沖銷 | 應計採購   |          | 1,600.00 |

接下來，過帳筆記型電腦的廠商發票。 不變更筆記型電腦狀態，因為固定資產已設定為在過帳廠商發票時禁止過帳資產購置交易。 在過帳廠商發票時選擇了 [建立新固定資產] 選項。 因此，使用了固定資產收貨科目。 由於未過帳任何購置，因此未使用固定資產發貨科目；稍後，當您組織的會計使用購置提議在固定資產中過帳購置交易時，將使用該帳戶。 

將出現以下交易。

| 描述                               | 客戶             | 借方    | 貸方   |
|-------------------------------------------|---------------------|----------|----------|
| 採購，產品收貨採購沖銷 | 應計採購   | 1,600.00 |          |
| 廠商餘額                            | 應付帳款    |          | 1,600.00 |
| 採購、固定資產收貨             | 電腦費用    | 1,600.00 |          |
| 採購，產品收貨採購        | 未開票收貨 |          | 1,600.00 |

最後，會計會審核所有狀態為「未購置」的固定資產。 因此，新的筆記型電腦資產也受審查。 然後，會計從固定資產日記帳行打開購置提議頁面，並為所有具有發票但狀態仍為「尚未購置」的資產建立購置交易。 過帳日記帳時，筆記型電腦資產的狀態變更為「未結」。 貸記固定資產發貨科目，借記資產購置科目。 

以下是此案例的變體：

-   如果固定資產設定為允許在過帳廠商發票時過帳資產購置交易，則會計不必使用固定資產中的購置提議，因為購置交易已建立。 此外，當您過帳廠商發票時會更新不同的帳戶。 借記固定資產收貨存貨科目而不是電腦費用，並發生兩個額外的交易：借記資產購置科目和貸記固定資產發貨庫存科目。
-   如果在過帳產品收貨時未選擇 [建立新固定資產] 選項，則此時不會建立任何資產。 如果您在過帳廠商發票之前選擇 [建立新的固定資產] 選項，則資產已建立並且狀態為尚未購置，或者如果您在過帳廠商發票時還過帳購置交易，則狀態為「未結」。
-   如果筆記型電腦成本為 1,400 而不是 1,600，則未達到資本化閾值。 因此，將建立資產並清除折舊選項。
-   如果使用發票登記，您可以在發票登記過帳後使用發票核准日記帳頁面搜尋憑證，將訂購單連結到廠商發票，選擇新建固定資產選項，然後過帳廠商發票。 如果您是可以建立購置交易的使用者群組的成員，則會建立購置並且資產的狀態為「未結」。
-   如果僅接收部分數量，則由於使用者群組限制，不會為第一個廠商發票建立資產購置。 只有在已為第一個廠商發票輸入了購置交易，並且您是允許過帳購置的使用者群組的成員的情況下，才能為完成訂購數量的第二個廠商發票過帳購置。


如需詳細資訊，請參閱[固定資產整合](fixed-asset-integration.md)。





[!INCLUDE[footer-include](../../includes/footer-banner.md)]