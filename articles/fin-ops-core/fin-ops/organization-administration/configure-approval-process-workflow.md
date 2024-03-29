---
title: 在工作流程中設定核准流程
description: 使用以下程序設定核准流程的屬性。
author: ChrisGarty
ms.date: 01/24/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 195643
ms.assetid: f853f57b-83ae-4fb0-a9fa-06ea3fc34fa1
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 99a4e131b2afa65152d8e9d41b8405895d997250
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8460283"
---
# <a name="configure-approval-processes-in-a-workflow"></a>在工作流程中設定核准流程

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

使用以下程序設定核准流程的屬性。

若要在工作流程編輯器中設定核准流程，請按右鍵點選該核准元素，然後點選 **屬性** 打開 **屬性** 頁面。

## <a name="name-the-approval-process"></a>命名核准流程

按照以下步驟輸入核准流程的名稱。

1. 在左側窗格中，點選 **基本設定**。
2. 在 **名稱** 欄位中，輸入核准流程的唯一名稱。

## <a name="specify-when-the-system-automatically-acts-on-the-document"></a>指定係統自動作用於文件的時間

您可以將系統設定為在滿足特定條件時自動處理文件。 例如，系統可以核准總金額小於 100 美元的費用報表。 按照以下步驟指定係統何時對文件進行操作。

1. 在左側窗格中，點選 **自動操作**。
2. 選取 **啟用自動操作** 核取方塊。
3. 點選 **新增條件**。
4. 輸入條件。
5. 如有必要，輸入附加條件。
6. 若要驗證您輸入的條件是否設定正確，請完成以下步驟：

    1. 點選 **測試** 即可打開 **測試工作流程條件** 表單。
    2. 在表單的 **驗證條件** 區域中選取一條記錄。
    3. 點選 **測試**。 系統評估記錄以確定它是否滿足您定義的條件。
    4. 點選 **確定** 或 **取消** 返回至 **屬性** 表單。

7. 在 **自動完成動作** 清單中，選取系統應對文件執行的操作。

## <a name="specify-when-notifications-are-sent"></a>指定何時發送通知

當文件被核准、拒絕、委派或升級，或者要求更改時，您可以向人員發送通知。 按照以下步驟指定通知的發送時間以及通知的發送對象。

1. 在左側窗格中，點選 **通知**。
2. 選取要發送通知的事件旁邊的核取方塊：

    - **委派** – 當文件已指派給其他使用者進行核准時。
    - **升級** – 當指派的使用者在指派的時間內沒有對文件進行操作時。
    - **核准** – 當檔案被核准時。
    - **拒絕** – 當檔案被核准時。
    - **要求更改** – 當指派的使用者要求更改已送出的文件時。

3. 選取您在步驟 2 中選取的事件所在的行。
4. 點選 **通知文字** 索引標籤。
5. 在文字方塊中，輸入通知的文字。
6. 若要個人化文字，您可以插入預留位置，這些預留位置在顯示給使用者時會替換為適當的資料。 若要插入預留位置，請執行以下步驟：

    1. 在應出現預留位置的位置點選文字方塊。
    2. 點選 **插入預留位置**。
    3. 在顯示的清單中，選取要插入的預留位置。
    4. 點選 **插入**。

7. 若要新增通知的翻譯，請點選 **翻譯**。 在顯示的表單中，請執行以下步驟：

    1. 選點 **新增**。
    2. 在顯示的清單中，選取輸入文字的語言。
    3. 在 **翻譯的文字** 文字方塊中，輸入文字。
    4. 若要個人化文字，請插入預留位置。
    5. 點選 **關閉**。

