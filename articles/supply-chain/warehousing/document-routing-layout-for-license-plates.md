---
title: 牌照標籤的文件路由配置
description: 本主題介紹如何使用格式化方法在標籤上列印值。
author: perlynne
ms.date: 04/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLicensePlateLabel, WHSLicensePlateLabelBuildConfig, WHSLicensePlateLabel, WHSDocumentRoutingLayout
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2012-04-01
ms.dyn365.ops.version: 10.0.10
ms.openlocfilehash: 9055e4c6e35099b7769faa6fc83f71523f2e64fd
ms.sourcegitcommit: fcb8a3419e3597fe855cae9eb21333698518c2c7
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/09/2022
ms.locfileid: "8450045"
---
# <a name="document-routing-layout-for-license-plate-labels"></a>牌照標籤的文件路由配置

[!include [banner](../includes/banner.md)]


文件路由配置定義了牌照標籤的配置，以及在標籤上列印的資料。 您可在設定行動裝置功能表項目及工作範本時設定列印觸發程序。

在一般情境下，倉庫收貨員記錄到達收貨區的棧板內容物之後，會立即列印牌照標籤。 實體標籤會貼在棧板上。 這些標籤之後可用於驗證，作為隨後入庫流程和未來出庫揀選作業的一部分。

您可以列印高度複雜的標籤，前提是列印設備可以解讀發送給它的文字。 例如，包含條碼的 Zebra 程式設計語言 (ZPL) 配置可能類似於以下範例。

```dos
^XA~TA000~JSN^LT0^MNW^MTD^PON^PMN^LH0,0^JMA^PR2,2~SD15^JUS^LRN^CI0^XZ
^XA
^MMT
^PW320
^LL0160
^LS0
^FT20,58^A0N,28,28^FH\^FDLabel:^FS
^FT20,81^AAN,18,10^FH\^FD$LicensePlateId$^FS
^BY1,3,17^FT20,106^BCN,,Y,N,N,A
^FD$LicensePlateId$^FS
^PQ1,,,Y^XZ
```

作為標籤列印過程的一部分，文字 `$LicensePlateId$` 在此範例中將替換為資料值。

如欲查看將列印的值，請前往 **Warehouse Management \>查詢和報告\>牌照標籤**。

幾種廣泛使用的標籤產生工具可以幫助您格式化標籤配置文字。 其中許多工具支援 `$FieldName$` 格式。 此外，Microsoft Dynamics 365 Supply Chain Management 使用特殊格式化邏輯作為文件路由配置的欄位對應的一部分。

## <a name="turn-on-this-feature-for-your-system"></a>為您的系統啟用此功能

如果您的系統尚未包含本主題中說明的功能，請前往 [功能管理](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)，並開啟 *強化牌照標籤配置* 功能。 (從 Supply Chain Management 版本 10.0.21 開始，此功能為預設開啟。 從 Supply Chain Management 10.0.25 開始，此項功能是強制性的，不能關閉。)

## <a name="custom-number-formats"></a>自訂數字格式

您可以使用具有以下格式的代碼，自訂格式化要列印的數字欄位值。

```dos
$FieldName:FormatString$
```

以下說明此項格式：

- `FieldName` 是資料欄位的名稱 (例如 **數量**)。
- `FormatString` 定義必須如何列印資料。

以下範例顯示如何自訂工作數量 (**數量**) 欄位：

- 如欲始終顯示四位數字 (使用零作為預留位置)，請使用 `$Qty:0000$`。 例如，如果數量為 10，則標籤將顯示「0010」。
- 如欲始終顯示兩位小數，請使用 `$Qty:0.00$`。 例如，如果數量為 10，則標籤將顯示「10.00」。

有關可用數字格式字串的完整清單，請參閱[自訂數字格式字串](/dotnet/standard/base-types/custom-numeric-format-strings)。

## <a name="custom-string-formats"></a>自訂字串格式

您可以使用以下欄位和格式代碼刪除字串的第一個字元。

```dos
$FieldName:#..$
```

這裡 `#` 指定要跳過的字元數。 例如列印不包含前兩個字元的序列裝運容器代碼 (SSCC) 牌照號碼，請使用 `$LicensePlateId:2..$`。 在這種情況下，牌照號碼 0011111111111222221 將列印為「11111111111222221」。

## <a name="custom-datetime-formats"></a>自訂日期/時間格式

以下範例顯示如何控制用於列印日期的格式。

```dos
$PrintedDate:dd-MM-yyyy$
```

在此範例中，2020 年 4 月 30 日的日期將列印為「30-04-2020」。

有關可用日期/時間格式字串的完整清單，請參閱[自訂日期和時間格式字串](/dotnet/standard/base-types/custom-date-and-time-format-strings)。

## <a name="print-individual-lines-from-multiline-data"></a>從多行資料列印單行

如果資料欄位包含多行 (即由換行符號分隔的行)，您可以使用以下格式列印單行。

```dos
$FieldName[#]$
```

這裡 `#` 是要列印的行號。 (第一行使用 1。)

例如，您的系統有一個 `AdditionalAddress` 欄位，儲存以下的多行地址：

Contoso Inc.  
123 街道名稱  
某個城市，某個州

您列印此地址時，可以使用以下代碼一次列印一行。

| 代碼 | 列印的文字 |
|---|---|
| `$AdditionalAddress[1]$` | Contoso Inc. |
| `$AdditionalAddress[2]$` | 123 街道名稱 |
| `$AdditionalAddress[3]$` | 某個城市，某個州 |

## <a name="print-and-format-from-a-display-method"></a>從顯示方法列印和格式化

您可以使用以下格式從顯示方法列印。

```dos
$DisplayMethod()$
```

您可以將此格式與本主題前面介紹的其他類型結合使用。 例如，您有一個顯示方法名為 `DisplayListOfItemsNumbers()`，並且您要列印此方法的第一個項目編號。 在這種情況下，您可以使用以下代碼。

```dos
$DisplayListOfItemsNumbers()[1]$
```

## <a name="more-information-about-how-to-print-labels"></a>有關如何列印標籤的更多資訊

有關如何設定和列印標籤的更多資訊，請參閱[啟用牌照標籤列印](tasks/license-plate-label-printing.md)。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]