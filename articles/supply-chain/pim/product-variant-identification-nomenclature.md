---
title: 產品變型編號與名稱的命名法
description: 本主題介紹您如何能設定產品編號命名法以替換固定的 [基準產品編號 - 設定 - 尺寸 - 顏色 - 樣式] 格式。
author: t-benebo
ms.date: 11/03/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResNomenclature, EcoResProductDimensionGroup, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelDetails
audience: Application User
ms.reviewer: kamaybac
ms.custom: 220104
ms.assetid: 3fe69fb7-5c32-423c-98a8-2f53186cda68
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 14ea9bb5afe7b05f1f0392fde523a95a04a6e2ad
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448230"
---
# <a name="nomenclature-of-product-variant-numbers-and-names"></a>產品變型編號與名稱的命名法

[!include [banner](../includes/banner.md)]

本主題介紹您如何能設定產品編號命名法以替換固定的 [基準產品編號 - 設定 - 尺寸 - 顏色 - 樣式] 格式。 新命名法具有目標格式，包括基準產品編號、活動產品維度和您選擇的文字分隔符號。 您還可以為產品名稱建立命名法。 最後，您可以建構一個命名法來識別由條件式產品設定程式建立的設定。 這些命名法可以包含您選擇的屬性。

產品變型編號和產品變型名稱的新命名法使您可以在產品變型的識別碼中包含細分。 這些細分可以包括基準產品編號和名稱、產品維度識別碼和名稱、編號序列、文本常數和屬性。 此功能可讓您在建立銷售訂單或採購單時快速尋找特定的產品變型。 您可以使用 **產品命名法** 頁面建立產品變型編號和產品變型名稱的命名法。 要打開此頁面，請按一下 **產品資訊管理** &gt; **設定**。

## <a name="nomenclature-of-predefined-product-variants"></a>預定義產品變型的命名法
根據三種設定技術之一為基準產品產生產品變型：

-   預定義的變體
-   條件式
-   維度式

每個產品變型都有一個編號和名稱，產品變型識別命名法讓您能選擇被包括在每個產品變型編號或名稱中的細分。 您可以在 **產品命名法** 頁面上選擇下列細分：

-   基準產品編號
-   基準產品名稱
-   編號序列值
-   文本常數
-   產品維度
    -   設定識別碼或名稱
    -   顏色識別碼或名稱
    -   尺寸識別碼或名稱
    -   樣式識別碼或名稱

在定義產品變型識別編號命名法後，您可以將其與產品維度群組建立關聯。  然後，將根據命名法為所有參考此產品維度群組的基準產品指派產品變型編號。 但是，產品變型名稱命名法不能與產品維度群組有關。 您還可以將產品變型識別命名法直接指派給基準產品。 在這種情況下，屬於基準產品的產品變型將根據命名法被指派產品變型編號和名稱。

### <a name="example"></a>範例

一件 T 恤 (TS1234) 生產三種尺寸（S、M、L）、四種顏色（紅、綠、藍、黃）和兩種款式（Polo、V）。 因此，可能會有 24 個產品變型 (= 3 × 4 × 2)。 您建立具有以下部分的產品變型編號命名法：

1.  基準產品編號
2.  文本常數： "-"
3.  色彩
4.  文本常數： "-"
5.  大小
6.  文本常數： "-"
7.  樣式

以此範例而言，紅色小馬球 T 恤的產品變型編號將為 TS1234-Red-Small-Polo。

## <a name="nomenclature-of-constraint-based-configurations"></a>條件式設定的命名法
對於條件式設定，您可以為設定產品維度建立專用的命名法。 您可以在 **產品命名法** 頁面上選擇下列細分：

-   編號序列值
-   文本常數
-   屬性值

產品設定模型中的每個組件都可以有自己的設定命名法。 只能使用屬於該組件的屬性。 不能使用來自子組件或使用者需求的屬性。

### <a name="example"></a>範例

產品設定模型有一個根組件，它有兩個屬性：

-   材料（塑料、木材、鋼）
-   長度 (10...100)

您建立具有以下部分的設定命名法：

1.  屬性值：材料
2.  文本常數： "AAA"
3.  屬性值：長度

以此範例而言，長度為 78 的木質材料的設定識別碼將為 WoodAAA78。

## <a name="nomenclature-of-dimension-based-configurations"></a>維度式設定的命名法
對於維度式設定，您可以為設定產品維度建立專用的命名法。 您可以在 **產品命名法** 頁面上選擇下列細分：

