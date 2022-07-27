---
title: 銷售訂單行動工作區
description: 本主題提供有關銷售訂單行動工作區的資訊。 此工作區可幫助您隨時隨地掌握最新的銷售訂單。
author: Mirzaab
ms.date: 12/01/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: 267134
ms.assetid: 0ce96511-002b-4de7-b31e-4303f94edc84
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mirzaab
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 712b45cf1fd35de9f823af1bf89db9c4a572d61ebf7aa3e1fded16902c09557a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447180"
---
# <a name="sales-orders-mobile-workspace"></a>銷售訂單行動工作區

[!include [banner](../includes/banner.md)]

本主題提供有關 **銷售訂單** 行動工作區的資訊。 此工作區可幫助您隨時隨地掌握最新的銷售訂單。 

此行動工作區旨在與「財務和營運」行動應用程式一起使用。

## <a name="overview"></a>概觀
**銷售訂單** 行動工作區可讓您查看有關每個銷售訂單的詳細資料。 此資訊包括訂單狀態、客戶的連絡資訊和訂單接受者的連絡資訊。 **銷售訂單** 行動工作區提供銷售訂單的即時檢視表。 您可以查看所有銷售訂單、依客戶查看銷售訂單，或查看特定銷售訂單的資訊。 

行動工作區提供兩個檢視表來幫助您深入分析銷售訂單。

### <a name="view-all-sales-orders"></a>檢視所有銷售訂單
此檢視表會列出所有銷售訂單。

-   使用以下其中一個篩選來選擇要檢視的銷售訂單：

    -   依銷售訂單搜尋
    -   依客戶帳戶搜尋
    -   依客戶名稱搜尋
    -   依狀態搜尋
    -   依下達狀態搜尋
    -   依建立日期和時間搜尋
    
-   選擇銷售訂單後，您可以檢視特定訂單的詳細資料。 特別是，您可以檢視以下資訊：

    -   客戶名稱和地址資訊
    -   銷售訂單的各種日期，例如要求出貨日期和確認出貨日期
    -   訂單接受者的連絡資訊
    -   客戶連絡資訊
    -   訂單行
    -   顯示銷售訂單的出貨方式和時間的出貨

### <a name="view-orders-for-a-customer"></a>檢視客戶的訂單
此檢視表會依客戶列出銷售訂單。

-   使用以下其中一個篩選來檢視客戶的訂單：

    -   依名稱搜尋
    -   依帳戶搜尋

-   選擇客戶後，您可以檢視以下資訊：

    -   客戶名稱和群組
    -   客戶連絡資訊
    -   客戶銷售訂單及其詳細資料：
    
        -   客戶名稱和地址資訊
        -   各種銷售訂單日期
        -   訂單接受者的連絡資訊
        -   客戶連絡資訊
        -   訂單行
        -   顯示銷售訂單的出貨方式和時間的出貨

## <a name="prerequisites"></a>先決條件
先決條件會根據為您組織部署的 Microsoft Dynamics 365 版本而異。

### <a name="prerequisites-if-you-use-supply-chain-management"></a>使用 Supply Chain Management 時的先決條件 
如果已為您的組織部署 Supply Chain Management，則系統管理員必須發佈 **銷售訂單** 行動工作區。 如需說明，請參閱[發佈行動工作區](../../fin-ops-core/dev-itpro/mobile-apps/publish-mobile-workspace.md)。

### <a name="prerequisites-if-you-use-dynamics-365-for-operations-version-1611-with-platform-update-3-or-later"></a>如果您使用具有平台更新 3 或更新版本的 Dynamics 365 for Operations 版本 1611 時的先決條件
如果已為您的組織部署了具有平台更新 3 或更新版本的 Dynamics 365 for Operations 版本 1611，則系統管理員必須完成以下先決條件。 

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
<td>實作 KB 4013633。</td>
<td>系統管理員</td>

<td>KB 4013633 是 X++ 更新或中繼資料 Hotfix，其中包含<strong>銷售訂單</strong>行動工作區。 若要實作 KB 4013633，您的系統管理員必須遵循以下步驟。
<ol>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/download-hotfix-lcs">從 Microsoft Dynamics Lifecycle Services (LCS) 下載中繼資料 Hotfix</a>。</li>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/install-metadata-hotfix-package">安裝中繼資料 Hotfix</a>。</li>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/deployment/create-apply-deployable-package">建立包含 <strong>SCMMobile</strong> 模型的可部署封裝</a>，然後將可部署封裝上傳到 LCS。</li>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/deployment/apply-deployable-package-system">套用可部署封裝</a>。</li>

</ol></td>
</tr>
<tr class="even">
<td>發佈<strong>銷售訂單</strong>行動工作區。</td>
<td>系統管理員</td>
<td>請參閱<a href="/dynamics365/fin-ops-core/dev-itpro/mobile-apps/publish-mobile-workspace">發佈行動工作區</a>。</td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-mobile-app"></a>下載並安裝行動裝置應用程序
下載並安裝「財務和營運」移動應用程式：

-   [如果是 Android 手機](https://go.microsoft.com/fwlink/?linkid=850662)
-   [如果是 iPhones](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a>登入行動裝置應用程式

1.  在您的行動裝置上啟動應用程式。
2.  輸入您的 Dynamics 365 URL。
3.  第一次登入時，系統會提示您輸入使用者名稱和密碼。 輸入您的認證。
4.  登入後，將顯示您公司的可用工作區。 請注意，如果您的系統管理員稍後發佈新工作區，您將必須重新整理行動工作區清單。

[![拖動以重新整理。](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)

## <a name="view-information-about-sales-orders-for-a-customer-by-using-the-sales-order-mobile-workspace"></a>使用此銷售訂單行動工作區檢視有關客戶銷售訂單的資訊

1.  在您的行動裝置上，選擇 **銷售訂單** 工作區。
2.  選取 **檢視客戶的訂單**。
3.  使用帳戶或客戶名稱資訊來尋找客戶。
4.  選取客戶。
5.  選取 **連絡資訊** 或 **銷售訂單**。 如果您選擇 **銷售訂單**，則會顯示客戶的銷售訂單清單。
6.  選取 **銷售訂單**。 您現在可以檢視銷售訂單行的資訊、出貨資訊、客戶連絡資訊，和訂單接受者的連絡資訊。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]