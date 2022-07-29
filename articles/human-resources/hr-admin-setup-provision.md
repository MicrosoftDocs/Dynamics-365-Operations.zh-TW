---
title: 佈建人力資源
description: 本主題說明佈建 Microsoft Dynamics 365 Human Resources 的新實際執行環境的流程。
author: twheeloc
ms.date: 01/07/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SystemAdministrationWorkspaceForm
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 0c856bca32c3dee44469c098961d85b4d8cb70a6
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8451986"
---
# <a name="provision-human-resources"></a>佈建人力資源

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



本主題說明佈建 Microsoft Dynamics 365 Human Resources 的新實際執行環境的流程。 

## <a name="prerequisites"></a>先決條件

在您開始佈建新實際執行環境之前，下列先決條件必須先準備就緒：

- 您已經透過 Cloud Solution Provider (雲端解決方案提供者) 或企業架構 (EA) 協議購買人力資源。 如果您既有的 Microsoft Dynamics 365 授權已經包含括力資源服務計劃，而您無法完成本主題的步驟，請聯絡支援中心。

- 全域管理員已登入 [Microsoft Dynamics Lifecycle Services](https://lcs.dynamics.com)(LCS) 並建立新人力資源專案。 

## <a name="provision-a-human-resources-trial-environment"></a>佈建人力資源試用環境

在佈建您的第一個沙箱或實際執行環境之前，您可能希望佈建[人力資源試用環境](https://go.microsoft.com/fwlink/p/?LinkId=2115962)驗證人力資源功能。 試用環境包含可用來安全探索程式的虛構資料。 儘管試用環境歸要求使用者名下，但仍可透過人力資源系統管理經驗邀請其他使用者。 

試用環境提供個人評估人力資源功能的能力，他們目前仍無人力資源環境的存取權。 如果您正在佈建試用環境，而且通過驗證的使用者已經有權存取一個或多個既有的人力資源環境，則使用者將被重新導向到既有環境或環境清單。

試用環境無意當成實際執行環境使用。 它們的試用期以 30 天為限。 當試用期到期時，環境和所有內含資料將被刪除且無法恢復。 此環境無法轉換為沙箱或實際執行環境。 您可以在既有環境到期後註冊新試用環境。

建立人力資源試用環境時，Power Apps 試用環境也會在租使用者基礎上建立並連結人力資源環境。 Power Apps 環境，又名 “TestDrive”，具有和人力資源環境相同的試用期。

> [!NOTE]
> 如果通過驗證的使用者沒有建立 Power Apps 試用環境的權限，則佈建人力資源試用環境將會失敗。 此名使用者必須納入可以建立 Power Platform 系統管理中心試用環境的使用者群組。 更多資訊，請參閱[控制可以在 Power Platform 系統管理中心建立與管理環境的使用者](/power-platform/admin/control-environment-creation)。

## <a name="plan-human-resources-environments"></a>規劃人力資源環境

在您建立第一個人力資源環境之前，您應該仔細計劃專案的環境需求。 人力資料的基本訂閱包括兩個環境：實際執行環境和沙箱環境。 按照您的專案的複雜度，您可能需要購買額外的沙箱環境支援專案活動。 

額外環境的考量因素：

- **資料移轉**：您可能需要額外的資料移轉活動環境，讓您的沙箱環境可以在整個專案用於測試目的。 擁有額外環境允許資料移轉活動繼續，同時測試和組態活動同時在不同的環境發生。
- **整合**：您可能需要考慮額外的環境配置和測試整合。 這可能包括原機整合像 Ceridian Dayforce LinkedIn Talent Hub 整合或自訂整合，例如工資單、申請人追蹤系統或福利系統和提供者的整合。
- **訓練**：您可能需要另外一組訓練資料配置的環境，以便訓練您的員工使用新系統。 
- **多階段專案**：您可能需要額外環境支援在專案初步上線後，專案階段中規劃的組態、資料移轉、測試或其他活動。

 > [!IMPORTANT]
 > 當您考慮您的環境時，我們建議如下：
 > - 在整個專案將您的實際執行環境當作為您的 GOLD 組態環境。 這很重要，因為您無法將沙箱環境複製到實際執行環境。 因此當您上線時，您的 GOLD 環境就是你的實際執行環境，您將在這個環境完成切換活動。</br></br>
 > - 在您上線之前，請使用您的沙箱或另一個環境執行模擬切換。 您可以將含有您的 GOLD 組態的實際執行環境重新整理到沙箱環境。</br></br>
 > - 保留一份詳細的切換核對清單，包括上線切換期間將最終資料移轉到實際執行環境所需的每個資料封包。</br></br>
 > - 請在整個專案將您的沙箱環境當作為您的 TEST 環境。 如果您需要額外環境，貴組織可以支付額外成本購買它們。</br></br>

## <a name="create-an-lcs-project"></a>建立 LCS 專案。

若要使用 LCS 管理您的人力資源環境，您必須先建立 LCS 專案。

1. 請使用您用來訂閱人力資源的帳戶登入 [LCS](https://lcs.dynamics.com/Logon/Index)。

   > [!NOTE]
   > 為了確保佈建成功，您用來佈建人力資源環境的帳戶必須指派給 Power Apps 環境中的 **系統管理員** 或 **系統自訂工具**，此環境與人力資源環境有關聯。 更多有關將資訊安全角色指派給 Power Platform 使用者的資訊，請參閱[配置各資源使用者安全性](/power-platform/admin/database-security)。

2. 請選取加號 (**+**) 建立專案。

3. 請選取 **Microsoft Dynamics 365 Human Resources** 作為產品名稱和產品版本。

4. 請選取 **Dynamics 365 Human Resources** 方法論。

5. 請選取 **建立**。

有關如何開始使用人力資源的資訊，請參閱您在新專案建立的 **人力資源** 方法論。 待您完成專案建立後，請完成下列程序佈建您的人力資源環境。

## <a name="provision-a-human-resources-project"></a>佈建人力資源專案

待您建立 LCS 專案之後，您可以將人力資源佈建到環境裡。

1. 請在您的 LCS 專案選取 **人力資源 App 管理** 圖格。

2. 指出此環境是人力資源的沙箱或實際執行的執行個體。 沙箱執行個體可能會開放提前預覽功能，方便早期反饋和測試。
   
    > [!NOTE]
    > 人力資源執行個體類型一旦設定就無法更改。 在繼續之前先驗證是否選取正確的執行個體類型。</br></br>
    > 人力資源執行個體類型與您在 Power Apps 系統管理中心設定的 Microsoft Power Apps 環境執行個體類型分開。
    
3. 如果您希望您的環境包括人力資源試用環境使用的相同示範資料集合，請選取 **包括示範資料** 選項。 示範資料有利於長期示範或訓練環境，絕不能用於實際執行環境。 您必須在初步部署時選擇此選項。 您日後無法更新既有的部署。

4. 人力資源始終佈建到 Microsoft Power Apps 環境裡啟用 Power Apps 整合和可擴充性。 請先閱讀本文章的 “選取 Power Apps環境” 小節後再繼續。 如果您還沒有 Power Apps 環境，請在 LCS 選取管理環境或瀏覽 Power Apps 系統管理中心。 然後按照這些步驟[建立 Power Apps 環境](/powerapps/administrator/create-environment)。

5. 請選取要佈建人力資源的環境。

6. 請選取 **是**，以表同意各項條款並開始部署。

   您的新環境會出現左側功能窗格的環境清單內。 然而您必須等到部署狀態更新為 **已部署** 才能使用環境。 這段流程通常需要幾分鐘。 如果佈建流程不成功，您必須聯絡支援中心。

7. 請選取 **登入人力資源** 使用您的新環境。

    > [!NOTE]
    > 如果您還沒有簽字認可最終要求，您可以在專案裡部署人力資源的測試執行個體。 接著您可以使用此執行個體測試您的解決方案，直到您簽字認可為止。 如果您使用新環境測試，您必須重覆這項程序建立實際執行環境。

## <a name="select-a-power-apps-environment"></a>選取 Power Apps 環境

您可以使用 Power Apps 工具整合與擴充對人力資源資料的使用範圍。 有關 Power Apps 環境，包括環境範圍、環境存取和建立與選擇環境的資訊，請參閱[宣布 Power Apps 環境](https://powerapps.microsoft.com/blog/powerapps-environments/)。 

判定要部署人力資源的 Power Apps 環境時請使用下列指引： 

1. 請在 LCS 選取 **管理環境**。 您也可以直接前往 Power Apps 系統管理中心檢視既有的環境和建立新環境。

2. 單一人力資源環境會測繪單一 Power Apps 環境。

3. Power Apps 環境包含人力資源和對應的 Power Apps、Power Automate 和 Dataverse 應用程式。 如果 Power Apps 環境遭到刪除，內含的應用程式也會一併刪除。 佈建人力資源環境時，您可以佈建 **試用** 或 **實際執行** 環境。 請根據環境的使用方式選擇環境類型。 

4. 應考慮資料整合和測試策略，例如沙箱、UAT 或實際執行。 仔細考慮對您的部署的隱含用意，因為要變更測繪 Power Apps 環境的人力資源環境不是那麼容易。

5. 下列 Power Apps 環境不能用於人力資源。 它們是從 LCS 內的選取清單篩選出來：
 
    - **預設 Power Apps 環境**- 由於每位租使用者都自動以預設的 Power Apps 環境佈建，因此我們不建議搭配人力資源使用。 所有租使用者都可以存取 Power Apps 環境並在測試和探索 Power Apps 或 Power Automate 整合時，可能無意中毁損實際執行資料。
   
    - **試用環境**- 這些環境建立時皆會設定到期日期。 到期時，您的環境和內含的任何人力資源執行個體將會自動移除。
   
    - **不支援的地理位置**- 環境必須在可支援的地理位置。 更多資訊，請參閱[支援的地理位置](hr-admin-setup-provision.md#supported-geographies)。

6. 如果環境選取 **啟用 Dynamics 365 Apps** 選項，則只能使用整合人力資源資料和 Power Apps 環境的雙重寫入功能。 更多雙重寫入的資訊，請參閱[雙重寫入首頁](../fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-home-page.md)。

    > [!NOTE]
    > **啟用 Dynamics 365 Apps** 選項必須在建立 Power Apps 環境時選取。 如果佈建時未選取此選項，您將無法使用雙重寫入功能整合 Dynamics 365 Human Resources 和 Power Apps 環境之間的資料，或在環境上安裝 Dynamics 365 Apps，例如 Dynamics 365 Sales 和 Field Service。 此選項不可逆。 更多資訊，請參閱 Power Platform 文件網站的[建立新環境時的一些重要考量因素](//power-platform/admin/create-environment#some-important-considerations-when-creating-a-new-environment)。

7. 待您判定要使用的正確環境後，您可以繼續佈建流程。 

### <a name="supported-geographies"></a>支援的地理位置

人力資源目前支援下列地理位置：

- 美國
- 歐洲
- 英國
- 澳洲
- 加拿大
- 亞洲 

當您建立人力資源環境時，您會選取與人力資源環境有關聯的 Power Apps 環境。 接著在與選取的 Power Apps 環境相同的 Azure 地理環境中佈建人力資源環境。 您可以在建立與人力資源環境有關聯的 Power Apps 環境時選取地理位置，進而選取實際並列的人力資源環境和資料庫。

您可以選取佈建環境的 Azure *地理環境*，但不能選取特定的 Azure *地區*。 自動化會判定已建立環境最佳化負載平衡和效能的地理位置內的特定地區。 您可以在 [Azure 地理位罝](https://azure.microsoft.com/global-infrastructure/geographies) 找到關於 Azure 地理位置和區域的資訊。

人力資源環境的資料將始終包含在建立它的 Azure 地理位置中。 然而它並不總是包含在相同的 Azure 區域內。 基於災害復原目的，資料將在此地理位置內的主要 Azure 區域和輔助容錯移轉區域中複製。

 > [!NOTE]
 > 不支援將人力資源環境從一個 Azure 區域遷移到另一個。

## <a name="grant-access-to-the-environment"></a>授予對環境的存取權

預設情況下，建立環境的全域管理員可以存取它。 您必須明確授予額外應用程式使用者的存取權限。 您必須在人力資源環境中新增使用者並指派適當的角色。 更多資訊，請參閱[建立新使用者](/dynamics365/unified-operations/dev-itpro/sysadmin/tasks/create-new-users)和[指派使用者資訊安全角色](/dynamics365/unified-operations/dev-itpro/sysadmin/tasks/assign-users-security-roles)。 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
