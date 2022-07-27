---
title: 設定查詢資料來源以使用該 ER 應用程式特定參數
description: 本主題說明如何設定電子報表 (ER) 格式的查詢資料來源以使用 ER 應用程式特定參數。
author: NickSelin
ms.date: 08/11/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, EROperationDesigner, ERLookupDesigner, ERComponentLookupStructureEditing
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-01-01
ms.dyn365.ops.version: Release 8.1.3
ms.openlocfilehash: c028b01aa2889a517bee69de46411ada12d6fe25
ms.sourcegitcommit: b9c2798aa994e1526d1c50726f807e6335885e1a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/13/2021
ms.locfileid: "8460572"
---
# <a name="configure-lookup-data-sources-to-use-er-application-specific-parameters"></a>設定查詢資料來源以使用該 ER 應用程式特定參數 

[!include[banner](../includes/banner.md)]

[電子報表 (ER)](general-electronic-reporting.md) 應用程式特定參數函數允許您以 ER 格式設定資料過濾，以便它根據一組抽象規則。 這組規則可以設定為使用以 ER 格式提供的 **查詢** 類型的資料來源。 然後，您可以使用根據相應 ER 格式的 **查詢** 資料來源的設定和現行法律實體資料自動產生的使用者介面 (UI) 來指定超出 ER 組件設計者的真實規則。 最終，當執行此 ER 格式時，指定的規則將被 ER 格式的 **查詢** 資料來源存取。

> [!NOTE]
> 使用可編輯 ER 格式的已設定資料來源來指定使用哪些應用程式資料來設定真實規則。

