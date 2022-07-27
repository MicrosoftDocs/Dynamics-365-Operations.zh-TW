---
title: 啟用 Power BI 用於全球庫存會計
description: 本主題介紹如何啟用 Microsoft Power BI 用於全球庫存會計。
author: AndersGirke
ms.date: 06/18/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2021-06-18
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: f0a8f5948d9e30eb220aa8177a4b9718223a4f9d
ms.sourcegitcommit: 5bfd6511d710deb539b4030eb0e9c48d25513595
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/19/2022
ms.locfileid: "8449790"
---
# <a name="enable-power-bi-for-global-inventory-accounting"></a>啟用 Power BI 用於全球庫存會計

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]
<!--KFM: Preview until 4/30/2022 -->

您可以將磚、儀表板和報告從您的 [PowerBI.com](https://powerbi.com/) 帳戶釘選到您的 Microsoft Dynamics 365 應用程式工作區。

## <a name="prerequisites"></a>先決條件

必須滿足以下先決條件才能啟用 Power BI 報告：

- 您必須是 Dynamics 365 應用程式中的系統管理員。
- 你必須有一個 [PowerBI.com](https://powerbi.com/) 帳戶。
- 您必須至少有一個儀表板和一份報告在您的 Power BI 帳戶。
- 您必須是您的 Azure Active Directory (Azure AD) 帳戶管理員。
- Azure AD 網域必須與您用於 [PowerBI.com](https://powerbi.com/) 帳戶的網域相同。

## <a name="setup"></a>設定

如欲設定 Power BI 整合，請按照以下步驟操作。

1. 登入 [Microsoft Dynamics Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index)。
1. 前往 **共用資產庫**，選取 **Power BI 報告模型** 作為資產類型，然後下載 **全球庫存會計** 套件。 
1. 登入 [PowerBI.com](https://app.powerbi.com/)，並按照以下步驟上傳 **全球庫存會計** Power BI 報告檔案：

    1. 選取 **新增**。
    1. 選取 **上傳檔案**。
    1. 選取 **全球庫存會計** Power BI 報告檔案。

1. 按照以下步驟設定 **全球庫存會計** Power BI 報告：

    1. 前往 **我的工作區**，找到全球庫存會計的資料集，然後在 **選項** 功能表選擇 **設定**。
    1. 在 **全球庫存會計設定** 展開 **參數**，並根據需要更新所有參數。 請特別務必檢查以下設定：
        1. 使用 LCS 之中 **Power Platform 環境資訊** 之下的值 (位於 **Power Platform 整合** 區段) 覆寫預設的 **Dataverse URL** 值。
        1. 使用 LCS 之中 **環境詳細資料** 之下 (位於 **管理環境** 區段) 的值覆寫預設的 **環境識別碼** 值。
        1. 選擇 **資料來源憑證** 區段之中 **CDS** 標籤旁邊的 **編輯憑證** 連結。 然後使用 **OAuth2** 身份驗證方法登入您的 Dataverse 帳戶。
    1. 驗證 Power BI 報告目前位於 **我的工作區\>報告\>全球庫存會計**，可正常運作，並顯示您系統中的內容。

1. 按照[設定 PowerBI.com 整合](../../fin-ops-core/dev-itpro/analytics/configure-power-bi-integration.md#registration-process)所述內容註冊應用程式。
1. 按照以下步驟將 **全球庫存會計** Power BI 報告檔案整合至 Dynamics 365 Supply Chain Management：

    1. 前往 **系統管理\>設定\> PowerBI.com 設定**。
    1. 選取 **編輯**。
    1. 選取 **啟用 PowerBI.Com 整合**。
    1. 在 **應用程式識別碼** 欄位輸入應用程式識別碼。
    1. 在 **應用程式金鑰** 欄位輸入應用程式金鑰。
    1. 選取 **儲存**。

1. 重新整理頁面，以便顯示 Power BI 登入對話方塊。
1. 在 **選項** 索引標籤選擇 **開啟報告目錄**，然後選擇您之前上傳的 **全球庫存會計** Power BI 報告檔案。
1. 重新整理頁面。 您應該看到您的報告已新增。
1. 在 **Power BI 報告** 之下選取 **全球庫存會計** 連結。

更多詳細資訊請參閱[設定 PowerBI.com 整合](../../fin-ops-core/dev-itpro/analytics/configure-power-bi-integration.md)。
