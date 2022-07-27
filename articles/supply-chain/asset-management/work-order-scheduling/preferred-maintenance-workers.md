---
title: 設定首選維護工人
description: 本主題說明如何在資產管理中設定首選維護工人。
author: johanhoffmann
ms.date: 08/19/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetWorkerPreferred
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 511d875baed029df9083da36baf6c48ca4b7abf866ae569038b554bf594473c8
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446829"
---
# <a name="set-up-preferred-maintenance-workers"></a>設定首選維護工人

[!include [banner](../../includes/banner.md)]

 

在工單排程期間，您可以選擇指派哪個維護工人或工人群組來完成該工單。 此功能的使用是選擇性的，但它可以幫助您根據工人的技能和能力選擇最合格的維護工人來完成工作。 只有在排程時間可調用的維護工人才會被安排。 如果首選維護工人設定在排程期間與工單匹配，但該維護工人被分配到其他工作，則該工單將被安排給另一個可調用的維護工人。

在可以設定首選維護工人之前，您必須先設定維護工人和工人群組。 有關如何設定維護工人和工人群組的描述，請參閱[維護工人和工人群組](../setup-for-objects/workers-and-worker-groups.md)。

## <a name="set-up-preferred-workers"></a>設定首選工人

首選維護工人或工人群組可以與以下一項或多項相關：

- 貿易  
- 維護作業變體  
- 維護作業類型  
- 維護作業類型類別  
- 資產  
- 資產類型  

您為同一記錄所做的選擇越多，您的設定就越具體。

1. 按一下 **資產管理** > **設定** > **工人** > **首選維護工人**。

2. 按一下 **新建** 建立新記錄。

3. 首先建立一個“預設”維護工人或工人群組。 這意味著您只在 **首選維護工人群組** 欄位或 **首選維護工人** 欄位選擇。 在下面的螢幕擷取畫面中，您會在第一個記錄中看到一個範例，其中“要求”被選為 **首選維護工人群組**。

    [!NOTE] 如果沒有其他更具體的組合與工單內容相符，則在工單排程期間將使用該預設設定。

4. 重複步驟 2 建立新記錄。 根據首選工人或工人群組的詳細程度進行所需的選擇。 

    *範例：* 在下面的螢幕擷取畫面中，在第六個記錄中，維護工人 Shawn Richardson 被選為首選工人。 如果他在排定時間可調用，則在安排包含資產“CH-BP1-03-02”和維護作業類型“設施評估”的工單時，將自動選擇他。

    [!NOTE] 一般來說，在工單排程期間選擇了首選維護工人時，資產管理會檢查所有 **首選維護工人** 記錄以檢查可能的符合對象，一律先檢查最具體的組合。 如果未找到符合對象，則會使用 **首選維護工人群組** 欄位或 **首選維護工人** 欄位中具有選擇的“預設”記錄。

![圖 1。](media/02-work-order-scheduling.png)

您還可以設定 *負責的* 維護工人，該維護工人可在維護要求或工單建立時被選擇。 如果需要的話，您可以編輯 **所有工單** 和 **所有維護要求** 中的選擇。 如需詳細資訊，請參閱[負責的維護工人](../setup-for-maintenance-requests/responsible-workers.md)。

在工單排程期間，計算不同的分數以確定哪些工人應該完成與工單相關的工作（那些分數設定在 **資產管理參數** > **工單排程** 連結）。 如果在工單排程過程中，有兩名或多名首選維護工人或負責的維護工人得分相同，則隨機選擇一名工人。 否則，一律指派給得分最高的工人完成工單。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]