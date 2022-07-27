---
title: 負責的維護工人
description: 本主題說明如何在「資產管理」中設定負責的維護工人。
author: johanhoffmann
ms.date: 07/26/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetWorkerResponsible
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-07-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d68c9e6de6e9d62d1dea95c747b17900d343e7324857dcfc083d48e5c1006b0e
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446796"
---
# <a name="responsible-maintenance-workers"></a>負責的維護工人

[!include [banner](../../includes/banner.md)]

 

負責的維護工人與資產類型、資產、功能位置、維護作業類型類別、維護作業類型、維護工作類型變體和貿易相關。 它們可用於工單和維護要求，以表示對應負責工單的維護工人的偏好。 (但是，這些維護工人不一定是計劃執行工單的工人。) 此功能為選用功能。 例如，它可用於為特定工作類型或工作區域選擇負責的工人或工人群組。

在工單生命週期或維護要求生命週期中，可以變更或更新負責的維護工人。 例如，此變更或更新可能與維護要求生命週期狀態或工單生命週期狀態的變更有關。

排程工單期間，*不* 使用 **負責的維護工人** 頁面上的設定。

> [!NOTE]
> 在資產管理中，您還可以設定在工單排程期間可能可以分配到工單的 *慣用* 維護工人。

在設定負責的維護工人之前，必須設定可供選擇的工人和維護工人群組。 有關如何設定工人和維護工人群組的資訊，請參閱[維護工人和工人群組](../setup-for-objects/workers-and-worker-groups.md)。

## <a name="set-up-responsible-maintenance-workers"></a>設定負責的維護工人

1. 選取 **資產管理** \> **設定**\>**工人**\>**負責的維護工人**。
2. 選取 **新增** 建立記錄。
3. 先建立預設的負責維護工人或負責維護工人群組設置，其中您只設定 **負責的維修工人群組** 欄位和/或 **負責的工人** 欄位。 將其餘欄位保留空白。 如果沒有其他更具體的組合與工單內容相符，則將在工單排程期間將使用此預設設定。

    > [!NOTE]
    > 在建立維護要求期間，**所有維護要求** 頁面中有負責的維護工人或負責的維護工人群組可選擇時，資產管理會瀏覽所有負責的維護工人記錄以檢查可能的相符對象。 一律先檢查最具體的組合。 換句話說，資產管理會先檢查 **貿易** 欄位的符合項目。 如果沒有找到符合項目，它會檢查 **維護作業類型變體** 欄位的符合項目。 如果沒有找到符合項目，它會檢查 **維護作業類型** 欄位的符合項目，依此類推。 正如您在頁面配置中看到的那樣，此行為代表為了尋找最具體的組合，資產管理從右到左檢查每個記錄，以尋找相符項目 (依次檢查 **貿易**、**維護作業類型變體**、**維護作業類型**、**維護作業類型類別**、**功能位置**、**資產**，最後檢查 **資產類型**)。 如果未找到符合項目，則會使用這七個欄位沒有選擇的預設記錄。

下圖顯示 **負責的維護工人** 頁面範例。

![負責的維修工人頁面。](media/08-setup-for-requests.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]