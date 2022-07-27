---
title: SPLITLIST ER 函數
description: 本主題提供有關如何使用 SPLITLIST 電子報表 (ER) 函數的信息。
author: NickSelin
ms.date: 03/15/2021
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
ms.openlocfilehash: ef0b548173a01cc5a15fcfb743dfb29397c1349b3c2926fa6401399459d07026
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460484"
---
# <a name="splitlist-er-function"></a>SPLITLIST ER 函數

[!include [banner](../includes/banner.md)]

`SPLITLIST` 函數將指定清單拆分為子清單 (或批次)，每個子清單包含指定數量的記錄。 然後它將結果回傳為包含批次處理的新 *記錄清單* 值。

## <a name="syntax-1"></a>語法 1

```vb
SPLITLIST (list, number)
```

## <a name="syntax-2"></a>語法 2

```vb
SPLITLIST (list, number, on-demand reading flag)
```

## <a name="arguments"></a>引數

`list`：*記錄清單*

*記錄清單* 資料類型的資料來源的有效路徑。

`number`：*整數*

每批的最大記錄數。

`on-demand reading flag`：*布林值*

指定是否應按需產生子清單元素的 *布林值*。

## <a name="return-values"></a>回傳值

*記錄清單*

產生的記錄清單。

## <a name="usage-notes"></a>使用方式說明

回傳的批次清單包含以下元素：

 - **Value：** *清單*

    屬於現行批次的記錄清單。

- **BatchNumber：** *整數*

    回傳清單中現行批次的編號。

當按需讀取標幟設定為 **True** 時，子清單是根據請求產生的，這樣可以減少記憶體消耗，但如果不按順序使用元素，可能會導致效能下降。

## <a name="example"></a>範例

在下圖中，**Lines** 資料來源建立為具有三個記錄的記錄清單。 此清單分為批次，每個批次最多包含兩條記錄。

<a href="./media/picture-splitlist-datasource.jpg"><img src="./media/picture-splitlist-datasource.jpg" alt="Data source that is divided into batches" class="alignnone wp-image-290681 size-full" width="397" height="136" /></a>

下圖顯示了設計的格式配置。 在此格式配置中，將建立與 **Lines** 資料來源的繫結以產生 XML 格式的輸出。 此輸出顯示每個批次的各個節點及其中的記錄。

<a href="./media/picture-splitlist-format.jpg"><img src="./media/picture-splitlist-format.jpg" alt="Format layout that has bindings to a data source" class="alignnone wp-image-290691 size-full" width="374" height="161" /></a>

下圖顯示了運行設計後格式時的結果。

<a href="./media/picture-splitlist-result.jpg"><img src="./media/picture-splitlist-result.jpg" alt="Result of running the format" class="alignnone wp-image-290701 size-full" width="358" height="191" /></a>

## <a name="additional-resources"></a>其他資源

[列出函數](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
