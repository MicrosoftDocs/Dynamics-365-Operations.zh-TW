---
title: 安裝庫存能見度增益集
description: 本主題介紹如何安裝適用於 Microsoft Dynamics 365 Supply Chain Management 的庫存能見度增益集。
author: yufeihuang
ms.date: 08/02/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: a49f35211f30cdb76104cc5be78f5b114320a228
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8449847"
---
# <a name="install-and-set-up-inventory-visibility"></a>安裝及設定庫存能見度

[!include [banner](../includes/banner.md)]


本主題介紹如何安裝適用於 Microsoft Dynamics 365 Supply Chain Management 的庫存能見度增益集。

您必須使用 Microsoft Dynamics Lifecycle Services (LCS) 以安裝庫存能見度增益集。 LCS 是一個協作入口網站，提供了一個環境和一組定期更新的服務，可幫助您管理財務和營運應用程式的應用程式生命週期。

如需更多資訊，請參閱 [Lifecycle Services 資源](../../fin-ops-core/dev-itpro/lifecycle-services/lcs.md)。

## <a name="inventory-visibility-prerequisites"></a>庫存能見度先決條件

在安裝庫存能見度之前，您必須完成以下工作：

- 獲取至少部署一個環境的 LCS 實作專案。
- 確保已完成設定增益集的先決條件。 有關這些先決條件的資訊，請參閱[增益集概述](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md)。 庫存能見度不需要雙重寫入連結。

> [!NOTE]
> 目前支援的國家和地區包括加拿大 (CCA、ECA)、美國 (WUS、EUS)、歐盟 (NEU、WEU)、英國 (SUK、WUK)、澳洲 (EAU、SEAU)、日本 (EJP、WJP) 和巴西 (SBR、SCUS)。

如果您對這些先決條件有任何疑問，請聯繫庫存能見度產品團隊：[inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com)。

## <a name="install-the-inventory-visibility-add-in"></a><a name="install-add-in"></a>安裝庫存能見度增益集

