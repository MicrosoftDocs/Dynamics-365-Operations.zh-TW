---
title: 建立一個資產
description: 本主題介紹如何在資產管理中建立資產。
author: johanhoffmann
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetObjectTableCopyStructure, EntAssetObjectTableCreate
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1e9c2b81e97a7b08dfdb596fbf6822ac94c7358dccd0b92c0677467dbc0c2e26
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446700"
---
# <a name="create-an-asset"></a>建立一個資產

[!include [banner](../../includes/banner.md)]

 

本主題介紹如何在資產管理中建立資產。

1. 按一下 **資產管理** > **通用** > **資產** > **所有資產** 或 **使用中資產**。
2. 按一下 **新增** 按鈕。
3. 在 **建立資產** 對話方塊中，插入有關 **資產** (即資產識別碼) 和資產名稱的資料。 在 **生效** 欄位中選擇資產的日期和時間。 從該日期起，您可以將資產安裝在功能位置以及在資產結構中移動和替換該資產。
4. 在 **資產類型** 欄位中，選擇資產的資產類型 (必要欄位)。 如果需要，請為該資產選擇 **資產製造商** 與 **資產型號**。 如果您僅設定了一項產品，則該產品會自動在 **資產製造商** 欄位被選定。 **資產製造商** 和 **資產型號** 欄位中可用的選項，取決於[資產製造商和型號](../setup-for-objects/product-and-model.md)中的設定。
5. 在 **父系資產** 群組中 **資產** 欄位預設為空白。 如果需要，您可以選擇一個父系資產，然後所有 **父系資產** 群組中的欄位都會自動填入。
    >[!NOTE]  
    >當您選擇父系資產時，將出現二個或三個可用索引標籤：**我的資產** 索引標籤包含與您 (登錄系統的維護工人) 可能被指派到的功能位置相關資產。 如果您沒有為維護人員設定功能位置 [維修工人和工人群組](../setup-for-objects/workers-and-worker-groups.md)表單，則無法看見 **我的資產** 索引標籤。 **使用中資產** 索引標籤包含資產生命週期狀態為「使用中」的所有資產清單。 **資產檢視** 索引標籤顯示功能位置和安裝在這些位置上的資產樹狀圖。

6. 建議在 **資產** 群組 > **功能位置** 欄位中為該資產設定您的預設功能位置。 如需要，選擇另一個功能位置。

    >[!NOTE]
    >如果需要，您可以在建立資產後將其安裝在另一個功能位置。 只有最高層的資產 (沒有目前父系資產的資產) 可以安裝在功能位置。 這代表您在選定的功能位置安裝最高層資產以及任何子系資產。 閱讀有關在功能位置安裝資產的更多資訊[功能位置介紹](../functional-locations/introduction-to-functional-locations.md)。

7. 按一下 **確定**。
8. 選擇 **所有資產** 清單中的資產，並按一下 **編輯** 按鈕，以向資產新增更多資訊。

## <a name="general-information"></a>一般資訊

資產相關的功能位置顯示在 **功能位置** 欄位中。 如果該資產是父系資產，則與該資產相關的子系資產數量會顯示在 **子系** 欄位。 如果該資產是現有資產的子資產，則該父系資產的識別碼會顯示於 **上層** 欄位中。

你可以在該資產上編輯 **資產製造商** 與 **資產型號** 資訊，用於管理備份零件、替代備份零件，和工作類型預設值。 參考[資產製造商和型號](../setup-for-objects/product-and-model.md)以了解更多資訊。 如果需要，您還可以新增有關 **型號年份** 和 **序號** 等資訊。

**目前生命週期狀態** 是用於定義資產為使用中或非使用中。 建立資產時，該階段會一律設定為資產階段群組中的第一個階段。 當您準備好啟用資產時，按一下 **更新資產狀態**，然後選擇您定義為「資產使用中」的生命週期狀態，然後按一下 **確定**。

**注意：** 當資產設定為「非使用中」時，您將無法再為該資產建立工單。 此外，您不能為非使用中資產安排預防性維護作業。

該 **服務等級** 與 **重要性** 欄位與為資產建立的工單相關。 這些欄位顯示為資產目前設定計算的 **服務等級** 和 **重要性** 數量。 有關這些值的設定，請參閱[資產服務等級](../setup-for-objects/object-priorities.md)和[資產重要性類型](../setup-for-objects/object-criticalities.md)。

