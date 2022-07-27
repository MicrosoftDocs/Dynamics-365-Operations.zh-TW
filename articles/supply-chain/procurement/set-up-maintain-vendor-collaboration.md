---
title: 設定與維護廠商共同作業
description: 本主題說明如何在 Dynamics 365 Supply Chain Management 中設定廠商共同作業。 這也會解釋如何設定新的廠商共同作業使用者並管理這些使用者的資訊安全角色。
author: Henrikan
ms.date: 12/03/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DirExternalRole, SysUserRequestListPage, VendVendorPortalUsers, WorkflowTableListPageRnr
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.custom: 220774
ms.assetid: 69d05e8b-7dc2-48ea-bc24-bea9ac963579
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: b635255fffa6fd3c6612cd248dc692df204aa76d
ms.sourcegitcommit: 614d79cba238e466d445767a7d0a012e785a9861
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/19/2021
ms.locfileid: "8449394"
---
# <a name="set-up-and-maintain-vendor-collaboration"></a>設定與維護廠商共同作業

[!include [banner](../includes/banner.md)]

廠商共同作業界面向外部廠商使用者公開了一組有限的訂購單、發票和寄售庫存的資訊。 透過該界面，廠商也可以回覆詢價 (RFQ)、查看和編輯基本的公司資訊。

本主題說明如何在 Dynamics 365 Supply Chain Management 中設定廠商共同作業。 這也會解釋如何設定工作流程以佈建新的廠商共同作業使用者，並管理這些使用者的資訊安全角色。

> [!NOTE]
> 關於廠商共同作業資訊安全角色的資訊僅適用於當前版本的財務與營運。 在 Microsoft DynamicsAX 7.0 (2016 年 2 月) 和 Microsoft Dynamics AX 應用程式版本 7.0.1 (2016 年 5 月)，您可以使用 **廠商入口網站** 模組。 關於 Microsoft Dynamics AX 中廠商入口網站的使用者權限資訊，請查看[廠商入口網站使用者安全性](configure-security-vendor-portal-users.md)。

## <a name="set-up-vendor-collaboration-security-roles"></a>設定廠商共同作業資訊安全角色

具有充分權限的採購專業人員或廠商可以透過在聯絡人記錄上啟用 **佈建廠商使用者** 來要求將聯絡人設定為使用者。 在佈建過程中，為新的外部使用者選擇使用者權限，並提交新的廠商使用者要求。 正確設定可在廠商使用者要求中選擇的使用者權限至關重要。 否則，廠商可能會被授予存取他們在 Supply Chain Management 中不應存取資訊的權限。

### <a name="set-up-the-security-roles-that-are-available-for-selection-when-a-new-user-request-is-used-for-a-contact-person"></a>設定當新使用者要求用於聯絡人時可供選擇的資訊安全角色

1. 選擇 **安全性系統管理**&gt;**安全性**&gt;**外部角色**。
2. 選擇 **新增**，然後選擇資訊安全角色和 **廠商** 合作對象角色。

您可能想要新增 **廠商管理員 (外部)** 和 **廠商 (外部)** Supply Chain Management 中提供的角色。 或者，您可以使用貴公司建立的資訊安全角色。

僅當廠商能夠建立新聯絡人、為新使用者提交廠商共同作業要求和變更使用者資訊，並透過工作流程處理這些要求時，您才應使用 **廠商管理員 (外部)**。

如果您計畫手動設定廠商聯絡人和使用者，您可以只設定 **廠商 (外部) 角色**。 然後，此角色將是唯一可以透過廠商使用者要求申請的角色。

> [!NOTE]
> 當您手動建立新使用者帳戶時，會自動授予 **SystemUser** 角色。 因此，您必須刪除該角色並分配 **SystemExternalUser** 角色。 如果透過廠商使用者要求啟動的工作流程建立新使用者帳戶以設定新使用者，則將分配您為廠商共同作業設定的一個或多個角色和 **SystemExternalUser** 角色。

#### <a name="vendor-admin-external-security-role"></a>廠商管理員 (外部) 資訊安全角色

**廠商管理員 (外部)** 角色可用於維護廠商聯絡資訊，並要求佈建新廠商共同作業使用者。 擁有此資訊安全角色的外部使用者可以執行以下任務：

