---
title: 工單的維護停機時間
description: 本主題描述如何為在工單中選擇的資產建立維護停機時間登記。
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
ms.openlocfilehash: 38c47a47fdf64c1d3601f6f3f7b84bf128823ec2ceb0c50e586822f6bdb97906
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447039"
---
# <a name="maintenance-downtime-for-work-orders"></a>工單的維護停機時間

[!include [banner](../../includes/banner.md)]


您可以為在工單中選擇的資產建立維護停機時間登記。 如果您想在生產區域的一或多台機器上登記維護停機時間，此功能便很實用。 您會先建立要使用的維護停機原因代碼，例如 **Breakdown** 和 **Planned stop**。 此一步驟可在 **維護停機原因代碼** 頁面完成。 然後，您可以在 **維護停機時間** 頁面建立維護停機時間登記，並新增相關的維護停機原因代碼。

## <a name="create-maintenance-downtime-reason-codes"></a>建立維護停機原因代碼

1. 選擇 **資產管理** > **設定** > **工單** > **維護停機原因代碼**。

2. 選擇 **新增**。

3. 在 **維護停機原因代碼** 欄位中，輸入維護停機時間原因代碼的識別碼。

4. 在 **名稱** 欄位中，輸入名稱。

5. 如果原因代碼應包含在資產的關鍵績效指標 (KPI) 計算中，則選取 **包括 KPI** 核取方塊。 一般來說，計劃性的生產暫停不應包含在 KPI 計算中，因為它們不會影響預期績效。

6. 選擇 **儲存**。

下圖顯示 **維護停機原因代碼** 頁面的範例。

![圖 1。](media/15-work-orders.png)

在您建立要使用的維護停機時間原因代碼後，您可以為工單和資產建立維護停機時間登記。


## <a name="create-maintenance-downtime-registrations"></a>建立維護停機時間登記

1. 按一下 **資產管理** > **通用** > **工單** > **所有工單** 或 **使用中的工單**。

2. 選擇工單，然後在 **工單** 索引標籤上的 **資產** 群組中，選擇 **維護停機時間**。

3. 選擇 **新增**。

4. 在 **開始** 和 **結束** 欄位中，定義維護停機時間登記的日期和時間間隔。

>[!NOTE]
>在您離開 **結束** 欄位時，以小時為單位的持續時間會自動插入到 **持續時間** 欄位。

5. 在 **維護停機原因代碼** 欄位中，選擇一個原因代碼。

6. 重複步驟 3 到 5，以新增更多登記。

7. 選擇 **儲存**。

下圖為維護停機時間登記的範例。

![圖 2。](media/16-work-orders.png)

用於計算維護停機時間登記的行事曆，取決於您在資產和參數設定中的選擇。 如果在 **所有資產** 頁面的 **固定資產** FastTab 的 **資源** 欄位中為資產選擇了資源，則會使用為關聯的資源群組設定的行事曆，如下圖所示。

![圖 3。](media/17-work-orders.png)

如果沒有在資產上選擇資源，則會使用在 **資產管理參數** 頁面上選取的標準行事曆，如下圖所示。

![圖 4。](media/18-work-orders.png)

如要查看所有維護停機時間登記的概觀，請按一下 **資產管理** > **查詢** > **維護停機時間**。

>[!NOTE]
>在 **資產管理** 模組中使用的所有日曆，可在 **組織管理** > **設定** > **行事曆** > **行事曆** 中進行設定。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]