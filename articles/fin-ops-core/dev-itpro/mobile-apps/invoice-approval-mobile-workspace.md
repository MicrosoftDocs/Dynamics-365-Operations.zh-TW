---
title: 發票核准行動工作區
description: 本主題提供有關發票核准行動工作區的資訊。
author: abruer
ms.date: 12/01/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 0d19e99776f04eab28eb7371bc0ac90ac046b62af0ad785fd3ab28309cae43ab
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460332"
---
# <a name="invoice-approvals-mobile-workspace"></a>發票核准行動工作區

[!include [banner](../includes/banner.md)]

本主題提供有關 **發票核准** 行動工作區的資訊。 此工作區提供已透過廠商發票抬頭工作流程指派給您的發票清單。 

此行動工作區旨在與「財務和營運」行動應用程式一起使用。

## <a name="overview"></a>概觀

**發票核准** 行動工作區允許應付帳款文員和經理查看已指派給他們的發票，作為廠商發票抬頭工作流程的一部分。 您可以查看發票資訊，甚至是明細和指派詳情，以幫助您做出明智的核准決策。 在工作區中，您可以採取措施在工作流程中移動發票。 

## <a name="prerequisites"></a>先決條件

在您可以使用此行動工作空間之前，必須滿足以下先決條件。

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
<td>Microsoft Dynamics 365 Finance 必須部署在您的組織中。</td>
<td>系統管理員</td>
<td>請參閱<a href="../deployment/deploy-demo-environment.md">部署示範環境</a>。
</td>
</tr>
<tr class="even">
<td>必須發佈<strong>發票核准</strong>行動工作區。</td>
<td>系統管理員</td>
<td>請參閱<a href="publish-mobile-workspace.md">發佈行動工作區</a>。</td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-mobile-app"></a>下載並安裝行動裝置應用程式

下載並安裝「財務和營運」移動應用程式：

-   [如果是 Android 手機](https://go.microsoft.com/fwlink/?linkid=850662)
-   [如果是 iPhones](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a>登入行動裝置應用程式

1.  在您的行動裝置上啟動應用程式。
2.  輸入您的 Microsoft Dynamics 365 URL。
3.  第一次登入時，系統會提示您輸入使用者名稱和密碼。 輸入您的認證。
4.  登入後，將顯示公司的可用工作區。 請注意，如果您的系統管理員稍後發佈新工作區，您將必須重新整理行動工作區清單。

    [![拖動以重新整理。](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)

## <a name="approve-invoices-by-using-the-invoice-approvals-mobile-workspace"></a>使用發票核准行動工作區核准發票
1.  在您的行動裝置上，選取 **發票核准** 工作區。
2.  選取已由廠商發票抬頭工作流程指派給您的發票。
3.  在 **發票明細** 頁面，查看發票抬頭資訊，例如廠商和日期資訊。
4.  選取發票上的一行以在 **發票明細詳情** 檢視表中查看有關它的更多詳情。
5.  在 **發票明細詳情** 檢視表，選取 **分佈** 顯示明細分佈。 在這裡，您可以查看發票明細的會計。 顯示的資訊包括財務維度和主科目。
6.  在 **發票詳情** 頁面，選取 **分佈** 顯示所有分佈。 在這裡，您可以查看整個發票的會計。 顯示的資訊包括財務維度和主科目。 
7.  選取 **附件** 查看附在發票上的任何附註或檔案。
8.  在 **發票明細** 頁面，選取適當的工作流程動作以完成您的審核過程。
9.  選取 **完成**。


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]