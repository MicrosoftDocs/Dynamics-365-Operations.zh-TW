---
title: 在工作流程中設定手動決策
description: 本主題說明如何設定手動決策的屬性。
author: ChrisGarty
ms.date: 06/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 192101
ms.assetid: 0bccad77-1a44-4f08-967b-12c62c02afc7
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d54c010c8fe0d8ca6cc8129948392fb56ef85283
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8460282"
---
# <a name="configure-manual-decisions-in-a-workflow"></a>在工作流程中設定手動決策

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

本主題說明如何設定手動決策的屬性。

若要在工作流編輯器中設定手動決策，請按右鍵點選該手動決策，然後點選 **屬性** 打開 **屬性** 頁面。 然後使用以下程序設定手動決策的屬性。

## <a name="name-the-decision"></a>為決策命名

按照以下步驟輸入手動決策的名稱。

1. 在左側窗格中，點選 **基本設定**。
2. 在 **名稱** 欄位中，輸入手動決策的獨特名稱。

## <a name="enter-a-subject-line-and-instructions"></a>輸入主題行列和指示

您必須向指派給該手動決策的使用者提供主題列和說明。 例如，如果您正在為採購申請設定任務，則指派給該決策的使用者會看到主題列和 **採購申請** 頁上的說明。 主題列顯示在頁面上的訊息欄中。 然後，使用者可以點選訊息欄中的圖標來查看說明。 按照以下步驟輸入主題列和說明。

1. 在左側窗格中，點選 **基本設定**。
2. 在 **指示** 索引標籤，在 **工作項目主題** 欄位，輸入主題列。
3. 若要個人化主題列，您可以插入預留位置。 向使用者顯示主題列時，預留位置將替換為適當的資料。 按照以下步驟插入預留位置：

    1. 在文字方塊中，點選應出現預留位置的位置。
    2. 點選 **插入預留位置**。
    3. 在出現的清單中，選取要插入的預留位置。
    4. 點選 **插入**。

4. 若要新增主題列的翻譯，請執行以下步驟：

    1. 點選 **翻譯**。
    2. 在出現的頁面上，點選 **新增**。
    3. 在出現的清單中，選取您輸入文字時使用的語言。
    4. 在 **翻譯的文字** 欄位中，輸入文字。
    5. 若要個人化文字，您可以按照步驟 3 中的說明插入預留位置。
    6. 點選 **關閉**。

5. 在 **工作項目指示** 欄位中，輸入指示。
6. 若要個人化指示，您可以插入預留位置。 向使用者顯示指示時，預留位置將替換為適當的資料。 按照以下步驟插入預留位置：

    1. 在文字方塊中，點選應出現預留位置的位置。
    2. 點選 **插入預留位置**。
    3. 在出現的清單中，選取要插入的預留位置。
    4. 點選 **插入**。

7. 若要新增指示的翻譯，請執行以下步驟：

    1. 點選 **翻譯**。
    2. 在出現的頁面上，點選 **新增**。
    3. 在出現的清單中，選取您輸入文字時使用的語言。
    4. 在 **翻譯的文字** 欄位中，輸入文字。
    5. 若要個人化文字，您可以按照步驟 6 中的說明插入預留位置。
    6. 點選 **關閉**。

## <a name="specify-the-possible-outcomes-of-a-decision"></a>指定決策的可能結果

通常，當將文件指派給決策者時，會向決策者提出問題。 這個問題的答案通常是 **是** 或 **否**，或 **True** 或 **False**。 按照以下步驟指定手動決策的可能結果。

1. 在左側窗格中，點選 **基本設定**。
2. 在 **結果** 索引標籤，在 **結果 1** 欄位中，輸入結果的名稱或選項。
3. 若要新增結果的翻譯，請執行以下步驟：

    1. 點選 **翻譯**。
    2. 在出現的頁面上，點選 **新增**。
    3. 在出現的清單中，選取您輸入文字時使用的語言。
    4. 在 **翻譯的文字** 欄位中，輸入文字。
    5. 點選 **關閉**。

4. 在 **結果 2** 欄位中，輸入結果的名稱或選項。
5. 若要新增結果的翻譯，請執行以下步驟：

    1. 點選 **翻譯**。
    2. 在出現的頁面上，點選 **新增**。
    3. 在出現的清單中，選取您輸入文字時使用的語言。
    4. 在 **翻譯的文字** 欄位中，輸入文字。
    5. 點選 **關閉**。

## <a name="specify-when-notifications-are-sent"></a>指定何時發送通知

您可以在做出、委派或升級決定時向人們發送通知。 按照以下步驟指定通知的發送時間以及通知的發送對象。

