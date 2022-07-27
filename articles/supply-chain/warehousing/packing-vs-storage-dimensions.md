---
title: 為包裝和儲存設定不同的尺寸
description: 本主題說明如何指定每個指定尺寸用於哪個程序 (包裝、儲存或巢狀包裝)。
author: mirzaab
ms.date: 01/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResPhysicalProductDimensions, WHSPhysDimUOM
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-01-28
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 0e8ce576f21f1f5ea5f3acb7d43bbe68826e6f39
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449262"
---
# <a name="set-different-dimensions-for-packing-and-storage"></a>為包裝和儲存設定不同的尺寸

[!include [banner](../../includes/banner.md)]

某些品項的包裝或儲存方式可能需要針對數個不同的程序以不同的方式追蹤實體尺寸。 *包裝產品尺寸* 功能可讓您為每個產品設定一種或多種類型的尺寸。 每個尺寸類型都提供一組實體測量值 (重量、寬度、深度和高度)，並建立一個流程來套用這些實體測量值。 啟用此功能後，您的系統將支援以下類型的尺寸：

- *儲存* - 儲存尺寸與位置體積一起使用，以決定每個項目有多少個可以儲存在各種倉庫位置。
- *包裝* - 在集裝箱化和手動包裝過程中使用包裝尺寸來判定每種項目有多少個適合各種容器類型。
- *巢狀包裝* - 當包裝流程包含多個層級時，會使用巢狀包裝維度。

支援 *儲存* 尺寸，即使 *包裝產品尺寸* 功能未啟用亦支援。 您可使用 Supply Chain Management 中的 **實體尺寸** 頁面進行這些設定。 所有未指定包裝與巢狀包裝尺寸的流程會使用這些尺寸。

*包裝* 和 *巢狀包裝* 尺寸設定是使用 **實體產品尺寸** 頁面設定的，當您啟用 *包裝產品尺寸* 功能時會新增此頁面。
本主題提供一個案例說明如何使用此功能。

## <a name="turn-on-the-packaging-product-dimensions-feature"></a>開啟包裝產品尺寸功能

使用此功能之前，您必須先在系統中開啟。 管理員可以使用[功能管理](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)工作區來檢查該功能的狀態，並視需要開啟該功能。 在那裡，該功能按以下方式列出：

- **模組：** *倉庫管理*
- **功能名稱：** *包裝產品尺寸*

## <a name="example-scenario"></a>範例案例

### <a name="set-up-the-scenario"></a>設定案例

在執行範例案例之前，您必須按照本節中的說明準備系統。

#### <a name="enable-demo-data"></a>啟用示範資料

若要使用此處指定的示範記錄和值完成此案例，您必須使用一個已安裝標準[示範資料](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md)的系統。 此外在開始之前，您必須先選擇 *USMF* 法律實體。

#### <a name="add-a-new-physical-dimension-to-a-product"></a>將新的實體尺寸新增至產品

透過以下步驟為產品新增新的實體尺寸：

1. 請前往 **產品資訊管理 \> 產品 \> 已發佈的產品**。
1. 選擇 **項目編號** 為 *A0001* 的產品。
1. 在「動作窗格」中，開啟 **管理庫存** 索引標籤，並且從 **倉庫** 群組選擇 **實體產品尺寸**。
1. **實體產品尺寸** 頁面隨即開啟。 在動作窗格上，選擇 **新增** 在格線中新增新尺寸，然後設定以下欄位：
    - **實體尺寸類型** - *包裝*
    - **實體單位** - *件*
    - **重量** - *4*
    - **重量單位** - *公斤*
    - **深度** - *3*
    - **高度** - *4*
    - **寬度** - *3*
    - **長度** - *公分*
    - **體積單位** - *立方公分*

**體積** 欄位是根據您的 **深度**、**高度** 及 **寬度** 設定自動計算而得。

#### <a name="create-a-new-container-type"></a>建立新的容器類型

移至 **倉庫管理 \> 設定 \> 容器 \> 容器類型**，並使用以下設定建立新記錄：

- **容器類型代碼** - *短盒*
- **描述** - *短盒*
- **淨重上限** - *50*
- **體積** - *144*
- **長度** - *6*
- **寬度** - *6*
- **高度** - *4*

#### <a name="create-a-container-group"></a>建立容器群組

移至 **倉庫管理 \> 設定 \> 容器 \> 容器群組**，並使用以下設定建立新記錄：

- **容器群組識別碼** - *短盒*
- **描述** - *短盒*

將新行項新增至 **詳細資料** 區段。 將 **容器類型** 設定為 *短盒*。

#### <a name="set-up-a-container-build-template"></a>設定容器建構範本

移至 **倉庫管理 \> 設定 \> 容器 \> 容器建構範本**，然後選擇 **盒子**。 將 **容器群組識別碼** 變更為 *短盒*。

### <a name="run-the-scenario"></a>執行案例

按照上一節所述準備好系統後，就可以按照下一節所述執行案例。

#### <a name="create-a-sales-order-and-create-a-shipment"></a>建立銷售訂單並建立運送

在此流程中，您將根據高度小於 3 的項目 *包裝* 尺寸建立運送。

1. 前往 **銷售和行銷\>銷售訂單\>所有銷售訂單**。
1. 在動作窗格上，選擇 **新增**。
1. 在 **建立銷售訂單** 對話方塊中，設定以下值：

    - **使用者帳戶：** *US-001*
    - **倉庫：** *63*

1. 選擇 **確定** 以建立銷售訂單並關閉對話方塊。
1. 此新的銷售訂單已開啟。 它應該在 **銷售訂單行** FastTab 上的格線中包含一個新的空白行。 在此行中設定以下值：

    - **品項編號：** *A0001*
    - **數量：** *5*

1. 在 **銷售訂單明細** FastTab上，選擇 **庫存 \> 保留**。
1. 在 **保留** 頁面，於動作窗格選擇 **保留批號** 以保留庫存。
1. 關閉頁面。
1. 在動作窗格上，開啟 **倉庫** 索引標籤，並選擇 **發佈到倉庫** 為倉庫建立工作。
1. 在 **銷售訂單行** FastTab 上選擇 **倉庫 \> 運送詳細資料**。
1. 在動作窗格上，開啟 **運輸** 索引標籤，並選擇 **檢視容器**。 確認該項目已集裝箱化為兩個 *短盒* 容器。

#### <a name="place-an-item-into-storage"></a>將項目放入儲存體

1. 開啟行動裝置，登入倉庫 63，移至 **貨庫 \> 調整入庫**。
1. 輸入 **Loc** = *SHORT-01*. 製作一個 **項目** = *A0001* 且 **數量** = *1 件* 的新牌照。
1. 選取 **確定**。 您將收到「位置 SHORT-01 失敗，因為項目 A0001 不適合位置的指定尺寸」錯誤訊息。 這是因為產品的 *儲存體* 類型尺寸大於在位置設定檔上指定的尺寸。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]