---
title: 管理測量單位
description: 本主題說明如何定義測量單位、提供單位及其描述的翻譯，並定義相關單位的轉換規則。
author: t-benebo
ms.date: 04/09/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResProductMaintainWorkspace, EcoResProductOpenCasesFormPart, UnitOfMeasure, UnitOfMeasureReportingTranslation, UnitOfMeasureTranslation, UnitOfMeasureConversion, UnitOfMeasureConversionEditOrCreate, UnitOfMeasureLookup, UnitOfMeasureCalculator, UnitOfMeasureWizard, UnitOfMeasureLookupTest
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e13897396810507bb4b2cbb415b873eb3dd7f4e8
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8447831"
---
# <a name="manage-units-of-measure"></a>管理測量單位

[!include [banner](../../includes/banner.md)]

本主題說明如何定義測量單位、提供單位及其描述的翻譯，並定義相關單位的轉換規則。

## <a name="open-the-units-page"></a>開啟單位頁面

若要建立並使用系統可用的測量單位，請移至 **組織管理 \> 設定 \> 單位 \> 單位**。

本主題其餘小節會說明您在 **單位** 頁面可執行的操作。

## <a name="create-standard-units-and-conversions"></a>建立標準單位與轉換

若您的系統尚未納入公制和/或美制 (USCS) 最常見的測量單位，單位設定精靈可協助您快速掌握基本單位定義與轉換工作。 若要完成精靈，請於動作窗格選擇 **單位建立精靈**，然後按照螢幕上的說明進行操作。

## <a name="create-or-edit-a-unit-of-measure"></a>建立或編輯測量單位

若要建立或編輯測量單位，請遵循以下步驟。

1. 請執行以下其中一個步驟：

    - 若要編輯現有單位，請在清單窗格中加以選取。
    - 若要建立新單位，請在動作窗格上，選擇 **新增**。

1. 在記錄的標頭上設定以下欄位：

    - **單位** – 輸入以系統語言表示的單位的識別碼或符號。 此識別碼或符號通常是該單位的常用縮寫，例如 *ea* 代表「個」、*cm* 代表「公分」。
    - **說明** – 以系統語言輸入單位的描述性名稱。 該名稱通常是單位的完整名稱，例如 *每個* 或 *公分*。

1. 在 **一般** FastTab 上設定下列欄位：<!-- KFM: confirm this:    - **Fixed unit assignment** and **Fixed unit** – These fields have an effect only if you're using the Microsoft Retail Essentials product. If the current unit can be mapped to one of the fixed units that are used by Retail Essentials, set the **Fixed unit assignment** option to *Yes*. Then select the fixed unit in the **Fixed unit** field. -->

    - **單位類別** – 選擇單位測量的屬性 (如長度、面積、品質或數量)。
    - **單位制** – 選擇單位所屬的測量系統 (*公制單位* 或 *美制單位*)。
    - **基準單位** – 此選項設為 *是*，目前單位就會當作其單位類別的基準單位。 此時，您只需要指定單位類別中基準單位和其他每個單位之間的轉換因數。 如此一來，此系統即可在該單位類別中的所有單位間進行轉換。 因此，轉換的設定就更容易。

        例如，若加侖是 *體積* 單位類別的基準單位，則只須設定夸脫到加侖、品脫到加侖的轉換因數。 而且系統也能從夸脫轉換為品脫。

        每個單位類別只能設定一個基準單位。

    - **系統單位** – 此選項設為 *是*，目前單位就會當作其單位類別內所有未指定的量測值的假設單位。 例如，若輸入數量的某個欄位無法指定單位 (若使用者並未選取單位)，則系統使用的單位就是 *數量* 單位類別設定的系統單位。 每個單位類別只能設定一個系統單位。
    - **小數點有效位數** – 指定目前單位或轉換後單位的值應四捨五入的小數位數。

1. 在動作窗格上，選擇 **儲存**。

## <a name="define-unit-translations"></a>定義單位翻譯

若要定義識別碼或符號的翻譯及測量單位的說明，請遵循以下步驟。

1. 建立或選取要建立翻譯的單位。
1. 在動作窗格上，選擇 **單位文字**。

    將出現 **單位文字** 頁面。 您可使用此頁面來定義所選單位識別碼或符號的翻譯。 之後，這些翻譯即可用於以客戶特定或廠商特定語言撰寫的外部文件。

1. 在動作窗格上，選擇 **新增**。
1. 在 **語言** 欄位中，選取單位識別碼或符號的翻譯目標語言。
1. 在 **文字** 欄位中，輸入單位識別碼或符號以所選語言表示的翻譯。
1. 在動作窗格上，選擇 **儲存**。
1. 關閉頁面。
1. 在 **動作窗格** 上，選擇 **翻譯單位說明**。

    將出現 **翻譯單位說明** 頁面。 您可使用此頁面來定義所選單位的語言特定說明。

1. 在動作窗格上，選擇 **新增**。
1. 在 **語言** 欄位中，選取單位說明的翻譯目標語言。
1. 在 **說明** 欄位中，輸入單位說明以所選語言表示的翻譯。
1. 在動作窗格上，選擇 **儲存**。
1. 關閉頁面。

## <a name="define-unit-conversion-rules"></a>定義單位轉換規則

若要定義測量單位間的轉換規則，請遵循以下步驟。

1. 建立或選取要定義轉換規則的單位。
1. 在動作窗格上，選擇 **單位轉換**。

    將出現 **單位轉換** 頁面。 您可使用此頁面來定義所選單位和該單位類別中其他單位的轉換規則。

1. 依據您要設定的轉換類型，選取以下索引標籤之一：

    - **標準轉換** – 為所有產品設定標準轉換規則。
    - **類別內轉換** – 為同一單位類別的單位設定產品特定的轉換規則。
    - **類別間轉換** – 為不同單位類別的單位設定產品特定的轉換規則。

1. 請執行以下其中一個步驟：

    - 若要建立新的轉換，請選擇工具列上的 **新增**。
    - 若要編輯現有轉換，請選擇網格內的轉換，然後選擇工具列上的 **編輯**。

1. 在下拉式對話方塊中，設定下列欄位：

    - **產品** – 選擇轉換適用的特定產品。 類別內與類別間轉換才有此欄位。
    - **公式配置** – 若是只有單一因數的簡單轉換，請保留此欄位的 *簡單* 設定。 若設定為 *進階*，即可設定較複雜的方程式。 進階方程式的格式取決於單位類別。
    - **來源單位** – 此欄位會顯示所選單位。 一般而言，這個值無須變動。 (若您變更此值，請務必於儲存後開啟所選單位的 **單位轉換** 頁面，檢視新的轉換。)
    - **目標單位** – 選擇轉換目標單位。
    - **進位** – 依據所選單位 **小數點有效位數** 的值，選擇小數部分四捨五入的方式 (*最接近*、*進位* 或 *捨去*)。
    - **轉換公式** – 使用下拉式對話方塊頂部的其餘欄位來指定兩個單位轉換的公式。 可用欄位會因您選取的單位類別和公式配置而有所差異。

1. 選擇 **確定**。
1. 關閉頁面。

> [!TIP]
> 您也可為每個產品變型設定單位轉換。 如需詳細資訊，請參閱[每個產品變型的測量單位轉換](../uom-conversion-per-product-variant.md)。

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
