---
title: 設定生產現場執行介面
description: 本主題介紹如何為生產現場執行介面建立一個或多個設定。 當您打開生產現場執行介面時，它會自動載入特定於瀏覽器和裝置的選定設定和作業篩選器。 在該設定中，您設定必須適用於特定使用方式的原則。
author: johanhoffmann
ms.date: 10/05/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: JmgProductionFloorExecutionConfiguration
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-10-05
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 5a0ead85eaeb6b96b80716614990af8c8e5e70f7
ms.sourcegitcommit: 2e554371f5005ef26f8131ac27eb171f0bb57b4e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/04/2022
ms.locfileid: "8450096"
---
# <a name="configure-the-production-floor-execution-interface"></a>設定生產現場執行介面

[!include [banner](../includes/banner.md)]

工廠工人使用生產現場執行介面來登記他們的日常工作，例如當他們開始作業時、報告關於工作的意見反應、登記間接活動和報告缺勤。 這些登記是追蹤生產訂單進度和成本的基礎，也是計算工人工資的基礎。

當您打開生產現場執行介面時，它會自動載入特定於瀏覽器和裝置的選定設定和作業篩選器。 在該設定中，您設定必須適用於特定使用方式的原則。 這裡有一些使用方式範例：

- 在公司大廳的一台裝置上，員工進辦公室打卡，下班打卡。
- 在工廠的裝置上，機器操作員在開始和完成工作時進行登記。 他們還記錄休息和間接活動。

本主題說明為您現場使用的每個裝置設定生產現場執行介面的各種選項。

## <a name="turn-on-the-production-floor-execution-interface-and-its-related-optional-features"></a>開啟生產現場執行介面及其相關可選功能

該生產現場執行介面本身以及本主題中描述的幾個可選設定必須在您的系統中開啟，然後才能使用它們。 使用 [功能管理](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) 頁面以根據需要開啟以下小節中描述的任何或所有功能。

### <a name="the-production-floor-execution-interface"></a>生產現場執行介面

這是本主題中描述的主要功能，並且是本節中提到的所有其他功能的先決條件。 從 Supply Chain Management 10.0.25 開始，它是強制性的，不能關閉。 如果您執行的版本為 10.0.25 之前的版本，管理員可以在 [功能管理](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) 工作區搜尋 *生產線場執行* 功能，然後開啟或關閉此功能。

### <a name="generate-license-plates"></a>產生牌照

這些功能使生產現場執行介面可以使用牌照功能。 若您想要使用它們，請在 [功能管理](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) (依此順序) 開啟以下功能：

1. *報告為已完成的牌照新增到工作卡裝置*<br>(從 Supply Chain Management 版本 10.0.21 開始，此功能為預設開啟。 從 Supply Chain Management 版本 10.0.25 開始，此功能為必要。)
1. *在工作卡裝置中報告為完成時啟用自動生成牌照號碼*<br>(從 Supply Chain Management 版本 10.0.25 開始，此功能為必要。)

### <a name="print-labels"></a>列印標籤

這些功能使生產現場執行介面可以使用標籤列印功能。 若您想要使用它們，請在 [功能管理](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) (依此順序) 開啟以下功能：

1. *報告為已完成的牌照新增到工作卡裝置*<br>(從 Supply Chain Management 版本 10.0.21 開始，此功能為預設開啟。 從 Supply Chain Management 版本 10.0.25 開始，此功能為必要。)
1. *從工作卡裝置列印標籤*<br>(從 Supply Chain Management 版本 10.0.25 開始，此功能為必要。)

### <a name="allow-locking-the-touch-screen"></a>允許鎖定觸控式螢幕

此功能使工作人員可以鎖定觸控式螢幕，以便對其進行清理。

從 Supply Chain Management 版本 10.0.21 開始，此功能預設開啟。 從 Supply Chain Management 10.0.25 開始，此功能為強制性開啟，且不能關閉。 如果您執行的版本低於 10.0.25，系統管理員可以在 [功能管理](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)工作區搜尋 *鎖定工作卡裝置和工作卡終端以便對其進行清潔消毒* 功能。

### <a name="asset-management-functionality-for-the-production-floor-execution-interface"></a>生產現場執行介面的資產管理功能

此功能在生產現場執行介面中新增資產管理索引標籤。 工作人員可以使用此索引標籤來選擇與作業清單的選定篩選器內的機器資源相連的資產。 對於選定的機器資產，工作人員可以從最多四個選定計數器的計數器值中查看資產的狀態和運行狀況。 若您想要使用此功能，請在 [功能管理](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) 開啟以下功能：

- *生產現場執行介面的資產管理功能*<br>(從 Supply Chain Management 版本 10.0.25 開始，此功能預設開啟。)