1. 在左側窗格中，點選 **通知**。
2. 選中應發送通知的事件旁邊的核取方塊：

    - **\[選擇 1\]** – 指派的使用者已選擇 **\[選擇 1\]**。
    - **\[選擇 2\]** – 指派的使用者已選擇 **\[選擇 2\]**。
    - **代理人** – 指派的使用者已將決策指派給另一個使用者。
    - **升級** – 指派的使用者未在指派的時間內做決策。

3. 選取您在步驟 2 中選取的事件所在的行。
4. 在 **通知文字** 索引標籤，在文字方塊中，輸入通知的文字。
5. 若要個人化通知，您可以插入預留位置。 向使用者顯示通知時，預留位置將替換為適當的資料。 按照以下步驟插入預留位置：

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
    <li>在<strong>參與者</strong>清單中，選擇要發送通知到的組或角色。</li>
    </ol>
    </td>
    </tr>
    <tr>
    <td>工作流程使用者</td>
    <td>現行工作流程中的使用者</td>
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

## <a name="assign-a-decision"></a>指派決定

按照以下步驟指定手動決策應指派給誰。

1. 在左側窗格中，點選 **指派**。
2. 在 **指派類型** 索引標籤上，選取下表中的選項之一，然後按照該選項的附加步驟進行操作，然後轉到步驟 3。

    <table>
    <thead>
    <tr>
    <th>選項</th>
    <th>指派到決策的使用者</th>
    <th>附加步驟</th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td>參與者</td>
    <td>指派給特定組或角色的使用者</td>
    <td>
    <ol>
    <li>選擇<strong>參與者</strong>後，在<strong>基於角色</strong>索引標籤上，在<strong>參與者類型</strong>清單中，選擇要指派決策的組或角色的類型。</li>
    <li>在<strong>參與者</strong>清單中，選擇要將決策指派到的組或角色。</li>
    </ol>
    </td>
    </tr>
    <tr>
    <td>階層</td>
    <td>特定組織階層中的使用者</td>
    <td>
    <ol>
    <li>選擇<strong>階層</strong>後，在<strong>階層選擇</strong>索引標籤上，在<strong>階層類型</strong>清單中，選擇要指派決策的階層類型。</li>
    <li>系統必須從階層中取出一系列使用者名。 這些名稱代表可以指派決策的使用者。 按照以下步驟指定系統取出的使用者名範圍的起點和終點： <ol>
    <li>若要指定起點，請在<strong>開始自</strong>清單選取人員。</li>
    <li>若要指定結束點，請點選<strong>新增條件</strong>。 然後輸入條件來確定系統在階層中停止取出名稱的位置。</li>
    </ol>
    </li>
    <li>在<strong>階層選項</strong>索引標籤上，指定應將決策指派給範圍內的哪些使用者： <ul>
    <li><strong>指派給擷取到的所有使用者</strong> – 決策指派給範圍內的所有使用者。</li>
    <li><strong>僅指派給擷取到的最後一個使用者</strong> – 該決策僅指派給範圍內的最後一個使用者。</li>
    <li><strong>排除具有以下條件的使用者</strong> – 該決策不指派給範圍內滿足特定條件的任何使用者。 點選<strong>新增條件</strong>指定條件。</li>
    </ul>
    </li>
    </ol>
    </td>
    </tr>
    <tr>
    <td>工作流程使用者</td>
    <td>現行工作流程中的使用者</td>
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
    <li><strong>可用使用者</strong>清單包括所有使用者。 選擇要指派決策的使用者，然後將這些使用者移動到<strong>選定的使用者</strong>清單。</li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

3. 在 **時限** 索引標籤上，在 **期間** 欄位中，指定使用者做決策的時間。 選取下列其中一個選項：

    - **小時** – 輸入使用者必須做決策的小時數。 然後選取您的組織使用的日曆，並輸入有關您組織的工作週的資訊。
    - **日** – 輸入使用者必須做決策的天數。 然後選取您的組織使用的日曆，並輸入有關您組織的工作週的資訊。
    - **週** – 輸入使用者必須做決策的週數。
    - **月**–選擇使用者必須做決策的日期和星期。 例如，您可能希望使用者在每月第三週的星期五之前做決策。
    - **年** – 選擇使用者必須做決策的日期、星期和月份。 例如，您可能希望使用者在 12 月第三週的星期五之前做決策。

    如果使用者沒有在指派的時間內和，該決策則會過期。 可根據您在該頁面地 **升級** 的區域升級過期的決策。

## <a name="specify-what-happens-when-a-decision-is-overdue"></a>指定決策過期時會發生的事

如果使用者沒有在指派的時間內和，該決策則會過期。 過期的決策可以升級或自動指派給其他使用者。 如果決策過期，請按照以下步驟升級。

