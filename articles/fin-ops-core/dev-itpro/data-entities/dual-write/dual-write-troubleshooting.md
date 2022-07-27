---
title: 一般疑難排解
description: 本主題提供有關財務和營運應用程式與 Dataverse 之間的雙重寫入整合的一般疑難排解資訊。
author: RamaKrishnamoorthy
ms.date: 03/16/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: f6f5b9f26990e2f4db9bf69040a6c4be31400b40
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8460199"
---
# <a name="general-troubleshooting"></a>一般疑難排解

[!include [banner](../../includes/banner.md)]



本主題提供有關財務和營運應用程式與 Dataverse 之間的雙重寫入整合的一般疑難排解資訊。

> [!IMPORTANT]
> 本主題解決的一些問題可能需要系統管理員角色或 Microsoft Azure Active Directory (Azure AD) 租使用者管理員認證。 每個問題的部分說明是否需要特定角色或認證。

## <a name="enable-and-view-the-plug-in-trace-log-in-dataverse-to-view-error-details"></a><a id="enable-view-trace"></a>在 Dataverse 中啟用並查看外掛程式追蹤記錄以查看錯誤詳情

**打開追蹤記錄和查看錯誤所需的角色：** 系統管理員

若要打開追蹤記錄，請執行以下步驟。

1. 登入到 Customer Engagement 應用程式，開啟 **設定** 頁面，然後在 **系統** 下選取 **管理**。
2. 在 **管理** 頁面上，選取 **系統設定**。
3. 在 **自訂** 選項卡上的 **外掛程式和自訂工作流程活動追蹤** 資料欄中，選取 **全部** 以啟用外掛程式追蹤記錄。 如果您只想在發生異常時記錄追蹤記錄，您可以選取 **例外狀況**。


若要檢視追蹤記錄，請執行以下步驟。

1. 登入到 Customer Engagement 應用程式，打開 **設定** 頁面，然後在 **自訂** 下選取 **外掛程式追蹤記錄**。
2. 尋找 **類型名稱** 資料欄設定為 **Microsoft.Dynamics.Integrator.DualWriteRuntime.Plugins.PreCommmitPlugin** 的追蹤記錄。
3. 按兩下點選項目以檢視完整記錄，然後在 **執行** FastTab 上查看 **訊息區塊** 文字。

## <a name="enable-debug-mode-to-troubleshoot-live-synchronization-issues-in-finance-and-operations-apps"></a>啟用偵錯模式以解決財務和營運應用程式中的即時同步問題

**檢視錯誤所需的角色：** 系統管理員

源自 Dataverse 的雙重寫入錯誤可能出現在財務和營運應用程式中。 若要為錯誤啟用詳細記錄，請執行以下步驟：

1. 對於財務和營運應用程式中的所有專案設定，**DualWriteProjectConfiguration** 表上都有一個標幟 **IsDebugMode**。
2. 使用 Excel 增益及集開啟 **DualWriteProjectConfiguration**。 若要使用增益集，請在 Finance and Operations Excel 增益集中啟用設計模式並將 **DualWriteProjectConfiguration** 新增到工作表。 如需相關資訊，請參閱[使用 Excel 檢視和更新實體資料](../../office-integration/use-excel-add-in.md)。
3. 在專案上將 **IsDebugMode** 設定為 **是**。
4. 執行產生錯誤的案例。
5. 詳細記錄儲存在 **DualWriteErrorLog** 表中。
6. 若要在資料表瀏覽器上查詢資料，請使用以下連結：`https://999aos.cloudax.dynamics.com/?mi=SysTableBrowser&tableName=DualWriteErrorLog`，按需求替換 `999`。
7. 在 [KB 4595434](https://fix.lcs.dynamics.com/Issue/Details?kb=4595434&bugId=527820&dbType=3&qc=98e5dc124ac125c57ad633d885ac612aea3ddb8f4abf9d71ab3aa354f2e06cbe) 之後再次更新，可用於平台更新 37 及更高版本。 如果您安裝了此修復程式，則偵錯模式將捕獲更多記錄。  

## <a name="check-synchronization-errors-on-the-virtual-machine-for-the-finance-and-operations-app"></a>檢查財務和營運應用程式的虛擬機器上的同步錯誤

**檢視錯誤所需的角色：** 系統管理員

1. 登入到 Microsoft Dynamics Lifecycle Services (LCS)。
2. 打開您選取為其執行雙重寫入測試的 LCS 專案。
3. 選取 **雲端託管環境** 圖格。
4. 使用遠端桌面登入到財務和營運應用程式的虛擬機器 (VM)。 使用 LCS 中顯示的本機帳戶。
5. 開啟事件檢視器。
6. 選取 **Applications and Services Logs \> Microsoft \> Dynamics \> AX-DualWriteSync \> Operational**。
7. 查看最近的錯誤清單。

## <a name="unlink-and-link-another-dataverse-environment-from-a-finance-and-operations-app"></a>從財務和營運應用程式取消連結並連結另一個 Dataverse 環境

**取消連結環境所需的角色：** 財務和營運應用程式或 Dataverse 的系統管理員。

1. 登入到財務和營運應用程式。
2. 進入 **工作區\>資料管理**，並選取 **雙重寫入** 圖格。
3. 選取所有正在執行的對應，然後選取 **停止**。
4. 選取 **取消連結環境**。
5. 選取 **是** 即可確認作業。

您現在可以連結一個新環境。

## <a name="unable-to-view-the-sales-order-line-information-form"></a>無法查看銷售訂單行資訊表單 

在 Dynamics 365 Sales 中建立銷售訂單時，點選 **+新增產品** 可能會將您重新導向到 Dynamics 365 Project Operations 訂單明細表單。 從該表單無法檢視銷售訂單線 **資訊** 表單。 **資訊** 的選項不會顯示在 **新訂單明細** 以下的下拉式清單中。 發生這種情況是因為您的環境中已安裝 Project Operations。

若要重新啟用 **資訊** 表單選項，請按照下列步驟操作：

1. 導覽到 **訂單明細** 表。
2. 在表單節點下尋找 **資訊** 表單。
3. 選取 **資訊** 表單，然後點選 **啟用資訊安全角色**。
4. 更改安全設定以 **顯示給每個人**。

## <a name="how-to-enable-and-save-network-trace-so-that-traces-can-be-attached-to-support-tickets"></a>如何啟用和儲存網路追蹤，以便可以將追蹤附加到支援票證

支援團隊可能需要查看網路追蹤以解決某些問題。 若要建立網路追蹤，請按照下列步驟操作：

### <a name="chrome"></a>Chrome

1. 在開啟的選項卡中，按 **F12** 或選取 **開發人員工具** 以開啟開發人員工具。
2. 在篩選文字方塊中開啟 **網路** 選項卡並輸入 **Integ**。
3. 執行您的方案並觀察正在記錄的要求。
4. 按右鍵點選項目，然後選取 **將全部儲存為 RAR** 內容。

### <a name="microsoft-edge"></a>Microsoft Edge

1. 在開啟的選項卡中，按 **F12** 或選取 **開發人員工具** 以開啟開發人員工具。
2. 打開 **網路** 索引標籤。
3. 執行您的案例。
4. 選取 **儲存** 將結果匯出為 HAR。

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
