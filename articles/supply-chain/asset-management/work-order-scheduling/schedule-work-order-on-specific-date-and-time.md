---
title: 將工單排程到特定日期和時間
description: 本主題說明如何在資產管理中將工單排程到特定日期和時間。
author: johanhoffmann
ms.date: 08/19/2019
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
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: d1264ea034789c9ce052b1da9a74a10dd910fac1a1c762d29bd06ca2063478d0
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447321"
---
# <a name="schedule-work-order-on-specific-date-and-time"></a>將工單排程到特定日期和時間

[!include [banner](../../includes/banner.md)]

 

如果必須將工單排程到特定日期 *和* 時間，可在資產管理中覆寫標準計劃流程，並為工單建立特定排程。

1. 按一下 **資產管理** > **一般** > **工單** > **所有工單** 或 **進行中工單**。

2. 在工單清單的 **工單** 資料行中，點選工單識別碼。

3. 按一下 **編輯**。

4. 在 **工單標題** FastTab 上，在 **預計開始** 和 **預期結束** 欄位插入開始和結束日期和時間。

    ![圖 1。](media/05-work-order-scheduling.png)

5. 在 **一般** 索引標籤上，點選 **排程** 以使用標準排程流程，如果想將工單指派給特定工作人員，則點選 **分派**。

6. 若要覆寫任何現有的產能預留以確保將工單排程在預期期間，請在 **排程工單** 對話方塊 >**有限產能** 區段。 這代表排程流程將忽略現有的產能預留，因為工單必須在預期的開始時間開始。

    ![圖 2。](media/06-work-order-scheduling.png)

7. 按一下 **確定** 以開始排程。

8. 如果排程流程導致重複預訂，您將在畫面上看到一則訊息，且可以調整相關的工單。

>[!NOTE]
>若要將維護工人安排給工單，則該維護工作人員必須在預期的開始日期和時間有空。 工作人員可用性在[工作人員行事曆](../work-order-scheduling/maintenance-worker-calendar-and-scheduling.md)上設定。 



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]