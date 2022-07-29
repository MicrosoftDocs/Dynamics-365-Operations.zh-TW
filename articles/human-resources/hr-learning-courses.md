---
title: 設定訓練課程
description: 人力資源管理員和經理可使用課程功能來維護有關提供給背景工作角色的訓練資訊。
author: twheeloc
ms.date: 08/26/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmCourseType, HcmCourseTypeGroup, HRMCourseTable, HcmLearningWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7532
ms.assetid: a6950c29-8b3e-45b2-9084-ddfb1317ffaa
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: c66459a044419535d66875cddac7eb73af744ca7
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452262"
---
# <a name="set-up-training-courses"></a>設定訓練課程


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

人力資源管理員和經理可使用課程功能來維護有關提供給背景工作角色的訓練資訊。

##  <a name="set-up-prerequisites"></a>設定先決條件

下列資訊為必要資訊，必須在您建立課程之前設定。
-   **課程類型**

下列資訊為非必要資訊，您可以針對課程指定。 如果您知道您將為課程輸入這項資訊，您應該在建立課程記錄之前設定此項資訊。
-   **課堂群組**
-   **課程群組**
-   **課程地點**
-   **教室**
-   **講師**

## <a name="course-types"></a>課程類型
您可以根據課程的結構或內容，使用課程類型對課程分門別類。 您可以在 **課程類型** 頁面上建立課程類型。 建立課程記錄時，您必須選取課程類型。

## <a name="course-setup-type"></a>課程設定類型
下表列出課程的三種設定類型。 設定類型判定課程結構。

<table>
<thead>
<tr class="header">
<th>設定類型</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>標準</strong></td>
<td>未訂定每日議程的課程可選取此類型的課程。 這是您建立新課程時預設的設定類型。</td>
</tr>
<tr class="even">
<td><strong>議程</strong></td>
<td>選取此類型計劃數日課程的每一天細節。</td>
</tr>
<tr class="odd">
<td><strong>議程 + 工作階段</strong></td>
<td>為更複雜的課程選取此類型。 例如，您可以將課程議程劃分為課程單元和工作階段。
<ul>
<li><strong>課程單元</strong> – 課程單元是課程的特定主題領域。</li>
<li><strong>工作階段</strong> – 工作階段劃分課程單元，有助於辨別與課程單元相關的特定流程或技術。</li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="course-tasks"></a>課程任務
您可以針對各門課程完成下列任務。
- 註冊參與者
- 指明註冊截止日期
- 定義最少和最多參與者人數
- 指派課程地點和教室
- 向課程參與者推薦下塌的飯店
- 建立課程描述，接著您可以在 **Employee 自助服務** 上刊登廣告

  >**注意事項** 您只能在無人註冊情況下刪除課程。 

## <a name="course-statuses"></a>課程狀態
下表列出可能的課程狀態以及當課程在特定狀態時，您可以完成的動作。

<table>
<thead>
<tr class="header">
<th>狀態</th>
<th>動作</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>已建立</strong></td>
<td><ul>
<li>輸入和修改課程資訊。</li>
<li>將課程狀態更改為<strong>打開</strong>，如此一來背景工作角色即可註冊該門課程。</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>開啟</strong></td>
<td><ul>
<li>註冊課程的參與者。</li>
<li>從課程移除參與者。</li>
<li>確認課程的參與者。</li>
<li>將課程狀態更改為<strong>關閉</strong>或<strong>取消</strong>。</li>
<li>針對狀態為<strong>確認</strong>的參與者計劃問卷。</li>
</ul></td>
</tr>
<tr class="odd">
<td><strong>已結案</strong></td>
<td>您可以重新打開課程。</td>
</tr>
<tr class="even">
<td><strong>已取消</strong></td>
<td>您可以重新打開課程。</td>
</tr>
</tbody>
</table>

## <a name="course-participants"></a>課程參與者
課程參與者是參加訓練課程或活動的背景工作角色。 您只能註冊公開課程的參與者。 您可以註冊課程的最少和最多參與者人數會在 **課程** 頁面上的 **一般** FastTab 定義。

## <a name="workflow"></a>工作流程

透過 **Employee 自助服務** 頁面註冊課程的員工可以路由歷經工作流程進行註冊與核准。 您可以在 **課程** 頁面上的 **一般** FastTab 指派到課程的工作流程。







[!INCLUDE[footer-include](../includes/footer-banner.md)]
