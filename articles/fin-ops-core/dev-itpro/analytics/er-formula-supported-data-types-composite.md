---
title: 電子報表公式支援的複合資料類型
description: 本主題提供有關電子報表 (ER) 公式中支援的複合資料類型的資訊。
author: NickSelin
ms.date: 06/02/2021
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bf7178888e39a5f26ae92e77df9c996374b76bf3
ms.sourcegitcommit: d5d6b81bd8b08de20cc018c2251436065982489e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/17/2022
ms.locfileid: "8460576"
---
# <a name="supported-composite-data-types-for-electronic-reporting-formulas"></a>電子報表公式支援的複合資料類型

[!include [banner](../includes/banner.md)]

本主題提供有關[電子報表 (ER)](general-electronic-reporting.md) 運算式中支援的複合資料類型的資訊。 複合資料類型是[類別](#class)、[容器](#container)、[記錄](#record)、[記錄清單](#record-list)，和[目的](#object)。

## <a name="class"></a><a name="class"></a>類別

該 *類別* 資料類型是指公開應用程式類。 在 ER 中，它表示為 [*記錄*](#record)，其中包含參考類的每個公開方法的單獨欄位。 當該方法的調用被參數化時，您還必須在設定為調用該方法的 ER 運算式中指定適當類型的所需參數。

在 ER 對應和格式組件中，您可以新增顯示為資料來源並回傳 *類別* 類型值的 **類別** 資料來源。 此資料來源公開可在執行階段調用的類的公開方法。

> [!NOTE]
> 只有回傳值的方法才能從 ER 運算式中調用。
>
> 只能從 ER 運算式調用具有 0 到 8 個參數範圍的方法。

*類別* 的預設值為 **Null**。

下圖展示了如何新增 **類別** 類型的 **系統資訊(xInfo)** 資料來源來製作 **xInfo** 應用程式類的實體，並調用其 **productName()** 方法來接收現行應用程式的名稱。 現行應用程式的名稱是在執行階段透過執行為 ER 資料模型的 **軟體名稱(SoftwareName)** 欄位設定的 `xInfo.productName` 繫結來獲取的。 此繫結調用在現行模型對應中表示為 **系統資訊(xInfo)** 資料來源的 **xInfo** 應用程式類的 `productName()` 方法。

[![在 ER 模型對應設計工具中設定類別資料來源。](./media/er-formula-supported-data-types-composite-class1.gif)](./media/er-formula-supported-data-types-composite-class1.gif)

下圖顯示了如何設定 ER 格式以將提供的應用程式名稱放入產生的文件中。 使用的資料模型的 **軟體名稱(SoftwareName)** 欄位繫結到巢狀在 ER 格式的 **softwareUsed** XML 元素下的 **字串** 組件。 因此，現行應用程式的名稱在執行階段被放置到 **softwareUsed** XML 格式的產生文件的 XML 元素中。

[![在 ER 格式設計工具中設定電子輸出文件的結構。](./media/er-formula-supported-data-types-composite-class2.png)](./media/er-formula-supported-data-types-composite-class2.png)

## <a name="container"></a><a name="container"></a>容器

該 *容器* 資料類型保留二進位內容。 *容器* 值可用於將特定資訊從儲存傳遞到產生的文件。 在 ER 架構中，這種資料類型經常用於將媒體內容 (例如公司標誌) 放入產生的文件中。

> [!NOTE]
> 儘管每個媒體項都可以表示為一個 *容器* 值，但並非每個 *容器* 值都代表一個媒體項。 因此，如果您設定 ER 格式，使其使用 *容器* 將影像放入產生的文件中，但參考的 *容器* 不回傳媒體內容，則可能會引發類似於以下範例的異常：「執行代碼時出錯：二進位 (對象)，使用無效參數調用的方法constructFromContainer。」

*容器* 的預設值為 **Null**。

下圖展示了 *容器* 類型的 **Bitmap(Image)** 欄位如何繫結到 **銷售發票** 模型對應中 **容器** 類型的資料模型 **標誌** 欄位。 此繫結使公司標誌可用於為 **SalesInvoice** 根定義設計並在執行階段使用此模型對應的任何 ER 格式。

[![繫結 ER 模型對應設計工具的容器類型的欄位。](./media/er-formula-supported-data-types-composite-container.png)](./media/er-formula-supported-data-types-composite-container.png)

## <a name="record"></a><a name="record"></a>記錄

*記錄* 是命名欄位的集合，每個欄位都與[原始](er-formula-supported-data-types-primitive.md)資料類型或複合資料類型的值相關。 通常，一個 *記錄* 可用於表示記錄清單的單個記錄。 在這種情況下，每個項目代表單獨的欄位、方法和關係。

*記錄* 的預設值為 **空白**。

> [!NOTE]
> 當取得空白 *記錄* 的某個欄位的值時，會回傳相應資料類型的預設值。

可以使用以下函數獲取 *記錄*：

- [FIRST](er-functions-list-first.md)
- [FIRSTORNULL](er-functions-list-firstornull.md)
- [EMPTYRECORD](er-functions-record-emptyrecord.md)
- [NULLCONTAINER](er-functions-record-nullcontainer.md)

如需 *記錄* 值轉換的相關資訊，請參閱[清單類別中的 ER 函數清單](er-functions-category-list.md)。

## <a name="record-list"></a><a name="record-list"></a>記錄清單

*記錄清單* 是 *記錄* 類型的項目的清單。 通常，一個 *記錄清單* 可用於表示已從資料庫表中獲取的記錄清單。

在預設情況下，*記錄清單* 的記錄可以按照順序存取。 若要存取特定記錄，您可以使用 [INDEX](er-functions-list-index.md) 函數並指定 *整數* 索引。

*記錄清單* 的預設值為 **空白**。 您可以使用 [ISEMPTY](/er-functions-list-isempty.md) 函數來評估 *記錄清單* 是否為空白。

> [!NOTE]
> 如果 *記錄清單* 為空白，則任何嘗試獲取其中 *記錄* 的欄位值都會在執行階段引發異常。 若要了解如何幫助防止此類執行階段異常，請參閱[空白清單情況的考慮](er-components-inspections.md#i9)。

可以使用以下函數啟動 *記錄清單*：

- [ALLITEMS](er-functions-list-allitems.md)
- [ALLITEMSQUERY](er-functions-list-allitemsquery.md)
- [EMPTYLIST](er-functions-list-emptylist.md)
- [LIST](er-functions-list-list.md)
- [LISTDISTINCT](er-functions-list-listdistinct.md)

如需 *記錄清單* 值轉換的相關資訊，請參閱[清單類別中的 ER 函數清單](er-functions-category-list.md)。 若要了解如何引入 *記錄清單* 項目，填入應用程式資料，然後使用這些資料產生商業文件，請參閱[設計新的 ER 解決方案以列印自訂報表](er-quick-start1-new-solution.md)。

## <a name="object"></a><a name="object"></a>物件

*對象* 是指某 *類別* 的有狀態實體。 通常，*對象* 可在原始程式碼中啟動。 然後將其傳遞給 ER 模型對應並提供執行內容的詳情。

*對象* 的預設值為 **Null**。

下圖顯示了如何新增 *對象* 類型的 **ReportDataContract** 資料來源，以便將有關產生發票的資訊從原始程式碼傳遞到 **專案發票** 模型對應。 例如，發票實體文字作為執行內容的一部分傳遞。 此文字在執行階段透過執行為 ER 資料模型的 **備註** 欄位設定的 `ReportDataContract.parmInvoiceInstanceText` 繫結從原始程式碼中獲取。 此繫結調用在現行模型對應中表示為 **ReportDataContract** 資料來源的 **PSAProjInvoiceContract** 應用程式類的 `parmInvoiceInstanceText()` 方法。

[![在 ER 模型對應設計工具中設定對象資料來源。](./media/er-formula-supported-data-types-composite-object.gif)](./media/er-formula-supported-data-types-composite-object.gif)

若要了解如何將執行內容的詳情從原始程式碼傳遞到正在執行的 ER 解決方案，請參閱[開發應用程式工件以調用設計好的報表](er-quick-start1-new-solution.md#DevelopCustomCode)。

## <a name="additional-resources"></a>其他資源

- [電子報表概觀](general-electronic-reporting.md)
- [電子報表公式語言](er-formula-language.md)
- [支援的原始資料類型](er-formula-supported-data-types-primitive.md)
