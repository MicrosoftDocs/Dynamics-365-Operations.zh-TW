---
title: 沖銷已過帳租賃交易
description: 本主題說明如何沖銷已過帳的租賃交易。 透過「資產租賃」建立的任何交易都可以沖銷。
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeaseLeaseTransactions
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: f76b75a968e9ee9a3c545f646077c16282b5b185aa88025653f7443fbcfd9581
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450756"
---
# <a name="reverse-posted-lease-transactions"></a>沖銷已過帳租賃交易

[!include [banner](../includes/banner.md)]

透過「資產租賃」建立的任何交易都可以沖銷。 透過「資產租賃」沖銷的交易會更新您的租賃資料。 因此，它們還會更新租賃負債和使用權 (ROU) 資產的帳面價值。

若要建立租賃的沖銷交易，請執行以下步驟。

1. 在 **資產交易** 頁面或 **負債交易** 頁面上，選擇交易，然後選擇 **沖銷交易**。
2. 在出現的對話方塊中，可以編輯沖銷分錄的過帳日期。 預設情況下，**日期** 欄位設定為所選交易的交易過帳日期。 沖銷分錄不能早於所選交易的原始過帳日期過帳。
3. 選取 **確定**。 將過帳一項日記帳分錄，以沖銷您選擇的分錄。 將在 **資產交易** 或 **負債交易** 頁面中顯示沖銷，並更新該頁面中顯示之目前餘額的淨額總計。

當您選擇 **沖銷追踪** 時，會出現一個對話方塊，其中顯示原始交易和沖銷交易，以及一個連結編號，稱為 *追踪編號*。 為了使沖銷更容易理解並提高可見性，您還可以使用租賃排程來追蹤沖銷。

**排程** 頁面中的 **最近日記帳編號** 欄位顯示交易的日記帳編號。 沖銷交易時，將使用沖銷交易的日記帳編號更新此欄位。 此外，將選取 **已沖銷** 核取方塊，以指示交易已沖銷，並且選取 **已過帳** 欄位。

## <a name="revoke-a-reversed-transaction"></a>撤銷已沖銷交易

若要撤消已沖銷交易，請按照下列步驟操作。

1. 在 **排程** 頁面或 **交易** 頁面上，選擇原始交易。
2. 請執行以下其中一個步驟：

    - 如果您已在 **排程** 頁面中選擇交易，則按照[批次建立月度日記帳分錄](create-monthly-journals-batch.md)中有關建立日記帳的步驟操作。 您必須手動過帳日記帳。
    - 如果您已在 **交易** 頁面中選擇交易，則選擇 **沖銷交易**。 您將收到一則訊息，指出該撤銷是對先前沖銷的撤銷，並且您可以編輯此撤銷的過帳日期。 但是，一般業務驗證會影響可在 **日期** 欄位中輸入的日期。 

3. 選取 **確定**。 將過帳一項日記帳分錄，以沖銷您選擇的分錄。 將在 **交易** 頁面中顯示沖銷，並將目前總淨餘額恢復為第一次沖銷之前的值。 因此，避免了沖銷對餘額的影響。

當您選擇 **沖銷追踪** 時，會出現一個對話方塊，其中顯示原始交易和沖銷交易，以及一個連結編號。

您還可以使用相應的 **排程** 頁面來追蹤沖銷。 **沖銷** 欄位已清除，但 **日記帳已過帳** 欄位已選取。 此外，將使用撤銷交易的日記帳編號更新 **最近的日記帳編號** 欄位，並使用沖銷日記帳編號更新 **日記帳編號** 欄位。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
