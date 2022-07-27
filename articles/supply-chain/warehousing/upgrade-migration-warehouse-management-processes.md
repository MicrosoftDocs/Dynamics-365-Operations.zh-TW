---
title: 將倉庫管理從 Microsoft Dynamics AX 2012 升級至 Supply Chain Management
description: 本主題概述了產品和倉庫管理遷移選項。
author: perlynne
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventLocationWHSProcessEnablement, WHSLocationProfile, InventTableStorageDimensionGroupChange, InventUpdateBlockedItem, WHSParameters, WHSReservationHierarchy, WHSUOMSeqGroupTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 1714054
ms.assetid: 79a1a3b9-3a36-4162-8839-ec39b5e26602
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5ac8c0d8781e5146186fbf71ce619f90ca3556ccefefe7e974efded7e0eb86dd
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447258"
---
# <a name="upgrade-warehouse-management-from-microsoft-dynamics-ax-2012-to-supply-chain-management"></a>將倉庫管理從 Microsoft Dynamics AX 2012 升級至 Supply Chain Management 


[!include [banner](../includes/banner.md)]

本主題概述執行 WMSII 模組從 Microsoft Dynamics AX 2012 R3 升級到 Supply Chain Management 的過程。

Supply Chain Management 不再支援來自 Microsoft Dynamics AX 2012 的舊版 **WMSII** 模組。 相反，您可以使用 **倉庫管理** 模組。 在 WMSII 模組中，可以為財務庫存選擇「位置」和「托盤識別碼」庫存維度，但是在 Supply Chain Management 中，不能將「托盤識別碼」庫存維度用於財務庫存。

在升級過程中，將識別與使用托盤識別碼庫存維度的儲存尺寸群組關聯的所有產品、並標記為已鎖定，並且不會進行升級處理。

## <a name="upgrading-to-supply-chain-management-when-ax-2012-r3-wmsii-is-used"></a>使用 AX 2012 R3 WMSII 時升級到 Supply Chain Management
升級後，您可以使用 **變更品項的儲存尺寸群組** 表單中的選項組取消鎖定在升級期間被鎖定的產品，然後處理這些產品的交易。

### <a name="enabling-items-in-supply-chain-management"></a>在 Supply Chain Management 中啟用品項 
之所以需要執行此變更，是因為在 Supply Chain Management 中，品項追蹤是倉庫管理流程的一部分。 對於這些流程，所有倉庫及其位置都必須與位置設定檔相關聯。 如果要使用倉庫管理流程，必須設定以下內容：
-   必須啟用現有倉庫以使用倉庫管理流程 
-   現有已發佈產品必須與使用倉庫管理流程的儲存尺寸群組相關聯 

如果來源儲存尺寸群組使用托盤識別碼庫存維度，則使用托盤識別碼庫存維度的現有庫存的位置必須與與選擇了 **使用牌照追蹤** 參數的位置範本相關聯。 如果不應啟用現有倉庫以使用倉庫管理流程，可以將現有庫存的儲存尺寸群組變更為僅處理站點、倉庫和位置庫存維度的群組。 

> [!NOTE] 
>  即使存在未結庫存交易，您也可以變更品項的儲存尺寸群組。

## <a name="find-products-that-were-blocked-because-of-pallet-id"></a>尋找因托盤識別碼而鎖定的產品
若要查看在升級過程中已鎖定且無法處理的已發佈產品清單，請點選 **庫存管理** &gt; **設定** &gt; **庫存** &gt; **針對庫存更新鎖定的品項**。

## <a name="change-storage-dimension-group-for-blocked-products"></a>變更已封鎖產品的儲存尺寸群組 
 
若要作為倉庫管理流程的一部分，品項必須與「位置」庫存維度處於活動狀態且選擇了 **使用倉庫管理流程** 參數的儲存尺寸群組相關聯。 選擇此設定後，站點、倉庫、庫存狀態、位置和牌照庫存維度將變為使用中狀態。

若要取消鎖定在升級期間已鎖定的產品，必須為該產品選擇新的儲存尺寸群組。 請注意，即使存在未結庫存交易，您也可以變更儲存尺寸群組。 若要使用在升級期間已鎖定的品項，有兩個選擇：

-   將品項的儲存尺寸群組變更為僅使用站點、倉庫和位置庫存維度的儲存尺寸群組。 進行此變更後，將不再使用托盤識別碼庫存維度。
-   將品項的儲存尺寸群組變更為僅使用倉庫管理流程的儲存尺寸群組。 進行此變更後，將立即開始使用牌照庫存維度。

## <a name="configure-warehouse-management-processes"></a>設定倉庫管理流程
在您可以使用 **倉庫管理** 模組中的已發佈產品之前，產品必須使用選擇了 **使用倉庫管理流程** 參數的儲存尺寸群組。

### <a name="enable-warehouses-to-use-warehouse-management-processes"></a>啟用倉庫以使用倉庫管理流程

1.  建立至少一個新的位置設定檔。
2.  點選 **倉庫管理** &gt; **設定** &gt; **啟用倉庫管理流程** &gt; **啟用倉庫設定**。
3.  在 **啟用倉庫設定** 頁面，新增應啟用的倉庫。 您可以直接在頁面上或使用 Microsoft Office 整合輕鬆完成此步驟。
4.  將位置設定綁指派到所有位置。 您可以直接從頁面使用 Microsoft Office 整合輕鬆完成此步驟。 您可以在[資料管理](../../fin-ops-core/dev-itpro/data-entities/data-entities.md)中匯出和匯入資料，也可以使用資料實體處理。
5.  驗證變更。 作為驗證流程的一部分，會進行各種資料完整性驗證。 作為更大的升級流程的一部分，可能必須在來源實作上調整發生的問題。 在這種情況下，將需要額外的資料升級。
6.  處理變更。

### <a name="change-the-storage-dimension-group-for-items-so-that-it-uses-warehouse-management-processes"></a>變更品項的儲存尺寸群組，已變其使用倉庫管理流程

1.  建立新的 **庫存狀態** 值，並將其指派為 **倉庫管理參數** 設定中的 **預設庫存狀態識別碼**。
2.  建立選擇了 **使用倉庫管理流程** 參數的新儲存尺寸群組。
3.  在 **預留階層** 頁面，根據品項的儲存和追蹤維度群組定義新的預留階層。
4.  建立一個或多個單位序列群組，其中至少包含用於品項庫存單位的相同單位。
5.  點選 **倉庫管理** &gt; **設定** &gt; **啟用倉庫管理流程** &gt; **變更品項的儲存尺寸群組**。
6.  在 **變更品項的儲存尺寸群組** 頁面，新增品項編號、儲存尺寸群組和單位序列群組。 您可以直接在頁面上，使用 Microsoft Office 整合，或使用[資料管理](../../fin-ops-core/dev-itpro/data-entities/data-entities.md)中的資料實體流程完成此步驟。
7.  驗證變更。 作為驗證流程的一部分，會進行各種資料完整性驗證。 作為更大的升級流程的一部分，可能必須在來源實作上調整發生的問題。 在這種情況下，將需要額外的資料升級。
8.  處理變更。 更新所有庫存維度可能需要一段時間。 您可以使用批次作業工作來監視進度。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]