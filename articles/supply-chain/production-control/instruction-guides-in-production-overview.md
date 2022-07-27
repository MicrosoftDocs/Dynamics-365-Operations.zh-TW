---
title: 為生產工作人員提供混合實境 Guides
description: 本主題說明如何運用 Dynamics 365 Guides 整合 Microsoft Dynamics 365 Supply Chain Management 的生產管理模組。
author: johanhoffmann
ms.date: 11/13/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WorkGuidesManufacturing
audience: Application User
ms.reviewer: kamaybac
ms.custom:
- "61943"
- intro-internal
ms.assetid: a3847f07-fca4-4140-a26f-d83c6ac68dde
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2020-08-01
ms.dyn365.ops.version: AX 10.0.15
ms.openlocfilehash: 703f2cb9a1ea8691420765a8598d59f3e6cc6488
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8449853"
---
# <a name="provide-mixed-reality-guides-for-workers-in-production"></a>為生產工作人員提供混合實境 Guides

[!include [banner](../includes/banner.md)]


生產流程工作人員將受惠於工作時適時出現的相關說明。 *說明* 適用於多個工作領域，包括：組件、服務、操作、認證和安全。 所有核心業務職能的持續訓練說明，可協助員工增加工作成果、提升工作品質。

## <a name="introduction"></a>簡介

