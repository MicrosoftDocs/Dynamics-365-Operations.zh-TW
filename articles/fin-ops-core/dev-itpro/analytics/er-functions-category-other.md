---
title: 商業領域特定類別中的 ER 函數清單
description: 本主題提供有關電子報表 (ER) 中支援的商業領域特定函數的信息。
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
ms.openlocfilehash: a8f0812e4262a264ffc89b72e0f4fc8c55d6c6822095f550c8f05296bb057a38
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460515"
---
# <a name="list-of-er-functions-in-the-business-domainspecific-category"></a>商業領域特定類別中的 ER 函數清單

[!include [banner](../includes/banner.md)]

電子報表 (ER) 領域特定函數可用於執行特定於 Microsoft Dynamics 365 Finance 實施的計算和資料存取請求。 本主題提供了這些函數的摘要。

## <a name="list-of-supported-functions"></a>支援的函數清單

| 函數| 描述 |
|---------|-------------|
| [CH_Bank_Mod_10](er-functions-other-chbankmode10.md) | 此函數根據指定發票編號的數字回傳一個 *字串* 值，該值將貸方參考表示為 MOD10 運算式。 |
| [CN_GBT_AdditionalDimensionID](er-functions-other-cngbtadditionaldimensionid.md) | 此函數回傳一個 *字串* 值，該值表示取自指定字串的單個財務維度識別碼。 指定的字串將所有維度顯示為以逗號分隔的識別碼清單。 |
| [ConvertCurrency](er-functions-other-convertcurrency.md) | 此函數回傳一個 *實數* 值，該值表示使用指定公司的設定在指定日期將指定貨幣金額從指定源貨幣轉換為指定目標貨幣的結果。 |
| [CurCredRef](er-functions-other-curcredref.md) | 此函數根據指定發票編號的數字回傳代表貸方參考的 *字串* 值。 |
| [FA_Balance](er-functions-other-fabalance.md) | 此函數回傳一個 *容器 (記錄)* 值，該值由指定固定資產項目的固定資產餘額、價值模型代碼、報表年度和報表日期的資料組成。 |
| [FA_Sum](er-functions-other-fasum.md) | 此函數回傳一個 *容器 (記錄)* 值，該值由指定固定資產項目的固定資產金額、價值模型代碼和日期期間的資料組成。 |
| [GetCurrentCompany](er-functions-other-getcurrentcompany.md) | 此函數回傳一個 *字串* 值，該值表示使用者現行登入的法律實體 (公司) 的代碼。 |
| [ISOCredRef](er-functions-other-isocredref.md) | 此函數根據指定發票編號的數字和字母符號回傳代表國際標準化組織 (ISO) 貸方參考的 *字串* 值。 |
| [IsValidCharacterISO7064](er-functions-other-isvalidchariso7064.md) | 如果指定的字串表示有效的國際銀行帳號 (IBAN)，則此函數回傳 *布林值* **TRUE**。 否則，它會回傳 **FALSE** 的 *布林值*。 |
| [Mod_97](er-functions-other-mod97.md) | 此函數根據指定發票編號的數字回傳一個 *字串* 值，該值將貸方參考表示為 MOD97 運算式。 |
| [NumSeqValue](er-functions-other-numseqvalue.md) | 該函數根據指定的數列、範圍和範圍識別碼回傳一個表示新產生的數列值的 *字串* 值。 範圍識別碼等於執行 ER 格式的內容提供的公司代碼。 |
| [RoundAmount](er-functions-other-roundamount.md) | 此函數回傳一個 *實數* 值，表示根據指定的進位規則將指定數量進位到指定小數位數的結果。 |
| [TableName2ID](er-functions-other-tablename2id.md) | 此函數將指定資料表名稱的資料表識別碼的數字表示形式回傳為 *整數* 值。 |

## <a name="additional-resources"></a>其他資源

[電子報表概觀](general-electronic-reporting.md)

[電子報表中的公式設計工具](general-electronic-reporting-formula-designer.md)

[電子報表公式語言](er-formula-language.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]