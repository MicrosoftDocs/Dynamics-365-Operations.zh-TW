---
title: 疑難排解財務和營運應用程式中的雙重寫入問題
description: 本主題提供疑難排解資訊，可幫助您解決財務和營運應用程式中的雙重寫入模組問題。
author: RamaKrishnamoorthy
ms.date: 08/10/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: db49c6a4555f39800362a5b248f9757b07ee5481
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8460204"
---
# <a name="troubleshoot-dual-write-issues-in-finance-and-operations-apps"></a>疑難排解財務和營運應用程式中的雙重寫入問題

[!include [banner](../../includes/banner.md)]



本主題提供有關財務和營運應用程式與 Dataverse 之間的雙重寫入整合的疑難排解信息。 具體來說，它提供的資訊可幫助您解決財務和營運應用程式中的 **雙重寫入** 模組問題。

> [!IMPORTANT]
> 本主題解決的一些問題可能需要系統管理員角色或 Microsoft Azure Active Directory (Azure AD) 租使用者管理員認證。 每個問題的部分說明是否需要特定角色或認證。

## <a name="you-cant-load-the-dual-write-module-in-a-finance-and-operations-app"></a>您無法在財務和營運應用程式中載入雙重寫入模組

如果您無法透過在 **資料管理** 工作區中選取 **雙重寫入** 圖格打開 **雙重寫入** 頁面，則資料整合服務可能已關閉。 建立支援票證以請求重新啟動資料整合服務。

## <a name="error-when-you-try-to-create-a-new-table-map"></a>嘗試建立新表對應時出錯

**解決問題所需的認證：** 安裝雙重寫入的同一使用者。

當您嘗試為雙重寫入設定新表時，您可能會收到以下錯誤訊息。 唯一可以建立對應的使用者是安裝雙重寫入連線的使用者。

*回應狀態碼不表示成功：401 (未授權)。*

## <a name="error-when-you-open-the-dual-write-user-interface"></a>打開雙重寫入使用者介面時出錯

當您嘗試從 **資料管理** 工作區存取雙重寫入時，您可能會收到以下錯誤訊息：

*login.microsoftonline.com 拒絕連線。*

若要解決此問題，請使用 Microsoft Edge 中的 InPrivate 窗口、Chromium 中的無痕式視窗或 Google Chrome 中的無痕式視窗登入。 您還必須解除封鎖或清除第三方 Cookie。

## <a name="error-when-you-link-the-environment-for-dual-write-or-add-a-new-table-mapping"></a>連結環境進行雙重寫入或新增新表對應時出錯

**解決問題所需的角色：** 財務和營運應用程式和 Dataverse 中的系統管理員。

連結或建立對應時可能會遇到以下錯誤：

```dos
Response status code does not indicate success: 403 (tokenexchange).
Session ID: \<your session id\>
Root activity ID: \<your root activity\> id
```

如果您沒有足夠的權限來連結雙重寫入或建立對應，則可能會發生此錯誤。 如果在未取消連結雙重寫入的情況下重設 Dataverse 環境，也會發生此錯誤。 在財務和營運應用程式和 Dataverse 中具有系統管理員角色的任何使用者都可以連結環境。 只有安裝雙重寫入連接的使用者才能新增新的表對應。 安裝後，任何具有系統管理員角色的使用者都可以監控狀態並編輯對應。

## <a name="error-when-you-stop-the-table-mapping"></a>停止表對應時出錯

當您嘗試停止表對應時，您可能會收到以下錯誤訊息：

*\[禁止\], \[{"狀態":403,"來源":"","訊息":"語彙基元交換錯誤：不允許使用者存取連線 dynamicscrmonline/xxxxxx-xxxx-xxxx-xxxxxxxx"}\], 遠端伺服器回傳錯誤：(403) 禁止。*

當連結的 Dataverse 環境不可用時，會發生此錯誤。

若要解決此問題，請為資料整合團隊建立票證。 附加網路跟踪，以便資料整合團隊可以在後端將對應標記為 **未執行**。

## <a name="errors-while-trying-to-start-a-table-mapping"></a>嘗試啟動表對應時出錯

### <a name="unable-to-complete-initial-data-sync"></a>無法完成初始資料同步

當您嘗試執行初始資料同步時，您可能會收到如下錯誤：

*無法完成初始資料同步。錯誤：雙重寫入失敗 - 外掛程式註冊失敗：無法構建雙重寫入查詢元資料。錯誤對象參考未設定為對象的實體。*

當您嘗試將對應的該狀態設定為 **執行中** 時，您可能會收到此錯誤。 修復取決於錯誤的原因：

+ 如果對應具有相依性對應，則確保啟用此表對應的相依性對應。
+ 對應可能缺少來源列或目的地資料欄。 如果財務和營運應用程式中的資料欄遺失，請按照[對應上的遺失資料表欄問題](dual-write-troubleshooting-finops-upgrades.md#missing-table-columns-issue-on-maps)章節中的步驟操作。 如果缺少 Dataverse 中的資料欄，則點選對應上的 **重新整理資料表** 按鈕，以便將資料欄自動填入回對應中。

### <a name="version-mismatch-error-and-upgrading-dual-write-solutions"></a>版本不比對錯誤並升級雙重寫入解決方案

當您嘗試執行表對應時，您可能會收到以下錯誤訊息：

+ *客戶組 (msdyn_customergroups)：雙重寫入失敗 -Dynamics 365 for Sales解決方案「Dynamics365Company」的版本不相符。版本：'2.0.2.10' 所需版本：'2.0.133'*
+ *Dynamics 365 for Sales解決方案「Dynamics365FinanceExtended」的版本不相符。版本：'1.0.0.0' 所需版本：'2.0.227'*
+ *Dynamics 365 for Sales解決方案「Dynamics365FinanceAndOperationsCommon」的版本不相符。版本：'1.0.0.0' 所需版本：'2.0.133'*
+ *Dynamics 365 for Sales解決方案「CurrencyExchangeRates」的版本不相符。版本：'1.0.0.0' 所需版本：'2.0.133'*
+ *Dynamics 365 for Sales解決方案「Dynamics365SupplyChainExtended」的版本不相符。版本：'1.0.0.0' 所需版本：'2.0.227'*

若要修復該問題，請更新 Dataverse 中的雙重寫入解決方案。 確保升級到與所需解決方案版本相符的最新解決方案。

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