您可透過不同方式提供說明。 開箱即可使用的高效系統採用 [Dynamics 365 Guides](https://dynamics.microsoft.com/mixed-reality/guides/)。

Dynamics 365 Guides 提供實作學習，協助員工提升技能。 您可以定義標準化流程，提供逐步說明指導員工使用所需工具和零件，並示範如何在實際工作環境中使用這些工具。

您可將指南附加到生產控制的各個層面，包括：

- [資源](#resources)
- [資源群組](#resource-groups)
- [已發佈產品](#released-products)
- [公式](#formulas)
- [公式版本](#formula-versions)
- [物料清單 (BOM)](#bom)
- [BOM 版本](#bom-versions)
- [途程](#routes)
- [途程版本](#route-versions)
- [途程作業關係](#route-operation-relations)

> [!NOTE]
> 您亦可將 Guides 附加至資產管理。 如需此選項的詳細資訊，請參閱[運用 Dynamics 365 Guides 整合 Dynamics 365 Supply Chain Management (資產管理)](../asset-management/asset-management-guides-integration.md)。

第一線工作人員透過 Supply Chain Management 在工廠選擇工作時，該工作人員可於工作卡上看到[相關指南](#logic)。 工作人員選擇特定指南後，螢幕上會顯示該指南的 QR 代碼。 之後使用 HoloLens 來掃描 QR 代碼，即可啟動 Guides 並顯示需要的說明。

下列小節提供數個特定情境，在這些情境中，各產業的公司都能觀察到運用 Guides 來呈現製造說明的最佳效益。

### <a name="assembly"></a>組件

![在組件任務中使用 Guides。](media/instruction-guides-hero-assembly.png "在服務任務中使用 Guides")

組件操作說明會向工作人員展示必要工具和零件，並示範如何在實際工作環境中使用。

生產經理可建立並指派 Guides，例如針對[生產途程](routes-operations.md)、[作業關係](routes-operations.md#operation-relations)或[物料清單](bill-of-material-bom.md)來建立並指派。 工作人員會在工廠內直接看到各個作業的相關說明。

### <a name="service"></a>服務

![在服務任務中使用 Guides。](media/instruction-guides-hero-service.png "在服務任務中使用 Guides")

在工作現場為技術人員提供指導說明，無須再次造訪。

例如，服務經理可將 Guides 指派給特定[產品](../../commerce/product.md)，提供例行品質評估的逐步流程。

### <a name="quality"></a>品質

![在品質保證任務中使用 Guides。](media/instruction-guides-hero-quality.png "在品質保證任務中使用 Guides")

將員工知識轉化為可重複使用的工具，推出新流程並確保提高一致性。

品質保證經理可將 Guides 指派給[產品](../../commerce/product.md)，提供例行品質評估的逐步流程。

### <a name="certifications"></a>認證

![認證相關任務運用 Guides。](media/instruction-guides-hero-certification.png "認證相關任務運用 Guides")

快速辨識需要協助的員工及其位置，確保每位員工都符合高標準。

### <a name="safety"></a>安全

![工作安全說明中使用 Guides。](media/instruction-guides-hero-safety.png "工作安全說明中使用 Guides")

在進入實體環境前，提供危險程序的虛擬逐步說明。 工作人員可透過混合實境，虛擬體驗危險程序。

生產經理可提供危險物質處理或精細處理程序專用的處理說明，方法是將說明指派給[產品項目](../../commerce/product.md)、[途程](routes-operations.md)和[操作](routes-operations.md#operation-relations)。

## <a name="get-started-with-instructions-and-guides"></a>開始使用說明和 Guides

為了在生產流程中啟用說明，Supply Chain Management 開箱即整合 Dynamics 365 Guides。 Guides 應用程式執行個體必須經過授權並安裝，才能建置並維護混合實境說明，並將其指派給生產資產與工作。

### <a name="prerequisites"></a>先決條件

若要使用此功能，您的系統必須擁有下列項目：

- Dynamics 365 Supply Chain Management 10.0.15 或更高版本
- Supply Chain Management 應用程式的[雙重寫入](../../fin-ops-core/dev-itpro/data-entities/dual-write/enable-dual-write.md)。
- [Dynamics 365 Guides](/dynamics365/mixed-reality/guides/setup#step-2-create-a-common-data-service-environment-and-install-the-dynamics-365-guides-solution) 400.0.1.48 或更高版本

### <a name="turn-on-the-feature"></a>開啟功能

若要在系統上使用此功能，您必須啟用其組態金鑰。 此操作僅須執行一次。 方法是管理員必須執行下列操作：

1. 進入系統的維護模式，如[維護模式](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md)中的說明。
1. 前往 **系統管理 \> 設定 \> 授權設定**。
1. 展開 **混合實境** 區段，然後選擇 **混合實境指南** 核取方塊。
1. 展開 **生產管理** 區段，然後選擇 **生產說明** 核取方塊。
1. 關閉維護模式，如[維護模式](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md)中的說明。
  
## <a name="configure-how-guides-appear-on-the-shop-floor"></a>設定 Guides 在工廠內的呈現方式

若要設定 Guides 在工廠內的呈現方式，請移至 **混合實境 \> Dynamics 365 Guides \> 設定 Guides 整合**。

![設定用於製造的 Guide 整合。](media/instruction-guides-configure-integration.png "設定用於製造的 Guide 整合")

設定以下欄位：

- **Microsoft Dataverse URL** - 指定建立 Guides 的 Microsoft Dataverse 環境 URL。 格式為「contoso.crm4.dynamics.com」，其中 URL 的第一部分通常以您的組織命名 (如「contoso」)。第二部分是環境的資料專屬區域 (如「crm4」)。最後一部分是網域 (如「dynamics.com」)。 確認 URL 正確的一個方法是前往 [home.dynamics.com](https://home.dynamics.com/)，然後開啟 Guides 應用程式。 Guides 開啟時，瀏覽器的網址列會出現 URL (基底 URL 應類似於上述範例)。 此值會構成您的 Guides 的網址，並編碼進 QR 代碼。
- **QR 代碼大小** - 設定呈現的 QR 代碼大小。 建議選擇能大致填滿整個顯示畫面的大小，不要過大。 通常 *15* 是建議值。
- **QR 代碼錯誤修正等級** - 設定 QR 代碼的細微性。 細微性高有助於提升代碼可靠性，但 **QR 代碼大小** 必須夠大，能支援您選擇的修正等級所需的詳細程度。

> [!TIP]
> - QR 代碼若大於您的顯示器，轉譯時間會更久，之後會再縮小以符合顯示器尺寸。 這沒有任何好處。
> - QR 代碼過小可能會減損 HoloLens 在特定環境正確讀取代碼的能力。
> - 建議您測試 HoloLens 使用者用於呈現 QR 代碼的所有裝置的設定。 選取在您的工廠環境具備足夠可讀性的設定。  

## <a name="get-an-overview-of-all-guide-assignments"></a>取得所有指南指派情形概覽

使用 **所有 Guides** 頁面，檢視組織內所有可用 Guides 清單，以及生產流程和資源的指派情形。 若要開啟此頁面，請前往 **混合實境 \> Guides \> 所有 Guides**。 頂部清單顯示所有可用的 Guides，您可使用此處欄位來篩選清單。 底部清單顯示所有指南指派情形，並提供管理工具列。

![管理 Guides。](media/instruction-guides-allguides.png "管理 Guides")

以下小節描述您可指派 Guides 的物件類型。 每個指派的指南提供的說明，會自動附加至相應的生產工作，並於工廠內提供。

## <a name="associate-a-guide-to-a-resource"></a><a name="resources"></a>將指南與資源建立關聯

將指南新增至[資源](operations-resources.md)，提供相關生產工作的指南。

### <a name="typical-scenario-using-resources"></a>使用資源的典型情境

例如，您可將具有一般機器安全性或處理說明的指南，附加到該機器類型的資源。 之後，該機器執行的所有工作都會提供指南。

### <a name="add-a-guide-to-a-resource"></a>將指南新增至資源

若要將指南新增至資源：

1. 移至 **生產控制 \> 設定 \> 資源 \> 資源**。
1. 從清單窗格中，選擇您要指派指南的資源。
1. 展開 **相關 Guides** FastTab。
1. 在 **相關 Guides** 工具列中選擇 **新增**。 系統會新增一個行到格線中。
1. 針對新的明細，使用 **名稱** 欄的下拉式清單來選取要指派的指南。 若您有大量 Guides，則可篩選清單以找出您要的Guides。
    ![管理 Guides。](media/instruction-guides-allguides.png "管理 Guides")

## <a name="associate-a-guide-to-a-resource-group"></a><a name="resource-groups"></a>將指南與資源群組建立關聯

若您使用資源群組來管理機器群組、生產線或工作單元，則可將指南新增至[資源群組](tasks/define-discrete-manufacturing-resource-group.md)。

### <a name="typical-scenarios-using-resource-groups"></a>使用資源群組的典型情境

**範例 1：** 您為相同型號的數台機器定義資源群組。 您可將指南指派至反映機器型號的資源群組，無須將該機器型號相關的處理說明指南一一指派給所有相關資源。

**範例 2：** 您將定義的資源群組用於擁有不同機器的工作單元，而您的指南會提供該工作單元如何維護的一般性說明。 該指南適用於該工作單元內的所有生產活動。

### <a name="add-a-guide-to-a-resource-group"></a>將指南新增至資源群組

若要將指南新增至資源群組：

1. 移至 **生產控制 \> 設定 \> 資源 \> 資源群組**。
1. 從清單窗格中，選擇您要指派指南的資源群組。
1. 展開 **相關 Guides** FastTab。
1. 在 **相關 Guides** 工具列中選擇 **新增**。 系統會新增一個行到格線中。
1. 針對新的明細，使用 **名稱** 欄的下拉式清單來選取要指派的指南。 若您有大量 Guides，則可篩選清單以找出您要的Guides。
    ![將指南新增至資源群組。](media/instruction-guides-resourcegroup.png "將指南新增至資源群組")

## <a name="associate-a-guide-to-a-released-product"></a><a name="released-products"></a>將指南與已發佈產品建立關聯

您可將指南新增至任何[已發佈產品](../pim/tasks/create-released-product-single-company.md)。

### <a name="typical-scenario-using-released-products"></a>使用已發佈產品的典型情境

產品層級 Guides 會提供特定已發佈產品或項目的操作或處理說明，以協助工廠工作人員。

### <a name="add-a-guide-to-a-released-product"></a>將指南新增至已發佈產品

若要將指南新增至已發佈產品：

1. 請前往 **產品資訊管理 \> 產品 \> 已發佈產品**。
1. 開啟您要指派指南的產品。
1. 在動作窗格上，開啟 **工程師** 索引標籤，並於 **檢視** 群組選擇 **相關 Guides**。
1. 將開啟您選擇的產品的 **相關 Guides** 頁面。
1. 在動作窗格上選擇 **新增**，即可將新的明細新增至網格中。 
1. 針對新的明細，使用 **名稱** 欄的下拉式清單來選取要指派的指南。
    ![將指南新增至已發佈產品。](media/instruction-guides-ReleasedProduct-AddGuides.png "將指南新增至已發佈產品")

## <a name="associate-a-guide-to-a-formula"></a><a name="formulas"></a>將指南與公式建立關聯

您可將指南新增至任何[公式](bill-of-material-bom.md#formulas-co-products-and-by-products)。

### <a name="typical-scenario-using-formulas"></a>使用公式的典型情境
  
公式層級 Guides 會為工廠工作人員提供公式或配方的處理說明。 Guides 也可指派給公式的版本。

> [!NOTE]
> 您可根據途程、途程版本或途程作業關係的公式，將指南指派給相關生產流程。  

> Guides 目前無法附加到個別公式明細。

### <a name="add-a-guide-to-a-formula"></a>將指南新增至公式

若要將指南新增至公式：

1. 請前往 **產品資訊管理 \> 物料清單和公式 \> 公式**。
1. 開啟您要指派指南的公式。
1. 於 FastTab 頂部開啟 **標題** 索引標籤。
1. 展開 **相關 Guides** FastTab。
1. 在 **相關 Guides** 工具列中選擇 **新增**。 系統會新增一個行到格線中。
1. 針對新的明細，使用 **名稱** 欄的下拉式清單來選取要指派的指南。
    ![將指南新增至公式。](media/instruction-guides-Formula.png "將指南新增至公式")

## <a name="associate-a-guide-to-a-formula-version"></a><a name="formula-versions"></a>將指南與公式版本建立關聯

您可將指南新增至任何[公式版本](bill-of-material-bom.md#bom-and-formula-versions)。

### <a name="typical-scenario-using-formula-versions"></a>使用公式版本的典型情境

附加到個別公式版本的 Guides，可為工廠工作人員提供該公式配方版本的生產逐步說明。

> [!TIP]
> 您可根據途程、途程版本或途程作業關係的公式版本，將指南指派給相關生產流程。  

> [!NOTE]
> Guides 目前無法附加到個別公式明細。

### <a name="add-a-guide-to-a-formula-version"></a>將指南新增至公式版本

若要將指南新增至公式版本：

1. 請前往 **產品資訊管理 \> 物料清單和公式 \> 公式**。
1. 開啟內含您想指派的版本的公式。
1. 於 FastTab 頂部開啟 **標題** 索引標籤。
1. 在 **公式版本** FastTab 上，選擇要指派指南的版本。
1. 在 **公式版本** 工具列上，選擇 **相關 Guides**。
    ![開啟所選公式版本相關 Guides。](media/instruction-guides-FormulaVersion.png "開啟所選公式版本相關 Guides")
1. 將開啟您的公式版本的 **相關 Guides** 頁面。
1. 在動作窗格上選擇 **新增**，即可將新的明細新增至網格中。 
1. 針對新的明細，使用 **名稱** 欄的下拉式清單來選取要指派的指南。
    ![將指南新增至公式版本。](media/instruction-guides-FormulaVersionAddGuide.png "將指南新增至公式版本")

## <a name="associate-a-guide-to-a-bill-of-materials"></a><a name="bom"></a>將指南與物料清單建立關聯

您可將指南新增至任何[物料清單](bill-of-material-bom.md) (BOM)。

### <a name="typical-scenario-using-bills-of-materials"></a>使用物料清單的典型情境

附加到 BOM 的 Guides 可為工廠工作人員提供如何準備並處理 BOM 的物料的說明。 Guides 也可指派給 BOM 的版本。

> [!NOTE]
> Guides 目前無法附加到個別 BOM 明細。

### <a name="add-a-guide-to-a-bill-of-materials"></a>將指南新增至物料清單

若要將指南新增至物料清單：

1. 請前往 **產品資訊管理 \> 物料清單和公式 \> 物料清單**。
1. 開啟您要指派指南的物料清單。
1. 於 FastTab 頂部開啟 **標題** 索引標籤。
1. 展開 **相關 Guides** FastTab。
1. 在 **相關 Guides** 工具列中選擇 **新增**。 系統會新增一個行到格線中。
1. 針對新的明細，使用 **名稱** 欄的下拉式清單來選取要指派的指南。
    ![將指南新增至 BOM。](media/instruction-guides-BOM.png "將指南新增至 BOM")

## <a name="associate-a-guide-to-a-bill-of-materials-version"></a><a name="bom-versions"></a>將指南與物料清單版本建立關聯

您可將指南新增至任何[物料清單版本](bill-of-material-bom.md#bom-and-formula-versions)。

### <a name="typical-scenario-using-bill-of-materials-versions"></a>使用物料清單版本的典型情境

附加到個別 BOM 版本的 Guides，可為工廠工作人員提供如何準備並處理 BOM 某版本且有別於通用 BOM 或其他版本的物料。

> [!NOTE]
> Guides 目前無法附加到個別 BOM 明細。

### <a name="add-a-guide-to-a-bill-of-materials-version"></a>將指南新增至物料清單版本

若要將指南新增至物料清單版本：

1. 請前往 **產品資訊管理 \> 物料清單和公式 \> 物料清單**。
1. 開啟內含您想指派的版本的 BOM。
1. 於 FastTab 頂部開啟 **標題** 索引標籤。
1. 在 **BOM 版本** FastTab 上，選擇要指派指南的版本。
1. 在 **BOM 版本** 工具列上，選擇 **相關 Guides**。
    ![開啟所選 BOM 版本相關 Guides。](media/instruction-guides-BOMVersion.png "開啟所選 BOM 版本相關 Guides")
1. 將開啟您的 BOM 版本的 **相關 Guides** 頁面。
1. 在動作窗格上選擇 **新增**，即可將新的明細新增至網格中。
1. 針對新的明細，使用 **名稱** 欄的下拉式清單來選取要指派的指南。
    ![將指南新增至 BOM 版本。](media/instruction-guides-BOMVersionAddGuide.png "將指南新增至 BOM 版本")

## <a name="associate-a-guide-to-a-route"></a><a name="routes"></a>將指南與途程建立關聯

您可將指南新增至任何[途程](routes-operations.md)。

### <a name="typical-scenario-using-routes"></a>使用途程的典型情境

途程通常會用於指定特定已發佈產品的生產應如何依據 BOM 或 BOM 版本並使用一組資源或資源群組。

將指南指派給途程，即可提供相對應生產流程的逐步說明。

### <a name="add-a-guide-to-a-route"></a>將指南新增至途程

若要將指南新增至途程：

1. 移至 **生產控制 \> 所有途程**。
1. 開啟您要指派指南的途程。
1. 展開 **相關 Guides** FastTab。
1. 在 **相關 Guides** 工具列中選擇 **新增**。 系統會新增一個行到格線中。
1. 針對新的明細，使用 **名稱** 欄的下拉式清單來選取要指派的指南。
    ![將指南新增至途程。](media/instruction-guides-Route.png "將指南新增至途程")

## <a name="associate-a-guide-to-a-route-version"></a><a name="route-versions"></a>將指南與途程版本建立關聯

您可將指南新增至任何[途程版本](routes-operations.md#route-versions)。

### <a name="typical-scenario-using-route-versions"></a>使用途程版本的典型情境

途程版本通常會用於指定以現有途程為基礎的生產流程變體。 您可為每個途程版本指派不同 Guides。

### <a name="add-a-guide-to-a-route-version"></a>將指南新增至途程版本

若要將指南新增至途程版本：

1. 移至 **生產控制 \> 所有途程**。
1. 開啟您要指派指南的途程。
1. 在 **版本** FastTab 上，選擇要指派指南的版本。
1. 在 **版本** 工具列上，選擇 **相關 Guides**。
    ![開啟所選途程版本相關 Guides。](media/instruction-guides-RouteVersion.png "開啟所選途程版本相關 Guides")
1. 將開啟您的 BOM 版本的 **相關 Guides** 頁面。
1. 在動作窗格上選擇 **新增**，即可將新的明細新增至網格中。
1. 針對新的明細，使用 **名稱** 欄的下拉式清單來選取要指派的指南。
    ![將指南新增至途程版本。](media/instruction-guides-RouteVersionAddGuide.png "將指南新增至途程版本")

## <a name="associate-a-guide-to-a-route-operation-relation"></a><a name="route-operation-relations"></a>將指南與途程作業關係建立關聯

您可將指南新增至任何[途程作業關係](routes-operations.md#operation-relations)。

### <a name="typical-scenario-using-route-operation-relations"></a>使用途程作業關係的典型情境

作業關係是將指南新增至產品流程及其相關作業最具體的方式。 您可為途城內的每個作業指定指南，並為特定途程的關係環境類型指定不同指南，例如針對特定項目、設定等。 您亦可指定指南適用的作業階段 (如設定、佇列、處理或運輸)。

> [!NOTE]
> 若您為途程內的多個作業關係指定指南，則這些指南中，只有關係最具體的指南會呈現在所創造工作的工廠內。

### <a name="add-a-guide-to-a-route-operation-relation"></a>將指南新增至途程作業關係

若要將指南新增至途程作業關係：

1. 移至 **生產控制 \> 所有途程**。
1. 開啟您要指派指南的途程。
1. 在動作窗格中，從 **維護** 群組中開啟 **途程** 索引標籤，並選擇 **途程詳細資料**。
1. 將開啟您選擇的途程的 **途程詳細資料**。
1. 在頂部網格中，選擇您要提供指南的作業。
1. 在底部網格中，選擇一個特定關係 (或通用 **全部** 關係)。
    ![選擇作業，然後選擇關係。](media/instruction-guides-RouteOperationRelation.png "選擇作業，然後選擇關係")
1. 在底部網格上方，開啟 **相關 Guides** 索引標籤。![相關 Guides 索引標籤。](media/instruction-guides-RouteOperationRelation-AddGuide.png "相關 Guides 索引標籤")
1. 從底部網格頂端的工具列中選擇 **新增**，在網格內新增明細。
1. 針對新的列，使用 **名稱** 欄的下拉式清單來選取要指派的指南。 在該列的其餘部分中，選擇應提供所選指南的每個環境的核取方塊。

> [!NOTE]
> 每個作業的每個階段都能新增一或多個指南。

## <a name="select-guides-from-the-shop-floor-execution-interface"></a>從工廠執行介面中選擇指南

工作人員在工廠執行介面開啟作業清單時，Supply Chain Management 就會尋找已顯示作業的相關指南。 使用 **Guides** 按鈕來檢視相關 Guides。

![工廠執行介面中的 Guides 按鈕。](media/instruction-guides-Shopfloor1.png "工廠執行介面中的 Guides 按鈕")

然後開啟 HoloLens，並掃描 QR 代碼及啟用相關指南，即可予以存取。

![透過 HoloLens 以 QR 代碼存取指南。](media/instruction-guides-Shopfloor2.png "透過 HoloLens 以 QR 代碼存取指南")

## <a name="resolving-the-logic-for-selecting-guides"></a><a name="logic"></a>解決選擇 Guides 的邏輯

您可將 Guides 新增至下列生產資料：

- [資源](#resources)
- [資源群組](#resource-groups)
- [已發佈產品](#released-products)
- [公式](#formulas)
- [公式版本](#formula-versions)
- [物料清單 (BOM)](#bom)
- [BOM 版本](#bom-versions)
- [途程](#routes)
- [途程版本](#route-versions)
- [途程作業關係](#route-operation-relations)

Supply Chain Management 為生產現場產生工作時，將從這些來源收集相關 Guides。 請注意以下重要規則。

- 若將 BOM 版本或公式版本附加到途程或生產訂單，則工作會顯示附加到此版本的 Guides，以及附加到該版本上層 BOM 或公式的 Guides。
- 若將途程版本附加到生產訂單，則工作會顯示附加到此版本的 Guides，以及附加到該版本上層途程的 Guides。
- 若您定義的數個途程作業關係納入 *全部* 關係並為其指派 Guides，則該作業只會顯示關係最具體的 Guides。  

![解決相關 Guides 的圖表。](media/instruction-guides-Resolve.png "解決相關 Guides 的圖表")


[!INCLUDE[footer-include](../../includes/footer-banner.md)]