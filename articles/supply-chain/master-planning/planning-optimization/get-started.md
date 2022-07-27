---
title: 開始使用規劃最佳化
description: 本主題說明如何開始使用 Planning Optimization 功能。
author: ChristianRytt
ms.date: 05/20/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: MpsIntegrationParameters, MpsFitAnalysis
audience: Application User
ms.reviewer: kamaybac
ms.custom: intro-internal
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 8e6328902cec840b98b401fe8dd46c2a6f18cb54
ms.sourcegitcommit: 88f8a0369ce66b82314db9639491b695e18a7e5c
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/09/2021
ms.locfileid: "8449553"
---
# <a name="get-started-with-planning-optimization"></a>開始使用規劃最佳化

[!include [banner](../../includes/banner.md)]

如[之前公佈的](../../get-started/removed-deprecated-features-scm-updates.md#use-of-built-in-supply-chain-management-master-planning-engine-for-distribution-scenarios)，規劃最佳化將取代現有的內建主計劃引擎。

如果您目前是使用內建的主計劃引擎，您應該馬上開始計劃移轉至規劃最佳化。 立即開始移轉程序非常重要，因為，當開始實行強制淘汰時，您的作業可能會受到影響。 為避免於實行強制淘汰時的最後一刻發生問題，我們強烈建議您於 2020 年 12 月 1 日之前完成移轉。 

規劃最佳化功能目前不支援 Supply Chain Management 內建的計劃引擎中全部的可用功能。 因此，評估目前規劃最佳化中的可用功能，是否可以滿足您的需求，非常重要。 在 Dynamics Lifecycle Services (LCS) 中，Planning Optimization 功能尚未預設開啟，因此您可以於開啟功能之前進行評估。

> [!NOTE]
> 如果您的總規劃程序未包括生產 (總規劃產生的已規劃生產訂單)，且您需要 10.0.15 版本之後的內建總規劃引擎時，您需要從移轉至規劃最佳化要求例外狀況。 從 10.0.16 版本開始，執行內建總規劃而不產生已規劃的生產訂單時，將在環境中顯示錯誤。 規劃最佳化應該用於在總規劃期間不產生已規劃生產訂單的所有新部署。 執行內建總規劃引擎，但不產生已規劃生產訂單的現有環境擁有者，將會收到一封例外狀況詳細資料的郵件。 我們建議您與合作夥伴一起評估和規劃移轉至規劃最佳化。

啟動規劃最佳化之前，我們強烈建議您評估規劃最佳化的適合度分析結果。 如需詳細資訊，請參閱[規劃最佳化適合度分析](planning-optimization-fit-analysis.md)。

## <a name="availability"></a>可用性

規劃最佳化目前可以用於以下 Azure 地理位置：美國、加拿大、歐洲、英國、澳大利亞、亞太地區、日本和印度。 如果，您嘗試從其他地理位置區域安裝增益集，則 LCS 將顯示不支援只地理位置區域的訊息。 如需 Azure 地理位置和相關區域的詳細資訊，請參閱 [Azure 地理位置](https://azure.microsoft.com/global-infrastructure/geographies/#geographies)。

請注意，規劃最佳化不支援 Dynamics 365 Supply Chain Management 的內部部署。

## <a name="licensing"></a>授權

如果您可以使用目前的授權執行總規劃，則無須額外購買授權，即可開始使用規劃最佳化。

## <a name="install-and-enable-planning-optimization"></a>安裝並啟用規劃最佳化

若要使用規劃最佳化，必須確保您的系統具備所有先決條件，安裝 Dynamics 365 Supply Chain Management 的規劃最佳化增益集並啟用其授權金鑰。

### <a name="prerequisites"></a>先決條件

安裝規劃最佳化增益集之前，必須滿足以下先決條件：

- 您必須在 LCS 上執行 Supply Chain Management，高可用性環境，第 2 層或更高層 (不是 OneBox 環境)，具有 Dynamics 365 Supply Chain Management 10.0.7 版本或更高版本。 如果您嘗試在 OneBox 環境中安裝增益集，將無法完成安裝，並且您需要取消安裝。

- 您的系統必須為 Power Platform 設定整合。 如需更多資訊，請參閱[Microsoft Power Platform 與財務和營運應用程式整合](../../../fin-ops-core/dev-itpro/power-platform/overview.md)。

### <a name="enable-the-planning-optimization-license"></a>啟用規劃最佳化授權

若要使用規劃最佳化，您必須啟用其設定金鑰。 若要這麼做：

1. 進入系統的維修模式，如[維修模式](../../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md)中的說明。
1. 前往 **系統管理 \> 設定 \> 授權設定**。
1. 在 **設定金鑰** 索引標籤上，選擇 **規劃最佳化** 核取方塊。
1. 關閉系統的維修模式，如[維修模式](../../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md)中的說明。

### <a name="install-the-planning-optimization-add-in"></a>安裝規劃最佳化增益集

您必須從 LCS 專案安裝增益集，然後從 Supply Chain Management 使用者介面開啟規劃最佳化功能。

若要安裝規劃最佳化增益集：

1. 登入 LCS，然後開啟所需的環境。
1. 前往 **全部詳細資料**。
1. 向下捲動至 **環境增益集** FastTab。
1. 選擇 **安裝新的增益集**。
1. 選擇 **規劃最佳化**。
1. 按照安裝指南，並同意條款及條件。
1. 選擇 **安裝**。
1. 在 **環境增益集** FastTab 上，您應該會看見正在安裝規劃最佳化。
1. 幾分鐘後，**安裝中** 應該會變更為 **已安裝** (您可能需要重新整理頁面)。 安裝之後，您就可以在 Dynamics 365 Supply Chain Management 上啟用規劃最佳化。

安裝規劃最佳化增益集的主要目的，是為了連接服務與環境。 因此，您必須在每個要使用規劃最佳化的環境中分別安裝增益集，

## <a name="integrate-planning-optimization-with-your-system"></a>將規劃最佳化與您的系統整合

若要設定是否將規劃最佳化增益集用於總規劃，前往 **總規劃** \> **設定** \> **規劃最佳化參數**。

### <a name="connection-status"></a>連線狀態

連線狀態表示 Supply Chain Management 和規劃服務最佳化之間目前連線狀態。 下列資料表顯示可能的值。

| 連線狀態 | 描述 | 是否可以使用規劃最佳化？ |
|---|---|---|
| 已連線 | 已建立規劃服務最佳化和 Supply Chain Management 之間的連線。 | 是 |
| 啟用連線 | 正在處理開啟連線至規劃服務最佳化的要求。 | 否 |
| 中斷連線 | 規劃服務最佳化沒有連線。 如本主題前面所述，可以從 LCS 開啟連線。 | 否 |
| 停用連線 | 正在處理關閉連線至規劃服務最佳化的要求。 | 否 |
| 正在取得狀態 | 系統正在等待規劃服務最佳化的狀態資訊。 | 否 |

### <a name="the-use-planning-optimization-option"></a>使用規劃最佳化選項

**使用規劃最佳化** 的設定選項，決定要將哪個規劃引擎用於主計劃：

- **是** - 將規劃最佳化用於進行總體規劃。
- **否** - Supply Chain Management 內建的規劃引擎將用於主計劃。

使設定適用於所有法律實體 (公司)。 無法在部分法人實體中使用規劃最佳化，另一部分的法人實體則無法使用內建的主計劃。

> [!NOTE]
> 如果觸發由 Supply Chain Management 規劃引擎建立的規劃批次工作，但是 **使用規劃最佳化** 選項設定為 **是**，則工作將會失敗。

### <a name="integration-with-the-setup"></a>與設定整合

如果已開啟規劃最佳化，則會使用規劃最佳化增益集完成主計劃。 在這種情況下，主計劃結果和功能會受到影響。

## <a name="additional-resources"></a>其他資源

[預覽條款及條件](https://go.microsoft.com/fwlink/?linkid=2015274)

[規劃最佳化概觀](planning-optimization-overview.md)

[規劃最佳化適合度分析](planning-optimization-fit-analysis.md)

[檢視計劃歷程與規劃日誌](plan-history-logs.md)

[將篩選條件套用至計劃](plan-filters.md)

[取消規劃作業](cancel-planning-job.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
