---
title: 產品配置模型計算
description: 本主題介紹為產品配置模型中的屬性建立計算的方法
author: t-benebo
ms.date: 03/18/2021
ms.topic: article
ms.search.form: PCProductConfigurationModelListPage, PCProductConfigurationModelDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-03-18
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 349fed3ca75b94db2f421a1ff3c3553c96c202c37d59857a3d973f3de8f995ad
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447060"
---
# <a name="product-configuration-model-calculations"></a>產品配置模型計算

[!include [banner](../includes/banner.md)]

本主題介紹為產品配置模型中的屬性建立計算的方法。

## <a name="prerequisites"></a>先決條件

在產品配置模型中使用計算來計算產品的配置值。 在開始設定計算之前，必須存在相關的產品配置模型。 有關配置模型的設定過程和相關任務的摘要，請參閱[設定產品配置模型 ](set-up-maintain-product-configuration-model.md).

## <a name="create-a-calculation"></a>建立計算

計算由目標屬性和運算式組成。 更多詳細資料，請參閱[常見問題集：產品配置模型的計算](calculate-product-configuration-models.md).

若要為現有產品模型建立計算，請執行以下步驟。

1. 請前往 **產品資訊管理\>一般\>產品設定模型**。
1. 打開產品配置模型，然後選擇 **編輯**。
1. 在 **計算** FastTab上，選擇 **新增** 新增一個計算，然後設定以下欄位：

    - **名稱** – 輸入該計算的名稱。
    - **說明** – 輸入計算的說明。
    - **目標屬性**–選取您要計算的屬性。

1. 選取 **編輯運算式**。
1. 在 **輸入計算** 對話方塊中，將必要的屬性、運算子和值新增到運算式中。 更多如何使用元素的資訊，請參閱[產品配置模型中的運算限制式和資料表限制式](expression-constraints-table-constraints-product-configuration-models.md)。
1. 當您的運算式準備好時，選取 **好的**。

## <a name="calculation-examples"></a>計算範例

本節提供了一些範例來說明計算的工作原理。

### <a name="example-1"></a>範例 1

目標屬性為布林值，計算使用以下條件運算式：

`If[(decimalAttribute1 / decimalAttribute2) < 1, True, False]`

如果 `decimalAttribute2` 大於或等於 `decimalAttribute1`，運算式回傳值 *True* 到目標屬性。 否則，它會回傳 *False* 的布林值。

### <a name="example-2"></a>範例 2

此範例使用文字屬性`textFixedList`作為目標屬性。 此屬性包含以下固定清單。

| 值 | 求解工具值 |
|---|---|
| A | 1a |
| B | 2b |
| C | 2c |

以下螢幕擷取畫面顯示了此屬性設定在您的系統中的樣子。

![範例 2 的屬性類型設定。](media/model-calculations-example2.png "範例 2 的屬性類型設定")

該屬性用於以下條件陳述式：

`If[integerAttribute < 150, 0, 2]`

如果`integerAttribute`小於 150，此陳述式回傳固定清單中第一條記錄的文字值，*A*。否則，它回傳固定清單中第三條記錄的文字值，*C*。

> [!NOTE]
> 固定請單等於從零開始的列舉 (enum)，其值由適當的整數值存取。 因此，第一個固定列表值 (*A*) 與 *0* 相符，第二個值 (*B*) 與 *1* 相符，第三個值 (*C*) 與 *2* 相符。

### <a name="example-3"></a>範例 3

此範例使用前例中的文字屬性`textFixedList`作為目標屬性。 它還使用了另一個文字屬性`textAttribute`，其中為以下固定清單。

| 值 | 求解工具值 |
|---|---|
| AA | 1 aa |
| BB | 2bb |

以下螢幕擷取畫面顯示了此屬性設定在您的系統中的樣子。

![範例 3 的屬性類型設定。](media/model-calculations-example3.png "範例 3 的屬性類型設定")

`textFixedList`的值用在條件陳述式計算屬性：

`If[textAttribute == "1aa", 0, 2]`

如果 `textAttribute` 有求解工具值等於 *1aa*，此運算式回傳 `textFixedList` 中第一條記錄的文字值，*A*。否則，它回傳 `textFixedList` 中第三條記錄的文字值， *C*。

> [!NOTE]
> - 條件陳述式必須使用屬性的求解工具值。
> - 在計算中只能使用固定清單文字屬性。

## <a name="see-also"></a>另請參閱

- [常見問題集：產品配置模型的計算](calculate-product-configuration-models.md)
- [對產品配置型號新增運算限制式](tasks/add-expression-constraint-product-configuration-model.md)
- [產品配置模型概觀](product-configuration-models.md)