### <a name="enable-job-search"></a>啟用作業搜尋

此功能可以將搜尋欄位新增到工作清單中。 工人可以透過輸入工作識別碼來尋找特定作業，或者透過輸入訂單識別碼來尋找特定訂單的所有作業。 工人可以使用鍵盤或掃描條碼輸入識別碼。 若您想要使用它，請在 [功能管理](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) 開啟以下功能：

- *生產現場執行介面的作業搜尋*<br>(從 Supply Chain Management 版本 10.0.25 開始，此功能預設開啟。)

### <a name="enable-reporting-on-co-products-and-by-products"></a>啟用對聯產品和副產品的報告

此功能讓工人使用生產現場執行介面來報告批次訂單的進度。 報告內容包含聯產品和副產品的報告。 要使用此功能，請在 [功能管理](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) 開啟以下功能：

- *從生產現場執行介面報告聯產品和副產品*

### <a name="enable-the-display-of-full-serial-batch-and-license-plate-numbers"></a>啟用完整序號、批次號碼和牌照號碼的顯示

此功能為在生產車間執行介面中查看序號、批次編號和牌照編號清單提供了更佳的體驗。 顯示從顯示有限數量字元的卡片檢視變為提供足夠空間來顯示完整值的清單檢視。 該清單還提供了搜尋特定數字的功能。

從 Supply Chain Management 版本 10.0.25 開始，此功能預設開啟。 管理員可以透過搜尋位在 [功能管理](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) 工作區中的 *在生產現場執行介面中顯示完整序號、批次號碼和牌照號碼* 功能打開或關閉此功能。

### <a name="enable-registering-of-material-consumption"></a>啟用材料消耗登記

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]
<!-- KFM: preview until further notice -->

此功能可讓工人使用生產現場執行介面來登記物料消耗、批次編號和序號。 某些製造商，尤其是加工業的製造商，必須明確登記每個批次或生產訂單消耗的材料量。 例如，工人可能會使用秤來稱量他們工作時消耗的材料量。 為了確保完全的材料可追溯性，這些組織還必須登記生產每種產品所消耗的批次號碼。

此功能有兩個版本。 其中一個支援的項目 *不* 啟用以使用進階倉庫流程 (WMS)。 另一個支援的項目 *要* 啟用以使用 WMS。 要使用此功能，請在 [功能管理](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) 中開啟下列其中一項或兩項功能（按此順序），取決於您是否有為 WMS 啟用的項目：

- *（預覽版）在生產現場執行介面（非 WMS）上登記材料消耗*
- *（預覽版）在生產現場執行介面（啟用 WMS）上登記材料消耗*

> [!IMPORTANT]
> 您可以單獨使用非 WMS 功能。 但是，如果您使用 WMS，則必須啟用這兩個功能。

### <a name="enable-reporting-on-catch-weight-items"></a>啟用對實秤重量品項的報告

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]
<!-- KFM: preview until further notice -->

工人可以使用生產現場執行介面來報告實秤重量品項批次訂單的進度。 批次訂單是從配方建立，能加以定義以包含實秤重量品項，例如配方品項、聯產品和副產品。 配方也可定義成包含成分的配方明細，這些成分則由實秤重量定義。 實秤重量品項使用兩種測量單位來追蹤庫存品項：實秤重量數量和庫存數量。 例如，在食品產業，盒裝肉可定義為實秤重量品項，其中實秤重量數量用於追蹤盒子的數量，庫存數量則用於追蹤盒子重量。

要使用此功能，請在 [功能管理](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) 開啟以下功能：

- *（預覽版）從生產現場執行介面報告實秤重量品項*

## <a name="work-with-production-floor-execution-configurations"></a>使用生產現場執行設定

要建立和維護生產現場執行設定，請前往 **產品控制 \> 設定 \>製造執行 \> 設定生產現場執行**。 此 **設定生產現場執行** 頁面顯示現有設定的清單。 在此頁面上，您可以執行以下動作：

- 選擇左欄中列出的任何生產現場設定以檢視和編輯它。
- 在動作窗格上選取 **新增**，將一個新設定新增至該清單。 接著，在 **設定** 欄位內輸入能識別此新設定的名稱。 您輸入的名稱在所有設定中必須是唯一的，而且您之後將無法對其進行編輯。

接下來，為所選設定設置各種設定。 可以使用以下欄位：

