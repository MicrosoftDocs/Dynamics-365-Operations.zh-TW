---
title: 未產生 TaxTrans 紀錄
description: 本主題提供的資料可在未產生 TaxTrans 記錄時，協助疑難排解。
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
ms.openlocfilehash: 82b00387e39b88e1ab2bc27d9dbc4e36aac3a7a605c04669171997ba236ae39a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450540"
---
# <a name="taxtrans-record-isnt-generated"></a>未產生 TaxTrans 紀錄

[!include [banner](../includes/banner.md)]

如果您為交易選擇 **已過帳銷售稅**，但是 **已過帳銷售稅** 頁面上未顯示稅務明細或缺少稅務明細，有可能是未產生 **TaxTrans** 記錄。

[![沒有明細項目的 [已過帳銷售稅] 頁面。](./media/taxtrans-is-not-generated-Picture1.png)](./media/taxtrans-is-not-generated-Picture1.png)

若要解決此問題，請根據需要按照以下各部分中的步驟操作。

## <a name="check-the-sales-tax-before-you-post-the-transaction"></a>過帳交易前檢查銷售稅

1. 在過帳交易之前，在 **過帳發票** 頁面中，選擇 **銷售稅** 檢查計算。

    [![過帳發票頁面上的帳銷售稅按鈕。](./media/taxtrans-is-not-generated-Picture2.png)](./media/taxtrans-is-not-generated-Picture2.png)

2. 在 **臨時銷售稅交易** 頁面中，查看計算結果。 如果未計算稅款，請參閱[未計算稅額或稅額為零](sales-tax-troubleshooting-tax-not-calculated-amount-zero.md)。

## <a name="find-the-taxtrans-record-in-all-posted-sales-tax"></a>在所有過帳的銷售稅中查找 TaxTrans 記錄

1. 前往 **稅** \> **查詢和申報** \> **銷售稅查詢** > **已過帳銷售稅**。
2. 在 **憑單** 列標題中，選擇篩選符號以查找 **TaxTrans** 記錄。
3. 如果找到要查找的銷售稅記錄，則檢查日期。 如果日期與日記帳標題的日期不同，請建立 Microsoft 服務要求以尋求額外支援。

    [![已過帳銷售稅頁面。](./media/taxtrans-is-not-generated-Picture4.png)](./media/taxtrans-is-not-generated-Picture4.png)

## <a name="debug-to-check-details"></a>偵錯以檢查詳細資料

1. 有關如何偵錯和確定是否正確產生 **TmpTaxWorkTrans** 和 **TaxUncommitted**，請參閱 [TaxTrans 中的欄位值不正確](sales-tax-troubleshooting-field-value-taxtrans-incorrect.md)。
2. 如果已正確產生 **TaxTmpWorkTrans** 或 **TaxUncommitted**，在 **TaxPost::SaveAndPost()** 和 **Tax::SaveAndPost** 處加入中斷點以偵錯未插入 **TaxTrans** 的原因。

    [![在代碼中加入中斷點。](./media/taxtrans-is-not-generated-Picture5.png)](./media/taxtrans-is-not-generated-Picture5.png)

    [![已加中斷點的結果。](./media/taxtrans-is-not-generated-Picture6.png)](./media/taxtrans-is-not-generated-Picture6.png)

## <a name="determine-whether-customization-exists"></a>確認是否存在自訂

如果您已完成前幾部分中的步驟，但仍未發現問題，請確認是否存在自訂。 如果自訂不存在，請建立 Microsoft 服務要求以獲得更多支援。

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
