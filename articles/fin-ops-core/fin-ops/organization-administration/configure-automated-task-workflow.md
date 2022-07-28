---
title: 在工作流程中設定自動工作
description: 本主題說明了如何為自動化工作設定屬性。
author: ChrisGarty
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 192061
ms.assetid: c0aceb57-b5e6-4ef3-91e7-89a21c9f048a
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c7346649108824eb4e7209a2476456a469affa1c
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8460358"
---
# <a name="configure-automated-tasks-in-a-workflow"></a>在工作流程中設定自動工作

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

本主題說明了如何為自動化工作設定屬性。

若要在工作流程編輯器中設定自動工作，請按右鍵點選工作，然後點選 **屬性** 以打開 **屬性** 頁面。 然後使用以下程序為自動化工作設定屬性。

## <a name="name-the-task"></a>命名該工作

按照以下步驟輸入自動化工作的名稱。

1. 在左側窗格中，點選 **基本設定**。
2. 在 **名稱** 欄位中，輸入工作的唯一名稱。

## <a name="specify-when-notifications-are-sent"></a>指定何時發送通知

您可以在執行或取消自動化工作時向人們發送通知。 請按照以下步驟指定何時發送通知以及發送給誰。

1. 在左側窗格中，點選 **通知**。
2. 選取要發送通知的事件旁邊的核取方塊：

    - **執行** – 執行工作時發送通知。
    - **取消** – 工作取消時發送通知。

3. 選取您在步驟 2 中選取的事件所在的行。
4. 在 **通知文字** 索引標籤，在文字方塊中，輸入通知的文字。
5. 若要個人化通知，您可以插入預留位置。 當向使用者顯示通知時，將預留位置替換為適當的資料。 按照以下步驟插入預留位置：

    1. 在文字方塊中，點選應出現預留位置的位置。
    2. 點選 **插入預留位置**。
    3. 在出現的清單中，選取要插入的預留位置。
    4. 點選 **插入**。

6. 若要新增通知的翻譯，請執行以下步驟：

    1. 點選 **翻譯**。
    2. 在出現的頁面上，點選 **新增**。
    3. 在出現的清單中，選取您輸入文字時使用的語言。
    4. 在 **翻譯的文字** 欄位中，輸入文字。
    5. 若要個人化文字，您可以按照步驟 5 中的說明插入預留位置。
    6. 點選 **關閉**。

7. 在 **收件者** 索引標籤，指定通知發送給誰。 選擇下表中的選項之一，然後按照該選項的附加步驟進行操作，然後轉到步驟 8。

    <table>
    <thead>
    <tr>
    <th>選項</th>
    <th>通知收件者</th>
    <th>附加步驟</th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td>參與者</td>
    <td>指派給特定組或角色的使用者</td>
    <td>
    <ol>
    <li>選擇<strong>參與者</strong>後，在<strong>基於角色</strong>索引標籤上，在<strong>參與者類型</strong>清單中，選擇要發送通知的組或角色的類型。</li>
    <li>在<strong>參與者</strong>清單中，選取要向其發送通知的組或角色。</li>
    </ol>
    </td>
    </tr>
    <tr>
    <td>工作流程使用者</td>
    <td>參與現行工作流程的使用者</td>
    <td>
    <ul>
    <li>選取<strong>工作流程使用者</strong>後，在<strong>工作流程使用者</strong>索引標籤上，在<strong>工作流程使用者</strong>清單中，選取參與工作流程的使用者。</li>
    </ul>
    </td>
    </tr>
    <tr>
    <td>使用者</td>
    <td>特定使用者</td>
    <td>
    <ol>
    <li>選取<strong>使用者</strong>後，點選<strong>使用者</strong>索引標籤。</li>
    <li><strong>可用使用者</strong>清單包括所有使用者。 選擇要發送通知的使用者，然後將這些使用者移動到<strong>選定的使用者</strong>清單。</li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

8. 對您在步驟 2 中選取的每個事件重複步驟 3 到 7。


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]