在安裝增益集之前，註冊應用程式並將用戶端密碼新增到在您 Azure 訂閱之下的 Azure Active Directory (Azure AD)。 相關說明請參閱[註冊應用程式](/azure/active-directory/develop/quickstart-register-app)和[新增用戶端密碼](/azure/active-directory/develop/quickstart-register-app#add-a-certificate)。 請務必記下 **應用程式 (用戶端) 識別碼**、**用戶端密碼** 和 **租用戶識別碼** 值，因為您稍後將需要它們。

註冊應用程式並將用戶端密碼新增到 Azure AD 之後，請按照以下步驟安裝庫存能見度增益集。

1. 登入 [LCS](https://lcs.dynamics.com/Logon/Index)。
1. 在首頁選擇部署您環境的專案。
1. 在專案頁面選擇要安裝增益集的環境。
1. 在環境頁面向下捲動直到找到 **Power Platform 整合** 區段之中的 **環境增益集** 區段。 您可以在其中找到 Dataverse 環境名稱。 確認 Dataverse 環境名稱是您要用於庫存能見度的名稱。

    > [!NOTE]
    > 目前只支援以 LCS 建立的 Dataverse 環境。 如果您的 Dataverse 環境是以其他方式建立 (例如使用 Power Apps 系統管理中心)，且如果該環境連結到您的 Supply Chain Management 環境，您首先必須聯繫庫存能見度產品團隊：[inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) 以修復對應問題。 之後您就可以安裝庫存能見度。

1. 在 **環境增益集** 區段選擇 **安裝新的增益集**。

    ![LCS 中的環境頁面](media/inventory-visibility-environment.png "LCS 中的環境頁面")

1. 選擇 **安裝新的增益集** 連結。 出現可用增益集清單。
1. 在清單中選取 **庫存能見度**。
1. 為您的環境設定以下欄位：

    - **AAD 應用程式 (用戶端) 識別碼** – 輸入您之前建立和記下的 Azure AD 應用程式識別碼。
    - **AAD 租用戶識別碼** – 輸入您之前記下的租用戶識別碼。

    ![設定增益集頁面](media/inventory-visibility-setup.png "設定增益集頁面")

1. 選擇 **條款及條件** 核取方塊以同意條款及條件。
1. 選擇 **安裝**。 增益集的狀態顯示為 **安裝中**。 安裝完成時請重新整理頁面。 狀態應變更為 **已安裝**。
1. 在 Dataverse 於左側導覽選擇 **應用程式** 區段，並確認 **庫存能見度** Power Apps 已安裝成功。 如果 **應用程式** 區段不存在，請聯繫庫存能見度產品團隊：[inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com)。

> [!TIP]
> 我們建議您加入庫存能見度增益集使用者群組，您可以在其中找到有用的指南、獲取我們的最新更新，並發佈您對使用庫存能見度的任何可能問題。 如欲加入，請發送電子郵件至庫存能見度產品團隊：[inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com)，並在其中包含您的 Supply Chain Management 環境識別碼。

> [!IMPORTANT]
> 如果您有多個 LCS 環境，請為每個環境建立一個不同的 Azure AD 應用程式。 如果您使用相同的應用程式識別碼和租用戶識別碼為不同的環境安裝庫存能見度增益集，則舊環境會出現權杖問題。 只有最後一個安裝的才是有效的。

## <a name="uninstall-the-inventory-visibility-add-in"></a><a name="uninstall-add-in"></a>解除安裝庫存能見度增益集

要解除安裝庫存能見度增益集，請選擇 LCS 頁面的 **解除安裝**。 解除安裝過程會終止庫存能見度增益集、從 LCS 取消註冊增益集，並刪除儲存在庫存能見度增益集資料快取的任何臨時資料。 但是您 Dataverse 訂閱儲存的主要庫存資料不會刪除。

如欲解除安裝您 Dataverse 訂閱儲存的庫存資料，請開啟 [Power Apps](https://make.powerapps.com)，選擇導覽列的 **環境**，然後選擇與您 LCS 環境綁定的 Dataverse 環境。 然後前往 **解決方案**，並依序刪除以下五項解決方案：

1. Dynamics 365 解決方案中 Inventory Visibility 應用程式的錨定解決方案
1. Dynamics 365 FNO SCM Inventory Visibility 應用程式解決方案
1. 庫存服務設定
1. Inventory Visibility 獨立版
1. Dynamics 365 FNO SCM Inventory Visibility 基礎解決方案

刪除這些解決方案後，儲存在資料表中的資料也將遭到刪除。

## <a name="set-up-inventory-visibility-in-supply-chain-management"></a><a name="setup-dynamics-scm"></a>在 Supply Chain Management 中設定庫存能見度

### <a name="deploy-the-inventory-visibility-integration-package"></a><a name="deploy-inventory-visibility-package"></a>部署庫存能見度整合套件

如果您執行的是 Supply Chain Management 版本 10.0.17 或更早版本，請聯繫庫存能見度線上支援團隊：[inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) 以獲取套件檔案。 然後在 LCS 中部署該套件。

> [!NOTE]
> 如果在部署過程中出現版本不符錯誤，您必須手動將 X++ 專案導入您的開發環境。 然後在您的開發環境中建立可部署的套件，並將其部署到您的實際執行環境中。
>
> 程式碼包含在 Supply Chain Management 版本 10.0.18 中。 如果您正在執行該版本或更高版本，則不需要部署。

確保在您的 Supply Chain Management 環境中啟用了以下功能。 (這些功能預設為開啟。)

| 功能說明 | 程式碼版本 | 切換類別 |
|---|---|---|
| 在 InventSum 資料表啟用或停用使用庫存維度      | 10.0.11 | InventUseDimOfInventSumToggle      |
| 在 InventSumDelta 資料表啟用或停用使用庫存維度 | 10.0.12 | InventUseDimOfInventSumDeltaToggle |

### <a name="set-up-inventory-visibility-integration"></a><a name="setup-inventory-visibility-integration"></a>設定庫存能見度整合

安裝增益集後，請執行以下步驟準備您的 Supply Chain Management 系統以配合使用增益集。

1. 在 Supply Chain Management 中，開啟 **[功能管理](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)** 工作區，並開啟以下功能：
    - *庫存能見度整合* – 必要。
    - *庫存能見度與保留抵銷整合* – 建議使用但可選用。 需要版本 10.0.22 或更高版本。 如需詳細資訊，請參閱[庫存能見度保留](inventory-visibility-reservations.md)。

1. 前往 **庫存管理 \> 設定 \> 庫存能見度整合參數**。
1. 開啟 **一般** 索引標籤並進行以下設定：
    - **庫存能見度端點** – 輸入執行庫存能見度的環境 URL。 有關詳細資訊，請參閱[尋找服務端點](inventory-visibility-configuration.md#get-service-endpoint)。
    - **單一請求的最大記錄數** – 設定單一請求中包含的最大記錄數。 您必須輸入小於或等於 1000 的正整數。 預設值為 512。 我們強烈建議您保留預設值，除非您已收到 Microsoft 支援服務的建議或確定您需要變更。

1. 如果您啟用了選用的 *庫存能見度與保留抵銷整合* 功能，請開啟 **保留抵銷** 索引標籤並進行以下設定：
    - **啟用保留沖銷**：設為 *是* 以啟用此功能。
    - **保留沖銷修飾詞**：選擇會沖銷在庫存能見度上設定的保留項目的庫存交易狀態。 此設定會決定觸發沖銷的訂單處理階段。 該階段由訂單的庫存交易狀態追蹤。 選擇下列其中一個選項：
        - *訂購*：若為 *交易中* 狀態，訂單將在建立時傳送沖銷要求。 沖銷數量將是建立訂單的數量。
        - *保留*：若為 *保留已訂購交易* 狀態，訂單將在保留、揀貨、裝箱單過帳或開立發票時傳送沖銷要求。 系統僅會在上述程序啟動第一步時觸發一次該要求。 沖銷數量將是相應訂單明細庫存交易狀態從 *訂購* 變更為 *訂購保留* (或更晚狀態) 時的數量。

1. 前往 **庫存管理 \> 定期 \> 庫存能見度整合**，並啟用該作業。 來自 Supply Chain Management 的所有庫存變更事件現在都將發佈到庫存能見度。

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
