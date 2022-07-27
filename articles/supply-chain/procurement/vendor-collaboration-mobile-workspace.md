---
title: 廠商共同作業行動工作區
description: 本主題提供廠商共同作業行動工作區的資訊。 此工作區可幫助您的廠商及時了解已發送給他們進行核准的訂購單最新資訊。 他們還可以查看有關新的和更新的訂購單和連絡人的資訊。
author: Henrikan
ms.date: 12/01/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: 267074
ms.assetid: 1d293b3a-2fa2-418d-9347-78c2809d67fe
ms.search.region: global
ms.author: henrikan
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: efbd0afb0d84f76058b75126af200a9b10197559
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448959"
---
# <a name="vendor-collaboration-mobile-workspace"></a>廠商共同作業行動工作區

[!include [banner](../includes/banner.md)]

本主題提供 **廠商共同作業** 行動工作區的資訊。 此工作區可幫助您的廠商及時了解已發送給他們進行核准的訂購單最新資訊。 他們還可以查看有關新的和更新的訂購單和連絡人的資訊。

此行動工作區旨在與「財務和營運」行動應用程式一起使用。

## <a name="overview"></a>概觀 
**廠商共同作業** 行動工作區會通知廠商新的訂購單資訊，以便他們可以在 Web 用戶端中查看訂購單並做出回應。 

>[!NOTE]
> 行動工作區應做為廠商共同作業 Web 介面的補充，而不是替代它。 

您的廠商可以使用 **廠商共同作業** 行動工作區來查看發送給他們進行核准的新訂購單。 其會顯示訂購單資訊，例如產品、數量和要求的交貨日期。 也會根據每個廠商的設定決定是否顯示價格資訊。 

以廠商身份登錄的使用者將看到哪些訂購單已得到回應，以及哪些訂購單仍在等待客戶操作。 例如，訂購單可能正在等待客戶動作，因為廠商建議了另一個交貨日期，但客戶尚未同意該日期。 廠商還將看到已確認但尚未交貨的訂購單清單。 

若要回應訂購單，廠商必須使用 Web 用戶端中提供的廠商共同作業 Web 介面。 在那裡，廠商還可以獲得有關訂單的更多資訊，例如文件附件、每行的交貨地址以及與廠商相關的費用。 

具有特殊安全角色的廠商可以查看為廠商帳戶註冊了哪些連絡人。 相同的安全角色可讓廠商查看已提交的任何使用者要求的狀態。 

必須使用 Web 用戶端中的廠商共同作業 Web 介面來建立新連絡人和提交新使用者要求。 

**廠商共同作業** 行動工作區可讓廠商執行以下工作：

-   查看發送給廠商的新訂購單。
-   查看廠商已回應且正在等待客戶操作的訂購單。
-   查看已確認但尚未完全收貨的訂購單。
-   查看為廠商帳戶註冊的連絡人資訊。 (此工作需要其他的安全角色。)
-   查看有關廠商提交的使用者要求的資訊，並追蹤要求的狀態。 (此工作需要其他的安全角色。)

## <a name="prerequisites"></a>先決條件
先決條件會根據為您組織部署的 Microsoft Dynamics 365 版本而異。

### <a name="prerequisites-if-you-use-supply-chain-management"></a>使用 Supply Chain Management 時的先決條件
如果您的組織已部署 Supply Chain Management，系統管理員就必須發佈 **廠商共同作業** 行動工作區。 如需說明，請參閱[發佈行動工作區](../../fin-ops-core/dev-itpro/mobile-apps/publish-mobile-workspace.md)。

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-for-operations-version-1611-with-platform-update-3-or-later"></a>如果您使用具有平台更新 3 或更新版本的 Microsoft Dynamics 365 for Operations 版本 1611 時的先決條件
如果已為您的組織部署了具有平台更新 3 或更新版本的 Microsoft Dynamics 365 for Operations 版本 1611，則系統管理員必須完成以下先決條件。 

<table>
<thead>
<tr class="header">
<th>先決條件</th>
<th>角色</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>如果您&#39;正在使用平台更新 3，則必須執行 KB 3216943。</td>
<td>系統管理員</td>
<td>KB 3216943 是您&#39;使用平台更新 3 時必需的二進位更新。 若要執行此 KB，系統管理員必須遵循以下步驟。
<ol>
<li>從 Microsoft Dynamics Lifecycle Services (LCS) 下載 KB 3216943。</li>
<li>安裝交貨為可部署套件的二進位更新。 有關如何套用可部署套件的資訊，請參閱<a href="/dynamics365/fin-ops-core/dev-itpro/deployment/apply-deployable-package-system">套用可部署套件</a>。</li>
</ol></td>
</tr>
<tr class="even">
<td>必須執行 KB 4013633。</td>
<td>系統管理員</td>
<td>KB 4013633 是 X++ 更新或中繼資料 Hotfix，其中包含<strong>現有庫存</strong>行動工作區。 若要實作 KB 4013633，您的系統管理員必須遵循以下步驟。
<ol>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/download-hotfix-lcs">從 LCS 下載中繼資料 Hotfix</a>。</li>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/install-metadata-hotfix-package">安裝中繼資料 Hotfix</a>。</li><li><a href="/dynamics365/fin-ops-core/dev-itpro/deployment/create-apply-deployable-package">建立包含 <strong>SCMMobile</strong> 模型的可部署封裝</a>，然後將可部署封裝上傳到 LCS。</li>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/deployment/apply-deployable-package-system">套用可部署封裝</a>。</li>
</ol></td>
</tr>
<tr class="odd">
<td>必須發佈<strong>廠商共同作業</strong>行動工作區。</td><td>系統管理員</td>
<td>請參閱<a href="/dynamics365/fin-ops-core/dev-itpro/mobile-apps/publish-mobile-workspace">發佈行動工作區</a>。</td>
</tr>
<tr class="even">
<td>廠商使用者必須有權存取 Web 用戶端中的廠商共同作業 Web 介面，和設定廠商共同作業使用者。</td><td>採購專業人員和系統管理員</td>
<td>按照以下主題中的步驟設定和使用廠商共同作業 Web 介面。
<ul>
<li><a href="vendor-collaboration-work-external-vendors.md">使用廠商共同作業與外部廠商合作</a></li>
<li><a href="manage-vendor-collaboration-users.md">管理廠商共同作業使用者</a></li>
<li><a href="set-up-maintain-vendor-collaboration.md">設定與維護廠商共同合作</a></li>
<li><a href="vendor-collaboration-work-customers-dynamics-365-operations.md">在 Supply Chain Management 中使用廠商共同作業與客戶合作</a></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-mobile-app"></a>下載並安裝行動裝置應用程序

