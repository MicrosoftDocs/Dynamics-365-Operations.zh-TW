---
title: LISTDISTINCT ER 函數
description: 本主題提供有關如何使用 LISTDISTINCT 電子報表 (ER) 函數的信息。
author: NickSelin
ms.date: 7/30/2020
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-08-01
ms.dyn365.ops.version: AX 10.0.14
ms.openlocfilehash: 7cc51695d261a63521ae88e2a9362b6f30b9618ed89300bcaeb606b050c81350
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460348"
---
# <a name="listdistinct-er-function"></a>LISTDISTINCT ER 函數

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

`LISTDISTINCT` 函數計算指定運算式作為指定清單的每條記錄的選取器。 它回傳一個新的 *記錄清單* 值，其中包含每個唯一選取值的單個記錄。

## <a name="syntax"></a>語法

```
LISTDISTINCT (list, selector)
```

## <a name="arguments"></a>引數

`list`：*記錄清單*

*記錄清單* 資料類型的資料來源的有效路徑。

`selector`：*原始資料類型*

用於計算指定清單中每條記錄的選取器值的有效運算式。

此參數支援以下資料類型：

- 布林值
- 日期
- DateTime
- GUID
- 整數
- Int64
- 實數
- 字串

## <a name="return-values"></a>回傳值

*記錄清單*

產生的記錄清單。

## <a name="usage-notes"></a>使用方式說明

建立的清單結構與指定清單的結構相匹配。

可能會為指定清單中的多個記錄計算相同的選取器值。 在這種情況下，建立的清單中相應記錄的欄位值等於指定清單中為其計算選取器值的第一條記錄的值。

此函數的執行是在記憶體中存在的 *記錄清單* 類型的任何[電子報表 (ER)](general-electronic-reporting.md) 資料來源上完成的。

**GROUPBY** 資料來源也可用於產生具有不同值的選取器計算的記錄清單。 但是，從效能和記憶體消耗的角度來看，使用 `LISTDISTINCT` 函數比使用 **GROUPBY** 資料來源更好，因為函數的執行是在記憶體中完成的。

## <a name="example"></a>範例

以下範例顯示了如何取得在特定期間至少已向其開具一張銷售發票或專案發票的唯一客戶帳號清單。

1. 輸入 `Record list` 類型的 **SalesInvoice** 資料來源，該資料來源參考 **CustInvoiceJour** 應用程式表並過濾特定期間的銷售發票。

    此資料來源的 `InvoiceAccount` 欄位回傳已開票客戶的帳號。

2. 輸入 `Record list` 類型的 **ProjectInvoice** 資料來源，該資料來源參考 **ProjInvoiceJour** 應用程式表並過濾特定期間的專案發票。

    此資料來源的 `InvoiceAccount` 欄位回傳已開票客戶的帳號。

3. 設定包含運算式 `LISTJOIN(SalesInvoice, ProjectInvoice)` 的 `Calculated field` 類型的 **AllInvoices** 資料來源。

    此資料來源回傳銷售發票和專案發票的合併清單。

4. 設定包含運算式 `LISTDISTINCT(AllInvoices, AllInvoices.InvoiceAccount)` 的 `Record list` 類型的 **InvoicedCustomer** 資料來源。

    此資料來源回傳一個新清單，其中包含在定義期間已開票的每個唯一客戶的單個記錄。 此清單的 `InvoiceAccount` 欄位包含帳號。

## <a name="additional-resources"></a>其他資源

[列出函數](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]