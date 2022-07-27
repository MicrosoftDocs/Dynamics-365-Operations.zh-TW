---
title: 委派工作流程中的工作項目
description: 如果您計畫不在辦公室或無法處理工作項目，您可以將您的工作項目委派或重新指派給其他使用者。
author: ChrisGarty
ms.date: 07/07/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SysUserSetup, WorkflowDelegationUserListLookup
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 128dce6a1b852d908e01c348cb767088031b11a5
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8460317"
---
# <a name="delegate-work-items-in-a-workflow"></a>委派工作流程中的工作項目

[!include [banner](../../includes/banner.md)]


[!INCLUDE [PEAP](../../../../includes/peap-1.md)]

## <a name="manually-delegate-a-work-item"></a>手動委派工作項目

若要委派單個工作項目，請選取 **工作流程** 選單中的 **委派** 選項，然後輸入要委派的使用者以及評論。 這會將工作項目重新指派給該使用者，以便他們可以完成它。

## <a name="manually-delegate-multiple-work-items"></a>手動委派多個工作項目

多個工作項目可以一起從 **指派給我的工作項目** 頁中委託。 以下工作流程類型符合批次處理委派條件：採購協議核准工作流程、採購訂單工作流程、採購申請核准和廠商發票工作流程。 **委派多個工作委託** 函數預設為停用狀態，可以在 **工作區 > 函數管理** 中啟用。 請聯絡您的系統管理員以獲取有關啟用此函數的說明。
1.  進入 **常用 > 常用 > 工作委託 > 指派給我的工作項目**。
2.  選取將被委派的工作項目。
3.  點選 **委派工作項目** 選單。
4.  在 **使用者** 欄位，選取要將工作項目委派給的使用者。
5.  在 **註解** 欄位中，輸入解釋您委派工作項目的原因的註解。
6.  點選 **委派工作項目** 按鈕完成工作項目委派。

## <a name="automatically-delegate-work-items"></a>自動委派工作項目

如果您計畫離開辦公室或在一段時間內無法處理工作項目，您可以使用 **使用者選項** 頁面自動將新的工作項目委派給其他使用者。

### <a name="set-up-automatic-delegation"></a>設定自動委派
1. 進入 **常用 > 設定 > 使用者選項**。
2. 點選 **工作流程** 標籤。確保擴展了委派部分。 若要將系統設定為自動將您的工作項目委派給其他使用者，您必須建立委派規則，該規則指定何時委派某些類型的工作項目。 按照以下步驟建立委派規則。  
3. 選點 **新增**。
4. 在 **範圍** 欄位中，選取一個選項：
    - 全部 - 委派指派給您的所有工作項目。
    - 模組 – 僅委派與特定類型的工作流程相關的工作項目。 如果選取此選項，則必須在 **名稱** 欄位中選取工作流程類型。
    - 工作流程 – 僅委派與特定工作流程相關的工作項目。 如果選取此選項，則必須在 **名稱** 欄位中選取工作流程。  
5. 在 **名稱** 欄位中：
    - 針對 **模組** 範圍，選取目標模組。
    - 針對 **工作流程** 範圍，選取目標工作流程。
6. 在 **委派** 欄位，選取要將工作項目委派給的使用者。 使用 **開始日期/時間** 和 **結束日期/時間** 欄位來指定您希望何時自動委派工作項目。  
7. 在 **開始日期/時間** 欄位中，輸入日期和時間。
8. 在 **結束日期/時間** 欄位中，輸入日期和時間。
9. 選取 **已啟用** 核取方塊以啟用委派規則。 
10. 在 **註解** 欄位中，輸入解釋您委派工作項目的原因的註解。


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]