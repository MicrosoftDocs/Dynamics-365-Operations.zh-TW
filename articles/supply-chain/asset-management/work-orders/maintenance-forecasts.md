---
title: 維護預測
description: 本主題說明資產管理中的維護預測。
author: johanhoffmann
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetWorkOrderForecastToJournals, EntAssetWorkOrderForecast
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 6503d5110a4cb5e4041afa7b4e80395b2974a64e5a150eb6bfce1f32a6703e06
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447135"
---
# <a name="maintenance-forecasts"></a>維護預測

[!include [banner](../../includes/banner.md)]



建立工單時，您會建立具有相關資產和維護作業類型的工單作業。 在您選擇包含維護預測的維護作業類型時，預測會自動複製到工單。

您或許能夠將預測明細新增到工單或從工單中刪除明細。 對工單生命週期狀態、關聯的專案類型和與專案類型關聯的階段規則之設定，決定您是否可以新增或編輯預測明細。 請參閱[預測、工單和專案](../integration-to-project-management-and-accounting/forecasts-work-orders-and-projects.md)，以瞭解有關工單生命週期狀態和相關專案階段的詳細資訊。

1. 選擇 **資產管理** > **通用** > **工單** > **所有工單** 或 **使用中的工單**。

2. 選擇清單中的工單，然後在動作窗格 > **工單** 索引標籤 > **專案** 群組中，選擇 **預測**。 **工單維護預測** 頁面會顯示在工單作業中選取的維護作業類型的預測明細。


## <a name="add-an-hours-forecast-to-a-work-order"></a>將工時預測新增到工單

1. 在 **工單維護預測** 頁面上，選擇要新增預測的工單作業。

2. 在 **工時** FastTab，選擇 **新增** 來建立一筆新明細。

3. 在 **類別** 欄位中，輸取一個類別。

4. 在 **工時** 欄位中，輸入預測的時數。

5. 在 **明細屬性** 欄位中，選擇應在明細上使用的費用類型。


## <a name="add-an-items-forecast-to-a-work-order"></a>將品項預測新增到工單

可以將品項新增到工單維護預測的方法有三種。 您可以為不包含在備品清單或資產物料清單 (BOM) 中的品項 (備品) 建立明細，您可以從核准的備品清單中選擇備品，也可以從資產 BOM 中選擇品項。

- 在 **工單維護預測** 頁面上，選擇要新增預測的工單作業。

- 在 **品項** FastTab 上，使用適當方法將品項新增到維護預測中。

如要為不在備品清單或資產 BOM 中的備品建立明細，請執行以下步驟：

1. 選擇 **新增**。
2. 在 **項目編號** 欄位中，選擇該項目。
3. 在 **銷售數量** 欄位中，輸入數量。
4. 在 **單位** 欄位中，選擇數量的測量單位。
5. 在 **成本價格** 和 **貨幣** 欄位中，輸入適當的值。
6. 在 **明細屬性** 欄位中，選擇一個明細屬性。
7. 如要變更顯示在品項明細上的維度清單，請選擇 **庫存** > **顯示維度**，選擇維度，然後將 **儲存設定** 選項設為 **是**。

如要從核准的備品清單中新增備品，請執行以下步驟：

1. 選擇 **新增備品**。
2. 選擇備品，並視需要編輯相關資訊。
3. 選擇 **確定**。

如要從資產 BOM 中新增品項，請執行以下步驟：

1. 選擇 **新增 BOM 品項**。
2. 選擇品項，並視需要編輯相關資訊。
3. 選擇 **確定**。

若要在 [資產管理] 中獲得顯示所選行項上的品項相對於資產、維護作業類型預設值、備用零件和工單的使用位置概觀，請選取 **使用的品項**。 更多有關此概觀的資訊，請參閱[使用的品項](../controlling-and-reporting/item-where-used.md)。


## <a name="add-an-expense-forecast-to-a-work-order"></a>將費用預測新增到工單

1. 在 **工單維護預測** 頁面上，選擇要新增預測的工單作業。

2. 在 **費用** FastTab，選擇 **新增** 以建立明細。

3. 在 **類別** 欄位中，輸取一個類別。

4. 在 **數量** 欄位中輸入數量。

5. 在 **成本價格**、**銷售貨幣**，與 **銷售價格** 欄位中，輸入適當的值。

6. 在 **明細屬性** 欄位中，選擇應在明細上使用的費用類型。

>[!NOTE]
>**維護預測總計** FastTab 會顯示每個 FastTab 上已為所選的工單作業和工單建立的明細數量概觀。 它也會顯示工單作業和工單的總預測工時。

下圖顯示 **工單維護預測** 頁面的範例。

![圖 1。](media/06-work-orders.png)


## <a name="automatic-update-of-work-order-forecasts"></a>工單預測自動更新

如果工時成本、品項成本和費用已在 Microsoft Dynamics 365 for Finance and Operations 中的其他模組進行了更新，則資產管理中的工單預測可以自動更新以反映這些變更。 此功能有助於確保在您的工單預測中一律使用最新的成本價格。 您也可以為[維護工作類型預測](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md)執行類似的更新。

1. 選擇 **資產管理** > **定期** > **預測** > **更新工單預測**。

2. 在 **更新工單預測** 對話方塊的 **要包括的記錄** FastTab 中，您可以根據需要新增有關特定工單或工單作業的選擇。 按一下 **篩選** 以進行相關選擇。

3. 您可於 **在背景執行** FastTab 根據需要將自動更新設定為批次作業。

4. 選擇 **確定** 開始預測更新。


下圖顯示 **更新工單預測** 對話方塊的範例。

![圖 2。](media/07-work-orders.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]