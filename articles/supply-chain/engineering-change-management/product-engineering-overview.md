---
title: 工程變更管理概觀 (包含影片)
description: 本主題概述工程變更管理，可幫助您規劃和管理產品版本設定，以及管理產品生命週期和工程變更。
author: t-benebo
ms.date: 01/11/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 54d91d009d70194dfc91c8c855e0088f9de01718
ms.sourcegitcommit: fcb8a3419e3597fe855cae9eb21333698518c2c7
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/09/2022
ms.locfileid: "8450033"
---
# <a name="engineering-change-management-overview"></a>工程變更管理概觀

[!include [banner](../includes/banner.md)]

## <a name="feature-summary"></a>功能摘要

當今的製造商需要強大的產品資料管理、版本控制和工程變更管理功能，才能在產品生命週期不斷縮短、品質和可靠性需求不斷提高，以及對產品安全性更加關注的世界中獲得成功。

工程變更管理為產品資料管理流程帶來結構和紀律，並能夠以工作流程支援的受控方式來定義、發行和修訂產品。 透過產品版本和工程變更管理，您可以在產品的整個生命週期中記錄工程變更、評估其影響並套用變更。

工程變更管理可幫助您規劃和管理產品版本設定，以及管理產品生命週期和工程變更。 以下是其主要功能清單：

- 產品版本設定
- 增強型產品會發佈功能，讓您可以在一個法律實體 (工程公司) 中維護基準產品資料，並將完全設定的已發行產品發佈到其他法律實體
- 在啟用產品版本之前，請先輸入驗證該必要資訊的規則 (整備度檢查)
- 已透過更細緻地控制已發行的產品何時可用於特定的業務流程中，來改進產品生命週期管理
- 工作流程支援的工程變更要求
- 工作流程支援的工程變更訂單

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4HE6B]

