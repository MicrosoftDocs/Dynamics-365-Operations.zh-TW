---
title: 批次確認資產租賃付款計劃
description: 本主題介紹如何批次確認多個付款計劃。
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeasePaymConfirmationDetails
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 82e985d3b1518a287fbf0916ab3afc71d4bd6466f93992b587942053af44cf59
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450708"
---
# <a name="confirm-asset-leasing-payment-schedules-in-a-batch"></a>批次確認資產租賃付款計劃

[!include [banner](../includes/banner.md)]

本主題介紹如何批次確認多個付款計劃。 付款計劃是在租賃到租賃的基礎上或透過確認批次流程來確認的。 日記帳分錄只能針對已確認付款計劃的租賃過帳。 確認付款計劃是對租賃財務資訊的最終核准。 未來對租賃財務資訊的所有變更 (例如付款和租賃期限) 均構成租賃調整，應以這種方式進行處理。

要確認多個付款計劃，請按照以下步驟操作。

1. 前往 **資產租賃 \> 定期 \> 確認批次**。
2. 在 **確認批次** 頁面，選擇 **確認批次**。
3. 在出現的對話方塊中，篩選出您要確認的帳簿。

    - 要確認特定租賃組中的所有帳簿，請在 **租賃群組** 欄位中選擇該群組。
    - 要確認特定帳簿，請在 **帳簿識別碼** 欄位中選擇該帳簿。
    - 要確認所有帳簿，請打開 **所有帳簿** 參數。

在 **已確認帳簿** 頁面將顯示新確認的帳簿的資訊。 確認付款計劃後，可以針對租賃過帳初始確認日記帳分錄。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
