---
title: 訂購單核准行動工作區
description: 本主題提供有關訂購單核准行動工作區的資訊，可讓您查看訂購單並透過動作據此回應。 例如，您可以批准或拒絕訂購單。
author: Henrikan
ms.date: 12/01/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PurchVendorPortalRequests
audience: Application User
ms.reviewer: kamaybac
ms.custom: 30211
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: fc88f20b50e034f2f27b7e2576fe6a4bb3486e23
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448308"
---
# <a name="purchase-order-approval-mobile-workspace"></a>訂購單核准行動工作區

[!include [banner](../includes/banner.md)]

本主題提供有關 **訂購單核准** 行動工作區的資訊。 這個工作區可讓您查看訂購單，並透過動作據此回應。 例如，您可以批准或拒絕訂購單。
 
## <a name="overview"></a>概觀 
需要核准的訂購單會進行核准工作流程。 工作流程可能包含需要一或多位人員採取行動的各種步驟。 例如，一人可能必須完成一項任務或訂購單。 

**訂購單核准** 行動工作區可讓您輕鬆地從行動裝置查看及回應訂購單。 此工作區還允許您執行可以從 Web 用戶端執行的相同工作流程動作。

## <a name="prerequisites"></a>先決條件
先決條件會根據您組織部署的 Supply Chain Management 版本而異。

### <a name="prerequisites-if-you-use-supply-chain-management"></a>使用 Supply Chain Management 時的先決條件 
如果您的組織已部署 Supply Chain Management，系統管理員就必須發佈 **訂購單核准** 行動工作區。 如需說明，請參閱[發佈行動工作區](../../fin-ops-core/dev-itpro/mobile-apps/publish-mobile-workspace.md)。

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
<td>實施知識庫 KB 4017918。</td>
<td>系統管理員</td>
<td>KB 4017918 是 X++ 更新或中繼資料 Hotfix，其中包含<strong>銷售訂單</strong>行動工作區。 若要實作 KB 4017918，您的系統管理員必須遵循以下步驟。
<ol>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/download-hotfix-lcs">從 Microsoft Dynamics Lifecycle Services (LCS) 下載中繼資料 Hotfix</a>。</li>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/install-metadata-hotfix-package">安裝中繼資料 Hotfix</a>。</li>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/deployment/create-apply-deployable-package">建立包含 <strong>SCMMobile</strong> 模型的可部署封裝</a>，然後將可部署封裝上傳到 LCS。</li>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/deployment/apply-deployable-package-system">套用可部署封裝</a>。</li>
</ol></td>
</tr>
<tr class="even">
<td>發佈<strong>訂購單核准</strong>行動工作區。</td>
<td>系統管理員</td>
<td>請參閱<a href="/dynamics365/fin-ops-core/dev-itpro/mobile-apps/publish-mobile-workspace">發佈行動工作區</a>。</td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-mobile-app"></a>下載並安裝行動裝置應用程序
下載並安裝「財務和營運」移動應用程式：

- [如果是 Android 手機](https://go.microsoft.com/fwlink/?linkid=850662)
- [如果是 iPhones](https://go.microsoft.com/fwlink/?linkid=850663)


## <a name="sign-in-to-the-mobile-app"></a>登入行動裝置應用程式

1. 在您的行動裝置上啟動應用程式。
2. 輸入您的 Microsoft Dynamics 365 URL。
3. 第一次登入時，系統會提示您輸入使用者名稱和密碼。 輸入您的認證。
4. 登入後，將顯示公司的可用工作區。 請注意，如果您的系統管理員稍後發佈新工作區，您將必須重新整理行動工作區清單。

![可用工作區清單中的訂購單核准工作區。](./media/po-workspaces.png)

## <a name="view-orders-that-are-assigned-to-you"></a>查看指派給您的訂單
1. 在您的行動裝置上，選擇 **訂購單核准** 工作區。
2. 選取 **指派給我的訂購單** 以查看在採購訂單核准工作流程中，要求您採取行動的所有訂購單。
3. 選取訂單 在 **訂單詳細資料** 頁面，您會看到訂單標題資訊和明細。 您也可以從工作流程任務中找到指引。
4. 選擇 **會計分配** 以開啟 **標題會計分配** 頁面。
5. 返回 **訂單詳細資料** 頁面，然後選擇一個明細。 從訂單明細詳細資料中，您還可以探索與明細相關的會計分配。

## <a name="complete-an-action-on-the-purchase-order"></a>完成對訂購單的動作
查看指派給您的訂購單並閱讀工作流程說明後，您應該準備好採取行動了。

1. 在您的行動裝置上，選擇 **訂購單核准** 工作區。
2. 選取 **指派給我的訂購單** 以查看在採購訂單核准工作流程中，要求您採取行動的所有訂購單。
3. 選擇一個訂單，然後查看詳細資料頁面。
4. 選擇 **行動** 顯示可用的操作。 可用的操作取決於指派給您的任務。

    | 任務動作    | 核准動作  |
    |----------------|------------------|
    | 完成       | 核准          |
    | 傳回         | 拒絕           |
    | 要求變更 | 要求變更   |
    | 委派       | 委派         |

5. 選擇適當的動作。
6. 在 **完成任務** 頁面上輸入評論。 請注意，如果您選擇 **代理人** 動作，則必須選擇一個使用者來委派任務。
7. 選取 **完成**。 重新整理工作區後，訂購單將不再出現在您的列表中。 


[!INCLUDE[footer-include](../../includes/footer-banner.md)]