- 查看和修改聯絡人資訊，例如聯絡人的職務、電子郵件地址和電話號碼。
- 將新的或現有的聯絡人新增至他們作為聯繫人的廠商帳戶。
- 刪除他們建立的任何聯絡人。
- 啟用或停用聯絡人與廠商帳戶之間的關聯。 聯絡人和廠商帳戶之間的關聯被停用後，無法在新的訂購單或其他文件中引用該聯絡人。
- 拒絕或允許聯絡人存取廠商共同作業界面上的廠商帳戶特定文件。 在停用聯絡人和廠商帳戶之間的關聯後，永遠拒絕存取特定供應商帳戶的文件。
- 使用 **佈建使用者** 動作，為聯絡人要求新使用者帳戶。
- 要求停用聯絡人的使用者帳戶。
- 要求修改聯絡人的使用者帳戶，以新增或刪除資訊安全角色。
- 檢視 RFQ。

#### <a name="vendor-external-security-role"></a>廠商 (外部) 資訊安全角色

**廠商 (外部) 角色** 可用於處理採購訂單的外部廠商。 擁有此資訊安全角色的外部使用者可以執行以下任務：

- 回應和查看訂購單的相關資訊。
- 維護廠商共同作業發票。
- 查看寄售庫存。
- 查看並回應 RFQ。
- 查看廠商資訊。

## <a name="set-up-security-roles-that-are-used-when-prospective-vendors-are-onboarded"></a>設定潛在廠商入職時使用的資訊安全角色

