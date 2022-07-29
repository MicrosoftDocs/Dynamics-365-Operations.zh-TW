---
title: Regulatory Configuration Service
description: 本主題概述 Regulatory Configuration Service (RCS) 功能，並解釋如何存取服務。
author: JaneA07
ms.date: 06/04/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: RCS, Regulatory Configuration Services, Localization
audience: Application User
ms.reviewer: kfend
ms.custom:
- "97423"
- intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-02-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 816b1bf9da9acdd5999320f39fb68fb6deda197c
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/15/2022
ms.locfileid: "8451386"
---
# <a name="regulatory-configuration-service"></a>Regulatory Configuration Service

[!include [banner](../includes/banner.md)]

Regulatory Configuration Service (RCS) 是無程式碼/低程式碼全球化功能的獨立設計工具和生命週期管理服務。 RCS 讓全球化的利害關係人得以擴展和客製化稅賦、電子發票、監管報表、銀行金融和商業文件的關鍵全球化領域，無需邀請開發人員參與。 這種無程式碼/低程式碼全球化方法使得全球化更容易、更快、更具成本效益地建立或擴展。

RCS 提供功能如下：

- 支援 Electronic 報表 (ER) 提供的所有功能。
- 新全球化微服務組態的先決行件。
- 支援 Electronic 發票。 更多資訊，請參閱 [Electronic Invoicing](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-finance/electronic-invoicing-add-on-dynamics-365-ga)。
- 支援 Tax Calculation。 更多資訊，請參閱[稅務服務](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-finance/tax-service-preview)。
- 支援新全球化特徵功能，進而簡化多組成要素特色的生命週期管理，和提供額外功能配置動作與設定功能參數。 更多資訊，請參閱 [Regulatory Configuration Service - 全球化服務的簡化全球化特色管理](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-finance/regulatory-configuration-service-simplified-globalization-feature-management-globalization-services)。
- 支援 Global 存放庫的集中式發佈、儲存和共用自訂組態，進而簡化組態管理，無需使用 Microsoft Dynamics Lifecycle Services (LCS)。

## <a name="access-rcs"></a>存取 RCS

您可以從 [Regulatory Configuration Service 頁面註冊或登入 RCS](https://marketing.configure.global.dynamics.com/)。

![RCS 註冊/登入。](media/202103_RCS%20Marketing%20page_updated_1.jpg)

請在 **Regulatory Configuration Service** 頁面審核與接受使用服務的補充條款和行件，接著選取下列其中一個按鈕：

- **註冊** 如果您是本服務首次使用者，並且您正在使用企業電子郵件地址為貴組織提供服務環境
- **登入** 如果您已經註冊本服務，並且希望存取貴組織環境

> [!NOTE] 
> 註冊後，我們建議您新增額外 SysAdmin 使用者到 RCS 環境。 此名使用者將被佈建為環境的共同管理員。 這將有助於提供 RCS 環境的存取穩定性，因為 SysAdmin 角色是管理此環境的使用者。 您可以使用 **RCS 工作區 > 系統管理** 新增使用者。

## <a name="regional-availability"></a>區域可用性

RCS 在下列區域已全面開放使用：

- 美國
- 印度
- 法國
- 歐洲

關於完整區域清單，請參閱 [Dynamics 365 和 Power Platform：可用性、資料位置、語言和在地化](https://aka.ms/dynamics_365_international_availability_deck)。

## <a name="rcs-default-company"></a>RCS 預設公司

RCS 使用的設計時間功能在所有公司之間共用。 目前尚未開放公司特定功能。 因此，我們建議您使用一間公司，**DAT**，連同您的 RCS 環境。

不過您可能希望在某些場合希望 ER 格式使用與特定法人實體相關的參數。 只有這些場合可以讓您使用預設的公司切換器。 例如，請參閱[配置 ER 格式為使用各個法人實體指定的參數](../../fin-ops-core/dev-itpro/analytics/er-app-specific-parameters-configure-format.md)。

## <a name="related-rcs-documentation"></a>相關 RCS 文件

更多有關相關組成要素的資訊，請參閱下列主題：

- **RCS：**

    - [在 RCS 建立 ER 組態並上傳到 Global 存放庫](rcs-global-repo-upload.md)

- **Global 存放庫：**

    - [建立 ER 組態並上傳到 Global repo](rcs-global-repo-upload.md)
    - [在 Global repo 共用組態](rcs-global-repo-share-configuration.md)
    - [Global repo 的強化篩選功能](enhanced-filtering-global-repo.md)
    - [從 Global 存放庫下載 ER 組態](../../fin-ops-core/dev-itpro/analytics/er-download-configurations-global-repo.md)
    - [中止 Global repo 的組態](discontinuing-configurations-rcs-global-repo.md)
    - [Regulatory Configuration Service (RCS) – Lifecycle Services (LCS) 儲存設備棄用](rcs-lcs-repo-dep-faq.md)

- **全球化特色：**

    - [Regulatory Configuration Service (RCS) - 全球化特色](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-finance/regulatory-configuration-service-simplified-globalization-feature-management-globalization-services)


## <a name="troubleshooting-rcs-sign-up"></a>RCS 註冊疑難排除

當您從服務頁面註冊 RCS 時，您可能會遭遇與 Azure Active Directory (Azure AD) 有關的問題。 您收到的錯誤訊息指出 RCS 註冊功能目前已關閉，必須先開啟才能完成註冊流程。

![RCS 註冊錯誤訊息。](media/01_RCSSignUpError.jpg)

此問題發生的原因是因為您被阻擋，無法註冊專案訂閱，而 `AllowAdHocSubscriptions` 屬性必須在您的租用戶中啟用。 

- 如果您的 IT 部門管理貴組織的 Azure 租用戶，請聯絡該部門通報此問題。
- 如果您負責管理 Azure 租戶，則您可以按照[何謂 Azure Active Directory 自助註冊裡的步驟修正問題](/azure/active-directory/enterprise-users/directory-self-service-signup#how-do-i-control-self-service-settings)。
