---
title: FA_BALANCE ER 函數
description: 本主題提供有關如何使用 FA_BALANCE 電子報表 (ER) 函數的信息。
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
ms.openlocfilehash: 17730b23313eaa417a824470d5b31abedb58bc7a7e8e62479358378b708b99e4
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460465"
---
# <a name="fa_balance-er-function"></a>FA_BALANCE ER 函數

[!include [banner](../includes/banner.md)]

`FA_BALANCE` 函數回傳一個 *容器 (記錄)* 值，該值由指定固定資產項目的固定資產餘額、價值模型代碼、報表年度和報表日期的資料組成。

## <a name="syntax"></a>語法

```vb
FA_BALANCE (fixed asset code, value model code, reporting year, reporting date)
```

## <a name="arguments"></a>引數

`fixed asset code`：*字串*

*字串* 值，表示為其計算餘額的固定資產項目的代碼。

`value model code`：*字串*

*字串* 值，表示為其計算餘額的值模型的代碼。

`reporting year`：*列舉值*

**AssetYear** 應用程式列舉的列舉值，用於定義餘額計算的周期。

`reporting date`：*日期*

定義餘額計算日期的 *日期* 值。

## <a name="return-values"></a>回傳值

*容器 (記錄)*

產生的記錄值。

## <a name="example"></a>範例

`FA_ BALANCE ("COMP-000001", "Current", AxEnumAssetYear.ThisYear, SESSIONTODAY ())` 回傳已為 **現行** 應用程式工作階段中的現行值模型準備的固定資產 **COMP-000001** 餘額的資料容器日期。

## <a name="additional-resources"></a>其他資源

[其他 (商業領域特定) 函數](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]