使用 [ER 作業設計工具](general-electronic-reporting.md#building-a-format-that-uses-a-data-model-as-a-base)將 **查詢** 類型的資料來源引入您的 ER 格式。 資料來源必須設定為描述抽象規則的外觀，包括以下內容：

   - 某些資料類型的參數集，其值被提供以指定單個規則。
   - 當該規則被認為是最合適的規則時，由單個規則回傳的特定資料類型的值類型。

您可以根據任何設定的規則回傳的值類型設定以下類型的 **查詢** 資料來源：

   - 當必須回傳模型列舉值時，使用 **資料模型\查詢** 類型。
   - 當必須回傳應用程式列舉值或應用程式 [擴展資料類型](../extensibility/extensible-edts.md)值時，使用 **Dynamics 365 Operations\查詢** 類型。
   - 當必須回傳格式列舉值時，使用 **格式列舉\查詢** 類型。

下圖顯示了如何在樣本 ER 格式中設定格式列舉。

   ![顯示格式列舉作為已設定查詢資料來源的基礎。](./media/er-lookup-data-sources-img1.gif)

下圖顯示了設定為在產生的報表的不同區段中報表不同類型的稅款的格式組件。

   ![顯示格式區段以分別報表不同類型的稅款。](./media/er-lookup-data-sources-img2.png)

下圖顯示了 ER 作業設計工具如何允許新增 **格式列舉\查詢** 類型的資料來源。  新增的資料來源設定為回傳 `List of taxation levels` 格式列舉的值。

   ![新增格式列舉\查詢類型的 ER 資料來源。](./media/er-lookup-data-sources-img3.gif)

下圖顯示了如何將新增的資料來源設定為使用 **模型** 資料來源的 **Model.Data.Tax** 記錄清單的 **代碼** 欄位作為必須為每個設定的規則指定的參數。

![設定格式列舉\查詢類型的新增資料來源的參數。](./media/er-lookup-data-sources-img4.gif)

新增的 `Model.Data.Tax` 資料來源被設定為透過存取 **TaxTable** 申請表的記錄為每個設定的規則指定一個稅碼。

   ![審查格式列舉\查詢類型的單公司查詢資料來源。](./media/er-lookup-data-sources-img5.gif)

您可以使用自動與已設定資料來源的結構對齊的 UI 安裝所選 ER 格式的查詢規則。 目前，此 UI 要求您將每個規則的回傳值指定為 `List of taxation levels` 格式列舉值以及稅碼作為參數。

   ![為設定的資料來源安裝該規則。](./media/er-lookup-data-sources-img6.gif)

下圖顯示了如何將 **匯出欄位** 類型的 `Model.Data.Summary.LevelByLookup` 資料來源設定為調用已設定的 **查詢** 資料來源並提供所需的參數。 若要在執行階段處理這個調用，ER 會按照定義的順序遍歷設定的規則清單，以找到滿足所提供條件的第一個規則。 在此範例中，它是包含與提供的稅碼相相符的稅碼的規則。 結果，找到了最合適的規則，並且為找到的規則設定的列舉值由此資料來源回傳。

> [!NOTE]
> 未找到適用規則時將引發異常。 若要防止出現這些異常，請在規則清單的末尾設定其他規則，以處理未提供值或未提供值的情況。 相應地使用 **\*非空白**\*和 **\*空白**\*選項。  
>
> ![新增資料來源以調用設定的查詢資料來源。](./media/er-lookup-data-sources-img7.png)

當您將可編輯查詢資料來源的 **跨公司** 選項設定為 **是** 時，您將新的必需 **公司** 參數新增到此資料來源的參數集中。 調用查詢資料來源時，必須在執行階段指定 **公司** 參數的值。 執行階段指定公司代碼時，使用為該公司設定的規則尋找最合適的規則，並回傳對應的值。 下圖顯示了如何執行此操作以及如何更改可編輯資料來源的參數集。

   ![查看格式列舉\查詢類型的跨公司查詢資料來源。](./media/er-lookup-data-sources-img8.gif)

> [!NOTE]
> 分別選取每個公司以設定此可編輯 ER 格式的查詢資料來源的規則集。 當使用未完成查詢設定的公司代碼調用跨公司查詢時，在執行階段會引發異常。
>
> 確保您授予使用跨公司 **查詢** 資料來源執行 ER 格式的使用者存取此資料來源範圍內每個公司的資料的權限。 否則，執行階段會引發異常。

從 10.0.19 版開始，可以使用 **查詢** 資料來源的擴充函數。 當您將可編輯查詢資料來源的 **擴充** 選項設定為 **是** 時，設定的查詢資料來源將轉換為結構化資料來源，該資料來源提供額外的函數來分析設定的規則集。 下圖顯示了這種轉換。

   ![查看格式列舉\查詢類型的結構化查詢資料來源。](./media/er-lookup-data-sources-img9.gif)

- 將 **查詢** 子項目設計為一個函數，用於根據提供的參數集從可設定的規則集中找到最合適的規則。
- 將 **IsLookupResultSet** 子項目設計為一個函數，用於接受基本列舉資料來源的提供值，並在規則集包含至少一個提供的列舉值設定為的規則時回傳 **True** 的 *布林值* 回傳值。 當沒有規則設定為回傳提供的列舉值時，此函數回傳 **False** *布林值*。
- 將 **設定** 子項目設計成一個函數，它把設定的規則集合作為記錄清單的記錄回傳。 已設定規則的回傳值和參數集在每個回傳記錄中顯示為相關資料類型的欄位：

    - 回傳值顯示為 **查詢結果** 欄位。
    - 設定的參數顯示為具有參數名稱的欄位 (本範例中的 **代碼** 欄位)。

如需如何設定 **查詢** 資料來源的相關資訊，請參閱[設定 ER 格式以使用為每個法律實體指定的參數](er-app-specific-parameters-configure-format.md)。 若要進一步了解如何設定查詢規則，請參閱[為每個法律實體設定 ER 格式的參數](er-app-specific-parameters-set-up.md)。

## <a name="additional-resources"></a>其他資源

[設定 ER 格式以使用每個法律實體指定的參數](er-app-specific-parameters-configure-format.md)

[為每個法律實體設定 ER 格式的參數](er-app-specific-parameters-set-up.md)
