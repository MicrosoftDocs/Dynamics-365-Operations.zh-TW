---
title: 資產計數器的自動更新
description: 本主題說明資產管理中自動更新資產計數器。
author: johanhoffmann
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 9a3814a575fbe4379b59723f269d83379a253ede71962c0c82b5f4cc55d36e6c
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446850"
---
# <a name="automatic-update-of-asset-counters"></a>資產計數器的自動更新

[!include [banner](../../includes/banner.md)]

有關手動登記資產計數器的資訊，請參閱[資產計數器的手動更新](../work-orders/manual-update-of-asset-counters.md)。 有關如何設定資產計數器的資訊，請參閱[計數器](../setup-for-objects/counters.md)。

計數器值也可以根據生產時數或生產數量 (即已生產的數量) 從生產登記中自動更新。 此更新可在 **更新資產計數器** 頁面完成。 您可以設定 **從日期** 參數來更新一項或多項資產。 此參數指定生產登記 (生產時數或生產數量) 的開始日期。 換句話說，它指定了計數器值的更新日期。

所有資產，只要與資源相關，*以及* 具有根據生產時數或生產數量更新的資產計數器，將包含在自動更新中。 將建立新的計數器值。

根據生產數量的計數器，計數內容包括登記的合格數量和錯誤數量。 如果生產數量登記的單位與計數器上的單位不同，則會轉換數量以對應計數器單位。

如前面提到的，可以從生產登記更新自動計數器。 因此，要自動更新計數器的資產必須與資源 (機器) 相關。 在資源上登記生產數量或生產時數後，則可以更新相關資產計數器。

1. 請選取 **資產管理** > **定期** > **資產** > **更新資產計數器**。

2. 在 **起始日期** 欄位，選取自動更新的開始日期。

    >[!NOTE]
    >此欄位中的日期是 **途程交易**(**產品控制** > **查詢和報告** > **生產** > **途程交易** > **實際日期** 欄位)中的「在製品」日期。

3. 在 **要包括的記錄** FastTab，您可以選取特定資產、資產類型或資源進行自動更新。 選取 **篩選**，並進行相關選擇。

4. 您可於 **在背景執行** FastTab 根據需要將自動更新設定為批次作業。

    下圖顯示了一個範例的 **更新資產計數器** 對話方塊。

    ![圖 1。](media/12-work-orders.png)

5. 選取 **確定**。 

資產計數器自動更新完成後，您可以在 **資產計數器** 頁面檢視相關資產的計數器登記。 請選取 **資產管理** > **一般** > **資產** > **所有資產**，選取資產，然後在動作窗格上的 **資產** 索引標籤，**預防性** 群組，選取 **計數器**。

在 **資產總值** 頁面，您可以概覽所有資產及所有計數器類型的最新登記。 請選取 **資產管理** > **查詢** > **資產** > **資產總值**。 此頁面與 **資產計數器** 頁面相似，但您不能新增或編輯註冊。 它僅用於摘要。

下圖顯示了一個範例的 **資產總值** 對話方塊。

![圖 2。](media/13-work-orders.png)

請注意以下幾點：

- 您仍然可以為自動更新的計數器類型建立手動計數器值登記。 更多詳細資訊，請參閱[資產計數器的手動更新](../work-orders/manual-update-of-asset-counters.md)。

- 您可以設定與另一個計數器相關的計數器。 在這種情況下，當一個計數器更新時，相關的計數器會同時自動更新。 更多如何設定相關計數器的資訊，請參閱[計數器](../setup-for-objects/counters.md)。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]