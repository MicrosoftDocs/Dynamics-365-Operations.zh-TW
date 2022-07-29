---
title: ATS 整合 API 的伺服器到伺服器驗證
description: 本主題說明如何按照 Dynamics 365 Human Resources 申請人追蹤系統 (ATS) 整合 API 設定伺服器到伺服器驗證。
author: jaredha
ms.date: 06/30/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-06-30
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d221e1a47dca85880fd683177ca95dd1b7766fb9
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452076"
---
# <a name="server-to-server-authentication-for-the-ats-integration-api"></a>ATS 整合 API 的伺服器到伺服器驗證


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

本主題說明如何按照 Dynamics 365 Human Resources 申請人追蹤系統 (ATS) 整合 API 設定伺服器到伺服器的應用程式整合驗證。 服務主體需要管理幾個安全層才能存取 Microsoft Dataverse 虛擬資料表和關聯資料。 用戶需要獲准取得 Microsoft Power Platform 的 Dataverse 虛擬資料表存取權限，才能存取 Dynamics 365 Human Resources 裡的資料。 

## <a name="enable-access-to-dataverse-virtual-tables-in-power-platform"></a>啟用 Power Platform 中的 Dataverse 虛擬資料表存取功能

啟用 Power Platform 裡的 Dataverse 虛擬資料表存取功能第一步是在 Power Platform 按照 Dataverse 虛擬資料表端點設定您的驗證應用程式。 這道步驟執行細節請參閱 [Microsoft Dataverse 開發人員指引](/powerapps/developer/data-platform)。

  - 單租用戶應用程式註冊方面：[使用單租用戶伺服器到伺服器驗證](/powerapps/developer/data-platform/use-single-tenant-server-server-authentication)
  - 多租用戶應用程式註冊方面：[使用多租用戶伺服器到伺服器驗證](/powerapps/developer/data-platform/use-multi-tenant-server-server-authentication)

### <a name="creating-a-security-role-for-ats-integrations"></a>針對 ATS 整合建立資訊安全角色

