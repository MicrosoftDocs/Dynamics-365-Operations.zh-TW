---
title: 常見問題集：產品配置模型的計算
description: 本主題介紹產品配置模型的計算，並說明如何將計算與限制式結合使用。
author: t-benebo
ms.date: 11/03/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PCConstraintEditor, PCProductConfigurationModelDetails, PCRuntimeConfigurator
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19191
ms.assetid: 8993f9a1-d1c0-49f5-afd3-5e1077ded0fe
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9463fac363f6bb25c1bd2afebe5737e47aa8b3cf
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448347"
---
# <a name="calculations-for-product-configuration-models-faq"></a>常見問題集：產品配置模型的計算

[!include [banner](../includes/banner.md)]

本主題介紹產品配置模型的計算，並說明如何將計算與限制式結合使用。

計算可用於算術或邏輯運算。 它們補充了產品配置模型中的運算限制式。 您可以 **限制式型產品配置模型詳細資料** 頁面定義計算，然後在運算式編輯器中構建計算的運算式。 如需詳細資訊，請參閱「建立計算」。

## <a name="what-is-a-calculation"></a>什麼是計算？
計算是您可以在產品配置模型中使用的元素。 計算讓您在設定產品時使用小數來計算值來補充限制式。 此外，計算具有比限制式更多的可用運算子集合。  

與限制式一樣，計算與產品配置模型中的特定組件相關聯，並且不能被另一個組件重複使用或共享。 計算和限制式之間的一個重要區別是計算是命令式的 (單向)，而限制式是宣告式的 (雙向)。 更多關於限制式的資訊，請參閱[產品配置模型中的運算限制式和限制式](expression-constraints-table-constraints-product-configuration-models.md)。  

計算由目標屬性和計算運算式組成。

## <a name="what-is-a-target-attribute"></a>什麼是目標屬性？
目標屬性為接收計算運算式結果的屬性。  

在以下運算式中，目標屬性是桌布測量值：  

**運算式：** If\[decimalAttribute1 &lt;= decimalAttribute2, True, False\]  

**DecimalAttribute1** 是桌子的長度，並且 **decimalAttribute2** 是桌布的長度。 如果 **decimalAttribute2** 大於或等於 **decimalAttribute1**，運算式回傳值 **True** 到目標屬性。 否則，運算式回傳 **False**。 因此，如果桌布長度等於或超過桌子的長度，則桌布測量值是可以接受的。

## <a name="what-attribute-types-can-be-set-to-target-attributes"></a>可以將哪些屬性類型設定為目標屬性？
產品設定器支援的所有屬性類型都可以設定為目標屬性，除了沒有固定清單的文字。

## <a name="can-the-value-of-a-target-attribute-restrict-the-values-of-the-input-attributes-in-a-calculation"></a>目標屬性的值能否限制計算中輸入屬性的值？
不行，目標屬性的值不能限制計算中輸入屬性的值，因為計算是單一方向的。 因此，目標屬性的值是依改變輸入屬性值來設定的，但目標屬性值的變化不會影響輸入屬性的值。 此行為不同於限制式的行為。 限制式在兩個方向出現。

### <a name="example"></a>範例

在下面的運算式中，計算的目標是電源線的長度，輸入值為顏色：  

**運算式：** \[If Color == "Green", 1.5, 1.0\]  

在設定品項時，如果指定顏色屬性值為 **綠色**，電源線長度設定為 **1.5**。 如果指定任何其他顏色，則長度設定為 **1.0**。 但是，由於計算是單向的，因此如果您指定長度 **1.5**，計算不會將顏色屬性的值設定為 **綠色**。

## <a name="what-happens-if-a-calculation-has-a-target-attribute-of-the-integer-type-but-a-calculation-generates-a-decimal-number"></a>如果計算具有整數類型的目標屬性但計算生成小數，會發生什麼情況？
如果目標屬性是整數類型，但計算生成的是小數，則只回傳計算結果的整數部分。 小數部分被移除，結果不四捨五入。 例如，12.70 的結果顯示為 12。

## <a name="when-do-calculations-occur"></a>什麼時候進行計算？
當為所有輸入屬性提供了值，就會進行計算。

## <a name="can-i-overwrite-the-value-that-is-calculated-for-the-target-attribute"></a>我可以覆寫計算給目標屬性的值嗎？
您可以覆寫計算給目標屬性的值，除非目標屬性設定為隱藏或唯讀。

## <a name="how-do-i-set-a-target-attribute-as-hidden-or-read-only"></a>如何將目標屬性設定為隱藏或唯獨？
要將屬性設定為隱藏或唯獨，請執行以下步驟。

1.  按一下 **產品資訊管理** &gt; **一般** &gt; **產品配置模型**。
2.  選取產品配置模型，然後在動作窗格中按一下 **編輯**。
3.  在 **限制式型產品配置模型** 頁面，選取屬性來作為目標屬性使用。
4.  在 **屬性** FastTab，選取 **隱藏** 或 **唯讀**。

## <a name="can-a-calculation-overwrite-the-values-that-i-set"></a>計算可以覆寫我設定的值嗎？
不行。 在設定產品時，您設定的值就是使用的值。 更改計算中的輸入值因而發生的計算，不能覆寫您為特定屬性提供的值。

## <a name="what-happens-if-i-remove-an-input-value-in-a-calculation"></a>如果我在計算中移除輸入值會怎樣？
如果在計算中移除輸入值，則目標屬性的值也會被移除。

## <a name="why-do-i-receive-an-error-message-that-says-that-my-model-is-in-contradiction"></a>為什麼我會收到一條錯誤消息，指出我的模型存在矛盾？
當計算包含錯誤或在限制式中存在一個或多個矛盾時，會顯示此訊息。 更多關於限制式的矛盾資訊，請參閱[產品配置模型中的運算限制式和限制式](expression-constraints-table-constraints-product-configuration-models.md)。 以下是計算中可能出現錯誤的一些情況：

-   一個值除以 0 (零)。
-   以下兩個元素之間存在矛盾：
    -   可用於屬性並受限制式限制的值
    -   由計算生成的值
-   計算回傳的值在屬性域之外。 一個例子是一個 \[1..10\] 的整數被計算為 0。

## <a name="why-do-i-receive-an-error-message-even-though-i-successfully-validated-my-product-model"></a>為什麼即使我成功驗證了我的產品型號，我仍會收到錯誤訊息？
計算不包括在驗證中。 您必須測試產品配置模型以發現計算錯誤。 要測試產品配置模型，請執行以下步驟。

1.  按一下 **產品資訊管理** &gt; **一般** &gt; **產品配置模型**。
2.  選取產品配置模型，然後在動作窗格，到 **執行** 群組，按一下 **測試**。






[!INCLUDE[footer-include](../../includes/footer-banner.md)]