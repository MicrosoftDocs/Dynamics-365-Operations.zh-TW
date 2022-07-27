---
title: FILTER ER 函數
description: 本主題提供有關如何使用 FILTER 電子報表 (ER) 函數的信息。
author: NickSelin
ms.date: 12/14/2021
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
ms.openlocfilehash: e857306574dda7bad5dd25fc7708514997d8e86f
ms.sourcegitcommit: b1c758ec4abfcf3bf9e50f18c1102d4a9c1316d0
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/15/2021
ms.locfileid: "8460353"
---
# <a name="filter-er-function"></a>FILTER ER 函數

[!include [banner](../includes/banner.md)]

`FILTER` 函數在查詢經更改後，會將指定的清單作為 *記錄清單* 值回傳，以便過濾指定的條件。

## <a name="syntax"></a>語法

```vb
FILTER (list, condition)
```

## <a name="arguments"></a>引數

`list`：*記錄清單*

*記錄清單* 資料類型的資料來源的有效路徑。

`condition`：*布林值*

一個有效的條件運算式，用於過濾指定清單的記錄。

## <a name="return-values"></a>回傳值

*記錄清單*

產生的記錄清單。

## <a name="usage-notes"></a><a name="usage-notes"></a>使用方式說明

此函數不同於 [WHERE](er-functions-list-where.md) 函數，因為指定的條件適用於資料庫級別的 *資料表記錄* 類型的任何電子報表 (ER) 資料來源。 可以使用資料表和關係來定義清單和條件。

如果為此函數設定的一個或兩個參數 (`list` 和 `condition`) 不允許將此請求轉換為直接 SQL 調用，在設計階段會引發異常。 此異常通知使用者不能使用 `list` 或 `condition` 來查詢資料庫。

> [!NOTE]
> 當 [`VALUEIN`](er-functions-logical-valuein.md) 函數用於指定選取標準時，`FILTER` 函數的行為與 `WHERE` 函數不同。
> 
> - 如果在 `WHERE` 函數範圍內使用 `VALUEIN` 函數，並且 `VALUEIN` 的第二個引數指的是不回傳任何記錄的資料來源，則考慮 `VALUEIN` 回傳的布林值 *[False](er-formula-supported-data-types-primitive.md#boolean)*。 因此，如果 **VendGroups** 資料來源沒有回傳廠商組記錄，則運算式 `WHERE(Vendors, VALUEIN(Vendors.VendGroup, VendGroups, VendGroups.VendGroup))` 不會回傳任何廠商記錄。
> - 如果在 `FILTER` 函數範圍內使用 `VALUEIN` 函數，並且 `VALUEIN` 的第二個引數指的是不回傳任何記錄的資料來源，則忽略 `VALUEIN` 回傳的布林值 *[False](er-formula-supported-data-types-primitive.md#boolean)*。 因此，運算式 `FILTER(Vendors, VALUEIN(Vendors.VendGroup, VendGroups, VendGroups.VendGroup))` 回傳 **廠商** 資料來源的所有廠商記錄，即使 **VendGroups** 資料來源沒有回傳廠商組記錄。

## <a name="example-1"></a>範例 1

如果 **廠商** 設定為參考 VendTable 表的 ER 資料來源，則運算式 `FILTER (Vendors, Vendors.VendGroup = "40")` 回傳僅屬於廠商組 40 的廠商的清單。

## <a name="example-2"></a>範例 2

如果 **廠商** 被設定為一個參考 VendTable 表的 ER 資料來源，如果 **parmVendorBankGroup** 被設定為一個回傳 *字串* 資料類型值的 ER 資料來源，運算式 `FILTER ( Vendor.'<Relations'.VendBankAccount, Vendor.'<Relations'.VendBankAccount.BankGroupID = parmVendorBankGroup)` 回傳一個隻屬於特定銀行組的廠商帳戶清單。

## <a name="example-3"></a>範例 3

您輸入 *匯出欄位* 類型的資料來源 **DS**，它包含運算式 `SPLIT ("A,B,C", ",")`。 然後您輸入另一個運算式，`FILTER( DS, DS.Value = "B")`。 當您嘗試在 ER 公式設計工具中儲存此運算式時，會引發以下異常：「驗證錯誤：FILTER 函數的清單運算式不可查詢。」

## <a name="additional-resources"></a>其他資源

[列出函數](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