應用程式用戶建立之後的其中一道步驟是將用戶指派給定義應用程序端點存取權限的資訊安全角色。 這是步驟 7 [應用程式用戶建立](/powerapps/developer/data-platform/use-single-tenant-server-server-authentication#application-user-creation)，針對單租用戶應用程序註冊和針對多租戶註冊的[為應用程式用戶建立資訊安全角色](/powerapps/developer/data-platform/use-multi-tenant-server-server-authentication#create-a-security-role-for-the-application-user)。 

指派給應用程式用戶的角色應該有權存取用於 ATS 整合的資料實體。 這不是開箱即用角色，因此將需要建立新資訊安全角色。 新角色可以按照[建立資訊安全角色](/power-platform/admin/create-edit-security-role#create-a-security-role) 概觀的步驟建立。

新角色方面，必須至少為下列新角色的 **自訂實體** 索引標籤上的實體指派適當的存取權限。 須留意的是，如果整合使用更廣泛的應用程式資料，您可能需要另外新增實體。 待新角色建立後，可以指派給應用程式用戶。

  - 基本背景工作角色 (mshr)
  - 準員工 (mshr)
  - 證書適格性 (mshr)
  - 證書類型 (mshr)
  - 公司
  - 薪酬工作職能 (mshr)
  - 薪酬工作類型 (mshr)
  - 國家/地區 (mshr)
  - 部門 (mshr)
  - 教育適格性 (mshr)
  - 教育程度 (mshr)
  - 教育學科 (mshr)
  - 教育要求 (mshr)
  - 身份識別 (mshr)
  - 辨別類型 (mshr)
  - 機構 (mshr)
  - 核發單位 (mshr)
  - 工作薪酬 (mshr)
  - 工作 (mshr)
  - 教育程度 (mshr)
  - 合作對象聯絡方式 (mshr)
  - 人 (mshr)
  - 個人地址 (mshr)
  - 個人篩選 (mshr)
  - 職位類型 (mshr)
  - 職位 V2 (mshr)
  - 專業經驗適格性 (mshr)
  - 評等級別 (mshr)
  - 評等模型 (mshr)
  - 原因代碼 (mshr)
  - 招募要求 (mshr)
  - 招募要求位置 (mshr)
  - 招募要求職位 (mshr)
  - 招募要求技能 (mshr)
  - 篩選類型 (mshr)
  - 技能適格性 (mshr)
  - 技能 (mshr)
  - 職銜 (mshr)
  - 退伍軍人身份 (mshr)
  - 背景工作角色 (mshr)

## <a name="granting-application-permissions-to-human-resources-data"></a>授予應用程式存取人力資源資料的權限

第二步是藉由連結應用程式到 Human Resources 應用程式用戶來確保應用程式已獲准對 Human Resources 資料存取的適當權限。 應用程式用戶方面，伺服器到伺服器呼叫 Dataverse 虛擬資料表的動作是在叫用動作的 Dataverse 用戶 (應用程式) 身份場合中進行。 虛擬資料表配接器服務隨即在 Human Resources 查閱關聯用戶並在該用戶的上下文執行查詢動作。 這代表用戶必須借助正確指派的角色在 Human Resources 建立，以便對整合應用程式將需要的資料提供存取權限。

人力資源用戶也需要被指派人力資源資料的正確權限。 **招募應用程式**(HcmRecruitingIntegrator) 角色具備整合招募資料所需的主要實體權限。 本角色可被指派給 **用戶** 頁的應用程式用戶，便於授予對資料的適當存取權。 更多有關人力資源資訊安全角色的資訊，請參閱[角色型安全性](/fin-ops-core/dev-itpro/sysadmin/role-based-security)。

### <a name="set-up-the-new-user-with-appropriate-permissions"></a>設定具有適當權限的新用戶

若要設定具有適當權限的新用戶，請按照這些步驟進行：

  1. 打開人力資源裡的 **用戶** 頁並選取 **新建**。
  2. 輸入新應用程式用戶的 **用戶識別碼** 和 **用戶名稱**。 例如，您可以輸入 “RecruitingIntegration”。

      > [!NOTE]
      > 如果應用程式沒有 Microsoft Azure Active Directory (Azure AD) 用戶帳戶或電子郵件地址，您可以在用戶的電子郵件地址和提供者欄位新增 “RecruitingApp” 之類的文字。

  3. 請在 **用戶角色** FastTab 上選取 **指派角色** 動作。
  4. 請在 **指派角色給用戶** 窗格中選取 **招募應用程式**，並選取 **確認**。
  5. 儲存新用戶記錄。

### <a name="link-the-new-human-resources-user-to-the-application"></a>將新人力資源用戶連結到應用程式

待用戶建立後，務必在 **Azure Active Directory 應用程式** 表單中建立應用程式記錄，以便將應用程式連結人力資源用戶。

  1. 請打開 **Azure Active Directory 應用程式** 表單並選取 **新建**。
  2. 請在 **客戶識別碼** 欄位中，輸入為應用程式建立應用程式用戶的用戶端識別碼。
  3. 請在 **姓名** 欄位中輸入整合應用程式名稱。
  4. 請在 **用戶識別碼** 欄位中選取為招募整合建立的新人力資源用戶。
  5. 儲存新記錄。

接著應用程式將有權存取人力資源資料，僅限招募應用程式整合所需的資料。

## <a name="see-also"></a>也請參閱

[招募求職者](hr-personnel-recruit.md)<br>
[何謂 Microsoft Dataverse？](/powerapps/maker/data-platform/data-platform-intro)<br>
[使用 Microsoft Dataverse Web API](/powerapps/developer/data-platform/webapi/overview)<br>
[使用 Web API 建立和更新選項集合](/powerapps/developer/data-platform/webapi/create-update-optionsets)<br>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
