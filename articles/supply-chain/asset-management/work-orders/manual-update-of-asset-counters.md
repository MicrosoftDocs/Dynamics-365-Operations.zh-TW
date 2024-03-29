---
title: 資產計數器的手動更新
description: 本主題說明資產管理中手動更新資產計數器。
author: johanhoffmann
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetCounter
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 74d840cbb064018560a6abc2823f520c2f3179ac42b149c0507c9421a4e73391
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447267"
---
# <a name="manual-update-of-asset-counters"></a>資產計數器的手動更新

[!include [banner](../../includes/banner.md)]



計數器是用於建立資產上的登記，例如登記資產運行的時數，或是登記已生產的數量。

可以將計數器類型選擇，設定為繼承計數器的值。 換句話說，在 **計數器** 頁面 **一般** FastTab 上的 **繼承資產計數器值** 選項設定為 **是** (**資產管理** > **設定** > **資產類型** > **計數器**)。 在這種情況下，當您建立該類型的新計數器行時，每個使用相同計數器類型的子資產都會自動更新。

在 **所有資產** 頁面，您可以根據資產的讀數，在資產上建立時數或數量的計數器登記。

1. 選擇 **資產管理** > **通用** > **資產** > **全部資產**。

2. 選擇資產，然後在動作窗格中的 **資產** 索引標籤，**預防性** 群組中，選擇 **計數器**。 這 **資產計數器** 頁面，會顯示已在所選資產上進行的所有先前計數器登記的清單。

3. 選擇 **新增** 建立新的登記。 系統會自動在 **資產** 欄位中輸入資產識別碼。

4. 在 **計數器** 欄位中，選擇相關的計數器。 只有與資產上選擇的資產類型相關的計數器可供選擇。 系統會自動在 **單位** 欄位中輸入相關單位。

5. 在 **已登記** 欄位，選取計數器登記的日期和時間。

6. 在 **值** 欄位，輸入自上次計數器登記以來的編號。 或者，在 **會總值** 欄位，輸入總計數。

請注意以下幾點：

- 如果您在資產上實際安裝了新計數器，則必須在 **資產計數器** 頁面登記變更。 接著，您必須建立兩個具有相同時間戳記的註冊行。 第一行必須是您要替換的計數器。 與新計數器相關的行上，選擇 **計數器重設** 核取方塊。 在 **總計** 欄位，總計數是該計數器類型上所有註冊值的計數器總數的總和。

- 如果 **計數器重設** 在使用具有「從...」或「一旦達到...」間隔類型的維護計劃的資產上選中核取方塊，計數器在新計數器行上仍處於使用中狀態，因為您建立了單獨的計數器行並從一個新的計數器重新開始。

下圖顯示 **資產計數器** 頁面的範例。

![圖 1。](media/11-work-orders.png)

在 **資產計數器** 頁面 (**資產管理** > **查詢** > **資產** > **資產計數器**)，您可以根據需要同時對多個資產進行計數器註冊。

>[!NOTE]
>您可以設定一個範圍來定義手動計數器註冊中的偏差。 如果註冊超出定義的範圍，您還可以指定顯示的訊息類型。 如需如何設定計數器的詳細資訊，請參閱[計數器](../setup-for-objects/counters.md)。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]