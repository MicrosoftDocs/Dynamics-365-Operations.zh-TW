---
title: 系統定義和使用者定義的資料表條件約束
description: 本文說明產品設定模型中組件資料表條件約束的兩種類型 - 使用者定義的和系統定義。 資料表條件約束表示允許的屬性組合的矩陣，其中每一行定義一組可能的屬性值。
author: t-benebo
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PCTableConstraintAttachAttributeTree, PCTableConstraintColumnSystem, PCTableConstraintContentUserDef, PCTableConstraintDefinition, PCTableConstraintWizard
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19781
ms.assetid: 0a4ea930-b344-43a8-871e-d5cd077892c4
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c4b484c99bc8f1cc830d4177460ec15a26714a56
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449007"
---
# <a name="system-defined-and-user-defined-table-constraints"></a>系統定義和使用者定義的資料表條件約束

[!include [banner](../includes/banner.md)]

本文說明產品設定模型中組件資料表條件約束的兩種類型 - 使用者定義的和系統定義。 資料表條件約束表示允許的屬性組合的矩陣，其中每一行定義一組可能的屬性值。

資料表條件約束表示產品設定模型中組件允許的屬性組合矩陣。 表中的每一行定義一組可能的屬性值。 您可以在產品設定模型中宣告兩種類型的條件約束：

-   **運算式條件約束** – 建立一個定義屬性之間關係的運算式，以確保在產品設定期間只能選擇相容的值。
-   **資料表條件約束** – 建立資料表，定義指定屬性集允許的所有組合。 有兩種類型的資料表條件約束可用：使用者定義的資料表條件約束和系統定義的資料表條件約束。

本文說明產品設定模型中組件的的使用者定義和系統定義資料表條件約束。

## <a name="user-defined-table-constraints"></a>使用者定義的資料表條件約束
使用者定義的資料表條件約束是一種矩陣，可用於描述由屬性類型定義的屬性值組合。 例如，如果您生產喇叭，您可以在使用者定義的資料表條件約束中包括箱體飾面和前格柵的資料行。 箱體飾面的屬性類型有四個值，前格柵的屬性類型有三個值。 因此，如果不使用條件約束，則有 4 × 3 = 12 種可能的組合。 但在此範例中，僅允許六種組合，如下表所示。 此資訊顯示在 **編輯資料表條件約束** 頁面的 **允許組合** 索引標籤上。

| 箱體飾面 | 前格柵 |
|----------------|-------------|
| 黑色          | 黑色       |
| 黑色          | 金屬       |
| 橡木            | 黑色       |
| 紅木       | 白色       |
| 白色          | 黑色       |
| 白色          | 白色       |

使用者定義的資料表條件約束由靜態資料表輸入定義，其工作方式與運算式約束相同。 使用使用者定義的資料表條件約束時，該資料表的優點是通常比長運算式約束更容易建立、理解和維護。

## <a name="system-defined-table-constraints"></a>系統定義的資料表條件約束
系統定義的資料表條件約束在資料表中的屬性類型與欄位之間建立動態對應。 當產品設定模型中包含系統定義的資料表條件約束時，對應保證顯示資料表中的資料而不是屬性類型的值。 結果是動態條件約束，因為可以修改資料表內容 (例如，由其他模組)。  

建立系統定義的資料表條件約束時，可以選擇一個資料表，可選擇定義要使用的查詢，然後將屬性類型與所選資料表中的欄位相關聯。 欄位的類型必須與屬性類型的類型相符。  

在資料表條件約束對產品設定模型生效之前，資料表條件約束必須包含在模型組件之一的條件約束中。 該程序是建立新條件約束，選擇資料表條件約束類型，然後選擇要使用的資料表條件約束定義。 最後，資料表條件約束中的所有欄位都必須對應到產品設定模型中的屬性。

## <a name="additional-resources"></a>其他資源

[產品配置模型概觀](product-configuration-models.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]