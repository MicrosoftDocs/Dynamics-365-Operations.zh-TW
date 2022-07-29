---
title: 未產生憑單
description: 本主題提供的資料可在未產生憑單時，協助疑難排解。
author: qire
ms.date: 04/13/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 1fbd5b5bb4a1d2a0c498b2abac82bd6f5ff3f1d2ed9960885eb8f44cbb17884d
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450627"
---
# <a name="voucher-isnt-generated"></a>未產生憑單

[!include [banner](../includes/banner.md)]

如果應產生憑單，但 **憑單交易** 頁面未顯示任何憑單，則根據需要按照以下各部分中的步驟解決此問題。

[![沒有憑單的憑單交易頁面。](./media/voucher-not-generated-Picture1.png)](./media/voucher-not-generated-Picture1.png)

## <a name="check-the-tax-applicability"></a>檢查稅金適用性

1. 前往 **稅** \> **定期任務** \> **未轉移的子分類帳日記帳分錄**。
2. 如果有日記帳記錄，選擇它，然後選擇 **立即轉移**。

    [![子分類帳日記帳分錄尚未轉移頁面上的立即轉移按鈕。](./media/voucher-not-generated-Picture2.png)](./media/voucher-not-generated-Picture2.png)

3. 再次打開 **憑單交易** 頁面，查看是否已產生憑單。

## <a name="determine-whether-customization-exists"></a>確認是否存在自訂

如果您已完成前幾部分中的步驟，但仍未發現問題，則確認是否存在自訂。 如果自訂不存在，請建立 Microsoft 服務要求以獲得更多支援。

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
