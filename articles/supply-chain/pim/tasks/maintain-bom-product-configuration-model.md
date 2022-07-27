---
title: 維護產品設定模型的 BOM
description: 執行此程序需要現有的產品設定模型。
author: t-benebo
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, PCBOMLineDetails, InventItemIdLookupSimple
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bd78b06f10d0c9b1df57dacdd824b06ebe414b3b
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448995"
---
# <a name="maintain-bom-for-a-product-configuration-model"></a>維護產品設定模型的 BOM

[!include [banner](../../includes/banner.md)]

執行此程序需要現有的產品設定模型。 此程序的建立使用了 USMF 示範資料公司的高品質喇叭型號。

## <a name="add-a-bom-line"></a>新增 BOM 明細

1. 移至 **產品資訊管理\>產品\>產品設定模型**。
1. 在清單中，尋找並選擇所需紀錄。
    * 為此程序選擇高品質喇叭。  
1. 在列表中，選擇所選行中的連結。
1. 展開 **BOM 明細** 區段。
1. 選擇 **新增**。
1. 在 **名稱** 欄位中，輸入一個值。
1. 在 **描述** 欄位中，輸入一個值。
1. 選擇 **儲存**。

## <a name="add-bom-line-details"></a>新增 BOM 明細詳細資料

1. 選擇 **BOM 行詳細資訊**。
2. 在 **項目號碼** 欄位中，輸入或選擇一個值。
    * 例如，您可以選取品項 M0055。  
    * 對於每個 BOM 明細屬性，您可以選擇它是否採用固定值或是對應到屬性。  
3. 選擇 **設定** 核取方塊。
4. 選擇 **計算** 欄位中的 *是*。
    * 將 **計算** 屬性設為 *是*，以確保 BOM 明細包含在成本計算中。  
5. 選擇 **設定** 索引標籤。
6. 選擇 **設定** 核取方塊。
7. 在 **數量** 欄位中，輸入一個數字。
    * 數量欄位決定了將包含在 BOM 中的品項數量。 這可能是屬性對應的明顯候選者。  
8. 選擇 **維度** 索引標籤。
    * 確認是否有任何產品維度處於使用中狀態，因此必須指派一個值或屬性。  
9. 選擇 **確定**。


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]