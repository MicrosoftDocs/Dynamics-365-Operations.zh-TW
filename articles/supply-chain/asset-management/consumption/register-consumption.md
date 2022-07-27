---
title: 登記消耗
description: 本主題說明如何在資產管理中登記消耗。
author: johanhoffmann
ms.date: 08/21/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetWorkOrderJournal, EntAssetWorkOrderAddSparePart
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 619da584ea37e80b1803ae5983e52e8ee4053f3751a8df75a8f5bc1ddf7e65d6
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447153"
---
# <a name="register-consumption"></a>登記消耗

[!include [banner](../../includes/banner.md)]

 

完成工單的維護作業後，下一步是進行消耗登記並過帳日記帳。 可以為以下消耗類型進行登記：工時、品項和費用。 在 **工單日記帳** 頁面中登記和過帳不同消耗類型。 **資產管理** 中的日記帳設定用於在 **專案管理和會計** 模組中為工時、品項和費用分別建立和過帳日記帳。

有些情況下，您可能可以在工單中新增或刪除預測明細。 對工單生命週期狀態、關聯的專案類型和與專案類型關聯的階段規則之設定決定是否可以新增或編輯日記帳明細。 在[預測、工單和專案](../integration-to-project-management-and-accounting/forecasts-work-orders-and-projects.md)中了解有關工單生命週期狀態和相關專案階段的詳細資訊。

>[!NOTE]
>可以為工單生命週期狀態設定日記帳自動過帳。 參考[工單生命週期狀態](../setup-for-work-orders/work-order-lifecycle-states.md)以了解更多資訊。

1. 按一下 **資產管理** > **一般** > **工單** > **所有工單** 或 **進行中工單**。

2. 選擇工單，然後按一下 **日記帳**。

3. 按一下 **從預測複製** 以傳輸可能與該工單關聯的所有預測明細。 可以選擇要傳輸哪些消耗類型。

4. 視需要，可透過按一下 **新增明細** 並在明細中填入資料，在相關 FastTab 中新增更多消耗明細。

5. 按一下 **驗證日記帳**，以在過帳前驗證日記帳明細。

6. 按一下 **過帳日記帳** 以過帳日記帳明細。

7. 過帳耗用日記帳後，您可以更新工單生命週期狀態。 例如，要表示工單已完成，可以將生命週期狀態更新為「已結束」。

    - 在 **工單日記帳** 頁面頂部的 **顯示** 欄位中，選擇要查看哪些日記帳明細：**全部**、**未過帳** 或 **已過帳**。 已過帳日記帳在 **已過帳** 核取方塊中具有勾選標記。  
    - 在工單日記帳中建立品項明細後，將把與品項關聯的產品維度和追蹤維度自動傳輸到這個日記帳明細。  

下面的螢幕擷取畫面顯示 **工單日記帳** 中工單的工時和品項登記之範例。

![圖 1。](media/01-consumption.png)


## <a name="split-hours-on-work-orders-with-several-work-order-jobs"></a>分割具有多個工單作業的工單

如果工單中包含多個工單作業，則可使用 **分割時數** 功能登記工時，這表示可以將一個工時登記明細平均分配給每個工單作業。

1. 按一下 **資產管理** > **一般** > **工單** > **所有工單** 或 **進行中工單**。

2. 選擇工單，然後按一下 **日記帳**。

3. 選擇要分割的工時登記明細，然後按一下 **分割時數**。

4. 將在 **工單維護作業的分割時數** 對話方塊的 **工作人員** 欄位中自動顯示已登錄工作人員的姓名。 如果需要，可以選擇其他工作人員。

5. 在 **類別** 欄位中為工時登記選擇類別。

6. 在 **工時** 欄位中插入要分割的工時數量。

    ![圖 2。](media/02-consumption.png)

7. 按一下 **確定**。

*範例：* 在下面的螢幕擷取畫面中，顯示包含三個工單作業的工單日記帳明細。 已分割第一個明細 (其中包含三個工時)，並為每個工單作業登記一個工時。 建立這三個工時登記明細之後，可以決定如何處理原始工時登記明細 (此範例中為第一個明細)。 可以保持原樣或刪除它。 

![圖 3。](media/03-consumption.png)

## <a name="financial-dimensions-on-consumption-registrations"></a>消耗登記的財務維度

建立消耗登記時，將把與不同登記類型關聯的財務維度按特定順序加到登記中。 

- *工時和費用登記：* 首先加入來自日記帳標題的財務維度 (如果有)。 接著，加入來自關聯的工單專案的財務維度。 最後，加入來自資源 (工作人員) 的財務維度。

- *品項登記：* 首先加入來自日記帳標題的財務維度 (如果有)。 然後，加入來自關聯的工單專案的財務維度。 接下來，加入來自站點的財務維度。 最後，加入來自品項的財務維度。

>[!NOTE]
>對於所有三種登記類型，都將驗證財務維度組合，並且無效組合將為空白。 這是其他財務和營運應用程式的標準設定。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]