---
title: 管理廠商共同作業使用者
description: 本主題說明如何要求佈建新的廠商共同作業使用者，以及如何新增廠商共同作業連絡人。
author: Henrikan
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: smmContactPerson, VendVendorContactPerson, VendVendorPortalUser
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.custom: 220744
ms.assetid: edc19ad0-3565-4d47-98ac-dda6098f63ac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: ff0d11bf2c42f7ae63e3db5f31f3ffea2c28f693
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449076"
---
# <a name="manage-vendor-collaboration-users"></a>管理廠商共同作業使用者

[!include [banner](../includes/banner.md)]

本主題說明如何要求佈建新的廠商共同作業使用者，以及如何新增廠商共同作業連絡人。 

Dynamics 365 Supply Chain Management 的廠商共同合作介面會向外部廠商提供訂購單、發票和寄售庫存資訊。 若您作業的身分是外部廠商且具備 **廠商管理員 (外部)** 資訊安全角色或類似權限，則可建立新的廠商共同作業連絡人，並要求佈建新的使用者。 若您是採購專業人員，也可執行這些任務。 在本主題中，此角色是指擁有 Supply Chain Management 執行個體的公司內工作的採購專業人員。 若您是外部廠商，需要廠商共同作業使用方式的更多資訊，請參閱[廠商與客戶共同作業](vendor-collaboration-work-customers-dynamics-365-operations.md)。  

若您是採購專業人員，需要廠商共同作業使用方式的更多資訊，請參閱[廠商與外部廠商共同作業](vendor-collaboration-work-external-vendors.md)。

## <a name="add-new-vendor-collaboration-contacts"></a>新增廠商共同作業連絡人
若您希望他人能存取廠商共同作業，則必須先將他們新增為廠商共同作業連絡人。 您可能也想將公司內不會使用廠商共同作業的員工新增為連絡人。 例如，他們可能是其他種採購資訊的連絡窗口。 新的連絡人會新增至 **所有連絡人** 頁面，存取位置位於 **廠商共同作業** &gt; **連絡人** 功能表。 若要新增連絡人：

1.  按一下 **新增**。
2.  輸入連絡人詳細資料。
3.  選擇他們在您的公司中代表的法律實體，以及他們在公司作業中欲合作的法律實體。 方法是選取 **我的公司中的法律實體**/**客戶公司中的法律實體** 的配對。
4.  按一下 **建立**。

若要刪除連絡人，只能刪除您建立的連絡人。

## <a name="vendor-collaboration-user-requests"></a>廠商共同作業使用者要求
廠商共同作業使用者要求可由採購專業人員或外部廠商管理員提出。

-   若您是外部廠商，您可從 **廠商共同作業** 模組中的 **所有連絡人** 頁面提出要求。
-   若您是採購專業人員，則可從 **檢視連絡人** 頁面提出要求。 方法是在動作窗格中 **設定** 區段的廠商記錄中，選擇 **連絡人** &gt; **檢視連絡人**。

您可要求佈建使用者、停用使用者，或修改資訊安全角色。 若您是外部廠商管理員，您必須註冊為使用者要求的廠商帳戶的連絡人，而且您必須擁有這些廠商帳戶的廠商共同作業介面存取權。  

要求提出後，將新增至 **廠商共同作業** 模組內的 **廠商共同作業使用者要求** 清單中，以及 **採購和開源** 模組內的 **廠商共同作業使用者要求** 清單中 (外部使用者無法存取採購和開源模組)。

### <a name="provision-a-user"></a>佈建使用者

要求佈建新使用者前，必須將該人員設定為一或多個廠商帳戶的連絡人。 若要為新的廠商共同作業使用者建立要求：

1. 在 **所有連絡人** 頁面中，按一下 **佈建廠商使用者**。
2. 輸入該使用者的電子郵件地址。 該使用者將使用此地址來登入 Supply Chain Management。 若該電子郵件地址所屬網域已註冊為 Microsoft Azure 租用戶，則必須為現有 Azure Active Directory (AAD) 帳戶，才能成功完成佈建流程。 若該電子郵件地址所屬網域並未向 Microsoft Azure 註冊，則佈建流程會建立 AAD 帳戶，且該名新使用者會收到邀請郵件。 網域為 @hotmail.com、@gmail.com 或 @comcast.net 等消費者的電子郵件地址無法用於註冊使用者。
3. 將使用者必須存取的所有法律實體的 **允許廠商共同作業存取** 選項設為 **是**。
4. 在 **指派使用者角色** 區段，選取新使用者應具備的資訊安全角色的 **指派** 核取方塊。
5. 按一下 **提交**。

廠商使用者要求提交後，所選廠商帳戶的 **允許廠商共同作業存取** 欄位會設為 **是**，並啟動使用者要求工作流程。 此工作流程將建立新的使用者，並指派資訊安全角色。 此外也會啟用 Azure B2B 服務，可與 Azure 入口網站展開互動，並將新的或現有的 AAD 帳戶與 Supply Chain Management 使用者帳戶建立關聯。 如需詳細資訊，請參閱[什麼是 Azure AD B2B 共同作業？](/azure/active-directory/active-directory-b2b-what-is-azure-ad-b2b)。

### <a name="inactivate-a-user"></a>停用使用者

有兩種方法可移除使用者對廠商共同作業的存取權：

-   在廠商的 **連絡人** 頁面，將該連絡人的 **允許廠商共同作業存取** 設為 **否**。 若該人員為多個法律實體的連絡人，則可針對個別法律實體一一設定。 僅採購專業人員可使用此選項。
-   停用整個使用者帳戶，方法是提交 **停用廠商使用者** 要求。

如需要求停用使用者：

1.  在 **所有連絡人** 頁面中，按一下 **停用****廠商使用者**。
2.  在 **業務理由** 欄位撰寫留言。
3.  按一下 **提交**。

### <a name="modify-security-roles"></a>修改資訊安全角色

**維護廠商使用者角色** 頁面與 **佈建廠商使用者** 頁面相同，唯一的差異在於可編輯的資訊安全角色清單。  

如需要求修改使用者的資訊安全角色：

1.  在 **所有連絡人** 頁面中，按一下 **維護****廠商使用者角色**。
2.  在 **業務理由** 欄位撰寫留言。
3.  在 **維護使用者角色** 區段，選取要指派的資訊安全角色，或清除要移除的資訊安全角色。
4.  按一下 **提交**。






[!INCLUDE[footer-include](../../includes/footer-banner.md)]