---
title: SPLITLISTBYLIMIT ER 函數
description: 本主題提供有關如何使用 SPLITLISTBYLIMIT 電子報表 (ER) 函數的信息。
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
ms.openlocfilehash: 52351c131480119ce9fb98a75307ebf6026cb12b9977e8b4236d3a24ef6a140e
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460483"
---
# <a name="splitlistbylimit-er-function"></a>SPLITLISTBYLIMIT ER 函數

[!include [banner](../includes/banner.md)]

`SPLITLISTBYLIMIT` 函數將指定清單拆分為新的子清單 (批次) 清單。 每批中的記錄數是動態計算的。 然後該函數將結果回傳為包含批次處理的新 *記錄清單* 值。

## <a name="syntax"></a>語法

```vb
SPLITLISTBYLIMIT (list, limit value, limit source)
```

## <a name="arguments"></a>引數

`list`：*記錄清單*

*記錄清單* 資料類型的資料來源的有效路徑。

`limit value`：*整數* 或 *實數*

用於將原始清單拆分為批次的限制的最大值。

`limit source`：*欄位*

指定清單中 *整數* 或 *實數* 類型欄位的有效路徑。 該欄位的值定義了總和增加的步驟。

## <a name="return-values"></a>回傳值

*記錄清單*

產生的記錄清單。

## <a name="usage-notes"></a>使用方式說明

回傳的批次清單包含以下元素：

- **Value**：*清單*

    屬於現行批次的記錄清單。

- **BatchNumber**：*整數*

    回傳清單中現行批次的編號。

如果限制來源超過定義的限制，則限制不會應用於原始清單的單個項目。

## <a name="example"></a>範例

下圖顯示了電子報表 (ER) 格式。

<a href="./media/ger-splitlistbylimit-format.png"><img src="./media/ger-splitlistbylimit-format.png" alt="Format" class="alignnone size-full wp-image-1204063" width="396" height="195" /></a>

下圖顯示了用於該格式的資料來源。

<a href="./media/ger-splitlistbylimit-datasources.png"><img src="./media/ger-splitlistbylimit-datasources.png" alt="Data sources" class="alignnone size-full wp-image-1204073" width="320" height="208" /></a>

下圖顯示了執行格式時的結果。 在這種情況下，輸出是商品項目的平面清單。

<a href="./media/ger-splitlistbylimit-output.png"><img src="./media/ger-splitlistbylimit-output.png" alt="Output" class="alignnone size-full wp-image-1204083" width="462" height="204" /></a>

在下圖中，同樣的格式進行了調整，如果單個批次必須包含商品且總重量不得超過 9 個，則以批次顯示商品項目清單。

<a href="./media/ger-splitlistbylimit-format-1.png"><img src="./media/ger-splitlistbylimit-format-1.png" alt="Adjusted format" class="alignnone size-full wp-image-1204103" width="466" height="438" /></a>

<a href="./media/ger-splitlistbylimit-datasources-1.png"><img src="./media/ger-splitlistbylimit-datasources-1.png" alt="Data sources for the adjusted format" class="alignnone size-full wp-image-1204093" width="645" height="507" /></a>

下圖顯示了執行調整後格式時的結果。

<a href="./media/ger-splitlistbylimit-output-1.png"><img src="./media/ger-splitlistbylimit-output-1.png" alt="Output of the adjusted format" class="alignnone size-full wp-image-1204113" width="676" height="611" /></a>

> [!NOTE] 
> 該限制不適用於原始清單的最後一項，因為值 (**11**) 的極限來源 (**重量**) 超過定義的限制 (**9**)。 若要在報表產生期間忽略子清單，請根據您的需要使用 `WHERE` 函數或 **啟用** 相應格式元素的運算式。

## <a name="additional-resources"></a>其他資源

[列出函數](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]