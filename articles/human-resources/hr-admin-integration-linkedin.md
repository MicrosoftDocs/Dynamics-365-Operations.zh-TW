---
title: 整合 LinkedIn 人才中心
description: 本主題說明如何設定 Microsoft Dynamics 365 Human Resources 和 LinkedIn 人才中心之間的整合。
author: jaredha
ms.date: 10/20/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-10-20
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: fb75c391809f1ce5c7d48728a735f347ef1784ed
ms.sourcegitcommit: 696796ca5635863850ae9ef16fc1fb0fc46ce8f0
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/28/2021
ms.locfileid: "8451953"
---
# <a name="integrate-with-linkedin-talent-hub"></a>整合 LinkedIn 人才中心

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

> [!IMPORTANT]
> Dynamics 365 Human Resources 和本主題描述的 LinkedIn 人才中心之間的整合將於 2021 年 12 月 31 日停用。 自此日期後，整合服務將不再開放供人使用。 尚未使用整合服務的組織將無法在停用前實施這項服務。

[LinkedIn 人才中心](https://business.linkedin.com/talent-solutions/talent-hub)是申請人追蹤系統 (ATS) 平台。 它讓您在一處地點尋找、管理和錄用員工。 憑藉整合 Microsoft Dynamics 365 Human Resources 和 LinkedIn Talent Hub，您可以在人力資源為已錄用某個職位的申請人建立員工記錄。

## <a name="setup"></a>設定

系統管理員必須完成設定任務才能啟用與 LinkedIn Talent Hub 的整合。 首先，您必須在 Power Apps 環境設定使用者和資訊安全角色以便授予 LinkedIn Talent Hub 適當權限將資料寫入人力資源。

### <a name="link-your-environment-to-linkedin-talent-hub"></a>將您的環境連結 LinkedIn Talent Hub

1. 打開 [LinkedIn Talent Hub](https://business.linkedin.com/talent-solutions/talent-hub)。

2. 請在使用者下拉清單中選取 **產品設定**。

3. 請在 **進階** 區的左側瀏覽窗格中選取 **整合**。

4. 選取 **授權** Microsoft Dynamics 365 Human Resources 整合。

5. 請在 **Dynamics 365 Human Resources** 頁選取要連結 LinkedIn Talent Hub 的環境，然後選取 **連結**。

    ![LinkedIn Talent Hub 上線中。](./media/hr-admin-integration-talent-hub-onboarding.jpg)

    > [!NOTE]
    > 您只能連結您的使用者帳戶對人力資源環境和關聯 Power Apps 環境有管理員存取權限的環境。 如果人力資源連結頁未列出任何環境，請確定您已在租使用者上獲得人力資源環境的授權，而您登入連結頁的使用者具有對人力資源環境和 Power Apps 環境的管理員權限。

### <a name="create-a-power-apps-security-role"></a>建立 Power Apps 資訊安全角色

1. 打開 [Power Platform 系統管理中心](https://admin.powerplatform.microsoft.com)。

2. 請在 **環境** 清單中選取與您想要連結您的 LinkedIn Talent Hub 執行個體的人力資源環境有關聯的環境。

3. 請選取 **設定**。

4. 請展開 **使用者 + 權限** 節點，然後選取 **資訊安全角色**。

5. 請在 **資訊安全角色** 頁的工具列上選取 **新角色**。

6. 請在 **細節** 索引標籤上輸入角色名稱，例如 **LinkedIn Talent Hub HRIS 整合**。

7. 請在 **客製化** 索引標籤上選取下列實體的組織級 **讀取** 權限：

    - 實體
    - 欄位
    - 關聯

8. 儲存並關閉資訊安全角色。

### <a name="create-a-power-apps-application-user"></a>建立 Power Apps 應用程式使用者

必須為 LinkedIn Talent Hub 轉接卡建立應用程式使用者，才能授予轉接卡將候選人記錄寫入 Power Apps 環境的權限。

1. 打開 [Power Platform 系統管理中心](https://admin.powerplatform.microsoft.com)。

2. 請在 **環境** 清單中選取與您想要連結您的 LinkedIn Talent Hub 執行個體的人力資源環境有關聯的環境。

3. 請選取 **設定**。

4. 請展開 **使用者 + 權限** 節點，然後選取 **使用者**。

5. 請選取 **在 Dynamics 365 中管理使用者**。

6. 請使用清單上方的下拉式選單將預設的 **啟用使用者** 視圖變更為 **應用程式使用者**。

    ![應用程式使用者視圖。](./media/hr-admin-integration-power-apps-application-users.jpg)

7. 在工具列上，選取 **新增**。

8. 請在 **新使用者** 頁上按照下列步驟操作：

    1. 請將 **使用者類型** 欄位值變更為 **應用程式使用者**。
    2. 請設定 **使用者名稱** 欄位為 **Dynamics365 HR LinkedIn HRIS 整合**。
    3. 請將 **應用程式識別碼** 欄位設定為 **3a225c96-d62a-44ce-b3ec-bd4e8e9befef**。
    4. 請在 **名字**、**姓氏** 和 **主要電子郵件信箱** 欄位輸入任意值。
    5. 請在工具列上選取 **儲存\&關閉**。

### <a name="assign-a-security-role-to-the-new-user"></a>為新使用者指派資訊安全角色

待您在上一區儲存和關閉新應用程式使用者之後，您將返回 **使用者清單** 頁。

1. 請在 **使用者清單** 頁上將視圖變更為 **應用程式使用者**。

2. 選取您在上一區建立的應用程式使用者。

3. 請在工具列上選取 **管理角色**。

4. 請選取您稍早針對整合建立的資訊安全角色。

5. 選擇 **確定**。

### <a name="add-an-azure-active-directory-app-in-human-resources"></a>請在人力資源新增 Azure Active Directory 應用程式

1. 請在 Dynamics 365 Human Resources 打開 **Azure Active Directory 應用程式** 頁。
2. 將新記錄新增到清單，並設定欄位如下：

    - **使用者端識別碼**: 輸入 **3a225c96-d62a-44ce-b3ec-bd4e8e9befef**。
    - **名稱**：輸入您稍早建立的 Power Apps 資訊安全角色名稱，例如 **LinkedIn 人才中心 HRIS 整合**。
    - **使用者識別碼**：選取在 Personnel Management 中擁寫入資料權限的使用者。

### <a name="create-the-table-in-dataverse"></a>在 Dataverse 中建立資料表

> [!IMPORTANT]
> 整合 LinkedIn Talent Hub 取決於 Dataverse 人力資源的虛擬資料表。 您必須配置虛擬資料表，因為這是設定中此步驟的前提條件。 有關如何配置虛擬資料表的資訊，請參閱[配置 Dataverse 虛擬資料表](./hr-admin-integration-common-data-service-virtual-entities.md)。

1. 請在人力資源中打開 **Dataverse 整合** 頁。

2. 請選取 **虛擬資料表** 索引標籤。

3. 請按照實體標籤過濾實體清單，尋找 **LinkedIn 匯出的候選人**。

4. 選取實體，然後選取 **產生/重新整理**。

## <a name="exporting-candidate-records"></a>匯出候選記錄

設定完成後，招募人員和人力資源 (HR) 專業人員可使用 LinkedIn Talent Hub 裡的 **匯出到 HRIS** 功能將已經錄用的候選人記錄從 LinkedIn Talent Hub 匯出到人力資源。

### <a name="export-records-from-linkedin-talent-hub"></a>從 LinkedIn Talent Hub 匯出記錄

待候選人走完招募流程並已經錄用後，您可以將候選人記錄從 LinkedIn Talent Hub 匯出到人力資源。

1. 請在 LinkedIn Talent Hub 中打開您錄用新員工的專案。

2. 選取候選人記錄。

3. 選取 **變更階段**，然後選取 **已錄用**。

4. 請在候選人刪節號選單上 (**...**) 選取 **匯出到 HRIS**。

5. 請在 **匯出到 HRIS** 窗格中輸入必須匯出的資訊：

    - 請在 **HRIS 提供者** 欄位中選取 **Microsoft Dynamics 365 Human Resources**。
    - 請在 **開始日期** 欄位中為新員工選取數值。
    - 請在 **職銜** 欄位中輸入新員工工作的職銜。
    - 請在 **位置** 欄位中輸入員工將任職的位置。
    - 請輸入或驗證員工的電子郵件信箱地址。

![請匯出到 LinkedIn Talent Hub 的 HRIS 窗格。](./media/hr-admin-integration-linkedin-talent-hub-export.jpg)

## <a name="complete-onboarding-in-human-resources"></a>請在人力資源完成上線動作

從 LinkedIn Talent Hub 匯出到 Human Resources 的候選人記錄會在 **人事管理** 頁的 **準員工** 區出現。

1. 請在人力資源中打開 **人事管理** 頁。

2. 請在 **準員工** 區選取 **錄用** 已入選的候選人。

3. 請在 **錄用新背景工作角色** 對話方塊中審核記錄並新增任何必要資訊。 您也可以選取已經錄用候選人的職位編號。

等必要資訊輸入後，您可以繼續建立員工記錄和上線員工的標準流程。

下列詳細資料已經匯入並且包括在新員工記錄：

- 名字
- 姓氏
- 雇用開始日期
- 電子郵件地址
- 電話號碼

## <a name="see-also"></a>也請參閱

[配置 Dataverse 虛擬資料表](./hr-admin-integration-common-data-service-virtual-entities.md)<br>
[何謂 Microsoft Dataverse？](/powerapps/maker/common-data-service/data-platform-intro)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