下載並安裝「財務和營運」移動應用程式：

-   [如果是 Android 手機](https://go.microsoft.com/fwlink/?linkid=850662)
-   [如果是 iPhones](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a>登入行動裝置應用程式
1.  在您的行動裝置上啟動應用程式。
2.  輸入您的 Microsoft Dynamics 365 URL。
4.  第一次登入時，系統會提示您輸入使用者名稱和密碼。 輸入您的認證。
5.  登入後，將顯示公司的可用工作區。 請注意，如果您的系統管理員稍後發佈新工作區，您將必須重新整理行動工作區清單。

    [![拖動以重新整理。](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)

## <a name="use-the-vendor-collaboration-mobile-workspace"></a>使用廠商共同作業行動工作區
當您選擇 **廠商共同作業** 工作區時，將看到以下選項。

![廠商共同作業行動工作區。](./media/vendor-collaboration-mobile-app.png)

**廠商共同作業** 工作區包括以下頁面。

### <a name="contacts"></a>連絡人
**連絡人** 頁面可讓您查看已為廠商帳戶設定的所有連絡人。 其會顯示連絡人的姓名、主要電子郵件地址和使用者別名 (如果連絡人有別名)。 此頁面還會顯示連絡人的使用者帳戶是否處於使用中狀態。 當您選擇連絡人時，將看到連絡人詳細資訊，例如此人為其連絡人的法律實體。 您還會看到連絡資訊，例如電話號碼或備用電子郵件地址。

### <a name="user-requests"></a>使用者要求
**使用者要求** 頁面可查看您透過廠商共同作業 Web 介面提交的所有使用者要求。 您還可以追蹤這些要求的狀態。 當您選擇使用者要求時，可以查看要求的內容、新增或停用使用者、變更安全性以及查看為使用者要求註冊了哪些資訊安全角色。

### <a name="purchase-orders-ready-for-review"></a>準備就緒可供審核的訂購單
**準備就緒可供審核的訂購單** 頁面可讓您查看客戶已傳送但尚未回應的所有訂購單。 您可以查看有關訂單的所選資訊，例如要求了哪些產品以及應該何時交貨。 根據廠商的設定決定是否顯示價格資訊。

您還可以查看訂購單是否有附註或附件。 但是，要打開附註和附件，您必須使用 Web 用戶端中的廠商共同作業 Web 介面。 選擇 **訂購單行** 查看所有行及其詳細資料。 對於每一行，將有一個指示器顯示是否有附註或附件，或者收貨地址是否與標題上顯示的收貨地址不同。

若要回應訂購單，必須使用 Web 用戶端中的廠商共同作業 Web 介面。

### <a name="awaiting-customer-action"></a>等待客戶動作
**等待客戶動作** 頁面可尋找您或您公司中有權存取廠商共同作業的其他人已回應的訂購單。 僅當客戶必須對訂購單執行以下動作之一時，訂購單才會顯示在此清單中：

-   如果已拒絕了訂購單，客戶必須更新或取消原始訂單，然後重新傳送。 重新傳送訂購單後，其不再顯示在 **等待客戶動作** 頁面上。
-   如果接受了包含變更的訂購單，客戶必須更新原始訂單，然後重新傳送以供審核，或者根據要求的變更更新訂單，然後立即確認。 在這兩種情況下，訂購單都不再顯示在 **等待客戶動作** 頁面上。
-   如果訂購單已被接受但仍顯示在 **等待客戶動作** 頁面，則在接受訂購單時並未自動確認訂購單。 其現在正在等待採購專員將訂單狀態變更為 **已確認**。 一旦廠商接受了訂單，通常訂購單就被視為客戶與廠商之間的協議。 因此，更新為 **已確認** 狀態通常只是一種形式。

選擇訂購單後，將顯示有關回應的其他詳細資料。 您可以查看每一行的行詳細資料和回應。 行狀態顯示已提供以下回應中的哪些回應：

-   已接受
-   已拒絕
-   已接受變更
-   已替代/替代
-   拆分為計劃/計劃行

請注意，**交貨** 欄位設定為 **是** 或 **否** 以指示行是否要完全交貨。 行可能由於以下原因而無法交貨：

- 行遭到拒絕。
- 已進行替換，且預計原始行不會按照已接收訂單中的要求交貨。
- 行拆分為多個計劃行，且預計原始行不會按照已接收訂單中的要求交貨。

顯示已對訂單行回應所做的任何變更。 但是，不會顯示已上傳的附註和附件。 若要查看附註和附件，必須使用 Web 用戶端中的廠商共同作業 Web 介面。

### <a name="open-confirmed-orders"></a>未結已確認訂單
當客戶確認了訂購單後 (即訂購單的狀態變更為 **已確認**)，它將顯示在未結已確認訂單中。 其將保留在清單中，直到客戶登記為已收貨。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]