---
title: FORMATELEMENTNAME ER 函數
description: 本主題提供有關如何使用 FORMATELEMENTNAME 電子報表 (ER) 函數的信息。
author: NickSelin
ms.date: 12/05/2019
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
ms.openlocfilehash: 72977edfbe06e0d68d9226c9c25fa0633e7951d22438e053ae2a7cf4ef9a5848
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460524"
---
# <a name="formatelementname-er-function"></a>FORMATELEMENTNAME ER 函數

[!include [banner](../includes/banner.md)]

`FORMATELEMENTNAME` 函數回傳一個 *字串* 值，該值表示現行電子報表 (ER) 格式元素的名稱。

## <a name="syntax"></a>語法

```vb
FORMATELEMENTNAME ()
```

## <a name="return-values"></a>回傳值

*字串*

產生的文字值。

## <a name="usage-notes"></a>使用方式說明

可以在 ER 運算式中調用此函數，這些運算式是為位於 **Common\\File** 組件下的 **文字** 組中的 ER 格式組件的 **收集的資料鍵名稱** 和 **收集的資料鍵值** 屬性設定的，其中 **收集輸出詳情** 選項已打開。

## <a name="example"></a>範例

如需如何使用此函數的相關信息，請參閱 **獲取/開發 IT 服務/解決方案組件** 業務流程的一部分 [ER 使用格式輸出的資料進行計數和求和](tasks/er-format-counting-summing-1.md)工作指南。

## <a name="additional-resources"></a>其他資源

[資料收集函數](er-functions-category-data-collection.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]