---
title: 內部環境的硬體大小要求
description: 本主題列出了內部環境的硬體大小要求。
author: sericks007
ms.date: 06/02/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.custom: 55651
ms.assetid: ''
ms.search.region: Global
ms.author: chwolf
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 8
ms.openlocfilehash: 443b80e44a90a68610fbb2bb5a5f4b6b7d545fa7ad772edb3672972fa82f8cbd
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460533"
---
# <a name="hardware-sizing-requirements-for-on-premises-environments"></a>內部環境的硬體大小要求

[!include [banner](../includes/banner.md)]

在開始內部環境的硬體和基礎結構規模調整過程之前，請熟悉[雲端部署的系統要求](system-requirements.md)和[設定和部署說明](../../dev-itpro/deployment/setup-deploy-on-premises-environments.md)，以深入了解內部基礎結構。

> [!NOTE]
> 密切關注系統設定最佳做法以獲得最佳效能。

在您審查文件後，便可開始估計您的交易和同時使用者量，並根據平均核心輸送量確定您的環境規模。

## <a name="factors-that-affect-sizing"></a>影響調整大小的因素

下圖中顯示的所有因素都會影響大小。 收集的資訊越詳細，您可以越精確地確定尺寸。 在沒有支援資料的情況下，硬體大小可能不準確。 必要資料的絕對最低要求是每小時的峰值交易線路負載。

[![內部環境的硬體大小。](./media/lbd-sizing-01.png)](./media/lbd-sizing-01.png)

從左到右看，準確估計規模所需的第一個也是最重要的因素是交易概況或交易特徵。 始終找到每小時的峰值交易量很重要。 如果有多個峰值時段，則需要準確定義這些時段。

當您了解影響基礎結構的負載時，您還需要了解有關以下因素的更多詳情：

- **交易** – 通常交易在一天/一週內都有一定的峰值。 這主要取決於交易類型。 時間和費用條目通常每週顯示一次高峰，而銷售訂單分錄通常透過整合或在白天大量輸入。
- **同時使用者數** – 同時使用者數是第二個最重要的調整大小因素。 您無法根據同時使用者數可靠地取得規模估計，因此，如果這是您唯一可用的資料，請估計一個近似數字，然後在您有更多資料時重新存取。 準確的同時使用者定義意味著：

    - 命名使用者不是同時使用者。
    - 同時使用者始終是命名使用者的子集。 
    - 峰值工作負載定義了大小調整的最大並行性。

    同時使用者的標準是使用者滿足以下所有標準：

    - 已登入。
    - 計數時的工作交易/查詢。
    - 不是閒置工作階段。

- **資料構成** – 這主要是關於如何設定和設定您的系統。 例如，您將擁有多少個法律實體、多少個項目、多少個 BOM 級別以及您的安全設定有多複雜。 這些因素中的每一個都可能對效能產生很小的影響，因此可以透過在基礎結構方面使用明智的選取來抵消這些因素。
- **擴充功能** – 自訂可以簡單也可以複雜。 自訂的數量以及複雜性和使用的性質對所需基礎結構的規模有不同的影響。 對於複雜的自訂，建議進行效能評估，以確保它們不僅經過效率測試，而且有助於了解基礎結構需求。 當擴充功能沒有根據效能和可擴縮性的最佳做法進行編碼時，這一點就更加重要了。
- **報表和分析** – 這些因素通常包括對系統中的各種資料庫執行繁重的查詢。 了解並減少執行昂貴報表的頻率將幫助您了解它們的影響。
- **第三方解決方案** – 這些解決方案與 ISV 一樣，具有與擴充功能相同的含義和建議。

## <a name="sizing-your-environment"></a>調整您的環境大小

若要了解您的規模要求，您需要知道您需要處理的交易的峰值量。 大多數輔助系統，如 Management Reporter 或 SSRS，對工作的關鍵程度較低。 因此，本文件主要關注 AOS 和 SQL Server。

> [!NOTE]
> 一般來說，計算層擴增並且應該以 N+1 方式設定，這代表如果您估計三個 AOS，則新增第四個 AOS。 應在 Always On 高可用性設定中設定資料庫層。

## <a name="sql-server-oltp"></a>SQL Server (OLTP)

### <a name="sizing"></a>調整大小

