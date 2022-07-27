---
title: 設定相依於動作的 ER 目的地
description: 本主題說明如何為設定為產生輸出文件的電子報表 (ER) 格式設定動作相關目的地。
author: NickSelin
ms.date: 02/09/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERFormatDestinationTable
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: f3055a27-717a-4c94-a912-f269a1288be6
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-12-01
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: e0c836d4a0be47b753d74dc9d6d40ea7d9197176
ms.sourcegitcommit: d5d6b81bd8b08de20cc018c2251436065982489e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/17/2022
ms.locfileid: "8460563"
---
# <a name="configure-action-dependent-er-destinations"></a>設定相依於動作的 ER 目的地

[!include [banner](../includes/banner.md)]

您可以為用於產生輸出文件的[電子報表 (ER)](general-electronic-reporting.md) 格式[設定](general-electronic-reporting.md#Configuration)的每個輸出組件 (資料夾或檔案) 設定[目的地](electronic-reporting-destinations.md)。 執行這種類型的 ER 格式並具有適當存取權限的使用者還可以在執行階段更改設定的目的地設定。

在 Microsoft Dynamics 365 Finance **10.0.17 及更高版本** 中，可以透過[佈建](er-apis-app10-0-17.md)動作代碼來執行 ER 格式，該代碼是由使用者透過執行該 ER 格式來執行。 例如，在 **應收帳款** 模組，在列印管理設定中，您可以選取產生特定商業檔案的 ER 格式，例如普通發票。 然後，您可以選取 **檢視** 以預覽發票或選取 **列印** 以將其發送到印表機。 如果在執行階段為正在執行的 ER 格式傳遞使用者動作，您可以為不同的使用者動作設定不同的 ER 目的地。 本主題說明如何為此類 ER 格式設定 ER 目的地。

## <a name="make-action-dependent-er-destinations-available"></a>使相依於動作的 ER 目的地可用

若要在現行 Finance 實體中設定與動作相關的 ER 目的地並啟用 [新的](er-apis-app10-0-17.md) ER API，請開啟 [函數管理](../../fin-ops/get-started/feature-management/feature-management-overview.md#the-feature-management-workspace)工作區，然後打開 **設定特定 ER 目的地以用於不同的 PM 動作** 函數。 若要在執行階段為 [特定](#reports-list-wave1)報表使用設定的 ER 目的地，請啟用函數，**即基於使用者動作特定的 ER 目的地路由 PM 報表的輸出 (第 1 波)**。

## <a name="configure-action-dependent-er-destinations"></a>設定相依於動作的 ER 目的地

當您打開 **設定特定 ER 目的地以用於不同 PM 動作** 函數時，您可以在 **電子報表目的地** 頁面的 **檔案目的地** FastTab 上設定與動作相關的 ER 目的地。 對於每個組件，您可以新增一條記錄並啟用特定的 ER 目的地。 對於每條記錄，您必須指定設定的 ER 目的地應申請的文件類型。 在 **檔案類型** 欄位，選取以下值之一：

- 如果在執行階段未提供使用者動作代碼，請選取 **電子** 套用設定的目的地。
- 如果在執行階段提供了使用者動作代碼，請選取 **列印管理** 以應用設定的目的地。
- 選取 **任何** 即可一律應用設定的目的地，無論是否在執行階段提供使用者動作。

如果您選取 **列印管理** 文件類型，則必須指定應應用設定的 ER 目的地的使用者動作。 在 **列印管理** 動作欄位中，選取以下值之一：

- 如果在執行階段提供了 **檢視** 使用者動作，請選取 **檢視** 以套用設定的目的地。
- 如果在執行階段提供了 **列印** 使用者動作，請選取 **列印** 以套用設定的目的地。
- 如果在執行階段提供了 **傳送** 使用者動作，請選取 **傳送** 以套用設定的目的地。

> [!NOTE]
> 可以為單個目的地記錄選取多個動作。

如果您選取 **任何** 文件類型，則會在 **列印管理動作** 欄位中自動選取 **自動檢測** 作為使用者動作，並且會發生以下行為：

- 如果在執行階段未提供使用者動作代碼，則應用所有設定的 ER 目的地。
- 如果在執行階段提供了使用者動作代碼，則應用為特定動作預定義的 ER 目的地，**無論它是否已啟用**：

    - 在執行階段提供 **檢視** 動作時，將套用 **畫面控制項** ER 目的地。
    - 在執行階段提供 **傳送** 動作時，將套用 **電子郵件** ER 目的地。
    - 在執行階段提供 **列印** 動作時，將套用 **印表機** ER 目的地。

例如，您可以在過帳時使用 **普通發票 (Excel)** ER 格式列印[普通發票](../../../finance/accounts-receivable/create-free-text-invoice-new.md)。 若要路由產生的文件，您必須為此 ER 格式設定 ER 目的地。 例如，您可能需要設定這些 ER 目的地以對產生的文件執行以下動作：

- 如果執行 ER 格式但未提供動作代碼 (例如，以電子方式發送文件時)，則封存文件。
- 當使用者執行 **檢視** 動作時，在網路瀏覽器中預覽文件。
- 當使用者執行 **列印** 動作時存檔並列印文件。
- 當使用者執行 **傳送** 動作時，歸檔文件並將其作為輸出電子郵件的附件透過電子郵件發送。

下圖顯示了當為單個使用者動作設定每條記錄時，如何將 ER 目的地設定為單個目的地記錄集：

![當為單個使用者動作設定每個目的地記錄時，電子報表目的地頁面具有 ER 格式的動作相關目的地設定。](./media/er-destination-action-dependent-01.png)

下圖顯示了當為單個目的地設定每條記錄時，如何實現與單個目的地記錄集相同的交替設定 ER 目的地：

![當每個目的地記錄都設定為單個目的地時，電子報表目的地頁面具有 ER 格式的動作相關目的地設定。](./media/er-destination-action-dependent-01a.png)

> [!NOTE]
> 如果為正在執行的 ER 格式提供了動作代碼，但尚未為該動作代碼設定目的地，則套用[預設](electronic-reporting-destinations.md#default-behavior)目的地行為。

## <a name="change-action-dependent-er-destinations-at-runtime"></a>在執行階段更改相依於動作的 ER 目的地

執行 ER 格式時，如果使用者動作已由具有在執行階段更改已設定目的地設定的適當[權限](electronic-reporting-destinations.md#security-considerations)的使用者提供，則會出現一個對話方塊，提供更改已設定目的地設定的選項。 此對話方塊是可選的，其外觀取決於 ER 架構為執行 ER 格式而進行的調用是如何實現的。 如果出現此對話方塊，將根據提供的使用者動作啟用其中的 ER 目的地。

下圖顯示了在 [過帳](../../../finance/accounts-receivable/create-free-text-invoice-new.md)普通發票並執行 **普通發票 (Excel)** ER 格式以產生此文件時出現的 **電子報表格式目的地** 對話方塊的範例，前提是已設定 **印表機** 動作並為此格式設定 ER 目的地，如本主題前面所示。

![提供選項的對話方塊，用於更改正在執行的 ER 格式的初始設定的 ER 目的地。](./media/er-destination-action-dependent-02.gif)

> [!NOTE]
> 如果您為正在執行的 ER 格式的多個組件設定了 ER 目的地，則會為每個已設定的 ER 格式組件單獨提供一個選項。

## <a name="verify-the-provided-user-action"></a>驗證提供的使用者動作

當您執行特定使用者動作時，您可以驗證為正在執行的 ER 格式提供了哪些使用者動作 (如果有)。 當您必須設定與動作相關的 ER 目的地時，此驗證很重要，但您不確定提供了哪個使用者動作代碼 (如果有)。 例如，當您開始過帳普通發票並在 **過帳普通發票** 對話方塊中將 **列印發票** 選項設定為 **是** 時，您可以將 **使用列印管理目的地** 選項設定為 **是** 或 **否**。

按照以下步驟驗證提供的使用者動作代碼。

1. 進入 **組織管理**\>**電子報表**\>**設定**。
2. 在 **設定** 頁面上，在動作窗格上，在 **設定** 索引標籤上，在 **進階設定** 組中，選取 **使用者參數**。
3. 在 **使用者參數** 對話方塊中，將 **在偵錯模式下執行** 選項 [設定](er-trace-reports-compare-baseline.md#configure-er-parameters-to-use-the-baseline-feature)為 **是**。
4. 透過執行 ER 格式執行使用者動作。 請記住，ER 使用者參數是公司特定和使用者特定的。
5. 進入 **組織管理**\>**電子報表**\>**設定偵錯記錄**。
6. 在 **設定偵錯記錄** 頁面上，篩選 ER 執行記錄以查詢您的 ER 格式執行的記錄。
7. 如果已為 ER 格式執行提供了任何動作，請查看必須包含提供所提供使用者動作代碼的記錄的記錄條目。

    ![電子報表執行記錄頁面，其中包含有關已為 ER 格式的過濾執行提供的使用者動作代碼的資訊。](./media/er-destination-action-dependent-03.png)

## <a name=""></a><a name="reports-list-wave1">商業檔案清單 (第 1 波)</a>

以下商業檔案清單由該功能控制，**基於使用者動作特定的 ER 目的地路由 PM 報表的輸出 (第 1 波)**：

- 客戶發票 (普通發票)
- 客戶發票 (銷售發票)
- 訂購單
- 訂購單採購查詢
- 銷售訂單確認
- 收款通知單
- 利息單
- 廠商付款建議
- 詢價

## <a name="additional-resources"></a>其他資源

[電子報表 (ER) 概觀](general-electronic-reporting.md)

[電子報表 (ER) 目的地](electronic-reporting-destinations.md)

[應用程式更新的電子報表架構 API 更改 10.0.17](er-apis-app10-0-17.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
