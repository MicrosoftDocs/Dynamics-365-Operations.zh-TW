---
title: 需求預測概觀
description: 需求預測是愈來預測獨立的銷售訂單需求，以及任何拆解客戶訂單下的依賴性需求。 增強後的需求預測減少規則，是大量自訂的理想解決方案。
author: ChristianRytt
ms.date: 07/07/2020
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: ReqDemPlanCreateForecastDialog
audience: Application User
ms.reviewer: kamaybac
ms.custom:
- "72004"
- intro-internal
ms.assetid: 916707c9-1333-460f-a0fa-4e95f6fda2ad
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 34a8cd4b17a5a75a5e817e6a1f982d75eefbb717
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/15/2022
ms.locfileid: "8449688"
---
# <a name="demand-forecasting-overview"></a>需求預測概觀

[!include [banner](../includes/banner.md)]

需求預測是愈來預測獨立的銷售訂單需求，以及任何拆解客戶訂單下的依賴性需求。 增強後的需求預測減少規則，是大量自訂的理想解決方案。

若要產生預測的基準，需要將歷史交易摘要，傳送至 Azure 上的 Microsoft Azure Machine Learning 主機。 由於這項服務尚未於使用者之間共用，因此可以自訂滿足特定產業的要求。 您可以使用 Supply Chain Management 將預測視覺化呈現、調整預測，並查看趨勢預測準確定的關鍵績效指標 (KPI)。

