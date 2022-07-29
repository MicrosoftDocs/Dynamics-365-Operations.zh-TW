---
title: 建立付款發票
description: 本主題說明如何建立每月租賃發票。 您可以為單一租賃建立發票，也可以使用批次處理為多個租賃建立發票。
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeasePaymentSchedule
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: bc87c329f6f5dd9532b1319f8d88fbc41dcd4d14
ms.sourcegitcommit: b9c2798aa994e1526d1c50726f807e6335885e1a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/13/2021
ms.locfileid: "8450897"
---
# <a name="create-payment-invoices"></a>建立付款發票

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]


您可以為單一租賃建立每月發票，也可以使用批次處理為多個租賃建立發票。 以下程序說明如何在已打開 **租賃帳簿設定** 頁面上的 **向廠商付款** 參數時，建立單獨的租賃付款分錄

1. 在 **租賃摘要** 頁面，選擇租賃，然後選擇 **帳簿 \> 付款計劃**。
2. 選擇必須支付的款項，然後選擇 **建立日記帳**。 您將收到一則訊息，指出已針對所選付款建立了日記帳。
3. 選擇 **發票日記帳**，然後選擇必須支付的發票。
4. 將日記帳分錄過帳到總帳之前，在 **行** 索引標籤上檢查該分錄。

    > [!NOTE]
    > 預設情況下，建立的廠商發票行使用來自 **應付帳款參數** 頁面的廠商過帳範本。

5. 選擇正確的日記帳，然後選擇必須支付的發票。

    在這個例子中，已開啟租賃帳簿上的 **向廠商付款** 參數。 因此，發票將在發票日記帳中。 **概觀** 區段會顯示日記帳分錄的摘要，**行** 區段顯示實際日記帳行的詳細資料。
    
   系統鎖定某些財務欄位，使其不能編輯，以防止交易和計劃之間出現任何差異。 已鎖定的欄位包括：**帳戶**、**金額**、**財務維度**、**貨幣** 和 **交易類型**。 此外，您將無法在任何資產租賃日記帳分錄中新增或刪除日記帳分錄行，因為這可能會導致計劃和交易之間出現差異。

    > [!NOTE]
    > 如果 **向廠商付款** 參數關閉，租賃帳簿的 **資產租賃** 頁面上將列出付款日記帳分錄，而系統將建立資產租賃分錄而不是發票。 租賃付款分錄將過帳到在 **月租日記帳** 欄位中指定的日記帳名稱。

6. 交易過帳後，您可以透過選擇查看租賃帳簿中的 **負債交易** 來查看租賃負債的交易資訊和帳面價值。

    在付款計劃中，選取 **已過帳的日記帳** 核取方塊，並且該行將顯示發票日記帳編號。 建立付款日記帳和該日記帳的分錄後，您必須先沖銷該分錄，然後才能重新建立它。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
