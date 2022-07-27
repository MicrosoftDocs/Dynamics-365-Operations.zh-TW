---
title: CONVERTCURRENCY ER 函數
description: 本主題提供有關如何使用 CONVERTCURRENCY 電子報表 (ER) 函數的信息。
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
ms.openlocfilehash: dc71ccedcdfc8a3dc9d7e087d29467bd3bbe72c3c5588872dbeaf3aa1dd35d2b
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460467"
---
# <a name="convertcurrency-er-function"></a>CONVERTCURRENCY ER 函數

[!include [banner](../includes/banner.md)]

`CONVERTCURRENCY` 函數回傳一個 *實數* 值，該值表示使用指定公司的設定在指定日期將指定貨幣金額從指定源貨幣轉換為指定目標貨幣的結果。

## <a name="syntax"></a>語法

```vb
CONVERTCURRENCY (amount, source currency, target currency, date, company)
```

## <a name="arguments"></a>引數

`amount`：*整數* 或 *實數*

表示必須轉換的金額的數值。

`source currency`：*字串*

來源貨幣目標的代碼

`target currency`：*字串*

目標貨幣的代碼

`date`：*日期*

*日期* 值，表示用於確定轉換匯率的日期。

`company`：*字串*

*字串* 值，表示提供用於轉換的設定的公司代碼。

## <a name="return-values"></a>回傳值

*真實*

產生的數值。

## <a name="example"></a>範例

`CONVERTCURRENCY (1, "EUR", "USD", TODAY(), "DEMF")` 根據 **DEMF** 公司的設定，在現行工作階段日期回傳相當於一歐元的美元金額。

## <a name="additional-resources"></a>其他資源

[其他 (商業領域特定) 函數](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]