8. 點選 **收件者** 索引標籤。
9. 指定將通知發送給誰。 選取下表中的選項之一，然後按照該選項的附加步驟進行操作，然後前往步驟 10。

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
    <td><strong>參與者</strong></td>
    <td>指派給特定組或角色的使用者</td>
    <td>
    <ol>
    <li>選取<strong>參與者</strong>後，點選<strong>基於角色</strong>索引標籤。</li>
    <li>在<strong>參與者的類型</strong>清單中，選取要向其發送通知的組或角色的類型。</li>
    <li>在<strong>參與者</strong>清單中，選取要向其發送通知的組或角色。</li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><strong>工作流程使用者</strong></td>
    <td>參與現行工作流程的使用者</td>
    <td>
    <ol>
    <li>選取<strong>工作流程使用者</strong>後，點選<strong>工作流程使用者</strong>索引標籤。</li>
    <li>在<strong>工作流程使用者</strong>清單中，選取參與工作流程使用者。</li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><strong>使用者</strong></td>
    <td>特定使用者</td>
    <td>
    <ol>
    <li>選取<strong>使用者</strong>後，點選<strong>使用者</strong>索引標籤。</li>
    <li>選取要發送通知的使用者，然後將那些使用者移動到<strong>選定的使用者</strong>清單。</li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

10. 對您在步驟 2 中選取的每個事件重複步驟 3 到 9。

## <a name="specify-a-final-approver"></a>指定最終核准者

對於核准者是送出檔案核准的人，並且正在使用「不允許送出者核准」的場景，您可以指定最終核准者。 按照以下步驟指定最終核准者。

1. 在工作流程編輯器中，按右鍵點選核准元素，然後選取 **屬性** 以開啟 **屬性** 表單。
2. 在左側窗格中，點選 **進階設定**。
3. 選取 **使用最終核准者** 核取方塊。
4. 在清單中，選取一個使用者作為最終核准者。

## <a name="set-a-time-limit"></a>設定時間限制

如果必須在特定時間完成核准流程，請按照以下步驟操作。

> [!NOTE]
> 您在這些步驟中選取的選項會覆寫您在每個核准步驟的 **指派** 和 **升級** 區域中選取的選項。

1. 在左側窗格中，點選 **進階設定**。
2. 選中 **為工作流程設定時間限制****元素** 核取方塊。
3. 在 **持續時間** 欄位中，指定必須完成核准流程的時間。 選取下列其中一個選項：

    - **小時** – 輸入必須完成核准流程的小時數。 然後選取您的組織使用的日曆，並輸入有關您組織的工作週的資訊。
    - **天** – 輸入必須完成核准流程的天數。 然後選取您的組織使用的日曆，並輸入有關您組織的工作週的資訊。
    - **週** – 輸入必須完成核准流程的週數。
    - **月** – 選取必須完成核准流程的日期和星期。 例如，您可能希望在該月第三週的星期五之前完成核准流程。
    - **年** – 選取必須完成核准流程的日期、星期和月份。 例如，您可能希望在 12 月第三週的星期五之前完成核准流程。

4. 如果超過時間限制，系統將處理文件。 在 **動作** 清單中，選取系統應採取的操作。

## <a name="specify-which-actions-are-available-to-the-user"></a>指定使用者可以使用哪些操作

將文件指派給使用者進行核准時，使用者必須對文件執行操作。 按照以下步驟指定使用者可以對送出的文件執行哪些操作。

1. 在左側窗格中，點選 **進階設定**。
2. 如果使用者可以核准文件，請選取 **核准** 核取方塊。
3. 如果使用者可以拒絕文件，請選取 **拒絕** 核取方塊。
4. 選取 **要求更改** 核取方塊，使用者可以要求更改文件。
5. 選取 **委派** 核取方塊，如果使用者可以將文件指派給其他使用者進行核准。

> [!NOTE]
> **啟用企業入口網站中工作清單中的操作** 核取方塊已被取代。

## <a name="configure-the-approval-steps"></a>設定核准步驟

核准流程由核准步驟組成。 完成以下過程以在核准流程中新增步驟並設定步驟。

1. 在工作流程編輯器中，雙擊點選核准流程。 工作流程編輯器顯示核准流程的步驟。
2. 若要新增核准步驟，請將步驟從 **工作流程元素** 區域拖到畫布上。
3. 若要設定核准步驟，請參閱[在工作流程中設定核准步驟](configure-approval-step-workflow.md)。


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]