- **只打卡上下班**- 將此選項設為 *是*，建立一個僅提供打卡上班和打卡下班功能的簡易介面。 這會停用此頁面上的大多數其他選項。 您必須從 **索引標籤選項** FastTab 移除所有行，然後才能啟用此選項。
- **啟用搜尋**- 將此選項設為 *是*，以便在作業列表上包含搜尋欄位。 工人可以透過輸入工作識別碼來尋找特定作業，或者透過輸入訂單識別碼來尋找特定訂單的所有作業。 工人可以使用鍵盤或掃描條碼輸入識別碼。
- **下班時報告數量** –將此選項設為 *是*，促使員工在下班時報告正在進行的工作的意見反應。當此選項設為 *否*，則不會強制員工。
- **鎖定員工**–當此選項設為 *否*，工人將在他們註冊後立即登出（例如新工作）。 然後介面將返回登入頁面。 當此選項設為 *是*，工人將保持登入到生產現場執行介面。 但是，當生產現場執行介面繼續在同一系統的使用者帳戶下執行時，一個工人可以手動登出，以便另一個工人可以登入。 更多有關這些類型帳戶的資訊，請參閱 [指派的使用者](config-job-card-device.md#assigned-users)。
- **使用實際註冊時間** –將此選項設為 *是*，將每個新註冊的時間設為工人提交註冊的確切時間。 當此選項設為 *否*，則會使用登入時間。 在員工經常長時間保持登入狀態的情況下，如果你已將 **鎖定員工** 和/或 **單一工人** 選項設為 *是*，則您通常會希望將此選項設為 *是* 。
- **單一工人** –若只有一個工人使用每個生產現場執行介面，其中此設定處於使用中，則將此選項設為 *是* 。 當此選項設為 *是*，則該 **鎖定員工** 選項會自動設為 *是*。 此外，此設定消除了工作人員使用徽章識別碼（或其他類似識別碼）登入的要求（和能力）。 工作人員可改為透過使用連接到 *時間登記工人*（來自 *工作人員* 資料表）登入到 Microsoft Dynamics 365 Supply Chain Management，同時以該工人的身份登入生產現場執行介面。
- **允許鎖定觸控式螢幕** –將此選項設為 *是*，允許工人鎖定生產現場執行介面的觸控式螢幕，以便對其進行清理。 當此選項設為 *是*，一種 **為清理鎖定螢幕** 按鈕會被新增到登入頁面。 當工作人員選擇此按鈕時，觸控式螢幕會暫時鎖定以防止意外輸入。 還會顯示倒數計時器。 然後工人可以安全地清潔裝置和螢幕。 倒數計時完成後，觸控式螢幕會自動解鎖。
- **螢幕鎖定持續時間** - 當 **允許鎖定觸控式螢幕** 選項設為 *是* 時， 使用此選項來指定觸控式螢幕應該被鎖定以進行清理的秒數。 秒數的值必須介於 5 到 120 之間
- **產生牌照** –將此選項設為 *是*，以便每次工人使用生產現場執行介面報告完成時可產生一個新的牌照。 牌照號碼是由設定在 **Warehouse Management參數** 頁面上的編號序列而產生。 當此選項設為 *否*，工人必須在報告完成時指定現有的牌照。
- **列印標籤** –將此選項設為 *是*，以便在工人使用生產現場執行介面報告完成時可列印一個牌照標籤。 標籤設定在文件路由中，如[牌照標籤的文件路由版型](../warehousing/document-routing-layout-for-license-plates.md)所述。
- **索引標籤選項** –當前設定處於使用中時，使用本節中的設定選擇生產現場執行介面應顯示哪些索引標籤。 您可以根據需要設計任意數量的索引標籤，然後根據需要在此處新增和排列它們。 有關如何設計索引標籤和使用此處設定的詳細資訊，請參閱 [設計生產現場執行介面](production-floor-execution-tabs.md)。

## <a name="clean-up-job-configurations"></a>清理作業設定

當工廠主管設定生產現場執行介面時，他們選擇設定和作業篩選器。 這些選擇儲存在 Supply Chain Management 的參考資料表中，瀏覽器使用儲存在本地 cookie 中的識別碼來尋找該表中的正確列。 該表還會記錄工作人員上次登入每個裝置的日期和時間。

批次處理作業會定期清除在過去 60 天內參考資料表中未記錄任何活動的裝置的項目。 您也可以隨時按照以下步驟手動清理項目。

1. 前往 **產品控制 \> 設定 \> 製造執行 \>  設定生產現場執行**。
1. 在動作窗格上，選取 **清理用戶端設定**。
1. 在 **清理用戶端設定** 對話方塊內，將 **天數** 欄位設為要考慮的非使用狀態天數（今天之前）。 您將刪除在此期間非使用狀態裝置的所有設定和登入記錄。
1. 根據 **天數** 設定，選擇 **確定** 清理相關設定。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
