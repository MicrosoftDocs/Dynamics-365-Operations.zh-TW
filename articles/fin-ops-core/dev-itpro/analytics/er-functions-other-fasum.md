---
title: FA_SUM ER 函數
description: 本主題提供有關如何使用 FA_SUM 電子報表 (ER) 函數的信息。
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
ms.openlocfilehash: 96b579cff1a61b8e1131317917ededb3b26963677e99da0e294501817cda26d1
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460464"
---
# <a name="fa_sum-er-function"></a>FA_SUM ER 函數

[!include [banner](../includes/banner.md)]

`FA_SUM` 函數回傳一個 *容器 (記錄)* 值，該值由指定固定資產項目的固定資產金額、價值模型代碼和日期期間的資料組成。

## <a name="syntax"></a>語法

```vb
FA_SUM (fixed asset code, value model code, start date, end date)
```

## <a name="arguments"></a>引數

`fixed asset code`：*字串*

*字串* 值，表示為其計算餘額的固定資產項目的代碼。

`value model code`：*字串*

*字串* 值，表示為其計算餘額的值模型的代碼。

`start date`：*日期*

*日期* 值，表示為其計算固定資產金額的期間的開始日期。

`end date`：*日期*

*日期* 值，表示為其計算固定資產金額的期間的結束日期。

## <a name="return-values"></a>回傳值

*容器 (記錄)*

產生的記錄值。

## <a name="example"></a>範例

`FA_SUM ("COMP-000001", "Current", Date1, Date2)` 會回傳為 **現行** 值模型準備的固定資產 **COMP-000001** 的資料容器，時間段為 **Date1** 到 **Date2**。

## <a name="additional-resources"></a>其他資源

[其他 (商業領域特定) 函數](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]