---
title: 開始使用全球庫存會計
description: 本主題介紹如何開始使用全球庫存會計。
author: AndersGirke
ms.date: 06/18/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.custom: intro-internal
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2021-06-18
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 88f1e9ef8c8b2aa494c44ea3b33713adc470eb96
ms.sourcegitcommit: 2e554371f5005ef26f8131ac27eb171f0bb57b4e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/04/2022
ms.locfileid: "8450102"
---
# <a name="get-started-with-global-inventory-accounting"></a>開始使用全球庫存會計

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]
<!--KFM: Preview until 4/30/2022 -->

全球庫存會計可讓您在設定的全球庫存會計分類帳中進行多個庫存會計。 您必須將每個全球庫存會計分類帳與 *規範* 建立關連。 規範是下列會計原則類型的集合：

- 成本物件
- 輸入測量基礎
- 成本流程假設
- 成本元素

> [!NOTE]
> 即便您開啟全球庫存會計，您仍然可以按照往常的方式在 Microsoft Dynamics 365 Supply Chain Management 使用庫存會計。

全球庫存會計是一種增益集。 若要使用，您必須從 Microsoft Dynamics Lifecycle Services (LCS) 安裝該功能。 您可以在測試環境中選擇評估，然後在將其用於實際執行環境。

全球庫存會計目前不支援 Supply Chain Management 中內建的所有成本管理功能。 因此，評估目前的可用功能，是否可以滿足您的需求，非常重要。

## <a name="how-to-get-the-global-inventory-accounting-public-preview"></a><a name="sign-up"></a>如何取得全球庫存會計公開預覽版

> [!IMPORTANT]
> 若要使用全球庫存會計，您必須具有啟用 LCS 的高可用性環境 (不是 OneBox 環境)。 此外，您必須執行 Supply Chain Management 10.0.19 版本或更高版本。

