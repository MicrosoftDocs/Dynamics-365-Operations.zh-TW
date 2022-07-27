---
title: 行動裝置應用程式首頁
description: 本主題介紹財務和營運應用程式(Dynamics 365) 行動裝置應用程式，並提供可幫助您在組織中實作它的資源連結。
author: ChrisGarty
ms.date: 01/22/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.custom: intro-internal
ms.assetid: c99f818f-27b3-4e45-92b4-74272dad0e17
ms.search.region: Global
ms.author: cgarty
ms.dyn365.ops.version: Platform update 4
ms.search.validFrom: 2017-02-28
ms.openlocfilehash: 8a91f603b4dd058341110c59039a6d3c782e06ee768fbf0e7f94e9527a6354ba
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460334"
---
# <a name="mobile-app-home-page"></a>行動裝置應用程式首頁

[!include [banner](../includes/banner.md)]

本主題介紹 **財務和營運應用程式(Dynamics 365)** 行動裝置應用程式，並提供可幫助您在組織中實作它的資源連結。

## <a name="overview"></a>概觀

行動裝置應用程式使您的組織能夠在行動裝置上提供其業務流程。 在您的 IT 管理員為您的組織啟用行動工作區後，使用者可以登入應用程式並立即開始從他們的行動裝置執行業務流程。 該行動裝置應用程式包括以下有助於提高生產力的功能：

- 使用者可以查看、編輯和處理業務資料，即使他們有斷斷續續的網路連線或他們的行動裝置完全離線。 當裝置重新建立網路連線時，離線資料動作會自動同步。
- IT 管理員或開發人員可以構建和發佈為其組織客製化的行動工作區。 該應用程式使用您現有的代碼資產。 因此，您不必重新實現驗證過程、業務邏輯或安全設定。
- IT 管理員或開發人員可以使用網路客戶端附帶的點選式工作區設計工具輕鬆設計行動工作區。
- IT 管理員或開發人員可以選取使用業務邏輯可擴展性架構最佳化工作區的離線功能。 由於裝置離線時資料會繼續處理，因此即使裝置沒有持續的網路連線，您的行動場景也會保持豐富和流暢。

## <a name="elements-of-the-mobile-app"></a>行動裝置應用程式的元素
行動裝置應用程式中的導覽包含四個基本概念：儀表板、工作區、頁面和動作。 

[![行動裝置應用程式中的導覽概念。](./media/mobilephoneapp1-1024x536.png)](./media/mobilephoneapp1.png)

1. 當您啟動應用程式時，您會進入 **儀表板**。
2. 在儀表板上，您可以看到已發佈的 **工作區** 清單。
3. 在每個工作區中，您可以看到該工作區可用的 **頁面** 清單。
4. 進入頁面後，您可以執行多項動作。 這裡有些範例：

    - 檢視詳細資料。
    - 導覽到其他頁面以取得相關資料，例如實體詳情或明細。
    - 查看可用於該頁面的 **動作** 清單。 動作允許您建立或編輯現有資料。

## <a name="implementation-process"></a>實作流程
下圖顯示了實作 Microsoft 提供的行動工作區和自訂行動工作區的過程。 

[![行動裝置應用程式實作過程。](./media/Mobile-implementation-process-5.png)](./media/Mobile-implementation-process-5.png)

下表包含指向可幫助您實作 Microsoft 提供的行動工作區和自訂行動工作區的資源的連結。 第一欄中的數字對應於上圖中的編號步驟。

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th>步驟</th>
<th>角色</th>
<th>動作</th>
<th>幫助您完成動作的資源</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>1</td>
<td>系統管理員</td>
<td>在您的組織中實作財務和營運應用程式。</td>
<td><ul><li>如果您尚未部署 Microsoft Dynamics 365 版本，請參閱<a href="../deployment/deploy-demo-environment.md">部署示範環境</a>。</li><li>若要查看可以使用的行動工作區清單，請參閱<a href="mobile-workspaces-released.md">最近發佈的行動工作區</a>。</li></ul></td>
</tr>
<tr class="even">
<td>2</td>
<td>系統管理員</td>
<td><strong>如果您使用 Microsoft Dynamics 365 for Operations 版本 1611：</strong>下載並安裝支援 Microsoft 提供的行動工作區的 KB。</td>
<td>如需相關資訊，請參閱以下主題：
<ul>

<li><a href="../../../finance/cost-accounting/cost-controlling-mobile-workspace.md">成本控制行動工作區</a></li>
<li><a href="../../../supply-chain/inventory/inventory-on-hand-mobile-workspace.md">現有庫存行動工作區</a></li>
<li><a href="../../../supply-chain/sales-marketing/sales-orders-mobile-workspace.md">銷售訂單行動工作區</a></li>
<li><a href="../../../supply-chain/procurement/vendor-collaboration-mobile-workspace.md">廠商共同作業行動工作區</a></li>
<li><a href="/dynamics365/project-operations/prod-pma/project-time-entry-mobile-workspace">專案時間分錄行動工作區</a></li>
<li><a href="/dynamics365/project-operations/prod-exp/expense-management-mobile-workspace">費用管理行動工作區</a></li>

</ul></td>
</tr>
<tr class="odd">
<td>3</td>
<td>系統管理員</td>
<td>發佈 Microsoft 提供的行動工作區。</td>
<td><a href="publish-mobile-workspace.md">發佈行動工作區</a>
</td>
</tr>
<tr class="even">
<td>4</td>
<td>開發人員或獨立軟體廠商 (ISV)</td>
<td>使用行動裝置平台建立自訂行動工作區。</td>
<td><a href="platform/mobile-platform-home-page.md">行動平台</a></td>
</tr>
<tr class="odd">
<td>5</td>
<td>ISV</td>
<td>建立包含自訂行動工作區的可部署套件，並將包上傳到 Microsoft Dynamics Lifecycle Services (LCS)。</td>
<td><a href="../deployment/create-apply-deployable-package.md">建立可部屬的套件</a></td>
</tr>
<tr class="even">
<td>6</td>
<td>系統管理員</td>
<td>應用包含由獨立軟體廠商 (ISV) 提供的自訂工作區的可部署套件。</td>
<td><a href="../deployment/apply-deployable-package-system.md">套用可部署套件</a></td>
</tr>
<tr class="odd">
<td>7</td>
<td>系統管理員</td>
<td>發佈 ISV 提供的自訂行動工作區。</td>
<td><a href="publish-mobile-workspace.md">發佈行動工作區</a></td>
</tr>
<tr class="even">
<td>8</td>
<td>使用者</td>
<td>下載並安裝行動裝置應用程式。</td>
<td>
<a href="https://go.microsoft.com/fwlink/?linkid=850662">財務和營運應用程式Android 應用程式</a><BR/>
<a href="https://go.microsoft.com/fwlink/?linkid=850663">財務和營運應用程式iOS 應用程式</a><BR/>
(不支援 Windows Phone)
</td>
</tr>
<tr class="odd">
<td>9</td>
<td>使用者</td>
<td>登入並使用行動裝置應用程式。 該應用程式包括系統管理員已發佈的行動工作區。</td>
<td>若要查看 Microsoft 提供的行動工作區清單，請參閱<a href="mobile-workspaces-released.md">最近發佈的行動工作區</a>。
</td>
</tr>
</tbody>
</table>

## <a name="troubleshooting"></a>疑難排解
[行動平台資源](platform/mobile-platform-home-page.md#troubleshooting-the-app)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]