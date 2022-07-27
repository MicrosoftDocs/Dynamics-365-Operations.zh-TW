---
title: 比較品項價格儲存報告
description: 了解如何生成比較品項價格儲存報告，然後瀏覽和/或匯出結果。
author: AndersGirke
ms.date: 01/30/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CostAdminWorkspace, CostAnalysisWorkspace, InventItemPriceCompareStorage, InventItemPriceCompareStorageDetailsChart, InventItemPriceCompareStorageDetails
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2020-03-01
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: 76a4ba07d191f79b4033fc78acff62d4909c7d32
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8447876"
---
# <a name="compare-item-prices-storage-report"></a>比較品項價格儲存報告

[!include [banner](../includes/banner.md)]

本主題說明如何執行 **比較物品價格儲存** 報告並以數位方式提供輸出，作為 Dynamics 365 Supply Chain Management 的互動式頁面，或從多種格式中選擇匯出文件。

當您在瀏覽器中查看報告時，欄和總餘額會根據您設定的配置進行動態調整。 您可以對結果進行排序、篩選、向下切入資料等。

報告結果儲存在 **比較品項價格** 資料實體，可讓您篩選並匯出為 CSV 或 Microsoft Excel。

**比較品項價格儲存** 報告在輸出包含多明細的情況下很有幫助。 例如，如果在成本核算版本中您有超過 40,000 個品項具有待定品項價格，則輸出將包含許多明細。

## <a name="enable-compare-item-prices-storage"></a>啟用比較品項價格儲存

使用該功能之前，必須先在系統中啟用。 系統管理員可以使用[功能管理](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)設定檢查功能狀態，並在需要時予以啟用或停用。 在這裡，該功能被列為：

- **模組**- 成本管理
- **功能名稱**- 比較品項價格儲存

## <a name="generate-a-compare-item-prices-storage-report"></a>生成比較品項價格儲存報告

按照以下步驟生成和儲存 **比較品項價格儲存** 報告：

1. 請前往 **成本管理 > 查詢和報告 > 預定成本報告 > 比較品項價格儲存**。

1. 選取 **新增** 打開 **比較品項價格** 窗格。 設定以下選項以定義要在報告中比較的價格：

    - 在 **參數** FastTab，給報告唯一的 **名稱** 並使用 **要比較的待訂價格** 和 **要比較的價格** 區段中的欄位來定義要比較的價格和日期。
    - 在 **要包括的記錄** FastTab 上，您可以設置篩選和限制式來定義報告要包含哪些日期。
    - 在 **背景執行** FastTab，設定生成報告的方式、時間和頻率。
    > [!NOTE]
    > 此報告始終作為批次作業的一部分執行。

1. 選取 **確定** 套用您的設定並關閉查詢窗格。

1. 批次作業完成後，將列在 **比較品項價格儲存** 頁面。 可能需要重新整理頁面才能查看報告。

## <a name="explore-the-compare-item-prices-storage-report"></a>探索比較品項價格儲存報告

生成報告後，您可以隨時查看和探索報告，如下所示：

1. 請前往 **成本管理 > 查詢和報告 > 預定成本報告 > 比較品項價格儲存**。

1. 從清單中選取一個報告。

1. 執行以下動作之一：

    - 選取 **摘要** 以概覽您的報告結果。
    - 選取 **查看詳情** 更詳細地查看您的報告

1. 選定檢視表打開後，您可以執行以下操作：

    - 幾乎任何欄標題都能選取，選取後可按該欄中的值對資料表進行排序或篩選，就像 Supply Chain Management 中的大多數的標準表格一樣。 請注意，您不能排序或篩選 **淨變動價格 %** 欄，因為它是一個導出欄位。
    - 選取 **維度顯示** 打開一個窗格，您可以在其中選擇要在表單中包含的維度欄。 如果您想保存這些設定，設定 **保存設定** 為 **是的**，在您下次打開報告前保留它們。 選取 **確定** 套用您的設定並關閉。
    - 選取表單中的任意列，然後選取 **查看詳情** 查看有關選定品項的更多資訊。 您將能夠從這裡向下切入數資料。
    - 選擇表單中的任意列，然後選取 **查看對比圖表** 查看選定項品項相關結果的互動式圖形呈現。 您可以在圖表和圖表圖例中選取各種圖形元素來探索這些結果。
    - 選取表單中的任意列，然後選取 **查看計算詳情** 查看與選定品項相關的計算的更多資訊。 您將能夠從這裡向下切入數資料。

## <a name="export-the-compare-item-prices-storage-report"></a>匯出比較品項價格儲存報告

您生成的每個報告都儲存在 **比較商品價格** 資料實體。 您可以使用 Supply Chain Management 的標準資料管理功能將此實體中的數據匯出為任何受支持的資料格式，包括 CSV 及 Microsoft Excel。

以下是匯出 **比較品項價格儲存** 報告的範例：

1. 請前往 **系統管理 > 工作區 > 資料管理**。

1. **資料管理** 區段，選取 **匯出** 按鈕。

1. **匯出** 頁面打開，即可用來設定匯出作業。 首先給你的作業一個 **群組名稱**。

1. 在 **選定實體** 區段，選取 **新增實體** 打開一個對話方塊，您可以在其中設定以下選項：

    - **實體名稱**- 選取 **比較品項價格**。
    - **目標資料格式**- 選擇匯出格式。

1. 選取 **新增** 新增新列，然後選取 **關閉** 關閉對話方塊。

1. 通常您一次會匯出一份報告。 為此，請為您剛剛新增到 **詢問** 窗格的列，設定一個 **篩選**。 這將讓您定義來自 **比較品項價格** 實體要包含在匯出中的報告。 設訂以下篩選選項以匯出單個報告：

    - 在 **範圍** 索引標籤，選取 **新增** 新增新列。
    - 設定 **資料表** 為 **比較品項價格**。
    - 設定 **衍生資料表** 為 **比較品項價格**。
    - 設定 **欄位** 為您想作為篩選依據的欄位。 通常你會使用 **執行名稱** 或 **執行時間**。
    - 設定 **準則** 為選定欄位中您要查找的值 (報告的名稱或報告的生成時間)。
    - 如有必要，將更多列新增到 **範圍** 資料表，直到您唯一識別出了您要查找的報告。

1. 選取 **確定** 儲存您的設定並關閉。

1. 選取 **儲存** 以儲存您的匯出設定。

1. 打開 **匯出選項** 索引標籤並選取 **立即匯出** 生成匯出文件。

1. **執行摘要** 頁面打開，您可以在其中查看匯出作業的狀態和已匯出的實體清單。 在 **實體處理狀態** 區域，選取列出的 **比較品項價格** 中實體，然後選取 **下載文件**，以下載從該實體匯出的資料。

有關如何使用資料管理匯出資料的更多資訊，請參閱[資料匯入和匯出工作概觀](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md)。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]