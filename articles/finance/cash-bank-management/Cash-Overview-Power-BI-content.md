---
title: 現金概觀 Power BI 內容
description: 本主題介紹現金概觀 Power BI 內容。 它說明了如何存取內容中包含的報表，並提供有關用於構建內容的資料模型和實體的資訊。
author: saraschi2
ms.date: 07/16/2020
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: BankTreasurerWorkspace
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 3f7e0c792df8519f3bcb2ade2e29cc4c5c8e4730
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/15/2022
ms.locfileid: "8451470"
---
# <a name="cash-overview-power-bi-content"></a>現金概觀 Power BI 內容

[!include [banner](../includes/banner.md)]

本主題介紹 **現金概觀** Microsoft Power BI 內容。 它說明了如何存取內容中包含的報表，並提供有關用於構建內容的資料模型和實體的資訊。

## <a name="overview"></a>概觀

**現金概觀** Power BI 內容是為組織中負責現金的人員建立的。 **現金概觀** Power BI 內容可讓您了解您的現金流。 它還提供預測，幫助您做出更好的決策，從而改善現金流的健康狀況。 您可以按法律實體、貨幣和銀行帳戶分析現金，以更好地了解盈餘和赤字。

## <a name="setup-needed-to-view-power-bi-content"></a>查看 Power BI 內容所需的設定

必須完成以下設定，才能在 **現金概觀** 和 **銀行管理** Power BI 視覺效果中顯示資料。

1. 前往 **系統管理 > 設定 > 系統參數**，設定 **系統貨幣** 和 **系統匯率** 欄位。
2. 前往 **總帳 > 日曆 > 會計日曆** 以驗證指派給活動時間間隔的會計日曆日期。
3. 前往 **總帳 > 設定 > 分類帳**，設定 **會計貨幣** 和 **匯率類型**。
4. 定義交易貨幣與會計貨幣、會計貨幣與系統貨幣，以及會計貨幣與銀行貨幣的匯率。 若要這樣做，請前往 **總帳 > 貨幣 > 貨幣匯率**。
5. 設定和執行現金流量預測。 有關如何設定現金流量預測的更多資訊，請參閱[現金流量預測](./cash-flow-forecasting.md)。 
6. 前往 **系統管理 > 設定 > 實體店** 以重新整理 **LedgerCovLiquidityMeasurement** 彙總測量值。

## <a name="accessing-the-power-bi-content"></a>存取 Power BI 內容

來自 **現金概觀** Power BI 內容的報表會顯示在 **現金概觀** 和 **銀行管理** 工作區。

若要查看具有資料的現金流量預測報表，必須先從「現金和銀行管理」區域使用 **計算現金流預測** 功能執行預測計算流程。 需要為預測中包含的每家公司完成此作業。  然後，需要重新整理 **實體店** 頁面上的 LedgerCovLiquidityMeasurement 彙總測量值。  

出於示範目的，您可以從示範資料模組使用 **產生資料** 頁面新增現金流量預測示範資料。  該指令碼會將資料插入到現金流量預測表中，以快速填入報表所需的資訊。  僅當您在環境中部署示範資料套件模型時，此模組才可用。 

## <a name="reports-that-are-included-in-the-power-bi-content"></a>Power BI 內容中包含的報表

下表提供了有關在 **現金概觀** Power BI 內容中的每個報表頁面上找到的指標的詳細資料。

| 報告                                | 內容 |
|---------------------------------------|----------|
| 現金概觀 – 所有公司         | <ul><li>系統貨幣的流入量和流出量</li><li>預測貨幣餘額</li><li>以系統貨幣計的銀行總餘額</li><li>依法律實體分類的餘額</li><li>銀行帳戶貨幣的今日實際餘額與預測餘額比較</li></ul> |
| 現金概觀 - 目前公司       | <ul><li>會計貨幣的流入量和流出量</li><li>預測貨幣餘額</li><li>會計貨幣的銀行總餘額</li><li>銀行帳戶貨幣的今日實際餘額與預測餘額比較</li></ul> |
| 現金流量預測 - 所有公司    | <ul><li>系統貨幣的流入量和流出量</li><li>每日預測摘要</li><li>預測詳細資料</li></ul> |
| 現金流量預測 - 貨幣公司 | <ul><li>會計貨幣的流入量和流出量</li><li>每日預測摘要</li><li>預測詳細資料</li></ul> |
| 貨幣預測                     | <ul><li>預測貨幣餘額</li><li>每日貨幣摘要</li><li>預測詳細資料</li></ul> |
| 銀行餘額                         | <ul><li>以系統貨幣計的銀行總餘額</li><li>依法律實體分類的餘額</li><li>銀行帳戶貨幣的今日實際餘額與預測餘額比較</li><li>依銀行帳戶分類的餘額</li><li>原幣餘額</li></ul> |


## <a name="understanding-the-data-model-and-entities"></a>了解資料模型和實體

下表顯示了 **現金概觀** Power BI 內容所基於的實體。

| 實體                                                                          | 內容 |
|---------------------------------------------------------------------------------|----------|
| LedgerCovLiquidityMeasurement\_Company                                          | 作為篩選報表依據的公司 |
| LedgerCovLiquidityMeasurement\_Date                                             | 作為篩選報表依據的日期 |
| LedgerCovLiquidityMeasurement\_LedgerCovForecastActual                          | 實際銀行餘額與上次預測的銀行餘額 |
| LedgerCovLiquidityMeasurement\_LedgerCovLiquidity                               | 預測交易詳細資料 |
| LedgerCovLiquidityMeasurement\_LedgerCovLiquidityInflowOutflowBalanceCompany    | 使用每家公司的會計貨幣匯總現金流入量、流出量和餘額 |
| LedgerCovLiquidityMeasurement\_LedgerCovLiquidityInflowOutflowBalanceEnterprise | 使用所有公司的系統貨幣匯總現金流入量、流出量和餘額 |
| LedgerCovLiquidityMeasurement\_LedgerCovLiquidityTransactionCurrency            | 使用交易貨幣匯總淨交易金額和貨幣餘額 |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]