1. 在左側窗格中，點選 **升級**。
2. 選取 **使用升級路徑** 核取方塊以建立升級路徑。 系統會自動將決次指派給升級路徑中列出的使用者。 例如，下表表示升級路徑。

    | 順序 | 升級路徑            |
    |----------|----------------------------|
    | 1        | 指派給：Donna           |
    | 2        | 指派給：Erin            |
    | 3        | 最終行動：\[選擇 1\] |

    在此範例中，系統將過期決策指派給 Donna。 如果 Donna 沒有在指派的時間內做決策，系統則會指派決策給 Erin。 如果 Erin 沒有在指派的時間內做決策，系統則會選取 **\[選擇 1\]** 作為決策。

3. 若要將使用者新增到升級路徑，請點選 **新增升級**。 選擇下表中的選項之一，然後按照該選項的附加步驟進行操作，然後轉到步驟 4。

    <table>
    <thead>
    <tr>
    <th>選項</th>
    <th>升級到決策的使用者</th>
    <th>附加步驟</th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td>階層</td>
    <td>特定組織階層中的使用者</td>
    <td>
    <ol>
    <li>選擇<strong>階層</strong>後，在<strong>階層選擇</strong>索引標籤上，在<strong>階層類型</strong>清單中，選擇要升級決策的階層類型。</li>
    <li>系統必須從階層中取出一系列使用者名。 這些名稱代表可以升級決策的使用者。 按照以下步驟指定系統取出的使用者名範圍的起點和終點： <ol>
    <li>若要指定起點，請在<strong>開始自</strong>清單選取人員。</li>
    <li>若要指定結束點，請點選<strong>新增條件</strong>。 然後輸入條件來確定系統在階層中停止取出名稱的位置。</li>
    </ol>
    </li>
    <li>在<strong>階層選項</strong>索引標籤上，指定應將決策升級給範圍內的哪些使用者： <ul>
    <li><strong>指派給擷取到的所有使用者</strong> – 決策升級給範圍內的所有使用者。</li>
    <li><strong>僅指派給擷取到的最後一個使用者</strong> – 該決策僅升級給範圍內的最後一個使用者。</li>
    <li><strong>排除具有以下條件的使用者：</strong> - 該決策不升級給範圍內滿足特定條件的任何使用者。 點選<strong>新增條件</strong>指定條件。</li>
    </ul>
    </li>
    </ol>
    </td>
    </tr>
    <tr>
    <td>工作流程使用者</td>
    <td>現行工作流程中的使用者</td>
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
    <li><strong>可用使用者</strong>清單包括所有使用者。 選擇要升級決策的使用者，然後將這些使用者移動到<strong>選定的使用者</strong>清單。</li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

4. 在 **時限** 索引標籤上，在 **期間** 欄位中，指定使用者做決策的時間。 選取下列其中一個選項：

    - **小時** – 輸入使用者必須做決策的小時數。 然後選取您的組織使用的日曆，並輸入有關您組織的工作週的資訊。
    - **日** – 輸入使用者必須做決策的天數。 然後選取您的組織使用的日曆，並輸入有關您組織的工作週的資訊。
    - **週** – 輸入使用者必須做決策的週數。
    - **月**–選擇使用者必須做決策的日期和星期。 例如，您可能希望使用者在每月第三週的星期五之前做決策。
    - **年** – 選擇使用者必須做決策的日期、星期和月份。 例如，您可能希望使用者在 12 月第三週的星期五之前做決策。

5. 對應新增到升級路徑的每個使用者重複步驟 3 到 4。 您可以更改使用者的順序。
6. 如果升級路徑中的使用者未在指派的時間內做決策，該系統會做決策。 若要指定該系統選擇的選項，請選擇 **動作** 資料列，然後，在 **結束動作** 索引標籤，選擇選項。

## <a name="set-a-time-limit"></a>設定時間限制

如果必須在特定時間做決策，請按照以下步驟操作。

> [!NOTE]
> 您在這個程序中選擇的選項會覆寫您在頁面的 **指派** 和 **升級** 區域選擇的選項。

1. 在左側窗格中，點選 **進階設定**。
2. 選擇 **為工作流程元素設定時間限制** 核取方塊。
3. 在 **持續時間** 欄位中，指定必須做決策的時間。 選取下列其中一個選項：

    - **小時** – 輸入小時數。 然後選取您的組織使用的日曆，並輸入有關您組織的工作週的資訊。
    - **日** – 輸入天數。 然後選取您的組織使用的日曆，並輸入有關您組織的工作週的資訊。
    - **週** – 輸入週數。
    - **月** – 選擇決策必須執行的日期和星期。 例如，您可能希望決策在當月第三週的星期五之前執行。
    - **年** – 選擇決策必須執行的日期、星期和月份。 例如，您可能希望決策在 12 月第三週的星期五之前執行。

4. 如果超過時間限制，該系統會做決策。 在 **動作** 清單中，選擇系統應選擇的選項。


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]