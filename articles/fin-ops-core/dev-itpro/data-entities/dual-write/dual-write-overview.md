---
title: 雙重寫入概述
description: 本主題概述了雙重寫入，它提供了 Customer Engagement 應用程式與財務和營運應用程式之間的近乎即時的互動。
author: RamaKrishnamoorthy
ms.date: 02/06/2020
ms.topic: overview
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: f39322a0c2ef50ef2bbeb256c80096e0687c4642
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8460365"
---
# <a name="dual-write-overview"></a>雙重寫入概述

[!include [banner](../../includes/banner.md)]





## <a name="what-is-dual-write"></a>什麼是雙重寫入？

雙重寫入是一種立即可用的基礎結構，可在 Customer Engagement 應用程式與財務和營運應用程式之間提供近乎即時的互動。 當有關客戶、產品、人員和營運的資料超出應用程式邊界時，組織中的所有部門都將獲得授權。

雙重寫入在財務和營運應用程式和 Dataverse 之間提供緊密耦合的雙向整合。 財務和營運應用程式中的任何資料更改都會導致對 Dataverse 的寫入，Dataverse 中的任何資料更改都會導致對財務和營運應用程式的寫入。 這種自動化的資料流程提供了跨應用程式的整合使用者體驗。

![應用程式之間的資料關係。](media/dual-write-overview.jpg)

雙重寫入有兩個方面：*基礎設施* 方面和 *應用程式* 方面。

### <a name="infrastructure"></a>基礎結構

雙重寫入基礎架構可擴展且可靠，並包括以下主要函數：

+ 應用程式之間的同步和雙向資料流程
+ 同步，以及播放、暫停和追趕模式，以支援在線和離線/非同步模式下的系統。
+ 能夠在應用程式之間同步初始資料
+ 資料管理員的活動和錯誤記錄的組合視圖
+ 能夠設定自訂警報和閾值，以及訂閱通知
+ 用於過濾和轉換的直觀使用者介面 (UI)
+ 能夠設定和查看資料表相依性和關係
+ 標準和自訂表格和地圖的可擴展性
+ 可靠的應用程式生命週期管理
+ 為新客戶提供立即可用的安裝體驗

### <a name="application"></a>應用程式

雙重寫入在財務和營運應用程式中的概念與 Customer Engagement 應用程式中的概念之間建立對應。 此整合支援以下案例：

+ 整合的客戶主資料
+ 存取客戶忠誠度卡和獎勵積分
+ 統一的基準產品體驗
+ 對組織階層的認識
+ 整合的廠商主資料
+ 存取財務和稅務參考資料
+ 按需價格引擎體驗
+ 整合的潛在客戶到現金體驗
+ 能夠透過現場代理為內部資產和客戶資產提供服務
+ 整合的採購到付款體驗
+ 客戶資料和文件的整合活動和註釋
+ 能夠查看現有庫存可用性和詳情
+ 專案到現金的體驗
+ 透過合作對象概念處理多個地址和角色的能力


## <a name="top-reasons-to-use-dual-write"></a>使用雙重寫入的主要原因

雙重寫入提供跨 Microsoft Dynamics 365 應用程式的資料整合。 這個強大的架構連結環境並使不同的業務應用程式能夠協同工作。 以下是您應該使用雙重寫入的主要原因：

+ 雙重寫入在財務和營運應用程式與客戶業務開發應用程式之間提供緊密耦合、近乎即時的雙向整合。 這種整合使 Microsoft Dynamics 365 成為您所有商業解決方案的一站式商店。 使用 Dynamics 365 Finance 和 Dynamics 365 Supply Chain Management 但使用非 Microsoft 解決方案進行客戶關係管理 (CRM) 的客戶正在轉向 Dynamics 365 以獲得雙重寫入支援。
+ 來自客戶、產品、營運、專案和物聯網 (IoT) 的資料透過雙重寫入自動流向 Dataverse。 此連線對於對 Power Platform 擴展感興趣的企業很有用。
+ 雙重寫入基礎架構遵循無代碼/低代碼原則。 擴展標準表到表對應並包含自訂對應需要最少的工程工作量。
+ 雙重寫入同時支援線上模式和離線模式。 Microsoft 是唯一一家提供線上和離線模式支援的公司。

## <a name="what-does-dual-write-mean-for-developers-and-architects-of-customer-engagement-apps"></a><a id="developer-architect"></a>雙重寫入對客戶業務開發應用程式的開發人員和架構師意味著什麼？

雙重寫入可自動執行財務和營運應用程式和 Customer Engagement 應用程式之間的資料流程。 雙重寫入由兩個安裝在 Dataverse 上的 AppSource 解決方案組成。 這些解決方案擴展了 Dataverse 上的資料表結構描述、外掛程式和工作流程，以便它們可以擴展到 ERP 大小。 為了成功實施，Customer Engagement 應用程式的開發人員和架構師必須了解這些變化，並與財務和營運應用程式的鄉對方協作。

為了與財務和營運應用程式建立同位關係，雙重寫入在 Dataverse 結構描述中進行了一些關鍵更改。 如果您了解該方案，則可以避免將來進行一些設計和開發復工。

+ 安裝雙重寫入 AppSource 套件後，Dataverse 會有公司、合作對象等新概念。 這些概念可幫助基於 Dataverse 構建的應用程式 (包括 Dynamics 365 Sales、Dynamics 365 Marketing、Dynamics 365 Customer Service 和 Dynamics 365 Field Service) 與財務和營運應用程式無縫互動。

+ 統一和擴展活動和註釋，以支援 C1s (系統使用者) 和 C2s (系統客戶)。

+ 若要防止在財務和營運應用程式和 Dataverse 之間的貨幣傳輸期間遺失資料，您將能夠擴展 Customer Engagement 應用程式的貨幣資料類型中的小數位數。 該函數將現有行自動轉換為中繼資料層的新擴展狀態。 在這個過程中，將貨幣值轉換為十進位資料而不是貨幣資料，貨幣值支援 10 位小數。 此函數為選取性，不需要超過 4 個小數位精度的組織不需要選取加入。 如需相關資訊，請參閱[雙重寫入的貨幣資料類型移轉](currrency-decimal-places.md)。

+ [日期有效性](../../dev-tools/date-effectivity.md)將被新增到 Dataverse。 它將支援同一張表上的過去、現在和未來的資料。

+ 產品[單位換算](../../../../supply-chain/pim/tasks/manage-unit-measure.md)支援產品、報價、訂單和發票。

如需即將發生之更改的相關資訊，請參閱[雙重寫入的新內容或變化](whats-new-dual-write.md)。



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
