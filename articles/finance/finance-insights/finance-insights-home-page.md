---
title: Finance Insights 首頁
description: Finance insights 提供可設定和可擴展的模型，幫助您準確、智能地預測公司的現金流量，預測您何時會收到未清應收賬款的付款，並生成可加快預算流程的預算提案。 所有這些功能都基於智能機器學習模型。
author: ShivamPandey-msft
ms.date: 01/27/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.custom:
- "14151"
- intro-internal
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-07-20
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 05b0de8b0104238a33f006234d4a0e8ba9fcdb2a
ms.sourcegitcommit: 7893ffb081c36838f110fadf29a183f9bdb72dd3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/02/2022
ms.locfileid: "8451518"
---
# <a name="finance-insights-home-page"></a>Finance Insights 首頁

[!include [banner](../includes/banner.md)]

Finance insights 提供可設定和可擴展的解決方案，幫助您智能地預測公司的現金流，預測您何時可能收到未清應收帳款的付款，並生成有助於加快預算流程的預算提案。 這些功能使用智能機器學習範本，使用您提供的資料 (包括來自第三方的資料，例如來自某局的消費者報告資訊) 建構模型。 這些智能功能為決策提供資訊，並幫助您採取行動有效應對當前和預期的業務挑戰。 您對與 Finance insights 一起使用或輸出的任何資料負責。

> [!NOTE]
> Finance insights 可在美國、加拿大、英國、歐洲、亞太地區、日本、澳大利亞和紐西蘭部署。 微軟正在逐步增加對更多地區的支持。

## <a name="prerequisites"></a>先決條件

本節列出了使用 Finance Insights 的要求。 在可能的情況下，會提供其他資訊來源的鏈接。

### <a name="system-requirements"></a>系統需求

預覽 Finance insights 需要第 2 層環境 (多框)。 有關環境的背景資訊，請參閱[環境計劃](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md)。

### <a name="version-requirements"></a>版本需求

本主題適用於 Microsoft Dynamics 365 Finance 版本 10.0.21 及更高版本。

### <a name="license-requirements"></a>授權要求

Finance insights 使用 AI Builder 信用來創建財務預測。 所有必要的授權都包含在租用戶授權中。 每個 Dynamics 365 Finance 租用戶提供 20,000 AI Builder 每個月的學分。 如果業務需要需要額外的積分，可以直接從 AI Builder。

### <a name="historical-data-requirements"></a>歷史資料要求

至少需要一年的客戶發票才能正確訓練用於客戶付款預測功能的機器學習模型。 現金流量預測建議使用三年的歷史資料。 建議智能預算提案使用三年的歷史預算和/或實際值。

## <a name="configure-finance-insights"></a>設定 Finance Insights

您必須先完成設定步驟，然後才能使用 Finance Insights。 有關如何設定財務見解的更多資訊，請參閱[Finance insights 設定](configure-for-fin-insites.md).

## <a name="create-a-data-integrator-project"></a>建立資料整合工具專案

您需要創建一個資料集成器項目，以便機器學習模型生成的資料可以流入 Dynamics 365 Finance。 有關創建該項目的步驟，請參閱[創建資料集成器項目](create-data-integrate-project.md)。

## <a name="enable-finance-insights-capabilities"></a>啟用 Finance insights 功能

完成設定步驟並設置演示資料後，您必須打開並設置您計劃使用的每個功能：客戶付款預測、現金流預測和預算建議。

### <a name="enable-customer-payment-predictions"></a>啟用客戶付款預測
如果您使用演示資料來測試客戶付款預測，您可能需要導入額外的演示資料才能成功創建您的 AI 模型。 

要啟用客戶付款預測，您必須完成一組步驟來建構機器學習模型，該模型使用您組織的資料來生成關於客戶何時可能支付未結髮票以及何時可能支付特定發票的預測。 有關詳細資訊和要完成的具體步驟，請參閱[啟用客戶付款預測 ](enable-cust-paymnt-prediction.md). 

### <a name="enable-cash-flow-forecasting"></a>啟用現金流量預測
要啟用現金流量預測，您必須完成一組步驟來建構機器學習模型，該模型使用您組織的資料來生成現金流量預測。 有關詳細資訊和要完成的具體步驟，請參閱[啟用現金流量預測](enable-cash-flow-forecasting.md)。

### <a name="enable-budget-proposals"></a>啟用預算專案

預算提案功能使用機器學習模型以及您組織的歷史資料來生成預算提案。 生成的提案可以幫助您開始一個比手動流程更有效和高效的預算流程。 有關啟用此功能的具體步驟，請參見[啟用預算提案](enable-budget-proposal.md)。 

## <a name="using-finance-insights-features"></a>使用 Finance insights 功能

### <a name="using-customer-payment-predictions"></a>使用客戶付款預測

- 要了解客戶付款預測如何提供主動開始收款活動所需的資訊，請參閱[使用客戶付款預測](use-customer-payment-predictions.md)。
- 有關可幫助您在開始使用該功能後評估預測模型有效性的資訊，請參閱[評估初始客戶付款預測模型](evaluate-payment-prediction.md)。
- 有關可幫助您調整用於建構預測的資料從而提高其有效性的資訊，請參閱[改進預測模型](improve-model.md)。
- 要了解有關 AI 預測模型結果的更多資訊，請參閱[機器學習模型的結果](confusion-matrix.md)。

### <a name="using-cash-flow-forecasts"></a>使用現金流量預測

現金流量預測功能可以幫助您更準確地估計您的現金頭寸。 智能現金流預測建立在 Dynamics 365 Finance 中現有的現金流預測功能之上。 要查看現有功能，請參閱[現金流量預測](../cash-bank-management/cash-flow-forecasting.md)。

- 要了解現金流量預測的新功能，請參閱[現金流量預測](cash-flow-forecast-intro.md)。
- 有關在此處導入外部資料以包含在您的現金流預測中的資訊，請參閱[在現金流預測中使用外部資料 ](external-data-in-cash-flow.md). 
- 有關如何使用 AI 模型來預測近期現金流的資訊，請參閱[現金頭寸](cash-position.md)。
- 有關將現金流頭寸和現金流預測保存為快照以及將快照與實際值進行比較的資訊，請參閱[快照概述 ](payment-snapshots.md)。

### <a name="using-budget-proposal"></a>使用預算專案

有關加速創建預算的資訊，請參閱[預算提案](budget-proposals.md)。 

## <a name="feedback-and-support"></a>意見反應及支援

如果您有興趣提供意見反應或需要支持，請發送電子郵件至 [Finance Insights](mailto:fiap@microsoft.com)。

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
