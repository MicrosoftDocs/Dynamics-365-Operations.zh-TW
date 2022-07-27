---
title: 維護屬性類型
description: 本主題說明如何在資產管理中建立屬性類型。
author: johanhoffmann
ms.date: 06/24/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetFunctionalLocationTypeCopy, EntAssetAttributeType, EntAssetAttributeTypeValue, EntAssetFunctionalLocationType
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ec5552d96473403931bbd513ae68ef0fe3069209f52e813963914417ad41b88a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446871"
---
# <a name="maintenance-attribute-types"></a>維護屬性類型

[!include [banner](../../includes/banner.md)]

 

本主題說明如何在資產管理中建立屬性類型。 屬性用於描述各種元素的屬性。 您可以在以下元素上設定屬性：

- [機能位置類型](../setup-for-functional-locations/functional-location-types.md)
- [建立功能位置](../functional-locations/create-functional-locations.md)
- [資產類型](../setup-for-objects/object-types.md)
- 資產

可設定的屬性因元素而異。 例如，對於功能位置，可以設定該位置的配置和物理大小的屬性。 對於資產類型或資產，可以設定不同條件下的引擎體積、功耗和最大負載能力的屬性。

## <a name="create-attribute-types"></a>建立屬性類型

您可以建立自己的屬性類型。 此外，您可以將產品尺寸移轉到 **屬性類型** 頁面。

1. 選取 **資產管理** \> **設定** \> **屬性類型**。
2. 首次設定屬性類型時，選擇 **建立產品尺寸** 以自動傳輸標準產品尺寸。
3. 選擇 **新增** 以建立新的屬性類型。
4. 在 **屬性類型** 欄位，輸入屬性類型的名稱。
5. 在 **描述** 欄位中，輸入描述。
6. 在 **單位** 欄位，根據需要選擇相關的屬性單位。
7. 在 **資料類型** 欄位，選取單位的資料類型。
8. 如果資料類型選擇的是 **字串**，請按照以下步驟為屬性類型建立值：

    1. 選取屬性類型，然後選取 **值**。
    2. 在 **屬性值** 欄位中，選擇 **新增**。
    3. 在 **屬性類型** 欄位，選擇屬性類型 (尺寸)。
    4. 在 **值** 欄位中，輸入相關值。
    5. 在 **描述** 欄位中，輸入描述。
    6. 儲存記錄。
    7. 返回 **屬性類型** 頁面。

9. 儲存記錄。

    **功能位置類型** 欄位顯示使用屬性類型的功能位置的數量。 **資產類型** 欄位會顯示正在使用功能位置的資產類型數目。


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]