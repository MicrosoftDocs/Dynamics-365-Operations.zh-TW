---
title: 建立新使用者
description: 使用者是您組織的內部員工或外部客戶和廠商，他們需要存取系統才能執行其工作。
author: peakerbl
ms.date: 01/12/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SysUserManagement, SysDataAreaSelectLookup, SysSecUserAddRoles, SysUserMSODSUserImport
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 480d181e8abb3af5a7406efd13c8bd9961a7490a
ms.sourcegitcommit: e40a9fac5bac9f57a6dcfe73a1f21856eab9b6a9
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/02/2021
ms.locfileid: "8460539"
---
# <a name="create-new-users"></a>建立新使用者

[!include [banner](../../includes/banner.md)]

在您可以存取財務和營運應用程式之前，您必須先新增到 **使用者** 頁 (**系統管理\>使用者\>使用者**)。 使用者包括您組織的內部員工，或外部客戶和廠商。 可以手動匯入或新增使用者。 所有使用者都必須獲得正確許可才能合規使用。

如需如何購買和授權財務和營運應用程式的相關資訊，請參閱[Microsoft Dynamics 365 授權指南](https://go.microsoft.com/fwlink/?LinkId=866544&amp;clcid=0x409)。

## <a name="assign-a-license-to-a-user"></a>將授權指派給使用者
系統管理員可以在[Microsoft 365系統管理中心](/office365/admin/admin-overview/about-the-admin-center)[為使用者指派授權](/office365/admin/subscriptions-and-billing/assign-licenses-to-users)。

## <a name="add-an-external-user-in-azure-ad-and-assign-a-license"></a>在 Azure AD 中新增外部使用者並指派授權 
外部使用者必須存在於您的租使用者目錄 (Azure Active Directory (Azure AD)) 中，以便為他們指派授權。 這些外部使用者應作為來賓使用者新增到 Azure AD 中的租使用者，然後指派適當的授權。 財務和營運應用程式的要求是來賓使用者的公司必須使用 Azure AD。 如需相關資訊，請參閱[在 Azure 入口網站中新增 Azure Active Directory B2B 共同作業使用者](/azure/active-directory/b2b/add-users-administrator)。

## <a name="import-new-users-from-azure-ad"></a>從 Azure AD 匯入新使用者 
1. 進入 **系統管理**\>**使用者**\>**使用者**。
2. 在動作窗格上，選取 **匯入使用者**。
3. 選取要匯入的使用者。 該清單包括現行不是此環境中的使用者的 Azure AD 使用者。
4. 選取 **匯入使用者**。
5. 選取 **關閉**。

> [!NOTE]
> **公司** 欄位的值將根據管理員的現行工作階段公司設定。匯入後，您必須根據需要指派角色和組織。 如需相關資訊，請參閱[為使用者指派資訊安全角色](assign-users-security-roles.md)。 在有條件約束的情況下，可能還需要將使用者與 **人員** 連結並更新使用者選項，例如語言。

## <a name="manually-add-a-new-user"></a>手動新增新使用者
1. 進入 **系統管理**\>**使用者**\>**使用者**。
2. 在動作窗格上，選取 **新建**。
3. 在 **使用者識別碼** 欄位，輸入使用者的唯一識別碼。   
4. 在 **使用者名稱** 欄位中，輸入使用者名稱。  
5. 在 **提供者** 欄位：
 - 對於內部使用者，使用預設值。 例如，您的 Azure AD 租使用者以 https://sts.windows.net/ 為前綴。  
 - 對於非 Azure AD 使用者，例如 Service-2-Service 帳戶，輸入基本文字值。 例如，NA。 如果使用有效的識別提供者值，此值將有助於避免可能導致錯誤的不正確識別提供者調用。  
 - 對於外部或來賓使用者，請在 https://sts.windows.net/ 之後新增其 Azure AD 租使用者名稱。
6. 在 **電子郵件** 欄位中，輸入使用者的完整電子郵件/使用者主體名稱。  
7. 在 **公司** 欄位中，為使用者選取預設的啟動公司。 
8. 選取 **儲存**。

儲存使用者記錄時，識別提供者和遙測識別碼的值將根據 [Microsoft 圖表](/graph/overview)調用進行更新。 遙測識別碼根據 Azure AD 中使用者的物件識別碼/安全性識別碼 (SID)。

> [!NOTE]
> 新增使用者後，您必須根據需要指派角色和組織。 如需相關資訊，請參閱[為使用者指派資訊安全角色](assign-users-security-roles.md)。 在有條件約束的情況下，可能還需要將使用者與 **人員** 連結並更新 **使用者選項**，例如語言。

## <a name="change-a-user-id"></a>更改使用者識別碼
若要更改使用者識別碼，您必須重命名資料庫中的索引鍵。 當您使用此過程更改使用者識別碼時，所有相關的使用者設定都會修改為使用新的使用者識別碼。 例如，更新 **SysLastValue** 表中的使用資訊以參考新的使用者識別碼。

> [!NOTE]
> 使用者識別碼是使用者資訊表的主索引鍵。 對於現有使用者，重新命名主索引鍵可能需要一些時間，因為對索引鍵的所有參考也會在資料庫中更新。 

1. 進入 **系統管理\>使用者\>使用者**。
2. 在清單中選取一個使用者，然後選取 **選項\>記錄資訊**。
3. 選取 **重新命名**。
4. 為使用者識別碼輸入一個新的唯一值，然後選取 **確定**。 
5. 選取 **是** 以確認。

## <a name="additional-resources"></a>其他資源

如需實施 B2B 使用者的更多選項，請參閱[將 B2B 使用者匯出到 Azure AD](../implement-b2b.md)。

如需預設定系統帳戶的相關資訊，請參閱[預設定的系統帳戶](../pre-configured-system-accounts.md)


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]