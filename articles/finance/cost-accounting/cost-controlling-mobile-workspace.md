---
title: 成本控制行動工作區
description: 本主題提供成本控制行動工作區的資訊。 此工作區讓成本中心經理可以隨時隨地查看有關成本中心績效的資訊。
author: AndersGirke
ms.date: 12/01/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CAMMobileCostObjectOverviewDetailsCurrentPeriod, CAMMobileCostObjectList, CAMMobileCostObjectOverviewDetailsPreviousPeriod, CAMMobileCostObjectOverview, CAMMobileCostObjectOverviewDetailsYearToDate, CAMMobileCostControlWorkspaceConfiguration
audience: Application User
ms.reviewer: roschlom
ms.custom: 267114
ms.assetid: 612f2988-b2b9-420d-9825-40b99dc0e204
ms.search.region: global
ms.author: aevengir
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: cd86fdf640e59885e5e8aea841dc1c1c9604825b0f18d3b741c5a2777f8e9ff8
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450288"
---
# <a name="cost-controlling-mobile-workspace"></a>成本控制行動工作區

[!include [banner](../includes/banner.md)]

本主題提供 **成本控制** 行動工作區的資訊。 此工作區讓成本中心經理可以隨時隨地查看有關成本中心績效的資訊。

此行動工作區旨在與財務和營運行動應用程式一起使用。

## <a name="overview"></a>概觀
**成本控制** 行動工作區透過比較實際成本與預算成本，提供成本中心目前績效的即時檢視表。 您可以深入了解各個成本元素的狀態。

例如，員工收到參加國際會議的邀請，但組織必須承擔所有差旅費用。 員工詢問他們的經理是否可以參加會議。 管理員打開行動裝置上的 **成本控制** 行動工作區，以查看是否有讓員工參加會議的預算。

### <a name="data-security"></a>資料安全性
**成本控制** 行動工作區中的資料透過使用者認證加以保護。 成本中心經理只能查看自己成本中心的資料。 存取等級的安全性在 **成本會計** 模組內管理。

成本會計師定義 **成本會計** 模組中的 **成本控制** 行動工作區設定。 工作區發佈到行動應用程式後，即可在應用程式中使用。 因此，組織中的所有成本中心經理都可以查看相同格式的資料。

### <a name="actions-views-and-links"></a>動作、檢視表和連結
**成本控制** 行動工作區提供以下動作、檢視表和連結：

-   **動作：**

    -   使用 **選擇設定** 選擇配置。
    -   使用 **選擇成本物件** 選擇要篩選資料的成本中心。
    
        > [!NOTE]
        > 清單中顯示的成本中心取決於在 **成本會計** 模組中授予的h存取權限。

-   **檢視：** 基於選擇的動作和 **成本會計** 模組中的設定，您可以查看卡片上的以下資訊：

    -   實際值與預算 (目前期間)
    -   實際值與已修訂的預算 (目前期間)
    -   實際值與預算 (上一個期間)
    -   實際值與已修訂的預算 (上一個期間)
    -   實際值與預算 (年初至今)
    -   實際值與已修訂的預算 (年初至今)

    每張卡片上都會顯示以下金額：實際值、預算、差異和差異百分比。

-   **連結：**

    -   目前期間的詳細資料
    -   上一個期間的詳細資料
    -   年初至今的詳細資料

    選擇連結時，會為每個成本元素顯示卡片。 每張卡片上顯示以下金額：實際值、預算、預算差異、預算差異百分比、已修訂的預算、已修訂的預算差異和已修訂的預算差異百分比。
    
    [![成本元素卡片。](./media/Cost-controlling.png)](./media/Cost-controlling.png)

## <a name="prerequisites"></a>先決條件
先決條件會根據為您組織部署的 Microsoft Dynamics 365 版本而異。

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-finance"></a>使用 Microsoft Dynamics 365 Finance 的先決條件
如果已為您的組織部署 Finance，則系統管理員必須發佈 **成本控制** 行動工作區。 如需說明，請參閱[發佈行動工作區](../../fin-ops-core/dev-itpro/mobile-apps/publish-mobile-workspace.md)。

### <a name="prerequisites-if-you-use-version-1611-with-platform-update-3-or-later"></a>使用具有平台更新 3 或更新版本的版本 1611 時的先決條件
如果已為您的組織部署了具有平台更新 3 或更新版本的版本 1611，則系統管理員必須完成以下先決條件。

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
<td>執行 KB 4013633。</td>
<td>系統管理員</td>

<td>KB 4013633 是 X++ 更新或中繼資料 Hotfix，其中包含<strong>成本控制</strong>行動工作區。 若要執行 KB 4013633，您的系統管理員必須遵循以下步驟。
<ol>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/download-hotfix-lcs">從 Microsoft Dynamics Lifecycle Services (LCS) 下載中繼資料 Hotfix</a>。</li>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/install-metadata-hotfix-package">安裝中繼資料 Hotfix</a>。</li>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/deployment/create-apply-deployable-package">建立包含 <strong>SCMMobile</strong> 模型的可部署封裝</a>，然後將可部署封裝上傳到 LCS。</li>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/deployment/apply-deployable-package-system">套用可部署封裝</a>。</li>

</ol></td>
</tr>
<tr class="even">
<td>發佈<strong>成本控制</strong>行動工作區。</td>
<td>系統管理員</td>
<td>請參閱<a href="/dynamics365/fin-ops-core/dev-itpro/mobile-apps/publish-mobile-workspace">發佈行動工作區</a>。</td>
</tr>
</tbody>
</table>


## <a name="download-and-install-the-mobile-app"></a>下載並安裝行動應用程式
下載並安裝財務和營運行動應用程式：

-   [如果是 Android 手機](https://go.microsoft.com/fwlink/?linkid=850662)
-   [如果是 iPhones](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a>登入行動應用程式

1.  在您的行動裝置上啟動應用程式。
2.  輸入您的 Dynamics 365 URL。
3.  第一次登入時，系統會提示您輸入使用者名稱和密碼。 輸入您的認證。
4.  登入後，將顯示公司的可用工作區。 請注意，如果您的系統管理員稍後發佈新工作區，您將必須重新整理行動工作區清單。

[![拖動以重新整理。](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)

## <a name="view-the-performance-of-your-cost-center-by-using-the-cost-controlling-mobile-workspace"></a>使用成本控制行動工作區查看成本中心的績效

1.  在您的行動裝置上，選擇 **成本控制** 工作區。
2.  選取 **成本物件控制**。
3.  選取 **動作**。
4.  選取 **選擇設定** 以選擇成本控制配置。
5.  選取 **完成**。
6.  選取 **動作**。
7.  選取 **選擇成本物件** 以選擇您有權存取的成本中心。
8.  選取 **完成**。
9.  查看成本中心的整體績效。
10. 選擇 **目前期間詳細資料** 連結。
11. 查看個別成本元素的績效。
12. 您還可以搜尋特定的成本元素。



[!INCLUDE[footer-include](../../includes/footer-banner.md)]