---
title: 對初始安裝期間的問題進行疑難排解
description: 本主題提供的信息可幫助您解決在初始安裝雙重寫入整合期間出現的問題。
author: RamaKrishnamoorthy
ms.date: 08/10/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 9a70de253eff2a3273be4a31ab32757bb014328f
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8460202"
---
# <a name="troubleshoot-issues-during-initial-setup"></a>對初始安裝期間的問題進行疑難排解

[!include [banner](../../includes/banner.md)]



本主題提供有關財務和營運應用程式與 Dataverse 之間的雙重寫入整合的疑難排解信息。 具體來說，它提供的信息可幫助您解決在初始安裝雙重寫入整合期間可能出現的問題。

> [!IMPORTANT]
> 本主題解決的一些問題可能需要系統管理員角色或 Microsoft Azure Active Directory (Azure AD) 租使用者管理員認證。 每個問題的部分說明是否需要特定角色或認證。

## <a name="you-cant-link-a-finance-and-operations-app-to-dataverse"></a>您無法將財務和營運應用程式連結到 Dataverse

**設定雙重寫入所需的角色：** 財務和營運應用程式和 Dataverse 中的系統管理員。

**安裝連到 Dataverse 的連結** 頁面上的錯誤通常是由不完整的安裝或權限問題引起的。 確保整個執行狀況檢查在 **安裝連到 Dataverse 的連線** 頁面上通過，如下圖所示。 除非整個健康情況檢查通過，否則您無法連結雙重寫入。

![健康情況檢查成功。](media/health_check.png)

您必須擁有 Azure AD 租使用者管理員認證才能連結 Finance and Operations 和 Dataverse 環境。 連結環境後，使用者可以使用其帳戶認證登入並更新現有資料表對應。

## <a name="find-the-limit-on-the-number-of-legal-tables-or-companies-that-can-be-linked-for-dual-write"></a>尋找可連結雙重寫入的法律表或公司的數量限制

當您嘗試啟用對應時，您可能會收到以下錯誤訊息：

*雙重寫入失敗 - 外掛程式註冊失敗：[(無法取得專案 DWM 的分區對應-1ae35e60-4bc2-4905-88ea-69efd3b29260-7f12cb89-1550-42e2-858e-4761fc1443ea。錯誤超過了對應 DWM 允許的最大分區數-1ae35e60-4bc2-4905-88ea-69efd3b29260-7f12cb89-1550-42e2-858e-4761fc1443ea)]，發生一個或多個錯誤。*

連結環境時的現行限制約為 40 個法律表。 如果您嘗試啟用地圖，並且環境之間連結了超過 40 個合法表，則會出現此錯誤。

## <a name="connection-set-failed-while-linking-environment"></a>連接環境時連接設定失敗

連結雙重寫入環境時，操作失敗並顯示錯誤訊息：

*儲存連接集失敗！已新增具有相同金鑰的項目。*

雙重寫入不支援具有相同名稱的多個法律實體/公司。 例如，如果您在 Dataverse 中有兩家名稱為「DAT」的公司，那麼它將收到此錯誤訊息。

若要解除對客戶的封鎖，請從 Dataverse 中的 **cdm_company** 表中刪除重複記錄。 此外，如果 **cdm_company** 表有空白名稱的記錄，刪除或更正這些記錄。

## <a name="error-when-opening-the-dual-write-page-in-finance-and-operations-apps"></a>在財務和營運應用程式中打開雙重寫入頁面時出錯

當您嘗試連結 Dataverse 環境以進行雙重寫入時，您可能會收到以下錯誤訊息：

*回應狀態碼不表示成功：404 (未找到)。*

當應用程式同意步驟未完成時會發生此錯誤。 您可以透過使用租使用者管理帳戶登入 `portal.azure.com` 來驗證是否提供了同意，並檢查 ID 為 `33976c19-1db5-4c02-810e-c243db79efde` 的第三方應用程式是否在 AAD 的企業應用程式清單中顯示。 如果不是，則按照下一節中的說明重新執行同意步驟。

### <a name="providing-app-consent"></a>提供應用程式同意

+ 使用您的管理員認證啟動以下 URL。

    `https://login.microsoftonline.com/common/oauth2/authorize?client_id=33976c19-1db5-4c02-810e-c243db79efde&response_type=code&prompt=admin_consent`

+ 選取 **接受** 即可同意。 您同意在您的租使用者中安裝應用程式 (包含 `id=33976c19-1db5-4c02-810e-c243db79efde`)。
+ Dataverse 需要此應用程式才能與財務和營運應用程式通訊。

    ![初始同步安裝疑難排解。](media/Initial-sync-setup-troubleshooting-1.png)

> [!NOTE]
> 如果這無法正常運作，請在 Microsoft Edge 的無痕式視窗模式或 Chrome 的無痕式視窗模式下啟動 URL。

## <a name="finance-and-operations-environment-is-not-discoverable"></a>無法發現 Finance and Operations 環境

您可能會收到以下錯誤訊息：

*財務和營運應用程式環境\*\*\*.cloudax.dynamics.com 是不可發現的。*

有兩件事會導致無法發現環境的問題：

+ 用於登入的使用者與 Finance and Operations 實體不在同一租使用者中。
+ 有一些由 Microsoft 託管的舊版 Finance and Operations 實體存在發現問題。 若要解決此問題，請更新 Finance and Operations 實體。 任何更新都可以發現環境。

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
