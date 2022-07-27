---
title: NUMSEQVALUE ER 函數
description: 本主題提供有關如何使用 NUMSEQVALUE 電子報表 (ER) 函數的信息。
author: NickSelin
ms.date: 12/17/2019
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
ms.openlocfilehash: 53040d1f4b3c8089fab264a524309df909a90ed5e617bd86658704b286fabb34
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460251"
---
# <a name="numseqvalue-er-function"></a>NUMSEQVALUE ER 函數

[!include [banner](../includes/banner.md)]

`NUMSEQVALUE` 函數根據指定的數列、範圍和範圍識別碼回傳一個表示新產生的數列值的 *字串* 值。 範圍識別碼等於執行電子報表 (ER) 格式的內容提供的公司代碼。

## <a name="syntax-1"></a>語法 1

```vb
NUMSEQVALUE (number sequence code)
```

## <a name="syntax-2"></a>語法 2

```vb
NUMSEQVALUE (number sequence record ID)
```

## <a name="syntax-3"></a>語法 3

```vb
NUMSEQVALUE (number sequence code, scope type, scope ID)
```

## <a name="arguments"></a>引數

`number sequence code`：*字串*

一個文字值，表示需要新值的數字序列的代碼。

`number sequence record ID`：*Int64*

一個 *Int64* 值，表示 NumberSequenceTable 表中記錄的記錄 ID，其中包含需要新值的編號規則的定義。

`scope type`：*列舉值*

**ERExpressionNumberSequenceScopeType** 列舉的列舉值，它定義了需要新值的數字序列的範圍。 可用的範圍類型為 **共用**、**法律實體** 和 **公司**。

`scope ID`：*字串*

基於指定範圍類型標識範圍的 *字串* 值。

## <a name="return-values"></a>回傳值

*字串*

產生的文字值。

## <a name="usage-notes"></a>使用方式說明

為了 **共用** 範圍類型，指定一個空白字串作為範圍 ID。

為了 **公司** 和 **法律實體** 範圍類型，指定公司代碼作為範圍 ID。 如果將空白字串指定為這些範圍類型的範圍 ID，則使用現行公司代碼。

使用語法 1 時，為 **公司** 範圍類型請求編號規則，公司代碼由執行 ER 格式的內容提供。

## <a name="example-1"></a>範例 1

在您的 ER 格式中，您定義 *使用者輸入參數* 類型的 **AskNumSeq** 資料來源。 此資料來源是指 **描述** 擴展資料類型 (EDT)。 接下來，您定義 *導出欄位* 類型的 **NumSeq** 資料來源。 此資料來源包含運算式 `NUMSEQVALUE (AskNumSeq)`。 當調用 **NumSeq** 資料來源時，它會回傳新產生的數字序列值，該值是在執行階段透過在對話方塊中輸入其代碼來指定的。 為 **公司** 範圍類型請求編號規則。 公司代碼由執行 ER 格式的內容提供。

## <a name="example-2"></a>範例 2

在您的模型對應中定義了以下資料來源：

- *資料表* 類型的 **LedgerParms** 資料來源。 此資料來源指的是 LedgerParameters 資料表。
- *導出欄位* 類型的 **NumSeq** 資料來源。 此資料來源包含運算式 `NUMSEQVALUE ( LedgerParameters.'numRefJournalNum()'.NumberSequenceId)`。

調用 **NumSeq** 資料來源時，它會回傳新產生的編號規則值，該編號規則已在總帳參數中為提供 ER 格式執行的內容的公司設定。 這個數字序列可以唯一識別日記帳，並作為批號將交易連結在一起。

## <a name="example-3"></a>範例 3

在您的模型對應中定義了以下資料來源：

- Microsoft Dynamics 365 Finance *列舉* 類型的 **enumScope** 資料來源。 此資料來源指的是 **ERExpressionNumberSequenceScopeType** 列舉。
- *導出欄位* 類型的 **NumSeq** 資料來源。 此資料來源包含運算式 `NUMSEQVALUE ("Gene_1", enumScope.Company, "")`。

當調用 **NumSeq** 資料來源時，它回傳新產生的 **Gene\_1** 編號序列值，該編號序列已為提供 ER 格式執行的內容的公司設定。

## <a name="additional-resources"></a>其他資源

[其他 (商業領域特定) 函數](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]