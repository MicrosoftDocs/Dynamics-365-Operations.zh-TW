---
title: FORMAT ER 函數
description: 本主題提供有關如何使用 FORMAT 電子報表 (ER) 函數的信息。
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
ms.openlocfilehash: 9dbde3ebfd2670639a2fff19d83ea9bd8d15c22b09b43ab49ae1b9e35562625a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460444"
---
# <a name="format-er-function"></a>FORMAT ER 函數

[!include [banner](../includes/banner.md)]

`FORMAT` 函數將指定的字串作為 *字串* 值回傳，透過用第 *N* 個引數替換任何出現的 **%N** 來格式化它。

## <a name="syntax"></a>語法

```vb
FORMAT (string, argument 1[, argument 2, …, argument N])
```

## <a name="arguments"></a>引數

`string`：*字串*

對必須格式化的 *字串* 類型的資料來源的參考。 此為必填引數。

`argument 1`：*字串*

第一個引數，用於替換 **%1** 的出現。 此為必填引數。

`argument N`：*字串*

第 *N* 個參數，用於替換 **%2**、**%3** 等的出現。 這些附加引數是可選的。

## <a name="return-values"></a>回傳值

*字串*

產生的文字值。

## <a name="usage-notes"></a>使用方式說明

如果未為參數提供引數，則參數在字串中回傳為 **「%N」**。 對於 *實數* 類型的值，預設字串轉換限制為兩位小數。

## <a name="example"></a>範例

在下圖中，**PaymentModel** 資料來源使用 **客戶** 組件回傳客戶記錄清單。 它使用 **ProcessingDate** 欄位回傳處理日期值。

<a href="./media/picture-format-datasource.jpg"><img src="./media/picture-format-datasource.jpg" alt="PaymentModel data source" class="alignnone wp-image-290751 size-full" width="293" height="143" /></a>

在旨在為選定客戶產生電子檔案的電子報表 (ER) 格式中，**PaymentModel** 被選為資料來源，它控制處理流程。 如果在處理報表的日期停止了選定的客戶，則會引發異常以通知使用者。 為此類處理控制設計的公式可以使用以下資源：

- 標籤 SYS70894，其中包含以下文字：

    - **對於 EN-US 語言：**「Nothing to print」
    - **對於 DE 語言：**「Nichts zu drucken」

- 標籤 SYS18389，其中包含以下文字：

    - **對於 EN-US 語言：**「Customer %1 is stopped for %2。」
    - **對於 DE 語言：**「Debitor '%1' wird für %2 gesperrt。」

這是可以設計的運算式。

```vb
FORMAT (CONCATENATE (@"SYS70894", ". ", @"SYS18389"), model.Customer.Name, DATETIMEFORMAT (model.ProcessingDate, "d"))
```

如果在 2015 年 12 月 17 日以 **EN-US** 文化和 **EN-US** 語言為 **Litware Retail** 客戶處理報表，則此公式將回傳以下文字，該文字可以作為異常訊息呈現給使用者：

*無法列印。客戶 Litware Retail 於 2015 年 12 月 17 日停止服務。*

如果在 2015 年 12 月 17 日以 **DE** 文化和 **DE** 語言為 **Litware Retail** 客戶處理相同的報表，則公式將回傳以下文字，該文字使用不同的日期格式：

*Nichts zu drucken. Debitor 'Litware Retail' wird für 17.12.2015 gesperrt.*

>[!NOTE]
> 以下語法適用於標籤的 ER 公式：
>
> - **對於 Microsoft Dynamics 365 Finance 應用中資源的標籤：** **\@X**，其中 **X** 是應用程式物件樹狀結構 (AOT) 中的標籤識別碼
> - **對於駐留在 ER 設定中的標籤：****@"GER_LABEL:X"**，其中 **X** 是 ER 設定中的標籤識別碼

## <a name="additional-resources"></a>其他資源

[文字函數](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]