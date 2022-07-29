---
title: 現金流預測設定疑難排解
description: 本主題針對您在設定現金流預測時可能遇到的問題提供解答。 可解決有關現金流設定、現金流更新和現金流 Power BI 的常見問題 (FAQ)。
author: panolte
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerCovParameters
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2020-12-30
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 39860a1960706aae7d223c8d2e810d39edc41b11deb80026925e6655f8e23ee8
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450507"
---
# <a name="troubleshoot-cash-flow-forecasting-setup"></a>現金流預測設定疑難排解

[!include [banner](../includes/banner.md)]

本主題針對您在設定現金流預測時可能遇到的問題提供解答。 可解決有關現金流設定、現金流更新和現金流 Power BI 的常見問題 (FAQ)。

## <a name="why-is-cash-flow-shown-for-only-one-legal-entity"></a>為什麼只顯示一個法律實體的現金流？

現金流預測是按法律實體設定和計算的。 Power BI 報表和 Finance Insights 中的現金流預測功能會顯示結果。

必須為要查看預測的每個法律實體設定現金流預測。 查看所有法律實體中現金流預測的設定。 或者，查看現金流預測的所有法律實體的設定，並確保它們的設定符合您的預期。

## <a name="why-doesnt-power-bi-show-all-the-cash-flow-data"></a>為什麼 Power BI 不顯示所有現金流資料？

必須先完成幾個步驟，現金流預測才能顯示在 Power BI 檢視表中。 查看以下清單，並確保每個步驟都已完成：

- 為每個法律實體設定現金流。
- 在總帳參數中，設定系統貨幣和系統匯率類型。
- 設定分類帳會計貨幣和匯率類型。
- 輸入交易貨幣與會計貨幣之間的匯率。
- 輸入會計貨幣與系統貨幣之間的匯率。
- 輸入會計貨幣與各銀行貨幣之間的匯率。

## <a name="why-did-cash-flow-power-bi-work-in-previous-versions-but-is-now-blank"></a>為什麼現金流 Power BI 可在先前的版本中運作，但現在是空白的？

驗證是否已設定來自實體商店的「現金流測量 V2」和「LedgerCovLiquidityMeasurement」測量。 如需如何使用實體商店資料的相關資訊，請參閱 [Power BI 與實體商店整合](../../fin-ops-core/dev-itpro/analytics/power-bi-integration-entity-store.md)。 驗證查看 Power BI 內容所需的所有步驟已經完成。 如需更多資訊，請參閱[現金概觀 Power BI 內容](Cash-Overview-Power-BI-content.md)。

## <a name="have-the-entity-store-entities-been-refreshed"></a>實體商店實體是否已重新整理？

您必須定期重新整理實體，以確保資料是最新且準確的。 若要手動重新整理特定實體，請前往 **系統管理 \> 設定 \> 實體商店**，選擇實體，然後選擇 **重新整理**。 資料也可以自動更新。 在 **實體商店** 頁面，將 **啟用自動重新整理** 選項設定為 **是**。

## <a name="which-calculation-method-should-be-used-when-calculating-cash-flow-forecasts"></a>計算現金流預測時應該使用哪種計算方法？

有兩個重要的現金流預測計算方法可選擇。 **新增** 選項將計算新單據和自上次執行批次作業以來已變更的單據的現金流預測。 此選項往往執行得更快，因為它處理的單據子集較小。 **總計** 選項將重新計算系統中每個單據的現金流預測。 此選項需要更多時間，因為它需要完成更多工作。

### <a name="how-do-i-improve-the-performance-of-the-cash-flow-forecasting-recurring-batch-job"></a>如何提高現金流預測定期批次作業的效能？

建議每天在非高峰時段使用 **新增** 計算方法執行現金流預測一次。 建議每週六天使用這種方法。 然後每週在活動量最少的一天使用 **總計** 計算方法執行現金流預測一次。

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