> [!NOTE]
> 使用機器學習時產生預測時，需要 Microsoft Azure Machine Learning 工作室 (傳統)。 自 2021 年 12 月 1 日起，您將無法建立新的 Machine Learning 工作室 (傳統) 資源。 但是，在 2024 年 8 月 31 日之前，您可以繼續使用現有的 Machine Learning 工作室 (傳統) 資源。 如需最新資訊，請參閱 [Azure Machine Learning 工作室](/azure/machine-learning/overview-what-is-machine-learning-studio#ml-studio-classic-vs-azure-machine-learning-studio)。
> 
> Dynamics 365 Supply Chain Management 10.0.23 及更高版本，支援新的 Azure Machine Learning 工作室。

## <a name="key-features-of-demand-forecasting"></a>需求預測的主要功能

以下是需求預測的一些主要功能：

- 根據歷史資料產生統計基準線預測。
- 使用動態的預測維度。
- 將需求趨勢、信賴區間和預測調整以視覺化方式呈現。
- 授權要用於計劃流程的調整後預測。
- 刪除異常值。
- 建立預測準確性測量。

## <a name="major-themes-in-demand-forecasting"></a>需求預測中的主要主題

需求預測中實行三大主題：

- **模組化** – 將需求預測模組化以便於設定。 您可以透過變更 **交易**&gt;**庫存預測**&gt;**需求預測** 的設定金鑰，開啟或關閉此功能。
- **重複使用 Microsoft Stack** – Machine Learning 是 Microsoft Cortana Analytics Suite 的一部分，通過使用 R 演算法或 Python 語言，搭配簡單的拖放功能介面，您可以快速輕鬆建立預測分析實驗，例如：需求預估實驗。
  - 您可以下載需求預測實驗，根據個人業務需求進行變更，並發佈至 Azure Web 服務上，用於產生需求預測。 如果您已購買 Supply Chain Management 訂用帳戶，為企業級使用者生產計畫員的身分，則可以下載實驗。
  - 您可以從 [Cortana Analytics Gallery](https://gallery.cortanaanalytics.com/) 下載任何目前可用的需求預測實驗。 儘管需求預測實驗會自動與 Supply Chain Management 整合，但是客戶與合作夥伴，必須處理從 [Cortana Analytics Gallery](https://gallery.cortanaanalytics.com/) 下載的實驗。 因此，[Cortana Analytics Gallery](https://gallery.cortanaanalytics.com/) 的實驗，與財務和營運的需求預測實驗不同，不能直接使用。 您必須修改實驗代碼，才能用於財務和營運應用程式介面 (API)。
  - 您可以在 Microsoft Azure Machine Learning 工作室 (傳統) 內建立自己的實驗，將它們作為服務發佈在 Azure 上，並用於產生需求預測。
  - 如果您不要求高效能，或是不用處理大量資料，則可以使用 Machine Learning 免費層。 我們建議您每次都從這一層開始，尤其是在實作和測試階段時。 如果您需要更高的效能與額外的儲存空間，可以使用 Machine Learning 標準層。 此階層需要 Azure 訂用帳戶，並涉及額外費用。 如需 Machine Learning 定價的詳細資訊，請參閱 [Machine Learning 工作室定價](https://aka.ms/machine-learning-price-info)。
- **任何解耦點的需求預測減少** – 根據此功能為基礎建置的需求預測，可讓您在任何解耦點上，預測非獨立和獨立需求。

## <a name="basic-flow-in-demand-forecasting"></a>需求預測的基本流程

下列圖表顯示需求預測的基本流程。

[![需求預測簡介圖表。](./media/demand-forecasting-introduction.png)](./media/demand-forecasting-introduction.png)

從 Supply Chain Management 開始產生需求預測。 來自 Supply Chain Management 交易資料庫中的歷史交易資料，會集中並填入暫存資料表中。 稍後，此暫存資料表將用於 Machine Learning 服務。 透過執行最小程度的自訂，您可以將各種資料來源插入暫存資料表。 資料來源可以是 Microsoft Excel 檔案、逗號分隔值 (CSV) 檔案和 Microsoft Dynamics AX 2009 與 Microsoft Dynamics AX 2012 的資料。 因此，您可以考慮分佈在多個系統中的歷史資料，用於建立需求預測。 但是，各種資料來源中的主資料 (例如：項目名稱和測量單位) 必須相同。

如果您使用需求預測 Machine Learning 實驗，會從五種時間序列中，尋找最合適的方法計算基準線預測。 預測方法的參數，可從 Supply Chain Management 中進行管理。

然後，先前反覆運算的預測、歷史資料，以及對需求預測進行的變更，才能用於 Supply Chain Management。

您可以使用 Supply Chain Management 視覺化並修改基準線預測。 將需求預測用於規劃之前，必須先授權手動調整。

## <a name="limitations"></a>限制

需求預測是幫助製造業客戶，建立預測處理程序的工具。 提供需求預測解決方案的核心功能，專為輕鬆擴展而設計。 需求預測可能不適合商務、批發、倉儲、運輸或其他專業服務等產業的客戶。

### <a name="demand-forecast-variant-conversion-limitation"></a>需求預測變量轉換限制

如果庫存的測量單位 (UOM) 與需求預測的 UOM 不同，則產生需求預測時，無法完全支援 UOM 的變量轉換。

產生預測 (**庫存 UOM > 需求預測 UOM**) 使用產品 UOM 轉換。 當載入產生需求預測的歷史資料時，從庫存 UOM 轉換為需求預測 UOM 時，即使變量中已定義轉換，每一次都仍會使用產品的 UOM 轉換。

授權預測的第一部分 (**需求預測 UOM > 庫存 UOM**) 使用產品 UOM 轉換。 授權預測的第二部分 (**庫存 UOM > 銷售 UOM**) 使用變量 UOM 轉換。 當產生的需求預測經授權之後，從需求預測 UOM 到庫存 UOM 的之間轉換，將會使用產品等級的 UOM 轉換完成。 同時，庫存單位與銷售 UOM 之間的轉換，會遵循轉換定義的變量等級。

請注意，需求預測 UOM 不具有任何特定意義。 可以將其視為「需求預測的單位」。 針對每項產品，您可以使用庫存 UOM 將轉換定義為 1:1。

## <a name="additional-resources"></a>其他資源

[需求預測設定](demand-forecasting-setup.md)

[產生統計基準線預測](generate-statistical-baseline-forecast.md)

[對基線預測進行手動調整](manual-adjustments-baseline-forecast.md)

[授權已調整預測](authorize-adjusted-forecast.md)

[監控預測準確性](monitor-forecast-accuracy.md)

[計算需求預測時，從歷史交易資料中刪除異常值](remove-historical-outliers-calculating-demand-forecast.md)

[擴展需求預測功能](https://www.youtube.com/watch?v=4OIKIXLiNjI&feature=youtu.be)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
