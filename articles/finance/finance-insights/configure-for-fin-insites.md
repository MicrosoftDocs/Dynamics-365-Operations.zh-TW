---
title: Finance Insights 的設定
description: 本主題介紹使您的系統能夠使用 Finance Insights 中可用功能的設定步驟。
author: ShivamPandey-msft
ms.date: 01/27/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-07-20
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: b9bad6445e9e77688f66c6c4186422d7a898edd7
ms.sourcegitcommit: 7fc0a9a6440ac087292e9e76c26c67f56154b9e6
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/28/2022
ms.locfileid: "8451503"
---
# <a name="configuration-for-finance-insights"></a>Finance Insights 的設定

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Finance Insights 結合了 Microsoft Dynamics 365 Finance 的功能和 Dataverse、Azure 和 AI Builder，以便為您的組織提供強大的預測工具。 本主題介紹使您的系統能夠使用 Finance Insights 中可用功能的設定步驟。 要成功完成本主題中的程序，您必須在 [Power 入口網站系統管理中心](https://admin.powerplatform.microsoft.com/)、Dynamics 365 Finance 中的系統管理員存取權限，和在 Microsoft Dynamics Lifecycle Services (LCS) 中具有建立環境的存取權。

> [!NOTE]
> 以下設定 Finance Insights 的程序適用於 Dynamics 365 Finance 版本 10.0.21 及更新版本。

## <a name="deploy-dynamics-365-finance"></a>部署 Dynamics 365 Finance

按照以下步驟部署環境。

1. 在 LCS 中，建立或更新 Dynamics 365 Finance 環境。 該環境需要應用程式版本 10.0.21 或更新版本。

    > [!NOTE]
    > 環境必須是高可用性 (HA) 環境。 (這種類型的環境也稱為第 2 層環境。) 有關更多資訊，請參閱[環境規劃](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md)。

2. 如果您在沙盒環境中設定 Finance Insights，您可能必須將生產資料複製到該環境，然後預測才會運作。 預測模型使用多年的資料來構建預測。 Contoso 示範資料不包含足夠的歷史資料來充分定型預測模型。 

## <a name="configure-your-azure-ad-tenant"></a>設定您的 Azure AD 租用戶

必須設定 Azure Active Directory (Azure AD)，以便它可以與 Dataverse 和 Microsoft Power Platform 應用程式一起使用。 此設定要求 **專案擁有者** 角色或 **環境管理員** 角色指派給 LCS **專案資訊安全角色** 欄位中的使用者。

驗證以下設定是否已完成：

- 你在 Power Portal 系統管理中心具有 **系統管理員** 和 **系統自訂者** 存取權。
- Dynamics 365 Finance 或等效授權適用於安裝 Finance Insights 增益集的使用者。

已在 Azure AD 中註冊下列 Azure AD 應用程式。

|  應用程式                             | 應用程式識別碼                               |
|------------------------------------------|--------------------------------------|
| Microsoft Dynamics ERP 微服務 CDS | 703e2651-d3fc-48f5-942c-74274233dba8 |
    
## <a name="configure-dataverse"></a>設定 Dataverse

請按照以下步驟為 Finance Insights 設定 Dataverse。

- 在 LCS 中，打開環境頁面，並驗證 **Power Platform 整合** 區段分已經設定好了。

    - 如果Dataverse已經設定好了，Dataverse應列出連結到財務環境的環境名稱。
    - 如果 Dataverse 尚未設定，請選擇 **設定**。 設定 Dataverse 環境可能需要長達一個小時。 設置成功完成後，應列出連結到 Finance 環境的 Dataverse 環境名稱。
    - 如果已使用現有的 Microsoft Power Platform 環境設定了此整合，請聯繫您的管理員以確保連結環境未處於停用狀態。

        更多資訊，請參閱[啟用 Power Platform 整合](../../fin-ops-core/dev-itpro/power-platform/enable-power-platform-integration.md)。 

        若要存取 Microsoft Power Platform 管理網站，請前往 <https://admin.powerplatform.microsoft.com/environments>。

## <a name="configure-the-finance-insights-add-in"></a>設定 Finance Insights 增益集

如果您之前安裝了 Finance Insights 增益集，請先將其卸載，然後再完成以下流程。

> [!NOTE]
> 如果您已經在 LCS 中安裝了資料湖增益集，Finance Insights 將使用它來儲存預測所需的資料。 如果您尚未在 LCS 中安裝資料湖增益集，Finance Insights 增益集將為您建立一個託管資料湖。

請按照以下步驟安裝 Finance Insights 增益集。

1. 登入 LCS，然後在頁面右側的環境名稱下，選擇 **詳細資料**。
2. 在 **環境增益集** 區段選擇 **安裝新的增益集**。
3. 設定 **Finance Insights** 增益集。
4. 同意條款和條件，然後選取 **安裝**。

增益集可能需要幾分鐘才能安裝。

## <a name="one-last-thing"></a>最後一件事...

增益整合功安裝後，您可能需要長達一個小時才能在 Dynamics 365 Finance 的 **功能管理** 工作區中啟用 Finance insights 功能。 如果不想等那麼久，可以手動執行 **Insights 佈建狀態檢查** 流程。 

1. 在 Dynamics 365 Finance，前往 **系統管理 \> 設定 \> 流程自動化**。
2. 在 **背景流程** 索引標籤，找到 **Insights 佈建狀態檢查**，並選擇 **編輯**。
3. 將 **下一次執行** 欄位設定為目前時間前 30 分鐘。

   此變更應會強制 **Insights 佈建狀態檢查** 流程立即執行。

   **Insights 佈建狀態檢查** 流程成功執行後，您可以在 **功能管理** 工作區中啟用 Finance insights 功能。

> [!NOTE]
> 如果 **Insights 佈建狀態檢查** 流程未執行，請前往 **系統管理** > **查詢** > **批次工作**。 在 **流程自動化輪詢系統** 欄位，將值變更為 **等待** 以啟動該流程。 
> 
## <a name="feedback-and-support"></a>意見反應及支援

如果您有興趣提供意見反應或需要支持，請發送電子郵件至 [Finance Insights (預覽版)](mailto:fiap@microsoft.com)。

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
