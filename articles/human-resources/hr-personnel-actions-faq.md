---
title: 人事動作常見問答集
description: 本主題包含貴組織如果使用人事動作功能，可能遇到的問題的解答。
author: twheeloc
ms.date: 10/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2017-06-16
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: c952bdc95b49c92fea34aef63b57c7e193b2f09a
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452097"
---
# <a name="personnel-actions-faq"></a>人事動作常見問答集


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

本主題包含貴組織如果使用人事動作功能，可能遇到的問題的解答。 人事動作是您在執行特定人事相關任務時必須額外完成的步驟。 

可能需要人事動作功能的任務範例如下：
 - 當您建立新職位時。 
 - 修改既有的位置值。 
 - 錄用新進背景工作角色。 
 - 轉調背景工作角色。 
 - 變更背景工作角色薪酬。 
 - 變更職位指派。 
 - 終止背景工作角色的雇用。

> [!NOTE]
> 人事動作只在 **人力資源共享參數** 頁上的 **人事動作** 索引標籤中，**啟用背景工作角色動作** 和 **啟用位置動作** 欄位已經設定為 **是** 的時候才會開放使用。 

## <a name="how-can-i-tell-if-my-organization-requires-personnel-actions"></a>如何區分我的組織是否需要人事動作？
如果您在建立新職位、變更既有職位、錄用新進背景工作角色、轉調背景工作角色、變更背景工作角色薪酬、變更職位指派、終止背景工作角色的雇用或輸入背景工作角色請假時被要求選取人事動作，貴組織就需要人事動作。 

## <a name="what-is-the-difference-between-a-position-action-and-a-worker-action"></a>職位動作和背景工作角色動作之間的差別？
共有兩種類型的人事動作：

- **職位** 動作 – 在既有職位或新職位上執行職位動作。 例如，如果您變更既有職位值或建立新季節性職位，可能需要職位動作。 

- **背景工作角色** 動作 – 對既有員工或新進員工執行背景工作角色動作。 例如，當錄用新員工或晋升既有員工時，可能需要背景工作角色動作。 

## <a name="what-do-the-statuses-of-the-personnel-actions-mean"></a>人事動作的狀態是什麼意思？
人事動作狀態包括：

- **草擬** – 如果使用工作流程，動作尚未提交。 如果未使用工作流程，動作尚未完成。
- **審核中** – 人事動作已經提交到工作流程，但工作流程尚未完成。
- **核准等候中** – 工作流程已經完成，但變更仍在進行。 **已取消** – 工作流程已取消或人事動作被重新叫用。 **遭拒** – 動作要求遭到核准人員拒絕。
- **處理動作** – 動作要求已經核准，正在處理變更。
- **工作流程完成** – 工作流程已完成，變更已處理。 **失敗** – 工作流程失敗，因為資訊過時。 點選 **重新啟動** 顯示最新資訊並繼續。
- **已完成** – 職位已經成功建立或修改，或員工已成功錄用、調動或終止，或薪酬已經變更。 **錯誤** – 發生資訊過時以外的問題。 打開 **人事動作訊息日誌** 判定錯誤的肇因。
- **駁回** – 動作要求遭到核准人員駁回。

## <a name="can-i-delete-a-personnel-action"></a>我可以刪除人事動作嗎？
是的，您可以刪除狀態為 **草稿**、**錯誤**、**失敗** 或 **已取消** 的人事動作。 您可以刪除狀態為 **已完成** 的人事動作，前提是您已經在 **人力資源共用參數** 頁面上將 **允許刪除已完成的背景工作角色動作** 選項為 **是**。

## <a name="what-is-the-fastest-way-to-check-the-status-of-a-personnel-action-request"></a>檢查人事動作要求狀態的最快方式？
打開任何一張 **人事動作** 清單頁面並選取人事動作。

## <a name="what-should-i-do-if-a-personnel-action-request-fails"></a>要是人事動作要求失敗，我該怎麼辦？
如果人事動作要求失敗，請按照下列步驟解決錯誤並重新提交要求：

> 1. 請在 **動作窗格** 上點選 **錯誤文字** 按鈕檢視描述問題的訊息文字。
> 
> 2. 請在 **動作窗格** 上點選 **重新啟動**，載入最新資訊並將人事動作狀態設回 **草稿**。
> 
> 3. 解決錯誤，然後點選 **完成** 或 **提交**。

## <a name="what-happens-to-a-personnel-action-that-uses-workflow-when-the-final-approval-is-completed"></a>完成最終核准後，使用工作流程的人事動作會發生什麼情況？
如果沒有錯誤，則人事動作會變成唯讀。 (您可以檢視 **所有背景工作角色動作** 清單頁面上的歷程，但不能變更人事動作。) 當人事動作的狀態是 **已完成**，職位或背景工作角色記錄就已經更新。 若要檢視已執行的變更，請打開 **職位** 或 **背景工作角色** 清單頁面。

## <a name="why-do-i-receive-the-following-error-when-i-enter-a-non-zero-value-in-the-pay-rate-field-the-value-is-out-of-its-valid-range--it-much-be-between-000-and-000"></a>當我在支付費率欄位輸入非零值時，為什麼會收到下列錯誤？ "此值超出有效範圍 - 它在 0.00 和 0.00 之間"
您收到這則訊息是因為 **工作** 頁面上，與選取職位相關聯的工作 **等級** 欄位是空白的。

若要解決此項錯誤，請按照下列步驟：

> 1. 請在 **背景工作角色職位指派** 頁面上點選 **職位** 欄位。  
> 2. 點選 **工作** 欄位值打開 **工作** 頁。
> 3. 請在動作窗格上點選 **編輯** 。
> 4. 點選 **薪酬** 索引標籤。
> 5. 在 **等級** 欄位，選取等級。
> 6. 關閉 **工作** 頁面。
> 7. 關閉 **職位** 頁面。
> 8. 退回 **背景工作角色** 頁面上的 **薪酬** 索引標籤，並選取 **固定薪酬**。  選取 **新增** 並在 **職位** 欄位輸入員工的職位。  請在 **計劃** 欄位輸入一直，然後在 **支付費率** 欄位輸入員工的薪酬。

## <a name="why-cant-i-change-the-effective-date-on-the-header-of-the-worker-action-page"></a>為何我無法變更背景工作角色動作頁面標題上的生效日期？
您無法變更生效日期，因為此欄位已填滿動作類型最合乎邏輯的日期。

例如： 

- **終止背景工作角色的雇用** 動作標題的生效日期是您在 **終止日期** 欄位輸入的日期。
- **錄用背景工作角色** 動作的生效日期是您在 **就業開始日期** 欄位輸入的日期。
- **轉調背景工作角色** 動作的生效日期是您在背景工作角色 **指派開始日期** 欄位輸入的日期。



[!INCLUDE[footer-include](../includes/footer-banner.md)]