上一個影片 ([Dynamics 365 Supply Chain Management](https://youtu.be/N313FqvRuBc) 中的變更管理功能) 包含在 YouTube 上提供的[Finance and Operations播放清單](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW)中。

## <a name="turn-on-the-engineering-change-management-features-for-your-system"></a>為您的系統開啟工程變更管理功能

您必須先同時啟用 *工程變更管理* 功能及其組態金鑰，才可以使用工程變更管理。 如果您也想要追蹤交易中產品的版本維度 (選擇性)，則還必須同時啟用 *產品版本維度* 功能及其組態金鑰。 在視需要設定這些先決條件後，您將能夠為工程變更管理開啟其他可選功能。

### <a name="turn-the-basic-engineering-change-management-features-on-or-off"></a>開啟或關閉基本工程變更管理功能

若要開啟或關閉基本工程變更管理功能，請按照以下步驟操作。 從 Supply Chain Management 10.0.25 版起，*工程變更管理* 功能預設為開啟。

1. 移至[功能管理](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)工作區。
1. 檢查更新。
1. 視需要開啟或關閉名為 *工作變更管理* 的功能。
1. 如果您想要追蹤交易中產品的版本維度 (可選)，請開啟名為 *產品維度版本* 的功能。

### <a name="turn-the-required-configuration-keys-on-or-off"></a>開啟或關閉所需的組態金鑰

接下來，按照以下步驟開啟組態金鑰。 這些金鑰預設為未開啟。

1. 進入系統的維修模式，如[維修模式](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md)中的說明。
1. 前往 **系統管理 \> 設定 \> 授權設定**。
1. 展開 **貿易** 節點。
1. 使用 **工作管理變更** 核取方塊啟用或停用主要功能的組態金鑰。
1. 展開 **工程變更管理** 節點，然後視需要選擇或清除以下核取方塊 (視您要使用的功能而定)：

    - **屬性搜尋** – 選擇此核取方塊以啟用[屬性搜尋功能 ](engineering-attributes-and-search.md)。 建議啟用此功能，但如果您不要使用，可以清除此核取方塊。
    - **流程製造的變更管理** – 如果您想使用工程變更管理功能來管理流程製造公式的變更，請選擇此核取方塊。 如果您不必管理公式，可以清除此核取方塊。 如需詳細資訊，請參閱[管理配方及其成分的變化 ](manage-formula-changes.md)。

1. 如果您還想使用版本維度，請選擇 **產品維度 - 版本** 核取方塊。 (此核取方塊在清單的下方，未嵌套在 **工程管理變更** 節點下方)。如果您不需要此功能，可以清除此核取方塊。
1. 關閉維修模式，如[維修模式](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md)中的說明。
1. 必須將資料庫同步化，以確保能正確更新組態金鑰以反映您的變更。 根據您正在工作的環境類型，執行以下步驟之一：
    - **對於第 1 層 (開發) 環境**：在 Microsoft Visual Studio 中開啟專案，然後選擇 **Dynamics 365 \> 同步化資料庫 \> 同步化**。
    - **對於第 2 層 (及更高) 環境**：在您讓環境進入和離開維護模式後，資料庫會自動同步化，因此您可以略過此步驟。

### <a name="turn-on-additional-engineering-change-management-features"></a>開啟其他的工程變更管理功能

在您開啟基本工程變更管理功能並啟用其組態金鑰後，會將數個附加和可選的工程變更管理功能新增至功能管理。 這些功能中都會一一列在 **工程變更管理** 模組下方。 下表描述每個可選功能，並提供連結以供取得更多資訊。 從 Supply Chain Management 10.0.25 版起始，這些功能預設皆為開啟，但您仍然可以選擇關閉。

| 功能管理中的功能名稱 | 描述 | 功能狀態 |
|---|---|---|
| 對現有產品啟用變更管理 | <p>此功能允許您將現有產品轉換為工程產品，以便您可以開始使用工程變更管理來管理它們。</p><p>如需詳細資訊，請參閱[對現有產品啟用變更管理](change-management-existing-products.md)。</p> |
| 生產工程通知 | <p>當產品在工程中發生變更時，將這些變更通知生產部門是很重要的。 如此一來，生產員工可以採取適當的動作，例如元件更換、物料清單 (BOM) 更換或路線更換。 此功能可讓您通知生產部門正在生產的產品發生變更。</p><p>如需詳細資訊，請參閱[管理工程產品變更](engineering-change-management.md)。</p> |
| 已改進工作管理變更的屬性繼承 | <p>此功能簡化成品或中間品項的屬性管理。 開啟此功能後，能更容易識別屬於某個品項的所有屬性，而且您可以選擇應該從該品項傳播到其父系品項的屬性。 例如，當成品的一個組件易碎、有毒或易燃時，此功能很有用，因為您可以輕鬆識別易碎、有毒或易燃屬性，並將其傳播到成品。</p><p>如需詳細資訊，請參閱[工程屬性與工程屬性搜尋](engineering-attributes-and-search.md)。</p> |
| 產品整備度檢查 | <p>此功能可讓您為標準 (非工程) 產品設定整備度檢查。 使用產品整備度檢查確保每個產品皆已完整定義，並且在產品可用且用於交易之前先設定所有必要的原則。 如果您在使用此功能一段時間將其停用，則標準產品的所有現有整備度檢查都將被刪除。</p><p>如需詳細資訊，請參閱[產品整備度](product-readiness.md)。</p> |
| 管理配方及其成分的變更 | <p>此功能可讓您追蹤配方成分、聯產品和副產品的變化。</p><p>如需詳細資訊，請參閱[管理配方及其成分的變化 ](manage-formula-changes.md)。</p> |
| 產生工程產品的變型 | <p>此功能可讓您根據可用的維度值產生工程產品的變型。</p><p>如需詳細資訊，請參閱[產生工程產品的變型](engineering-variants.md)。</p> |

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
