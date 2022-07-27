---
title: ALLITEMSQUERY ER 函數
description: 本主題提供有關如何使用 ALLITEMSQUERY 電子報表 (ER) 函數的信息。
author: NickSelin
ms.date: 12/12/2019
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5db58d91e68d6ce2d1d85c330ca240c71156870bd6fb6625c033191c4c06ef8e
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460400"
---
# <a name="allitemsquery-er-function"></a>ALLITEMSQUERY ER 函數

[!include [banner](../includes/banner.md)]

`ALLITEMSQUERY` 函數作為連接的 SQL 查詢運行。 它回傳一個新的展平 *記錄清單* 值，該清單值包括表示與指定路徑相符的所有項目的記錄清單。

## <a name="syntax"></a>語法

```vb
ALLITEMSQUERY (path)
```

## <a name="arguments"></a>引數

`path`：*記錄清單*

*記錄清單* 資料類型的資料來源的有效路徑。 它必須包含至少一個關係。

## <a name="return-values"></a>回傳值

*記錄清單*

產生的記錄清單。

## <a name="usage-notes"></a>使用方式說明

指定的路徑必須定義為 *記錄清單* 資料類型的資料來源元素的有效資料來源路徑。 它必須也包含至少一個關係。 路徑 *字串* 和 *日期* 等資料元素應在設計階段在電子報表 (ER) 運算式建立幫手中引發錯誤。

當該函數應用於 *記錄清單* 資料類型的資料來源時，該資料來源參考可以透過 SQL 直接調用的應用程式對象 (例如，資料表、實體或查詢)，它作為連接的 SQL 查詢運行。 否則，它將作為 [ALLITEMS](er-functions-list-allitems.md) 函數在記憶體中運行。

## <a name="example"></a>範例

您在模型對應中定義以下資料來源：

- 參考 CustInvoiceTable 表的 *資料表記錄* 類型的 **CustInv** 資料來源
- 包含運算式 `FILTER (CustInv, CustInv.InvoiceAccount = "US-001")` 的 *導出欄位* 類型的 **FilteredInv** 資料來源
- 包含運算式 `ALLITEMSQUERY ( FilteredInv.'<Relations'.CustInvoiceJour.'<Relations'.CustInvoiceTrans)` 的 *導出欄位* 類型的 **JourLines**

當您運行模型對應以調用 **JourLines** 資料來源時，將運行以下 SQL 陳述式：

```sql
SELECT ... FROM CUSTINVOICETABLE T1 CROSS JOIN CUSTINVOICEJOUR T2 CROSS JOIN
CUSTINVOICETRANS T3 WHERE...
```

## <a name="additional-resources"></a>其他資源

[列出函數](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]