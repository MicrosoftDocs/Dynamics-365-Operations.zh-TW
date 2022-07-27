---
title: 美國國家汽車貨運分類 (NMFC) 代碼
description: 本主題介紹如何在 Microsoft Dynamics 365 Supply Chain Management 中使用美國國家汽車貨運分類 (NMFC) 代碼
author: Henrikan
ms.date: 04/22/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-04-22
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 8e6aac6b3a8b730b6adc5c3d4410b98c3e8d5090eac866c337ed1d03409ba765
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446790"
---
# <a name="national-motor-freight-classification-nmfc-codes"></a>美國國家汽車貨運分類 (NMFC) 代碼

[!include [banner](../includes/banner.md)]

美國國家汽車貨運分類 (NMFC) 代碼可幫助您對可運輸的物品進行分類。 NMFC 代碼是用於對商品進行分組的名稱。 它使運輸公司能夠根據如卡車適合性、裝載問題、處理問題和易腐性等考慮因素對項目進行分類，來評估要裝運的貨物。 透過使用 50 到 500 的數字範圍，將商品分組成 18 個貨運類別之一。 將商品分組的類別是根據對四個運輸特性來評估的，分別是：密度、可裝載性、搬運性和責任。 這些特性共同確立了商品的可運輸性。

NMFC 代碼與每個汽車零載量 (LTL) 運輸項目相關聯。 例如，可為筆記型電腦指派一個分類為 2.5 的 NMFC，也可為電線分配一個分類為 65 的 NMFC。

此功能可以幫助工作人員使用 NMFC 代碼對 LTL 運輸項目進行分類。 這裡有些範例：

- 如果貴公司在提單 (BOL) 上包含貨物說明，承運業者就會知道貨物是什麼。 貨物是一個重要的分類，因為許多運輸公司的整個商業模式都是以他們運送的貨物為依據。
- 此分類對於您的公司可能至關重要，因為它用於決定所指定裝載的成本。
- 貴公司可以判定 LTL 物流和運輸公司的獲利能力。

本主題介紹如何在 Microsoft Dynamics 365 Supply Chain Management 中使用 NMFC 代碼。

## <a name="prerequisites"></a>前提條件

在您可以建立 NMFC 代碼之前，您必須設定所有必須對應到代碼的 LTL 貨物類別。 LTL 貨運分類代表物品的類別，而 NMFC 代碼會與 18 個貨運分類裡的每一個分類中的特定商品相關。 如需如何使用 LTL 類別的詳細資訊，請參閱[零載量 (LTL) 類別](ltl-class.md)。

## <a name="create-an-nmfc-code"></a>建立 NMFC 代碼

若要建立 NMFC 代碼，請按照以下步驟。

1. 請執行以下其中一個步驟：

    - 移至 **Warehouse Management \> 設定 \> 庫存 \> NMFC 代碼**。
    - 移至 **運輸管理 \> 設定 \> 運輸標準 \> NMFC 代碼**。

1. 選取 **新增** 建立 NMFC 代碼。 然後設定以下欄位：

    - **NMFC 代碼** – 輸入商品類型的 NMFC 代碼。
    - **名稱** – 輸入 NMFC 代碼的名稱。
    - **LTL 類別** – 選取與 NMFC 代碼相關聯的 LTL 類別。
    - **BOL 處理單位** – 定義貨品的預設處理類型。

## <a name="example-set-up-nmfc-codes"></a>範例：設定 NMFC 代碼

以下範例顯示如何設定兩個可用於不同產品的不同 NMFC 代碼。

1. 移至 **Warehouse Management \> 設定 \> 庫存 \> NMFC 代碼**。
1. 在動作窗格上，選擇 **新增**。
1. 在新的明細上，設定以下值：

    - **NMFC 代碼：** *92.5*
    - **名稱：** *電腦*
    - **LTL 類別：** *92.5*
    - **BOL 處理單位：** *單位*

1. 在動作窗格上，選擇 **儲存**。
1. 在動作窗格上，選擇 **新增**。
1. 在新的明細上，設定以下值：

    - **NMFC 代碼：** *125*
    - **名稱：** *電話*
    - **LTL 類別：** *125*
    - **BOL 處理單位：** *單位*

1. 在動作窗格上，選擇 **儲存**。

## <a name="additional-resources"></a>其他資源

- [零載量 (LTL) 類別](ltl-class.md)
- [建立提單](create-bill-of-lading.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