若要加入透過潛在廠商註冊要求啟動的廠商，您必須設定外部資訊安全角色。 此角色將在佈建程序中分配給新使用者，該程序由 **使用者要求工作流程 (平台)** 類型。 關於更多詳細資訊，請查看此主題中[設定工作流程以處理廠商共同作業使用者要求](#set-up-workflows-to-process-vendor-collaboration-user-requests)段落的後續內容。

關於如何加入潛在廠商的資訊，請查看[上線廠商](vendor-onboarding.md)。

### <a name="set-up-a-security-role-that-is-used-when-a-new-prospective-vendor-user-request-is-submitted"></a>設定在提交新的潛在廠商使用者要求時使用的資訊安全角色

1. 選擇 **安全性系統管理** > **安全性** > **外部角色**。
2. 選擇 **新增**，然後選擇資訊安全角色和 **潛在廠商** 合作對象角色。

你應該新增 **廠商潛在客戶 (外部)** Supply Chain Management 中提供的角色。

資訊安全角色將僅授予對新廠商註冊精靈的存取權限。

## <a name="set-up-workflows-to-process-vendor-collaboration-user-requests"></a>設定工作流程以處理廠商共同作業使用者要求

為協助確保完成所有相關任務，並獲得適當的核准，您必須設定工作流程來處理廠商共同作業使用者要求。

廠商共同作業要求由具有 **廠商管理員 (外部)** 資訊安全角色或類似權限的外部廠商，或由貴公司的採購專業人員提交。 他們也可以在廠商上線程序中，從潛在廠商註冊要求中生成。

要求分為三種類型：

- 提供給新使用者的要求
- 停用現有使用者的要求
- 修改現有使用者的資訊安全角色要求

如需廠商共同作業使用者要求的詳細資訊，請參閱[管理廠商共同作業使用者](manage-vendor-collaboration-users.md)。

您必須建立兩個或更多工作流程，來處理共三種類型的廠商共同作業要求。 新的工作流程會建立在 **使用者工作流程** 頁面上。

### <a name="example-of-a-workflow-for-provisioning-new-users-and-modifying-security-roles"></a>佈建新使用者和修改資訊安全角色的工作流程範例

若要處理廠商使用者建立新使用者和修改資訊安全角色的要求，您可以在工作流程的開頭放置一個分支條件。 如此一來，使用工作流程的不同分支，具體取決於要求是建立新使用者還是修改現有使用者。

若要設定此分支，請建立一個新的 **使用者要求工作流程 (平台)** 工作流程類型。 此工作流程的分支可能包含以下元素。

#### <a name="branch-to-provision-new-users"></a>分支以佈建新使用者

1. 將核准工作分配給負責核准新使用者存取廠商共同作業權限的人員。
2. 將任務分配給負責要求 Azure 入口網站中新的 Microsoft Azure Active Directory (Azure AD) 使用者帳戶的人員。 在此步驟，使用預定義的 **發送 Azure B2B 使用者邀請** 工作。 B2B 使用者可以自動匯出至 Azure AD。 使用預定義的 **佈建 Azure AD B2B 使用者**。 關於更多詳細資訊，請參閱[將 B2B 使用者匯出至 Azure AD](../../fin-ops-core/dev-itpro/sysadmin/implement-b2b.md)。
3. 將核准工作分配給上傳至 Azure 的人員。 如果未成功建立帳戶，此人員將拒絕工作並結束工作流程。 如果您已包含透過 B2B 應用程式編程介面 (API) 將新使用者帳戶自動匯出到 Azure 的步驟，則可以跳過此核准工作。
4. 新增佈建新使用者的自動化任務。 在此步驟，使用預定義的 **自訂化佈建使用者** 工作。
5. 新增通知新使用者的工作。 您可能會希望向新使用者發送一封歡迎電子郵件，其中包含 Supply Chain Management 的 URL。 此電子郵件可以使用您在 **電子郵件** 頁面建立的範本，然後選擇 **使用者工作流程參數** 頁面。 此範本可以包括 **%portalURL%** 標籤。 生成歡迎電子郵件時，此標籤將替換為 Supply Chain Management 租用戶的 URL。

    > [!NOTE]
    > 此工作流程可用於涉及使用者上線的多個情境。 例如，當潛在廠商或聯絡人需要廠商共同作業帳戶時則可以使用。 因此，您應該將電子郵件表述為可用於多種目的的一般性聲明。

#### <a name="branch-to-modify-security-roles"></a>分支以修改資訊安全角色

1. 將核准工作分配給負責核准資訊安全角色變更的人員。
2. 新增負責新增或刪除相關資訊安全角色的自動化任務。 在此步驟，使用 **自訂化佈建使用者** 工作。

### <a name="example-of-a-workflow-for-inactivating-a-user"></a>停用使用者的工作流程範例

建立 **停用使用者要求工作流程平台** 類型的工作流程，然後新增下列工作。

1. 將核准工作分配給負責接受未啟用使用者要求的人員。 您可以新增條件以自動執行此核准步驟。
2. 新增停用使用者的自動化任務。 在此步驟，使用 **自訂化停用使用者** 工作。
3. 新增所需的任何清理工作。 例如，您可以新增一個從 Azure 入口網站中的目錄中刪除帳戶的任務。

## <a name="enable-vendor-collaboration-for-a-specific-vendor"></a>為特定廠商啟用廠商共同作業

在為將要使用廠商共同作業的使用者建立使用者帳戶前，您必須設定廠商，方便它可以使用廠商共同作業。 在 **廠商** 頁面、在 **一般** 索引標籤，設定 **協作啟用** 欄位。 可以使用以下選項：

- **啟用 (訂購單會自動確認)** – 如果廠商在沒有要求變更的情況下接受訂購單，則會自動確認訂購單。
- **啟用 (訂購單未自動確認)** – 您的組織必須在廠商接受訂購單後手動確認訂購單。

> [!NOTE]
> 貴公司的採購專業人員也可以完成此工作。

## <a name="troubleshoot-the-provisioning-of-new-vendor-collaboration-users"></a>對新廠商共同作業使用者的佈建進行疑難排解

新的廠商共同作業是透過您設定的工作流程佈建，以處理 **佈建廠商使用者** 類型的廠商共同作業使用者要求。

如果新廠商共同作業使用者的電子郵件地址屬於在 Azure 中註冊為租用戶的網域 (如果是受控網域帳戶)，則該電子郵件地址必須是現有的 Azure AD 帳戶。 否則，佈建程序將無法完成。

關於 Azure AD 帳戶管理工作流程中的 **發送 Azure B2B 使用者邀請** 任務中使用的程序詳細資訊，請參閱 [Azure Active Directory B2B 共同作業](/azure/active-directory/external-identities/what-is-b2b)。

## <a name="additional-resources"></a>其他資源

[與外部廠商的廠商共同作業](vendor-collaboration-work-external-vendors.md)

觀看關於廠商上線程序的短片：[新廠商上線](https://www.youtube.com/watch?v=0KUc3AGaTKk&feature=youtu.be)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