- DB 伺服器上每個核心每小時 3K 到 15K 交易行。
- 主 SQL Server 的典型 AOS 與 SQL 核心比率為 3:1。 根據所選的高可用性設定，需要額外的核心。

    - 處理資料庫繁重的動作可能會將其倒退到 2:1。

- 以下因素會影響變化：

    - 使用中的參數設定。
    - 擴展級別。
    - 使用附加函數，例如資料庫記錄和警報。 極端資料庫記錄記錄將進一步將每個核心每小時的輸送量降低到 3K 行以下。
    - 資料組成的複雜性 - 簡單的會計科目表與詳細的細微度會計科目表對輸送量有影響 (如範例)。
    - 交易特徵。
    - 每個核心 2 GB 到 16 GB 記憶體。
    - DB 伺服器上的輔助資料庫，例如 Management Reporter 和 SSRS 資料庫。
    - 暫存 DB = DB 大小的 15%，檔案數量與物理處理器一樣多。
    - SAN 大小和輸送量基於總同時交易量/使用量。

### <a name="high-availability"></a>高可用性

我們建議一直在叢集或鏡像設定中使用 SQL Server。 第二個 SQL 節點應具有與主節點相同的核心數。

### <a name="active-directory-federation-services-ad-fs"></a>Active Directory 同盟服務 (AD FS)

如需 AD FS 大小的資訊，請參閱[AD FS 伺服器容量文件](/windows-server/identity/ad-fs/design/planning-for-ad-fs-server-capacity)。

[調整工作表大小](https://adfsdocs.blob.core.windows.net/adfs/ADFSCapacity2016.xlsx)可用於規劃部署中的實體數量。

## <a name="aos-online-and-batch"></a>AOS (線上和批次)

### <a name="sizing"></a>調整大小

- 按交易量/使用量調整大小

    - 每個核心 2K 到 6K 行
    - 每個實體 16 GB
    - 標準盒 – 4 到 24 核心
    - 每個核心 10 到 15 個企業使用者
    - 每個核心 15 到 25 個有效使用者
    - 每個核心 25 到 50 名團隊成員

- 批次

    - 每個核心 1 到 4 個批次處理線程
    - 基於批次處理視窗特徵的大小

- 請注意，AOS、資料管理和批次處理在 Service Fabric 中的角色相同。 您需要為這三個工作負載組合調整大小，而不是像在 Microsoft Dynamics AX 2012 中那樣將它們分開。
- SQL Server 的相同可變因素適用於此。

### <a name="high-availability"></a>高可用性

- 確保您的可用 AOS 至少比您估計的多 1 到 2 個。
- 確保您至少有 3 到 4 個可用的虛擬主機。

## <a name="management-reporter"></a>Management Reporter

在大多數情況下，除非廣泛使用，否則建議的使用兩個節點的最低要求應該可以很好地運作。 只有在大量使用的情況下，您才需要兩個以上的節點。 請根據需要進行縮放。

## <a name="sql-server-reporting-services"></a>SQL Server Reporting Services

對於正式發行版本，只能部署一個 SSRS 節點。 在測試時監控您的 SSRS 節點，並根據需要增加可用於 SSRS 的核心數量。 確保您在不同於 SSRS VM 的虛擬主機上具有可用的預設定輔助節點。 如果託管 SSRS 的虛擬機器或虛擬主機出現問題，這一點很重要。 如果是這種情況，則需要更換它們。

從版本 10.0.17 開始，可以設定額外的 SSRS 節點以實現高可用性。 如需相關資訊，請參閱[為 SQL Server Reporting Services (SSRS) 節點設定高可用性](../../dev-itpro/deployment/onprem-ssrsha.md)。

## <a name="environment-orchestrator"></a>環境協調器

協調器服務是管理您的部署以及與 LCS 相關通訊的服務。 此服務部署為主要 Service Fabric 服務，並且需要至少三個 VM。 此服務與 Service Fabric 協調流程服務位於同一位置。 這應該根據集群的峰值負載調整大小。 如需相關資訊，請參閱[規劃和準備 Service Fabric 獨立叢集部署](/azure/service-fabric/service-fabric-cluster-standalone-deployment-preparation)。

## <a name="virtualization-and-oversubscription"></a>虛擬化和超額認購

像 AOS 這樣的關鍵工作服務應該託管在具有專用資源 (核心、記憶體和硬碟) 的虛擬主機上。


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