## <a name="asset"></a>資產

您可以為該資產選擇一個 **資源**。 該資源選擇可確定用於工單計劃的日曆。 資源選擇通常用於固定資產。 您可在 **組織管理** > **資源** > **資源群組** 或 **資源** 中設定資源和資源群組。

在 **固定資產編號** 欄位中，您可以選擇與資產相關的固定資產。 如果您的資產與投資專案相關，則這是相關的。

- 如果資產與固定資產相關，您可以建立工單類型以用於與投資專案相關的工單。 
- 一項資產的固定資產資訊與在 Dynamics 365 Supply Chain Management 中的 **固定資產** 模組相關。 這代表在 **固定資產**  >  **固定資產**  >  **固定資產** 中，您可以透過選擇清單中的資產，並檢視 **相關資訊** 窗格 > **關聯的專案** 部分中的內容，來取得可能與固定資產相關的資產管理專案概觀。


## <a name="details"></a>詳細資料​​

在 **啟用自** 欄位中，將顯示您將資產生命週期更新為使用中狀態的日期 (請參閱[資產生命週期狀態](../setup-for-objects/object-stages.md)關於資產生命週期狀態的設定)。 如果該資產不再處於使用中狀態，並且您已將資產生命週期狀態更新為非使用中，則該資產的非使用中狀態日期將顯示於 **使用至** 欄位。 如需要，您可以手動變更這些日期。

如需要，您可以在 **替換日期** 欄位插入預期的資產替換日期。 替換資產的估計值可以插入到 **替換值** 欄位中。 範例：您可以使用替換資訊將它與維護資產的成本進行比較，然後在現有資產維護成本迅速增加時，做出購買新資產的決定。

## <a name="notes"></a>附註

您可以在 **附註** FastTab 上新增與資產相關的註記。 如果要在註記中新增使用者資訊和日期/時間戳記，請在撰寫註記之前按一下 **新增時間戳記**。

## <a name="attributes"></a>屬性

在此 FastTab 上，您可設定資產屬性的值。 這些屬性可用於描述與資產相關的屬性或特徵，例如尺寸、重量或機器設定。

按一下 **新增明細**，並選擇屬性類型。 下一步，插入與屬性類型相關的 **值** 並儲存記錄。

>[!NOTE] 
>您可以在 **資產屬性** 與 **資產屬性概觀** 中取得資產屬性類型及其與資產的關係。 參考[資產屬性概觀](../objects/object-specification-overview.md)以了解更多資訊。

## <a name="vendor"></a>廠商

在 **廠商** FastTab 上，選擇資產的廠商帳戶。 此外，如果廠商保固已被授予，您可以在此處插入保固資訊。

## <a name="address"></a>地址

在 **地址** FastTab 上，您可以插入設備的地址。 如果資產上沒有插入地址，若父系資產有地址，則該資產會使用父系資產地址。 如果沒有與資產或資產階層中的任何父系相關的地址，則可以使用安裝資產的功能位置地址。 如果該功能位置沒有與其相關的地址，則該資產會使用父系功能位置的地址。

## <a name="asset-management-plans"></a>資產管理計劃

維護計劃是用於定期對資產安排預防性維護工作。 在此 FastTab 上，您可以為所選資產設定維護計劃明細。 您可以為各種資產設定維護週期，而您需要定期在這些資產上執行類似工作。 在 **功能位置維護計劃** 索引標籤上，您會看到與安裝資產功能位置相關的維護計劃。

>[!NOTE]
>如果您在 **所有資產** 中刪除與資產相關的維護計劃明細或維護週期，您也會自動刪除所有根據該維護計劃或維護週期建立，狀態為「已建立」的維護計劃。

## <a name="functional-location-maintenance-plans"></a>功能位置維護計劃

在此 FastTab 上，您會取得與安裝資產功能位置相關的維護計劃概觀。

## <a name="maintenance-rounds"></a>維護週期

在此 FastTab 上，您可以新增或刪除與資產相關的維護週期。

## <a name="financial-dimensions"></a>財務維度

您可為資產選擇財務維度。


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]