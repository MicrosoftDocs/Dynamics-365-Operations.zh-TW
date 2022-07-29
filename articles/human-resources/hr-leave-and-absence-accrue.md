---
title: 累計請假與缺勤計劃
description: 您可以在 Dynamics 365 Human Resources 累計多名員工或個人的請假和缺勤數據。
author: andreabichsel
ms.date: 05/04/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: a5f3ae95d0670369ac63e5a5d521885fe55ce8af
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452649"
---
# <a name="accrue-leave-and-absence-plans"></a>累計請假與缺勤計劃


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

您可以在 Dynamics 365 Human Resources 累計多名員工或個人的請假和缺勤數據。

## <a name="accrue-leave-and-absence-for-multiple-employees"></a>多名員工的累計請假和缺勤數據

1. 請在 **請假和缺勤** 頁面上選取 **連結** 索引標籤。

2. 請在 **管理請假** 下方選取 **累計請假和缺勤計劃**。

3. 此時會出現 **累計請假和缺勤計劃** 對話方塊。 請在 **累積截止日期** 中選取 **今天日期** 或選取 **自訂日期** 後輸入自訂日期。

4. 如果您希望執行所有公司的累計數據，請選取 **所有公司**。 如果您希望處理單項請假計劃的累計數據，**所有計劃** 請選取 **否**，然後選取 **請假計劃**。 如果您選取所有公司，就無法選取個人請假計劃。

5. 如果您希望背景執行累計流程，請選取 **背景執行** 並執行任務如下：

    1. 輸入累計流程資訊。
    2. 若要設定重覆性工作，請選取 **重覆性**、輸入重覆性資訊，然後選取 **確定**。
    3. 若要設定工作警報，請選取 **警報** 和要接收的警報，然後選取 **確定**。
    4. 選取 **確定**。 累計流程將會同您設定的參數一起執行。 

## <a name="accrue-leave-and-absence-for-an-employee"></a>累計員工的請假和缺勤

1. 請在員工記錄上選取 **請假**。

2. 請選取 **累計請假和缺勤**。

3. 此時會出現 **累計請假和缺勤計劃** 對話方塊。 請在 **累積截止日期** 中選取 **今天日期** 或選取 **自訂日期** 後輸入自訂日期。

4. 如果您希望執行所有公司的累計數據，請選取 **所有公司**。 如果您希望處理單項請假計劃的累計數據，**所有計劃** 請選取 **否**，然後選取 **請假計劃**。 如果您選取所有公司，就無法選取個人請假計劃。

5. 如果您希望背景執行累計流程，請選取 **背景執行** 並執行任務如下：

   1. 輸入累計流程資訊。

   2. 若要設定重覆性工作，請選取 **重覆性**，輸入重覆性資訊並選取 **確定**。

   3. 若要設定工作警報，請選取 **警報** 和要接收的警報，然後選取 **確定**。

   4. 選取 **確定**。 累計流程將會同您設定的參數一起執行。

## <a name="delete-leave-and-absence-accruals-for-multiple-employees"></a>刪除多名員工的請假和缺勤累計數據

刪除特定計劃和日期範圍的累計記錄。 累計的日期必須是今天或未來的日期。

1. 請在 **請假和缺勤** 頁面上選取 **連結** 索引標籤。

2. 請在 **管理請假** 下方選取 **刪除請假和缺勤計劃累計數據**。

3. 請在 **刪除請假和缺勤計劃累計數據** 對話方塊中選取 **請假計劃**。

4. 若情況適用，請選擇 **刪除剩餘天數調整**。

5. 輸入或選取 **請假累計日期**。 此日期必須是今天或未來的日期。

6. 選取 **確定**。 累計流程將會同您設定的參數一起刪除累計數據。

## <a name="delete-leave-and-absence-accruals-for-a-single-employee"></a>刪除單名員工的請假和缺勤累計數據

1. 請在員工記錄上選取 **請假**。

2. 選取 **刪除請假和缺勤計劃累計數據**。

3. 請在 **刪除請假和缺勤計劃累計數據** 對話方塊中選取 **請假計劃**。

4. 若情況適用，請選擇 **刪除剩餘天數調整**。

5. 輸入或選取 **請假累計日期**。 此日期必須是今天或未來的日期。

6. 選取 **確定**。 累計流程將會同您設定的參數一起刪除累計數據。

## <a name="review-leave-accrual-and-deletion-processes"></a>審核請假累計和刪除流程

**請假累計稽核** 會顯示您每次執行或刪除一名或所有員工的累計數據。 也會顯示執行動作的日期和人員。

1. 請在 **請假和缺勤** 頁面上選取 **連結** 索引標籤。

2. 請在 **管理請假** 下方選取 **刪除請假累計稽核**。

## <a name="leave-accrual-transaction-auditing"></a>請假累計交易稽核中

本功能有助於請假和缺勤經理了解，員工在特定請假類型上，與休假剩餘天數有關的請假和缺勤累計交易。

若要檢視交易細節：

1. 請在員工記錄上選取 **請假**。

2. 請選取 **檢視休假時間**，然後選取 **剩餘天數** 索引標籤。

若要檢視與特定休假類型有關的累計交易，請選取 **目前剩餘天數** 欄位的數值。

若要檢視特定累計數額的交易詳情，請選取累計行、打開右側的 **相關資訊** 面板，然後打開 **交易明細** 專區。 交易明細專區會顯示：

- 員工請假類型剩餘天數的變更
- 特定累計期間的就業細節
- 有關累計期間和費率的細節
- 針對請假計劃組態所做的任何變更

![顯示請假累計交易稽核。](media/hr-leave-and-absence-accrue-audit.png)

## <a name="see-also"></a>也請參閱

[請假和缺勤概觀](hr-leave-and-absence-overview.md)</br>
[建立請假和缺勤計劃](hr-leave-and-absence-plans.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
