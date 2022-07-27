---
title: 服務等級和描述
description: 本主題說明資產管理中的服務等級和描述。
author: johanhoffmann
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetObjectServiceLevel, EntAssetWorkOrderStandardDescription, EntAssetWorkOrderServiceLevel, EntAssetServiceLevelLookup
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 32e6dd6ba7291e8ea1cb78eeed2d8e2fcec0f6dd3cbd039336be0169730101ba
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447102"
---
# <a name="service-level-and-description"></a>服務等級和描述

[!include [banner](../../includes/banner.md)]

 

建立工單時，您可能希望為其定義服務等級並為其新增一般描述。 您可以在 **工單服務等級** 頁面建立工單服務等級，在 **工單描述** 頁面上建立描述。

## <a name="create-a-service-level"></a>建立服務等級

1. 選取 **資產管理** \> **設定** \> **工單** \> **服務等級**。
2. 選取 **新增**。
3. 在 **服務等級** 欄位輸入服務等級 (例如，數字)。
4. 在 **名稱** 欄位中，輸入名稱。

    在 **工單** FastTab，您可以定義預期的開始和結束日期和時間。 此 FastTab 上的欄位定義工單應該開始和結束的期間。 它們用於手動建立的工單和根據維護要求建立的工單。 

5. 在 **開始日期** 欄位中，輸入天數以定義工單應開始的期間。 天數從工單的建立日期開始計算。 例如，如果工單應在建立時開始，請輸入 **0**。 如果工單應在建立後的一週內開始，請輸入 **7**。
6. 若要設定工單的開始時間，除了開始日期之外，還需要將 **設定開始時間** 選項設定為 **是**。 然後在 **開始時間** 欄位輸入開始時間。 如果將選項設定為 **否**，則使用目前時間。
7. 在 **結束日期** 欄位中，輸入天數以定義工單應結束的期間。 天數從工單的開始日期開始計算。 例如，如果工單應在其開始日期的一週內結束，請輸入 **7**。
8. 若要設定工單的結束時間，除了結束日期之外，還需要將 **設定結束時間** 選項設定為 **是**。 然後在 **結束時間** 欄位輸入結束時間。 如果將選項設定為 **否**，則使用目前時間。
9. 選取 **儲存**。

![工單服務等級頁面。](media/19-setup-for-work-orders.png)

## <a name="create-a-description"></a>建立描述

1. 選取 **資產管理** \> **設定** \> **工單** \> **描述**。
2. 選取 **新增**。
3. 在 **描述** 欄位中，輸入描述。
4. 選取 **儲存**。


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]