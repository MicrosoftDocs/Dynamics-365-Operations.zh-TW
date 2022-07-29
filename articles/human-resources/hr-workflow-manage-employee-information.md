---
title: 使用工作流程管理員工資訊
description: 本主題說明您如何使用工作流程管理員工資訊。
author: twheeloc
ms.date: 11/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 269074
ms.assetid: 426c6127-42ee-4163-8dd0-b2867f95581d
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: d80ed49a4f423179997ac35562284a4e28af803f
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452412"
---
# <a name="use-workflows-to-manage-employee-information"></a>使用工作流程管理員工資訊


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

本主題說明您如何使用人力資源工作流程功能管理員工資訊。 例如，您可以產生工作流程與職位的關聯性，並且配置員工更改記錄時，啟動的核准工作流程。

人力資源工作流程功能提供許多用來管理人力資源活動的工作流程。 此外，也開放許多選項讓您修改特定的工作流程，並產生它們與報表階層結構的關聯。 開放工作流程幫助管理對幾種員工資訊類型的更改。 您可以產生工作流程與職位的關聯。 接著，如果員工更改他們的員工記錄，會啟動要求儲存新資訊之前先取得核准的工作流程。 工作流程會針對下列類型的資訊預先定義，以便幫助您有效地管理更改並保持員工資料的精確度：

-   身份證號碼
-   課程
-   學歷
-   影像
-   已借項目
-   專業經驗
-   專案經驗
-   技能
-   受到信任的職位
-   人力資源動作
-   課程註冊

當員工被雇用、調動或終止時，工作流程會包括審查流程。 文件可利用這個方式修訂，或者動作條款可定義為工作流程的一部分。 完成審核流程後，文件或動作即宣告完成，工作流程遂移往最終核准步驟。

## <a name="associate-a-workflow-with-a-position-hierarchy"></a>產生工作流程與職位階層結構的關聯
您可以在工作流程與您配置的任何階層結構之間產生關聯性。 例如，如果某個職位與矩陣報表階層結構有關聯，您可以配置工作流程，將特定專案開銷路由到專案負責人，而不是與該職位有關聯的員工的經理。 若要建立新工作流程或修改既有的工作流程，請在 **人力資源工作流程** 頁面，選取 **新增**。 在清單選取工作流程打開工作流程設計工具。 您可以使用設計工具建立新工作流或更改既有工作流程的步驟。 當您更改既有的工作流程時，您的更改會儲存為新版本。 因此，必要時您始終可以返回前版本。

## <a name="configure-a-human-resources-workflow"></a>配置人力資源工作流程
若要配置員工要求個人身份更改時啟動的基本工作流程，請按照下列步驟。

1.  請在 **人力資源工作流程** 頁面，選取 **新增**。
2.  請在開放工作流程清單中，選取 **身份證號碼**。
3.  選取 **執行** 打開工作流程設計工具，接著在出現提示時輸入您的使用者名稱和密碼。
4.  將 **核准身份證號碼** 元素從工作流程元素拖曳到設計工具畫布。
5.  連接核准元素到 **開始** 和 **完成**。
6.  點兩下 (或點選兩下) **核准元素**，選取並按住 (或點選右鍵)，然後選取 **屬性**。
7.  按照下列步驟新增工作項目指示：

    1.  選取 **指派**，然後選取指派類型下方的 **階層結構**。
    2.  請在 **階層結構** 選取項目下方，選取 **可配置的階層結構**。
    3.  新增停止條件並關閉頁面。

8.  完成任何額外指示 (不應存在額外警告)。
9.  選取 **儲存並關閉**。 對話方塊打開時啟動新工作流程，並選取 **使它生效**。
10. 請前往 **人力資源**&gt;**職位**&gt;**職位階層結構類型**。
11. 選取 **矩陣**。
12. 新增 **背景工作角色身份證號碼** 工作流程到清單。

## <a name="additional-resources"></a>其他資源

[檢視和管理地址更改](hr-personnel-view-address-changes.md) 





[!INCLUDE[footer-include](../includes/footer-banner.md)]
