---
title: 資產製造商與模型
description: 本主題介紹如何在資產管理中設定資產製造商與相關模型。
author: johanhoffmann
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetProductLookup, EntAssetModelLookup, EntAssetProduct
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 80fcb493d96209d78f842414c198a8275e4818ba365759466034faf5f3405540
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446877"
---
# <a name="asset-manufacturers-and-models"></a>資產製造商與模型

[!include [banner](../../includes/banner.md)]

 

本主題介紹如何在資產管理中設定資產製造商與相關模型。 模型可以與資產類型相關。

## <a name="set-up-product-model-relations"></a>設定產品-模型關係

1. 選擇 **資產管理** \> **設定** \> **資產** \> **製造商與型號**。
2. 選取 **新增** 建立新的產品。
3. 在 **製造商** 欄位中，輸入資產製造商的名稱。
4. 在 **描述** 欄位中，輸入描述。
5. 在 **型號** FastTab 上，選擇 **新增** 建立應與資產製造商相關的資產型號。
6. 在 **型號** 欄位中，輸入資產型號的名稱。
7. 在 **描述** 欄位中，輸入描述。
8. 在 **資產類型** 欄位中，選擇製造商型號應相關的資產類型。

    > [!NOTE]
    > 您也可以在 **資產類型** 查詢中設定資產類型、製造商與型號的關係。 如需詳細資訊，請參閱[資產類型](../setup-for-objects/object-types.md)。

    在 **詳細資料** FastTab 中，**型號** 欄位會顯示在對所選資產製造商設定的資產模型數目。 **資產** 欄位會顯示正使用所選製造商的資產數量。
    
    **資產** 欄位會顯示正使用所選製造商型號的物件數量。

> [!NOTE]
> 一個資產類型可以沒有資產製造商型號關係、可以與一個資產製造商型號關聯，也可以與多個資產製造商型號關聯。 如果資產類型與至少一個製造商型號相關，則在這些 [資產管理] 頁面上只能選擇在 **製造商型號** 查詢中設定的組合；在該頁面可以設定資產類型、製造商和型號的組合。 這些頁面包括 **所有資產**、**資產服務層級**、**作業類型預設值** 及 **維護預算行**。 如果某些資產類型與任何製造商型號無關，則在頁面上只會顯示這些資產類型，以及也與資產類型沒有關係的製造商型號。

## <a name="select-a-manufacturer-and-model-on-an-object"></a>在物件上選擇製造商與型號

1. 選取 **資產管理** \> **一般** \> **資產** \> **全部資產**。
2. 在 **資產** 欄中選擇資產的連結。 **詳細資料** 頁面隨即顯示。
3. 選擇 **編輯**。
4. 在 **一般** FastTab 上，選擇 **製造商** 與 **型號** 欄位中的值。


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]