---
title: ALLITEMS ER 函數
description: 本主題提供有關如何使用 ALLITEMS 電子報表 (ER) 函數的信息。
author: NickSelin
ms.date: 12/04/2019
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
ms.openlocfilehash: cf1e05e9377ba18ad0269a48b13bd242a8e5356f4a52ea3723e347dcf5e138e0
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460401"
---
# <a name="allitems-er-function"></a>ALLITEMS ER 函數

[!include [banner](../includes/banner.md)]

`ALLITEMS` 函數作為記憶體式的選取運行，並回傳一個新的扁平化 *記錄清單* 值作為記錄清單，該清單表示與指定路徑相符的所有項目。

## <a name="syntax"></a>語法

```vb
ALLITEMS (path)
```

## <a name="arguments"></a>引數

`path`：*記錄清單*

*記錄清單* 資料類型的資料來源的有效路徑。

## <a name="return-values"></a>回傳值

*記錄清單*

產生的記錄清單。

## <a name="usage-notes"></a>使用方式說明

該路徑必須定義為 *記錄清單* 資料類型的資料來源元素的有效資料來源路徑。 路徑字串和日期等資料元素應在設計階段在電子報表 (ER) 運算式建立幫手中引發錯誤。

我們不建議您將此函數用於可能包含大量資料的交易資料來源。 相反，請考慮使用[ALLTEMSQUERY](er-functions-list-allitemsquery.md)函數。

## <a name="example-1"></a>範例 1

如果您輸入 `SPLIT("abcdef" , 2)` 作為資料來源 **DS**，運算式 `COUNT( ALLITEMS (DS))` 則會回傳 **3**。

## <a name="example-2"></a>範例 2

如果您輸入 **Vend** 作為參考 VendTable 應用程式表的 *記錄清單* 資料類型的資料來源，則運算式 `ALLITEMS (Vend.'<Relations'.ContactPerson)` 將回傳具有 **ContactPerson** 表結構並包含可以透過使用存取的所有聯繫人的平展記錄清單 **ContactPerson.ContactForParty == VendTable.Party** 關係，它適用於參考的廠商表中的所有廠商。

## <a name="additional-resources"></a>其他資源

[列出函數](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]