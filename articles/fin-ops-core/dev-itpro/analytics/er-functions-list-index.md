---
title: INDEX ER 函數
description: 本主題提供有關如何使用 INDEX 電子報表 (ER) 函數的信息。
author: NickSelin
ms.date: 05/20/2021
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
ms.openlocfilehash: e68f1690d6f852b0db560ef67a36fbde9e099715942a4b8a6e486d759af46682
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460351"
---
# <a name="index-er-function"></a>INDEX ER 函數

[!include [banner](../includes/banner.md)]

`INDEX` 函數回傳一個 *容器 (記錄)* 值，該值是透過使用指定清單中的指定數字索引選取的。 如果索引超出指定清單中記錄的範圍，則會引發異常。

## <a name="syntax"></a>語法

```vb
INDEX (list, index)
```

## <a name="arguments"></a>引數

`list`：*記錄清單*

*記錄清單* 資料類型的資料來源的有效路徑。

`index`：*整數*

一個數字索引，指示所需記錄在指定清單中的位置。

> [!NOTE]
> 由於此函數使用從一開始的編號，因此指定值 **1** 以回傳指定清單的第一條記錄。

## <a name="return-values"></a>回傳值

*容器 (記錄)*

產生的記錄值。

## <a name="example-1"></a>範例 1

如果您輸入 *導出欄位* 類型的資料來源 **DS**，並且它包含運算式 `SPLIT ("A|B|C", "|")`，則運算式 `DS.Value` 回傳文字值 **「B」** 此記錄清單的第二條記錄。 運算式 `INDEX (SPLIT ("A|B|C", "|"), 2).Value` 還會回傳文字值 **「B」**。

## <a name="example-2"></a>範例 2

如果輸入 *匯出欄位* 類型的資料來源 **DS**，它包含運算式 `SPLIT ("A|B|C", "|")`，運算式 `INDEX (SPLIT ("A|B|C", "|"), 4).Value` 在執行階段引發異常。

## <a name="additional-resources"></a>其他資源

[列出函數](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