若要註冊全球庫存會計公開預覽版，請通過電子郵件將您的 LCS 環境 ID 傳送至[全球庫存會計團隊](mailto:GlobalInvAccount@microsoft.com)。 計劃獲得核准之後，團隊發送一封後續追蹤電子郵件，其中包含全球庫存會計測試版金鑰和您的服務端點。 收到測試版金鑰之後，您便可以[安裝增益集](#install)。

## <a name="licensing"></a>授權

全球庫存會計授權與 Supply Chain Management 庫存會計中可用的標準功能共用。 無須額外購買用於全球庫存會計的授權。

## <a name="prerequisites"></a>先決條件

### <a name="set-up-microsoft-power-platform-integration"></a>Microsoft Power Platform 整合設定

啟用曾益集功能之前，您必須按照下列步驟整合 Microsoft Power Platform。

1. 打開您要新增服務的 LCS 環境。
1. 前往 **全部詳細資料**。
1. 在 **Power Platform 的整合** 部分，選擇 **設定**。
1. 在 **Power Platform 環境設定** 對話方塊中，選擇核取方塊，然後選擇 **設定**。 通常，設定需要 60 至 90 分鐘。
1. 完成 Microsoft Power Platform 環境設定之後，頁面會您是您的環境名稱。 此外，**Power Platform 整合** 部分會顯示「Power Platform 環境設定完成」的狀態。 全球庫存會計不需要雙重寫入應用程式。

如需更多資訊，請參閱[環境部署後啟用](../../fin-ops-core/dev-itpro/power-platform/enable-power-platform-integration.md#enable-after-deploy)。

### <a name="set-up-dataverse"></a>設定 Dataverse

設定 Dataverse 之前，請按照以下步驟將全球庫存會計服務原則，新增至您的租用戶中。

1. 安裝適用於 Windows PowerShell v2 模組的 Azure AD，如[安裝 Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2) 中所述。
1. 執行下列 PowerShell 命令。

    ```powershell
    Connect-AzureAD # (open a sign in window and sign in as a tenant user)

    New-AzureADServicePrincipal -AppId "7a1dd80f-c961-4a67-a2f5-d6a5d2f52cf9" -DisplayName "d365-scm-costaccountingservice"

    New-AzureADServicePrincipal -AppId "5f58fc56-0202-49a8-ac9e-0946b049718b" -DisplayName "d365-scm-operationdataservice"
    ```

下一步，按照下列步驟，在 Dataverse 中建立全球庫存會計應用程式使用者。

1. 打開 Dataverse 環境的 URL。
1. 前往 **進階設定 \> 系統 \> 安全性 \> 使用者**，並建立應用程式使用者。 使用 **檢視** 欄位，變更頁面為檢視 *應用程式使用者*。
1. 選擇 **新增**。
1. 將 **應用程式識別碼** 欄位設定為 *7a1dd80f-c961-4a67-a2f5-d6a5d2f52cf9*。
1. 選擇 **指派角色**，然後選擇 *系統管理員*。 如果有另一個角色名稱為 *Common Data Service 使用者*，請一併選擇。
1. 重複上述步驟，但是將 **應用程式識別碼** 欄位設定為 *5f58fc56-0202-49a8-ac9e-0946b049718b*。

如需更多資訊，請參閱[建立應用程式使用者](/power-platform/admin/create-users-assign-online-security-roles#create-an-application-user)。

如果您的 Dataverse 預設安裝語言不是英文，請按照下列步驟。

1. 前往 **進階設定 \> 管理 \> 語言**。
1. 選擇 *英文* (*語言代碼=1033*)，然後選擇 **套用**。

## <a name="install-the-add-in"></a><a name="install"></a>安裝增益集

按照下列步驟安裝增益集，以便您可以使用全球庫存會計。

1. [登入](#sign-up)全球庫存會計公開預覽版。
1. 登入 [LCS](https://lcs.dynamics.com/Logon/Index)。
1. 前往 **預覽功能管理**。
1. 選擇加符號 (**+**)。
1. 在 **代碼** 欄位中，輸入您的全球庫存會計增益集測試版金鑰。 (您應該在通過電子郵件註冊時收到您的測試版金鑰。)
1. 選擇 **解除封鎖**。
1. 打開您要新增服務的 LCS 環境。
1. 前往 **全部詳細資料**。
1. 前往 **Power Platform 整合**，並選擇 **設定**。
1. 在 **Power Platform 環境設定** 對話方塊中，選擇核取方塊，然後選擇 **設定**。 通常，設定需要 60 至 90 分鐘。
1. 完成設定 Microsoft Power Platform 環境之後，在 **環境增益集** FastTab 上，選擇 **安裝新的增益集**。
1. 選擇 **全球庫存會計**。
1. 按照安裝指南，並同意條款及條件。
1. 選擇 **安裝**。
1. 在 **環境增益集** FastTab 上，您應該會看見正在安裝全球庫存會計。 幾分鐘後，狀態應該會從 *正在安裝* 變更為 *已安裝*。 (您可能需要重新整理葉面才能看見此變更。) 此時，全球庫存會計已可以使用。

## <a name="set-up-the-integration"></a>整合設定

按照下列步驟，設定全球庫存會計和 Supply Chain Management 之間的整合。

1. 登入 Supply Chain Management。
1. 前往 **系統管理 \> 功能管理**。
1. 選擇 **檢查更新**。
1. 在 **全部** 索引標籤上，搜尋名稱為 *全球庫存會計(預覽版)* 的功能。
1. 選擇 **立即啟用**。
1. 前往 **全球庫存會計 \> 設定 \> 全球庫存會計參數\>整合參數**。
1. 在 **資料服務端點** 和 **全球庫存會計端點** 欄位中，輸入您註冊預覽版時，全球庫存會計團隊向您發送電子郵件中的 URL。

全球庫存會計現在已可以使用。
