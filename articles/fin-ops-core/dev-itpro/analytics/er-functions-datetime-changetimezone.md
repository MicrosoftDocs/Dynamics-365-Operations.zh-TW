---
title: CHANGETIMEZONE ER 函數
description: 本主題提供有關如何使用 CHANGETIMEZONE 電子報表 (ER) 函數的資訊。
author: NickSelin
ms.date: 09/09/2021
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: AX 10.0.23
ms.openlocfilehash: 48e96cfbc19503daf6a20363c4520c765f11a249
ms.sourcegitcommit: 9e8d7536de7e1f01a3a707589f5cd8ca478d657b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2021
ms.locfileid: "8460585"
---
# <a name="changetimezone-er-function"></a>CHANGETIMEZONE ER 函數

[!include [banner](../includes/banner.md)]

該 `CHANGETIMEZONE` 函數回傳國際標准時間 (格林威治標準時間 \[GMT\]) 中的 *[日期時間](er-formula-supported-data-types-primitive.md#datetime)* 值，該值從一個時區中的給定日期/時間值轉換為另一個時區中的日期/時間值。

## <a name="syntax"></a>語法

```vb
CHANGETIMEZONE (datetime, base time zone, target time zone)
```

## <a name="arguments"></a>引數

`datetime`：*日期時間*

國際標準時間時區中的日期/時間值，表示要轉換的日期/時間值。

`base time zone`*[字串](er-formula-supported-data-types-primitive.md#string)*

給定日期/時間值在轉換之前轉換到的時區名稱。

`target time zone`：*字串*

在轉換過程中轉換的日期/時間值轉移到的時區名稱。

## <a name="return-values"></a>回傳值

*DateTime*

以國際標準時間時區產生的日期/時間值。

## <a name="usage-notes"></a>使用方式說明

若要指定來源時區和目標時區，您可以使用[網際網路號碼指派局 (IANA)](https://www.iana.org/) [提供](https://data.iana.org/time-zones/releases/)的或 Microsoft Windows [支援](/windows-hardware/manufacture/desktop/default-time-zones)的時區名稱。

在執行階段，如果在 IANA 清單或 Windows 註冊表中找不到提供的名稱，則會引發異常「時區『\<time zone name\>』不存在」。

對於遵守夏令時間的時區，轉換會考慮國際標準時間夏令時間的偏移。 在轉換期間使用有關此偏移的最新可用資訊。

## <a name="example-1"></a>範例 1

在此範例中，使用了 Windows 的時區名稱。

您設定 **匯出欄位** 類型的 **DSX** 資料來源。 它包含以下運算式：

```vb
CONCATENATE(
    DATETIMEFORMAT( DSY, "O"), 
    " -> ", 
    DATETIMEFORMAT( CHANGETIMEZONE(DSY, "E. Europe Standard Time", "Hawaiian Standard Time"), "O")
)
```

如果將 **匯出欄位** 類型的 **DSY** 資料來源的運算式設定為 `DATETIMEVALUE ("01-Jun-2021 12:55:00", "dd-MMM-yyyy HH:mm:ss", "EN")`，則 **DSX** 資料來源回傳文字 **2021-06-01T12:55:00.0000000+00:00 -> 2021-05-31T23:55:00.0000000+00:00**。 這段文字顯示，提供的兩個時區在 6 月 1 日的時差超過 24 小時。 因此，轉換後的日期/時間值比給定的日期/時間值早一天，因為基準時區早於目標時區。

如果將 **匯出欄位** 類型的 **DSY** 資料來源的運算式設定為 `DATETIMEVALUE ("01-Dec-2021 12:55:00", "dd-MMM-yyyy HH:mm:ss", "EN")`，則 **DSX** 資料來源回傳文字 **2021-12-01T12:55:00.0000000+00:00 -> 2021-12-01T00:55:00.0000000+00:00**。 此文字顯示，12 月 1 日提供的兩個時區之間的時差小於 24 小時。 因此，轉換後的日期/時間值等於給定的日期/時間值。

> [!NOTE]
> 相同的運算式回傳相同時區對的提供的和轉換的日期/時間值之間的不同差異，因為在給定的日期/時間為提供的時區觀察到不同的國際標準時間夏令時間偏移。

## <a name="example-2"></a>範例 2

在此範例中，使用了 IANA 時區名稱。

您設定 **匯出欄位** 類型的 **DSX** 資料來源。 它包含以下運算式：

```vb
CONCATENATE(
    DATETIMEFORMAT( DSY, "O"), 
    " -> ", 
    DATETIMEFORMAT( CHANGETIMEZONE(DSY, "Europe/Athens", "US/Hawaii"), "O")
)
```

如果將 **匯出欄位** 類型的 **DSY** 資料來源的運算式設定為 `DATETIMEVALUE ("01-Jun-2021 12:55:00", "dd-MMM-yyyy HH:mm:ss", "EN")`，則 **DSX** 資料來源回傳文字 **2021-06-01T12:55:00.0000000+00:00 -> 2021-05-31T23:55:00.0000000+00:00**。 這段文字顯示，提供的兩個時區在 6 月 1 日的時差超過 24 小時。 因此，轉換後的日期/時間值比給定的日期/時間值早一天，因為基準時區早於目標時區。

如果將 **匯出欄位** 類型的 **DSY** 資料來源的運算式設定為 `DATETIMEVALUE ("01-Dec-2021 12:55:00", "dd-MMM-yyyy HH:mm:ss", "EN")`，則 **DSX** 資料來源回傳文字 **2021-12-01T12:55:00.0000000+00:00 -> 2021-12-01T00:55:00.0000000+00:00**。 此文字顯示，12 月 1 日提供的兩個時區之間的時差小於 24 小時。 因此，轉換後的日期/時間值等於給定的日期/時間值。

## <a name="example-3"></a>範例 3

您設定 **匯出欄位** 類型的 **DSX** 資料來源。 它包含以下運算式：

```vb
CONCATENATE(
    DATETIMEFORMAT( DSY, "O"), 
    " -> ", 
    DATETIMEFORMAT( CHANGETIMEZONE(DSY, "US/Hawaii", "Europe/Athens"), "O")
)
```

如果將 **匯出欄位** 類型的 **DSY** 資料來源的運算式設定為 `DATETIMEVALUE ("01-Jun-2021 12:55:00", "dd-MMM-yyyy HH:mm:ss", "EN")`，則 **DSX** 資料來源回傳文字 **2021-06-01T12:55:00.0000000+00:00 -> 2021-06-02T01:55:00.0000000+00:00**。 這段文字顯示，提供的兩個時區在 6 月 1 日的時差超過 24 小時。 因此，轉換後的日期/時間值比給定的日期/時間值晚一天，因為目標時區早於基準時區。

## <a name="example-4"></a>範例 4

您可能會收到來自外部來源的日期/時間戳作為不包含時區資訊的文字。 但是，您可能知道來源操作所在的時區。 例如，您從在西班牙營運的服務收到日期/時間戳記 **01/12/2021 12:55:00**。 若要將此日期/時間值正確儲存到資料庫，請完成以下轉換：

- 設定 **匯出欄位** 類型的 **DSY** 資料來源以將日期/時間戳從文字轉換為國際標準時間日期/時間值。

    `DATETIMEVALUE ("01/12/2021 12:55:00", "dd/MM/yyyy HH:mm:ss", "ES")`

- 設定 **匯出欄位** 類型的 **DSX** 資料來源，將轉換後的日期/時間值轉換為國際標準時間，作為外部來源時區的日期/時間值。

    `CHANGETIMEZONE(DSY, "Romance Standard Time", "GMT Standard Time")`

> [!NOTE]
> 當您使用 `CHANGETIMEZONE` 函數進行日期/時間轉換時，請注意任何日期/時間值都儲存在資料庫中作為國際標準時間時區中的值。 它在此值可以顯示在應用程式頁面上之前已被轉換。 轉換會考慮[設定](../../fin-ops/organization-administration/tasks/set-users-preferred-time-zone.md)為現行登入應用程式使用者的偏好區域的時區。

## <a name="additional-resources"></a>其他資源

[日期和時間函數](er-functions-category-datetime.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
