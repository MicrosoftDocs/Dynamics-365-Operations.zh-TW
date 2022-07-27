---
title: 文字類別的 ER 函數清單
description: 本主題提供有關電子報表 (ER) 支援的文字函數的資訊。
author: NickSelin
ms.date: 02/28/2022
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
ms.openlocfilehash: 5d185c128de1120e93d1779db04a7666ba557707
ms.sourcegitcommit: 753714ac0dabc4b7ce91509757cd19f7be4a4793
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/01/2022
ms.locfileid: "8460492"
---
# <a name="list-of-er-functions-of-the-text-category"></a>文字類別的 ER 函數清單

[!include [banner](../includes/banner.md)]

電子報表 (ER) 文字函數可用於對 *字串* 資料類型的資料來源執行操作。 本主題提供了這些函數的摘要。

## <a name="list-of-supported-functions"></a>支援的函數清單

| 函數 | 描述 |
|----------|-------------|
| [Char](er-functions-text-char.md) | 此函數回傳一個 *字串* 值，該值表示由指定 Unicode 編號參考的單個字元。 |
| [連接](er-functions-text-concatenate.md) | 此函數將所有指定的文字字串作為 *字串* 值在它們連接成一個字串後回傳。 |
| [格式](er-functions-text-format.md) | 此函數透過將任何出現的 **%N** 替換為第 *N* 個引數對其進行格式化後，將指定的字串回傳一個 *字串* 值。 |
| [GetEnumValueByName](er-functions-text-getenumvaluebyname.md) | 此函數使用指定為 *字串* 值的列舉名稱在指定的列舉資料來源中搜尋特定的 *列舉* 值。 如果找到 *Enum* 值，則函數將其回傳。 |
| [GetLabelText](er-functions-text-getlabeltext.md) | 此函數搜尋特定標籤以回傳一個 *[字串](er-formula-supported-data-types-primitive.md#string)* 值，該值表示指定標籤在指定語言中的翻譯。 |
| [GuidValue](er-functions-text-guidvalue.md) | 該函數將 *字串* 類型的指定輸入轉換為 *GUID* 類型的資料項。 |
| [JsonValue](er-functions-text-jsonvalue.md) | 此函數解析在指定路徑存取的 JavaScript Object Notation (JSON) 格式的資料，並提取基於指定 ID 的標量值。 然後它將提取的標量值作為 *字串* 值回傳。 |
| [左](er-functions-text-left.md) | 此函數回傳一個 *字串* 值，該值表示從指定字串的開頭開始的指定字元數。 |
| [Len](er-functions-text-len.md) | 此函數回傳一個 *整數* 值，表示指定字串中的字元數。 |
| [Lower](er-functions-text-lower.md) | 該函數將指定的文字字串轉換為小寫字母後作為 *字串* 值回傳。 |
| [Mid](er-functions-text-mid.md) | 此函數回傳一個 *[字串](er-formula-supported-data-types-primitive.md#string)* 值，該值表示指定字串中的指定字元數，從指定位置開始。 |
| [NewGUID](er-functions-text-newguid.md) | 此函數回傳一個新產生的 *[GUID](er-formula-supported-data-types-primitive.md#guid)* 值。 |
| [NumberFormat](er-functions-text-numberformat.md) | 此函數回傳一個 *字串* 值，該值表示以指定格式和可選指定區域性表示的指定數字。 |
| [NumeralsToText](er-functions-text-numeralstotext.md) | 此函數將指定的數字以指定語言拼寫 (即轉換為文字字串) 後作為 *字串* 值回傳。 |
| [PadLeft](er-functions-text-padleft.md) | 此函數回傳一個指定長度的 *字串* 值，其中指定字串的開頭用指定字元的一個或多個實體填入。 |
| [QrCode](er-functions-text-qrcode.md) | 此函數回傳一個 *容器* 值，該值以二進位格式顯示指定字串的快速回應碼 (QR 碼) 影像。 |
| [取代](er-functions-text-replace.md) | 該函數將指定文字字串的全部或部分替換為另一個字串後，將其作為 *字串* 值回傳。 |
| [右](er-functions-text-right.md) | 此函數回傳一個 *字串* 值，該值表示從指定字串的結尾開始的指定字元數。 |
| [文字](er-functions-text-text.md) | 此函數在將指定的數字轉換為根據現行應用程式實體的伺服器區域設定格式化的文字字串後，將其作為 *字串* 值回傳。 |
| [Translate](er-functions-text-translate.md) | 此函數回傳一個 *字串* 值，該值包含將指定的字元中的文字替換為另一組提供的字元的結果。 |
| [Trim](er-functions-text-trim.md) | 此函數在製表符、回車、換行和換頁字元被單個空格字元替換後，在前導和尾隨空格被截斷後，在單詞之間的多個空格被替換後，將指定的文字字串作為 *字串* 值回傳刪除。 |
| [Upper](er-functions-text-upper.md) | 該函數將指定的文字字串轉換為大寫字母後作為 *字串* 值回傳。 |

## <a name="additional-resources"></a>其他資源

[電子報表概觀](general-electronic-reporting.md)

[電子報表中的公式設計工具](general-electronic-reporting-formula-designer.md)

[電子報表公式語言](er-formula-language.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
