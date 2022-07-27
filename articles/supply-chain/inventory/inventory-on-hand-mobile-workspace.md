---
title: 現有庫存行動工作區
description: 本主題提供現有庫存行動工作區的資訊。 此工作區可幫助您隨時隨地取得對預留和可用庫存的行動深入解析。
author: yufeihuang
ms.date: 12/01/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: 267094
ms.assetid: 3fa385ba-894d-4a9e-b394-ef3697abf895
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: yufeihuang
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 9e67e16acc8ed72d571e9010131723038c8586a9
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448668"
---
# <a name="inventory-on-hand-mobile-workspace"></a>現有庫存行動工作區

[!include [banner](../includes/banner.md)]

本主題提供 **現有庫存** 行動工作區的資訊。 此工作區可幫助您隨時隨地取得對預留和可用庫存的深入解析。

此行動工作區旨在與「財務和營運」行動應用程式一起使用。

## <a name="overview"></a>概觀
通常，公司每天都會有多次庫存的裝運和收貨。 這些變動會不斷改變現有庫存狀況。 **現有庫存** 行動工作區可讓您查看跨公司的現有庫存狀態，以便您在選擇的行動裝置上取得對庫存資料的最新深入解析。 無論您是在倉庫、採購、銷售、製造或管理部門作業，還是擔任其他角色，您都可以隨時隨地存取現有庫存資料。 

行動工作區提供了跨設施的現有狀態即時檢視。 它讓您可以檢視跨設施的現有庫存、目前材料保留，和未預留的現有庫存。 您還可以輸入品項編號來查詢現有庫存，並且可以對現有產品或變體進行篩選搜索。 

具體來說，行動工作區提供以下功能：

-   您可以按產品編號或產品名稱搜索來查找產品，以檢視其現有庫存狀態。
-   對於選定的產品，您可以檢視以下資訊：

    -   每個站點的現有庫存
    -   每個倉庫的現有庫存
    -   每個位置的現有庫存
    -   每批次的現有庫存 (針對批次控制的產品)
    -   每個庫存狀態的現有庫存
    
-   產品現有庫存透過以下方式顯示：

    -   按實物庫存 (此檢視表示總量。)
    -   按實物保留 (此檢視表示保留量。)
    -   按可用實物 (此檢視表示沒有保留的可用數量。)

## <a name="prerequisites"></a>先決條件
根據您組織部署的 Supply Chain Management 版本，先決條件會有所不同。

### <a name="prerequisites-if-you-use-supply-chain-management"></a>使用 Supply Chain Management 時的先決條件
如果您的組織已部署 Supply Chain Management，系統管理員就必須發佈 **現有庫存** 行動工作區。 如需說明，請參閱[發佈行動工作區](../../fin-ops-core/dev-itpro/mobile-apps/publish-mobile-workspace.md)。

### <a name="prerequisites-if-you-use-platform-update-3-or-later"></a>如果您使用平台更新 3 或更高版本時的先決條件 
如果已為您的組織部署了平台更新 3 或更高版本，則系統管理員必須完成以下先決條件。 

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

<td>KB 4013633 是 X++ 更新或中繼資料 Hotfix，其中包含<strong>現有庫存</strong>行動工作區。 若要實作 KB 4013633，您的系統管理員必須遵循以下步驟。
<ol>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/download-hotfix-lcs">從 Microsoft Dynamics Lifecycle Services (LCS) 下載中繼資料 Hotfix</a>。</li>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/install-metadata-hotfix-package">安裝中繼資料 Hotfix</a>。</li>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/deployment/create-apply-deployable-package">建立包含 <strong>SCMMobile</strong> 模型的可部署封裝</a>，然後將可部署封裝上傳到 LCS。</li>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/deployment/apply-deployable-package-system">套用可部署封裝</a>。</li>

</ol></td>
</tr>
<tr class="even">
<td>發佈<strong>現有庫存</strong>行動工作區。</td>
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
4.  登入後，將顯示公司的可用工作區。 請注意，如果您的系統管理員稍後發佈新工作區，您將必須重新整理行動工作區清單。

    [![拖動以重新整理。](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)

## <a name="view-the-on-hand-inventory-for-a-product-by-using-the-inventory-on-hand-mobile-workspace"></a>使用現有庫存行動工作區檢視產品的現有庫存

1.  在您的行動裝置上，選擇 **現有庫存** 工作區。

2.  選擇 **檢查現有的項目**。 您會看到載入到您的應用程式以供離線使用的產品清單。 預設情況下會載入 50 個品項，但開發人員可以變更此數量。 如需詳細資訊，開發人員應查看[行動平台](../../fin-ops-core/dev-itpro/mobile-apps/platform/mobile-platform-home-page.md)。
3.  如果您的品項不在清單中，請選擇 **搜尋更多**。 按產品編號搜尋，或切換到按產品名稱搜尋。

4.  選擇產品。 如果品項有影像，則顯示影像。
5.  選擇以下選項之一以檢視現有庫存狀態：

    -   檢視每個站點的現有
    -   檢視每個倉庫的現有
    -   檢視每個位置的現有
    -   檢視每批次的現有 (針對批次控制的產品)
    -   檢視每個庫存狀態的現有

    產品現有庫存透過以下方式顯示：
    -   按實物庫存 (此檢視表示總量。)
    -   按實物保留 (此檢視表示保留量。)
    -   按可用實物 (此檢視表示沒有保留的可用數量。)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]