---
title: 停用生產流程版本
description: 當不再需要啟用的生產流程版本時，可以將其停用。
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LeanProductionFlow
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1691dc644e2e191a9e74980784d6dcf741dcd598
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448938"
---
# <a name="deactivate-a-production-flow-version"></a>停用生產流程版本

[!include [banner](../../includes/banner.md)]

當不再需要啟用的生產流程版本時，可以將其停用。 只有當所有的看板規則和活動都已經結束，且不會再次啟用時，您才能使用此選項。 請注意，與此生產流程版本相關的所有看板規則的到期日期，將更新為當前日期和時間。 

若要修改活動的生產流程版本，請考慮為活動版設定到期日期並建立新版本。 這可讓您在準備新版本，和相關看板規則的同時繼續生產作業。 

若要使活動的生產流程版本到期，您需要設定到期日期。 從這個意義上說，停用更像是例外狀況，而不是規則。 

對於此過程，您需要具有可停用版本的生產流程。 除非您 100% 肯定該版本已完全過時，否則請勿在生產環境中嘗試此操作。


## <a name="deactivate-a-production-flow-version"></a>停用生產流程版本
1. 前往生產控制 > 設定 > 精益生產流程 > 生產流程。
2. 在清單中，尋找並選擇所需紀錄。
3. 在列表中，按一下所選行中的連結。
4. 在清單中，尋找並選擇所需紀錄。
5. 按一下停用。
    * 如果您不是 100% 肯定此生產流程版本已過時，請不要繼續。 按一下確定，會將使所有活動的看板規則失效，並立即停止該生產流程版本的所有生產和補貨活動。  
6. 按一下確定。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]