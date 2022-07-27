---
title: DATETODATETIME ER 函數
description: 本主題提供有關如何使用 DATETODATETIME 電子報表 (ER) 函數的信息。
author: NickSelin
ms.date: 12/04/2019
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
ms.openlocfilehash: 1e5fa64b776ed2702ac65a2f6416adcf657c748caa1156a71b4c3e99ee188880
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460163"
---
# <a name="datetodatetime-er-function"></a>DATETODATETIME ER 函數

[!include [banner](../includes/banner.md)]

`DATETODATETIME` 函數回傳一個 *日期時間* 值，該值從給定的日期值轉換為國際標準時間 (格林威治標準時間 \[GMT\]) 中的日期/時間值。

## <a name="syntax"></a>語法

```vb
DATETODATETIME (date)
```

## <a name="arguments"></a>引數

`date`：*日期*

表示要轉換的日期的日期值。

## <a name="return-values"></a>回傳值

*DateTime*

產生的日期/時間值。

## <a name="example-1"></a>範例 1

`DATETODATETIME (CompInfo. 'getCurrentDate()')` 將現行 Microsoft Dynamics 365 Finance 工作階段的日期 (2015 年 12 月 24 日) 回傳為 **12/24/2015 12:00:00 AM**。 在此範例中，**CompInfo** 是 **Finance and Operations/Table** 類型的電子報表 (ER) 資料來源，它參考 CompanyInfo 表。

## <a name="example-2"></a>範例 2

`DATETODATETIME (DATEVALUE ("2019-11-12T16:00:00.0000000-07:00", "O"))` 會回傳日期/時間值 **11/12/2019 12:00:00 AM**。

## <a name="additional-resources"></a>其他資源

[日期和時間函數](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]