---
title: 分佈式混合拓撲中的縮放單位
description: 本主題講述製造和倉庫管理工作負載的雲端和邊緣縮放單位。
author: cabeln
ms.date: 04/22/2021
ms.topic: article
ms.search.form: ScaleUnitWorkloadsWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: cabeln
ms.search.validFrom: 2021-04-13
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 30f455f37b5161878cf9c864b92966aa74da051f
ms.sourcegitcommit: b52ff5dfd32580121f74a5f262e5c2495e39d578
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/03/2022
ms.locfileid: "8450069"
---
# <a name="scale-units-in-a-distributed-hybrid-topology"></a>分佈式混合拓撲中的縮放單位

[!include [banner](../includes/banner.md)]

> [!IMPORTANT]
> 依據服務使用條款向您提供 Microsoft Dynamics 365 Supply Chain Management的縮放單位功能。 如需詳細資訊，請參閱 [Microsoft Dynamics 法律聲明資訊](https://go.microsoft.com/fwlink/?LinkID=290927)。
>
> 當您啟用雲端和邊緣縮放單位時，系統會確認您了解在雲端和邊緣縮放單位的設定和處理中，某些相關的資料可能儲存在美國的資料中心。 若要深入了解雲端和邊緣縮放單位的資料處理，請參閱本主題後面的[縮放單位管理程序時的資料處理](#data-processing-management)部分。

## <a name="core-value-proposition-for-a-distributed-hybrid-topology"></a>分佈式混合拓撲的核心價值主張

從事製造和配送的公司必須能夠 24/7 不間斷、大規模的執行關鍵業務流程。 分佈式混合拓撲支援公司即便偶爾面臨網路連線問題或延遲，仍能不間斷地執行關鍵任務型的製造和倉庫流程。

分佈式混合拓撲引入了 *縮放單位*，它可以在不同環境之間分散分佈車間和倉庫工作負載執行。 此功能有助於提高性能、防止服務中斷並最大化運轉時間。 以下增益集可為 Supply Chain Management 訂閱提供縮放單位：

- Dynamics 365 Supply Chain Management 雲端縮放單位增益集
- Dynamics 365 Supply Chain Management 邊緣縮放單位增益集

工作負載功能正以累加強化的方式持續發布中。

## <a name="scale-units-and-dedicated-workloads"></a>縮放單位和專用工作負載

縮放單位可增加專用處理能力來擴展您的核心 Supply Chain Management hub environment 中樞環境。 縮放單元可以在雲端中執行。 或者，它們可以在[邊緣](cloud-edge-edge-scale-units-lbd.md)執行，在您當地的設施中內部部署。

:::image type="content" source="./media/cloud_edge-HeroDiagram.png" alt-text="縮放單位與 Dynamics 365。":::

縮放單位提供彈性、可靠性和可擴展性給已指派的工作負載。 邊緣縮放單位可以暫時與雲端中樞環境斷開連接，工作人員繼續在邊緣內已指派的工作負載中工作。

一種 *工作負載* 是已定義的一組業務功能，可以去因素化並委派給一個縮放單位。 雖然倉庫管理的工作負載已經發佈，但製造執行的工作負載仍是預覽版。

您可以使用[縮放單位管理者入口網站](https://sum.dynamics.com)管理選定的工作負載其中樞環境和雲端縮放單位。 您還可以對每個縮放單元指派多個工作負載。 有關目前版本中，雲端縮放單位的先決條件和限制資訊，請參閱本主題後面的[雲端縮放單位的先決條件和限制](#cloud-scale-unit-prerequisites)部分。

### <a name="dedicated-warehouse-management-workload-capabilities-in-a-scale-unit"></a>縮放單位中的專屬倉庫管理工作負載功能

倉庫管理工作負載使您的倉庫作業能夠使用隔離式維護視窗在韌性環境中進行縮放和執行。 倉庫管理工作負載支援大多數企業中樞倉庫管理流程。 更多資訊，請參閱[雲端和邊緣縮放單位的倉庫管理工作負載](cloud-edge-workload-warehousing.md)。

### <a name="dedicated-manufacturing-execution-workload-capabilities-in-a-scale-unit"></a>縮放單位中的專屬製造執行工作負載功能

製造工作負載提供以下功能：

- 機器操作人員和車間主管可以存取運轉生產計劃。
- 機器操作人員可以離散執行並執行製造作業來讓計劃與現況相符。
- 車間主管可以調整運轉計劃。
- 工作人員可以在邊緣存取時間及出勤以打卡上班或打卡下班，可確保正確計算工資。

更多資訊，請參閱[雲端和邊緣縮放單位的製造執行工作負載](cloud-edge-workload-manufacturing.md)。

## <a name="considerations-before-you-enable-the-distributed-hybrid-topology-for-supply-chain-management"></a>在 Supply Chain Management 啟用分佈式混合拓撲之前的注意事項

啟用分佈式混合拓撲，您可以轉換 Supply Chain Management 雲端環境作為中樞。 您還可以關聯到在雲端或邊緣中設定成縮放單位的其他環境。

### <a name="prerequisites-and-limitations-for-cloud-scale-units"></a><a name="cloud-scale-unit-prerequisites"></a>雲端縮放單位的先決條件和限制

在縮放單位的目前版本中，某些功能尚不可用，但可能會在未來持續以遞增版本新增。

#### <a name="you-must-be-a-licensed-customer-of-supply-chain-management"></a>您必須是 Supply Chain Management 的授權客戶

若要加入分佈式拓撲，您必須擁有 Supply Chain Management 的授權。 您現有的雲端環境將成為混合拓撲中的中樞。 您可以將沙箱環境和生產環境都宣告為中樞環境，並且可以依據您取得的增益集新增縮放單位。

#### <a name="your-existing-project-must-be-administered-via-the-global-commercial-version-of-lcs"></a>現有的專案必須以 LCS 的全球商業版本進行管理

現有的 Microsoft Dynamics Lifecyle Services (LCS) 專案必須滿足以下版本要求：

- 現有的專案必須在 [lcs.dynamics.com](https://lcs.dynamics.com) 以 LCS 的全球商業版本進行管理。
- 不支援 LCS 的區域版本 (例如：[eu.lcs.dynamics.com](https://eu.lcs.dynamics.com)  和[fr.lcs.dynamics.com](https://fr.lcs.dynamics.com))。
- 不支援 LCS 的政府雲端版本。
- 不支援 LCS 的 Mooncake 版本。

#### <a name="your-current-production-environment-must-be-of-the-self-service-type-in-lcs"></a>目前的生產環境在 LCS 中必須是自助服務類型

目前的生產環境在 LCS 中必須標記為 **自助服務** 類型。 此類型表示您的 LCS 專案的租用戶已經轉換，並支援 Azure Service Fabric 託管模式。

> [!IMPORTANT]
> 不支援作為基礎結構即服務 (IaaS) 執行的環境類型。 在 LCS 中這些環境通常是 **Microsoft 管理** 類型。 如果您有這種類型的環境，請與您的 Microsoft 連絡人合作，了解 **自助服務** 類型的遷移日程。

Microsoft 正在將 Supply Chain Management 的所有雲端環境從 IaaS 模型轉換為託管在 Service Fabric 中的拓撲型。 這一舉措帶來了更好的可擴展性，並有助於簡化服務管理。 因此，部署和維護作業更快。 相同的，服務組件正在遷移到微服務概念，服務託管模型將從虛擬機器 (VM) 模型[轉換](/virtualization/windowscontainers/about/containers-vs-vm)到輕量級容器化架構。

最終，同一個 Service Fabric 型的容器化服務基礎結構將提供為的雲端服務執行個體和邊緣服務執行個體，無論執行個體是雲端中的中樞，還是雲端中或邊緣的縮放單位。

在進入支援縮放單位的混合拓撲之前，您的專案租用戶必須轉換到 Service Fabric 託管模型。 此外，要作為中樞的任何環境都必須要轉換。

> [!TIP]
> 要查詢 LCS 專案租用戶的狀態，請在[LCS](https://lcs.dynamics.com/)查詢環境類型，或聯繫您的合作夥伴或 Microsoft 連絡人。

#### <a name="local-business-data-on-premises-environments-arent-supported-as-hubs-for-scale-units"></a>不支援以本地業務資料 (內部部署) 環境作為縮放單元的中樞

內部部署環境不能用作縮放單位的中樞。 中樞環境必須都是雲端託管的。

#### <a name="scale-unit-management-capabilities-are-limited"></a>縮放單位管理能力有限

可以幫助移動工作負載的管理功能是有限的。 自助方式不支援某些管理作業，您可能必須與您的合作夥伴或 Microsoft 連絡人請求支援。 範例包括縮放單位之間的一些工作負載移動和災害場景中臨機應變的移動。

#### <a name="metrics-and-measurements-arent-yet-available"></a>計量和測量尚不可用

將幫助您為縮放單位選擇最佳應用程式的計量和量值尚不可用。 與您的 Microsoft 連絡人或實作合作夥伴一起選擇最有益的應用程式。

### <a name="data-processing-during-management-of-scale-units"></a><a name="data-processing-management"></a>縮放單位管理期間的資料處理

當您啟用 Dynamics 365 環境以支援雲端和邊緣縮放單位的分佈式混合拓撲時，某些管理服務將僅能在美國託管，如 LCS。 此行為會影響某些管理和設定資訊的傳輸和儲存，這些資訊由[縮放單位管理者入口網站](https://sum.dynamics.com)使用。 這裡有些範例：

- 您的租用戶名稱和識別碼
- 您的 LCS 專案識別碼
- 可登入的系統管理員和專案擁有者的電子郵件地址
- 中樞和縮放單位的環境識別碼
- 工作負載設定，包括法律實體和設施的名稱和實際地址，以便您的拓撲可以顯示在地理地圖上
- 已收集的計量 (例如延遲和輸送量) 將顯示在地圖分析頁面上，幫助您選擇最有益的縮放單位用途

根據 Microsoft 資料保留原則，傳輸並儲存在美國數據中心的數據將被刪除。 Microsoft 很重視您的隱私。 若要了解更多，請閱讀我們的[隱私聲明](https://go.microsoft.com/fwlink/?LinkId=521839)。

## <a name="onboard-to-the-distributed-hybrid-topology-for-supply-chain-management"></a>加入 Supply Chain Management 分佈式混和拓撲

### <a name="try-out-the-distributed-hybrid-topology"></a>嘗試分佈式混合拓撲

進入分佈式混合拓撲的過程有兩個階段。 在第一階段，你應該[試用](cloud-edge-try-out.md)解決方案並驗證您的自訂，以確保它們在包含縮放單位的分佈式拓撲中能運作。 (您可以使用現有的開發環境進行驗證。) 然後您可以繼續進行第二階段，取得生產環境。

## <a name="select-your-lcs-project-tenant-and-the-detailed-onboarding-process"></a>選取您的 LCS 專案租用戶和詳細的進入流程

縮放單位以多種庫存單位 (SKU) 和價格選項提供。 因此，您可以選擇最符合您計劃的每月交易量和效能要求的選項。

> [!TIP]
> 要找出最能滿足您的需求的規模，請與實作合作夥伴和 Microsoft 一起了解您需要的每月交易規模。

入門級 SKU 被稱為 *基本*，而效能更高的 SKU 被稱為 *標準*。 每個 SKU 都預先載入了特定數量的每月交易。 但是，您可以為每個 SKU 新增超額增益集來增加每月交易預算。

:::image type="content" source="media/SKUs-highlevel.png" alt-text="雲端縮放單位增益集。":::

> [!NOTE]
> 縮放單位增益集不與有限數量的使用者耦合。 現有訂閱中的任何使用者都可使用它們 (只要系統管理員已指派了必要的使用者角色)。

購買每個縮放單位增益集不僅可以為您提供每月的交易量，還可以讓您在 LCS 中獲得特定數量的環境位置。 對於每個雲端縮放單位增益集，您能獲得一個新的生產位置和一個新的沙箱位置。 在上線過程中，將新增一個具有這些位置的 LCS 專案。 位置的使用方式權限是固定的，因此位置必須用作具有雲端中樞的縮放單位。

超額增益集不會讓您獲得新的環境位置。

如果您想取得更多沙箱環境，您可以購買額外的常規沙箱位置。 然後，Microsoft 可以幫助您在這些位置啟用混合拓撲的沙箱縮放單位。


在您規劃完如何加入 Supply Chain Management 的分佈式混合拓撲後，您將使用[縮放單位管理者入口網站](https://aka.ms/SCMSUM)開始加入流程。 在入口網站中，選取 **Dynamics 365 租用戶** 索引標籤。此索引標籤顯示您的帳戶在其中且您是 LCS 專案的擁有者或環境管理員的租用戶清單。

如果您要查找的租用戶不在清單中，請前往[LCS](https://lcs.dynamics.com/v2)，並確保你是該租用戶的 LCS 專案的環境管理員或專案擁有者。 在選定租用戶中僅 Azure Active Directory(Azure AD) 的帳戶被授權可完成註冊體驗。

> [!NOTE]
> 套用變更到 LCS 後，租用戶清單可能需要 30 分鐘才能反映變更。

對於每個租用戶，清單會顯示上線狀態。

:::image type="content" source="media/cloud_edge-EnableHybrid1.png" alt-text="Dynamics 365 租用戶索引標籤上的租用戶清單。":::

選取 **點擊這裡開始** 要求 LCS 租用戶的上線。 您必須接受條款。 您還必須提供一個企業電子郵件地址，以利 Microsoft 發送與上線流程相關的郵件訊息。

:::image type="content" source="media/cloud_edge-EnableHybrid2.png" alt-text="租用戶的註冊提交。":::

Microsoft 將審核您的請求，並透過註冊表單中的電子郵件地址發送郵件通知您後續步驟。 Microsoft 將與您密切合作，為您的業務案例啟用混合拓撲中的縮放單位。

上線完成後，您可以使用連接埠設定縮放單位和工作負載。

### <a name="manage-scale-units-and-workloads-by-using-the-scale-unit-manager-portal"></a><a name="scale-unit-manager-portal"></a>使用縮放單位管理者入口網站管理縮放單位和工作負載

請前往[縮放單位管理者入口網站](https://aka.ms/SCMSUM)，並使用您的租用戶帳戶登入。 在 **設定縮放單位** 頁面，如果尚未列出，您可以新增中樞環境。 然後，您可以選取中樞，以設定縮放單位和工作負載設定。

:::image type="content" source="media/cloud_edge-Manage.png" alt-text="縮放單位管理者入口網站，設定縮放單位頁面。":::

若要在訂閱中新增一個或多個可用縮放單位，請選取 **新增縮放單位**。

在 **定義的工作負載** 索引標籤，使用 **建立工作負載** 按鈕，將倉庫管理工作負載新增到任一個縮放單位。 對於每個工作負載，您必須指定工作負載將擁有的程序內容。 對於倉庫管理工作負載，內容是法律實體中的特定站點的特定倉庫。

:::image type="content" source="media/cloud_edge-DefineWorkload.png" alt-text="定義工作負載對話方塊。":::

#### <a name="manage-workloads"></a><a name="manage-workloads"></a>管理工作負載

當啟用一個或多個工作負載時，使用 **管理工作負載** 選項可初始化和管理程序，例如下表中列出的程序。

| 程序 | 描述 |
|---|---|
| 暫縮放單位溝通 | 暫停中樞和縮放單位之間的管道訊息。 此過程將停止溝通並耗盡中樞和縮放單位之間的資料管道。 在中樞或縮放單位上執行 Supply Chain Management 服務作業之前，您必須執行此程序，但您也可以在其他情況下使用。 |
| 繼續縮放單位溝通 | 繼續中樞和縮放單位之間的管道訊息。 例如，在中樞或縮放單位上執行 Supply Chain Management 服務作業之後，您可能必須使用此程序。 |
| 升級工作負載 | 在中樞和縮放單位工作負載之間同步新功能。 您可能必須在，例如，當服務導致資料交換查詢出現變更和/或向工作負載新增新資料表或欄位時，使用此過程。 |
| 將工作負載轉移到縮放單元 | 將目前在中樞上執行的工作負載排程移動到縮放單位上。 執行此程序時，資料同步處理將流動，中樞和縮放單位都將設定更改工作負載的擁有權。 |
| 轉移縮放單位到中樞 | 將目前在縮放單位上執行的工作負載排程移動到中樞上。 執行此程序時，資料同步處理將流動，中樞和縮放單位都將設定更改工作負載的擁有權。
| 緊急轉換到中樞 | <p>立即將現有工作負載轉移到中樞。 *此過程僅對目前在中樞上可用的資料更改擁有權。*</p><p><strong>警告：</strong>這個過程會導致資料不同步的資料丟失和業務處理失敗。 因此，它應只在緊急情況下使用，在這種情況下，業務程序必須在中樞上處理，因為縮放單位發生了無法在合理時間內緩解的斷線。</p> |
| 解除分佈式拓撲 | 移除縮放單位部署並僅在中樞上運行，無需工作負載處理。 |

:::image type="content" source="media/sum-manage-workloads.png" alt-text="縮放單位和工作負載管理經驗。":::

> [!TIP]
> 未來，縮放單位管理者體驗中將新增累加增強，以協助簡化生命週期管理作業。 目前版本的特定功能記錄在入門手冊中，提供正在加入 Supply Chain Management 的分佈式混合拓撲的客戶使用。 <!-- KFM: Add a link to the handbook when it is published -->

## <a name="feature-management-considerations-for-workloads"></a>工作負載的功能管理注意事項

本節介紹在分佈式混合拓撲部署中安裝工作負載、新增或移除功能時應考慮的一些重要方面。 有幾種情況會影響在改變之後，是否必須執行[工作負載升級](#manage-workloads)。 但是，當您更新或新增資料交換查詢和/或新增資料表或欄位到先前安裝的工作負載時，您通常必須這樣做。

### <a name="mandatory-features-for-installing-a-workload"></a>安裝工作負載的必要功能

安裝工作負載時，安裝過程會建立一個工作負載定義，其中的資訊包含在兩個部署之間同步資料時使用的資料表。 工作負載定義的建立是根據目前在[功能管理](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)中啟用的功能自動處理的。 下表列出的功能，必須啟用才能為倉庫或製造工作負載，生成執行時必要的工作負載定義。

| 必要功能 | 工作負載 |
|---|---|
| 為 WHS 使用者建立自動指派 GUID | 倉庫 |
| 組織範圍內的工作中斷 | 倉庫 |
| 裝運波次標籤詳細資料 | 倉庫 |
| 支援倉庫應用程式工作清單的縮放單位 | 倉庫 |
| 生產現場執行 | 製造 |

當您使用[單箱式開發環境的縮放單位部署工具](https://github.com/microsoft/SCMScaleUnitDevTools)或者[縮放單位管理者入口網站](https://sum.dynamics.com)來部署工作負載，所有強制功能將自動啟用。 但是，如果您手動測試缺少一個以上強制功能的部署，工作負載安裝將失敗，並且您將收到一封訊息列出缺少的功能的。 然後，您必須手動啟用這些功能並重新觸發工作負載安裝。

### <a name="enabling-or-disabling-features-that-have-data-synchronization-dependencies"></a>啟用或禁用具有資料同步依賴性的功能

在中樞及其縮放位元之間同步處理的資料，影響其選擇的功能也會影響工作負載定義的建立方式。 因此，在安裝工作負載之前啟用這些功能非常重要。 如果在執行工作負載時啟用此類功能，則啟用該功能後，必須執行[工作負載升級](#manage-workloads)重新產生工作負載。 同樣，如果在執行工作負載時禁用具有資料同步依賴性的功能，則必須執行[工作負載升級](#manage-workloads)從工作負載定義中移除相關資料的同步處理資訊。

[!INCLUDE [cloud-edge-privacy-notice](../../includes/cloud-edge-privacy-notice.md)]

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
