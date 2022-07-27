---
title: 組織和組織階層架構概觀
description: 組織階層表示組成企業的組織之間的關係。
author: sericks007
ms.date: 01/03/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: OMHierarchyManager, OMOperatingUnit,
audience: Application User
ms.reviewer: sericks
ms.custom:
- "17291"
- intro-internal
ms.assetid: 76b7ca45-93d4-45cc-b191-66ee63afa1fd
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c8e8f2c2004582f42c3f464fedf9f3d049b5278f
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/15/2022
ms.locfileid: "8460393"
---
# <a name="organizations-and-organizational-hierarchies-overview"></a>組織和組織階層架構概觀

[!include [banner](../includes/banner.md)]

組織是一起工作以執行業務流程或實現目標的一群人。 組織階層表示組成企業的組織之間的關係。

## <a name="organizations"></a>組織

您可以定義以下類型的內部組織：法律實體、營運單位和團隊。

一切內部組織都是 **參與方** 的實體類型。 因此，這些組織使用通訊錄來儲存地址和聯絡資訊。 一方，可以是個人或組織，可以屬於一個或多個通訊錄。

### <a name="legal-entities"></a>法律實體

法律實體是具有註冊或法定法律結構的組織。 法律實體可以簽訂法律合同，並被要求準備報表其業績的報表。

公司是一種法律實體。 目前，公司是您可以建立的唯一一種法律實體，並且每個法律實體都與一個公司 ID 相關聯。 存在這種關聯是因為程式中的某些函數區域在其資料模型中使用公司 ID 或 DataAreaId。 在這些函數領域，公司被用作資料安全的邊界。 使用者只能存取他們目前登入的公司的資料。

### <a name="operating-units"></a>營運單位

營運單位是用於劃分企業中經濟資源和營運流程控制權的組織。 營運單位的人員有責任最大限度地利用稀缺資源、改進流程並說明他們的績效。

營運單位的類型包括成本中心、事業單位、價值流、部門和商業管道。 下表提供了有關每種營運單位的更多資訊。

| 營運單位類型 | 描述 | 用途 |
|---------------------|-------------|---------|
| 成本中心         | 管理人員對預算支出和實際支出負責的營運單位。 | 用於跨法律實體的業務流程的管理和動作控制。 |
| 事業單位       | 為實現策略商業目標而建立的半自主營運單位。 | 用於基於組織獨立於法律實體服務的行業或產品線的財務報表。 |
| 價值流        | 控制一個或多個生產流程的營運單位。 | 常用於精益製造，以控制向消費者提供產品或服務所需的活動和流程。 |
| 部門          | 代表執行特定工作 (例如銷售或會計) 的組織的類別或函數部分的營運單位。 | 用於報表函數區域。 一個部門可能有損益責任，並且可能由一組成本中心組成。 |
| 零售管道      | 代表實體店、線上商店或呼叫中心的營運單位。 | 用於法律實體內部或跨法律實體的一家或多家商店的管理和營運控制。 |

### <a name="teams"></a>團隊

團隊是成員分享共同責任、利益或目標的組織。 團隊不能在組織階層中使用。

## <a name="organizational-hierarchies"></a>組織性階層

設定組織階層以從不同角度查看和報表您的業務。 例如，您可以為稅務、法律或法定報表設定法律實體階層。 建立基於營運單位的階層，以報表法律上不要求但用於內部控制的財務資訊。 例如，您可以建立採購階層來控制採購原則、規則和業務流程。

> [!NOTE]
> 將營運單位新增到階層後，將無法刪除該營運單位。 

每個階層都有一個用途。 階層的目的決定了可以包含在階層中的組織類型。 目的還決定了可以在哪些應用程式場景中使用階層。

階層中的組織可以分享參數、原則和交易。 組織可以繼承或覆寫其父組織的參數。 但是，共用的主資料 (例如產品和通訊錄) 適用於整個組織，並且不能被單個組織覆寫。 建立組織和階層需要仔細規劃。 如需相關資訊，請參閱[規劃您的組織階層](plan-organizational-hierarchy.md)。

## <a name="additional-resources"></a>其他資源
- [規劃您的組織階層](plan-organizational-hierarchy.md)
- [建立組織階層](tasks/create-organization-hierarchy.md)
- [建立法律實體](tasks/create-legal-entity.md)
- [建立營運單位](tasks/create-operating-unit.md)



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
