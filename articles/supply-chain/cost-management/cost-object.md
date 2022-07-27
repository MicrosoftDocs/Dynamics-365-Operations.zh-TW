---
title: 成本物件
description: 本文提供有關成本物件的資訊，並說明如何累積成本和數量。 成本物件是累計成本和數量的實體。 成本物件實體可以是產品或產品變體，例如樣式和顏色的變體。
author: AndersGirke
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventCostOnhandItem
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19451
ms.assetid: ec776b98-813a-490d-848f-468452d98fac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d27e2dcfd8f70c8d4b0f2ae1254f3c4fce63bb4d
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448488"
---
# <a name="cost-objects"></a>成本物件

[!include [banner](../includes/banner.md)]

本文提供有關成本物件的資訊，並說明如何累積成本和數量。 成本物件是累計成本和數量的實體。 成本物件實體可以是產品或產品變體，例如樣式和顏色的變體。  

## <a name="cost-objects"></a>成本物件

**成本物件** 頁面列出了在產品上註冊的所有成本物件。 成本物件由以下來源的資料所定義：

-   產品
-   產品尺寸群組
-   儲存尺寸群組
-   追蹤維度群組

**注意：** 成本物件僅代表 **直接材料** 類型的成本要素。 成本物件和庫存物件的不同之處，在於成本物件是由為財務庫存選擇的庫存維度定義。 例如，一個項目具有以下設定：

-   **網站：** 實體庫存 = 是，財務庫存 = 是
-   **倉庫：** 實體庫存 = 是，財務庫存 = 否
-   **批號：** 實體庫存 = 是，財務庫存 = 否

下表顯示了何謂成本物件以及庫存物件。

| 物件類型      | 品項編號 | 網站 | 倉庫 | 批號。 |
|------------------|-------------|------|-----------|-----------|
| 成本物件      | x           | x    |           |           |
| 庫存物件 | x           | x    |  x        | x         |

## <a name="accumulation-of-costs-and-quantities"></a>成本和數量的累積
-   **值** 欄位中的值是以下值的總和：
    -   實體成本金額
    -   財務成本金額
    -   調整
-   **數量** 欄位中的值是以下值的總和：
    -   已收到
    -   扣除
    -   張貼數量
-   **平均單位成本** 欄位是導出欄位。 該值是透過將 **Value** 值除以 **Quantity** 值來計算的。

**注意：** **包括實體值**參數對前面的計算沒有影響。

## <a name="additional-resources"></a>其他資源

[產品尺寸群組](/dynamicsax-2012/appuser-itpro/about-product-dimensions)

[儲存尺寸群組](/dynamicsax-2012//storage-dimension-groups-form)

[追蹤維度群組](/dynamicsax-2012//tracking-dimension-groups-form)

[新消息或變更](../../fin-ops-core/fin-ops/get-started/whats-new-changed.md)

[成本項目](cost-entries.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]