-   編號序列值
-   文本常數
-   設定群組項目

您可以為物料清單 (BOM) 定義設定命名法。

### <a name="example"></a>範例

一個 BOM 有四個 BOM 行，它們分為兩個設定群組：

-   BOM 行：M0007，標準櫃
    -   設定群組：櫃
-   BOM 行：M0008，高端櫃
    -   設定群組：櫃
-   BOM 行：M0021，前格柵布
    -   設定群組：前格柵
-   BOM 行：M0022，前格柵金屬
    -   設定群組：前格柵

您建立具有以下部分的設定命名法：

1.  設定群組：櫃
2.  文本常數： "&"
3.  設定群組：前格柵

以此範例而言，具有布質前格柵的標準櫃的設定識別碼將為 M0007&M0021。

## <a name="nomenclature-for-a-combination-of-product-variants-and-configurations"></a>產品變型和設定組合的命名法
當您使用條件式設定技術或維度式設定技術為基準產品設定產品變型時，產品變型的產品變型編號可以包含來自設定維度的命名法。 按照這些步驟設定變體。

1.  在 **產品命名法** 頁面上，定義包含設定維度的產品變型編號命名法。
2.  將該命名法指派給具有設定維度的產品維度群組。
3.  為將用於設定產品變型的組件或 BOM 定義設定命名法。

您還可以為該產品變型名稱建立命名法。 產品變型名稱可以設定為包含設定識別碼或名稱。

### <a name="example-for-constraint-based-configurations"></a>條件式設定範例

對於此範例，您使用由以下部分組成的產品變型編號命名法：

1.  基準產品編號
2.  文本常數 "\_"
3.  組態

該設定命名法由以下部分組成：

1.  屬性值：材料
2.  文本常數： "AAA"
3.  屬性值：長度

您為各部分輸入以下值：

-   基準產品編號= **M0099**
-   材料 = **塑料**
-   長度= **12**

以此範例而言，產品變型編號將為 M0099\_塑料 AAA12。

### <a name="example-for-dimension-based-configurations"></a>維度式設定範例

對於此範例，您使用由以下部分組成的產品變型編號命名法：

1.  基準產品編號
2.  文本常數 "//"
3.  組態

該設定命名法由以下部分組成：

1.  設定群組：櫃
2.  文本常數： "&"
3.  設定群組：前格柵

您為各部分輸入以下值：

-   基準產品編號= **D0123**
-   櫃 = **M0008**
-   前格柵 = **M0022**

以此範例而言，產品變型編號將為 D0123//M0008&M0022。

## <a name="numbering-conflicts"></a>編號衝突
在某些情況下，您設定的產品變型編號命名法可能不會產生唯一的產品變型編號。 例如，如果一個活動產品維度未包含在使用預定義變體設定技術的基準產品的命名法中，則產品變型編號將不是唯一的。 處理衝突的方式因設定技術而異。

### <a name="predefined-variants"></a>預定義的變體

如果您嘗試手動建立或自動產生產品變型，且多個產品變型最終具有相同的產品變型編號，則會發生錯誤。 要避免這種情況，您應該使用產品尺寸群組中的所有活動產品維度。 或者，包括一個編號序列，以幫助確保產品變型編號是唯一的。

### <a name="constraint-based-configurations"></a>條件式設定

根據命名法，系統可能會嘗試將非唯一的產品變型編號指派給設定。 在這種情況下，系統會使用設定維度的編號序列作為產品變型編號，然後您會收到警告。 為避免這種情況，您應該在命名法中包含足夠的屬性以幫助保證唯一的產品變型編號。 您還應該確保已開啟組件的 **重複使用** 選項。

### <a name="dimension-based-configurations"></a>維度式設定

在設定過程的一個步驟中，系統會根據命名法建議設定值。 在此步驟中，您可以手動更改設定值。 當您儲存設定時，系統會驗證設定值是否唯一。 如果您輸入的值不是唯一的，您會收到一則錯誤訊息。 要儲存設定，您必須輸入唯一的設定值。

## <a name="additional-resources"></a>其他資源

[為預定義產品變型建立產品編號命名法](tasks/create-product-number-nomenclature-predefined-variants-2016-11.md)

[為已設定的產品變型建立產品編號命名法](tasks/create-product-number-nomenclature-product-variants_2016_11.md)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]