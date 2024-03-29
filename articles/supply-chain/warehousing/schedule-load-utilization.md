---
title: 排程負載利用率
description: 本主題說明如何設定和排程倉庫的負載。
author: Mirzaab
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WMSSpaceUtilSetup
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 728cf6e0b1bce660328f970176c218f66646ec8a
ms.sourcegitcommit: fd6270dc7f49f93a8155d2b827153b13edb7be8a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/09/2021
ms.locfileid: "8449529"
---
# <a name="schedule-load-utilization"></a>排程負載利用率

[!include[banner](../includes/banner.md)]

您可以為所選位置類型排程負載利用率，還可以預測目前和未來的負載利用率。 您可以預測一個或多個站點、負載單元 (區域或倉庫) 或區域和倉庫組合的負載。

## <a name="schedule-and-view-the-load-for-a-warehouse-or-site"></a>排程和查看倉庫或站點的負載

若要排程站點、倉庫或區域的負載，您可以建立空間利用率設定並將其與主計劃相關聯。

在設定空間利用率時可使用位置類型 (例如 **散裝位置** 和 **揀貨位置**) 來指定應如何預測空間利用率。 您還可以指定儲存負載模式，例如 **區域**。

未來空間利用率的預測是以相關主計劃上的計算資訊為基礎。 主計劃預測生產和營運的入庫和出庫訂單的資源計劃。 可用空間的預測是以空間利用率設定和所選主計劃之間的關係為基礎。

透過使用您在空間利用率設定中選擇的儲存負載模式，您可以指定是否應為每個倉庫或區域預測負載，或者預測是否應包含有關倉庫和區域的資訊。 您還可以指定是否應在負載利用率計算中排除鎖定位置。

您可以透過產生 **倉庫負載利用率** 報表預測空間利用率。 產生此報告時，您可以指定是否應該為每個站點、跨站點或所選負載單位 (例如區域或倉庫) 預測負載利用率。

### <a name="create-a-space-utilization-setup-for-a-warehouse"></a>為倉庫建立空間利用率設定

1. 選擇 **庫存管理** \> **設定** \> **倉庫監視** \> **空間利用率**。
2. 選擇 **新增** 以建立空間利用率設定。 指定新設定的識別碼和名稱。
3. 在 **儲存負載模式** 欄位中，選擇空間利用率概觀是否應按倉庫、區域或倉庫和區域顯示資訊。
4. 將 **排除鎖定位置** 選項設定 **是**，將在計算可用空間時排除鎖定的庫存位置。 您可以在 **庫存位置** 頁面 **其他** FastTab 上的 **輸入已鎖定** 或 **輸出已鎖定** 中，指定位置鎖定原因來鎖定輸入和輸出的庫存位置。
5. 在 **位置類型** FastTab 上，選擇要包含在空間利用率計算中的位置類型。 您必須為預測選擇至少一個位置類型。

### <a name="associate-a-space-utilization-setup-with-a-master-plan"></a>將空間利用設定與主計劃相關聯

1. 選擇 **庫存管理** \> **定期工作** \> **排程負載利用率**。
2. 在 **主計劃** 欄位中選擇主計劃。
3. 在 **天數** 欄位中，指定要包括在目前和未來工作負載預測中的天數。
4. 在 **空間利用率** 欄位中，選擇空間利用率設定以用於預測目前和未來的工作負載。

### <a name="specify-the-load-utilization-projection-and-view-information"></a>指定負載利用率預測並查看資訊

1. 選擇 **庫存管理** \> **查詢和報表** \> **實際庫存報告** \> **倉庫負載利用率**。
2. 在 **顯示依據** 欄位中，選擇空間利用率預設的等級：

    - **站點** – 預測每個站點的空間利用率。 例如，如果您想查看一個站點的所有倉庫，以便平衡倉庫之間的空間利用率，則此預測會很有用。
    - **負載單位** – 預測區域或倉庫的空間利用率。 然後根據您建立空間利用率設定時在 **空間利用率** 頁面 **儲存負載模式** 欄位中選擇的值預測可用空間。

3. 根據您在上一步中選擇的值，執行以下其中一個步驟：

    - 如果在 **顯示依據** 欄位中選擇的是 **站點**，則 **站點** 欄位可用。 選擇一個或多個要包含在預測中的站點。
    - 如果在 **顯示依據** 欄位中選擇的是 **負載單位**，則 **負載單位** 欄位可用。 選取 [負載單位]。

4. 在 **負載類型** 欄位中，選擇 **體積** 或 **重量** 以指定要預測的空間所屬的倉庫營運單位。
5. 在 **空間利用率設定** 欄位中，選擇應做為預測基礎的空間利用率設定。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]