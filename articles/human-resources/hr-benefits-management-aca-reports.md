---
title: 在福利管理中產生平價醫療法案報告
description: 本主題說明福利管理如何追蹤 1095-B 表單和 1095-C 表單上回報的平價醫療法案 (ACA) 雇主授權資訊。
author: twheeloc
ms.date: 08/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-12-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 79bd8e02aeac1be94e735373740cf9508f494a06
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452184"
---
# <a name="generate-aca-reports-in-benefits-management"></a>在福利管理中產生 ACA 報告


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

福利管理追蹤 1095-B 表單和 1095-C 表單上回報的平價醫療法案 (ACA) 雇主授權資訊。 如同舊版的 **福利** 工作區的 ACA 回報功能，本功能只適用美國境內的法人實體。

若要使用本功能，您必須先開啟 **進階福利管理**。 更多資訊包括有關福利管理的重要注意事項，請參閱[啟用或停用福利管理](hr-admin-manage-features.md#enable-or-disable-benefits-management)。

> [!IMPORTANT]
> 您只能從 **福利管理** 工作區或舊版 **福利** 工作區使用 ACA 回報功能，而不是兩者。 例如，如果您切換到福利管理，ACA 回報功能只能從 **福利管理** 工作區，而不是從舊版的 **福利** 工作區開放使用。
>
> 如果您在註冊年中切換到福利管理，您必須在福利管理中正確配置全年的員工資料。 您可藉此方式確保將收到準確的全年回報資訊。

## <a name="getting-started"></a>開始使用

若要追蹤 1095 表單資訊，您必須先建立一個或多個平價醫療承保範疇群組。 這些群組指出的資訊如下：

- 提供給員工承保範疇的投保方案
- 如果成本高於聯邦貧窮線，員工分攤的最低月保費成本
- 雇主依適用情況使用的安全港條款

平價醫療承保範疇群組幫助您針對條件相同的多名員工記錄管理這項資訊。 您可以輕鬆地將群組指派給一名或多名員工。

### <a name="create-or-edit-an-affordable-care-coverage-group"></a>建立或編輯平價醫療承保範疇群組

1. 請在 **福利管理** 工作區中選取 **平價醫療承保範疇群組**。

    ![選取平價醫療承保範疇群組。](./media/hr-benefits-management-aca-coverage-group.png)

2. 選取 **新增** 以建立新平價醫療承保範疇群組或 **編輯** 以變更既有群組。

    ![選取新增或編輯。](./media/hr-benefits-management-aca-new.png)

3. 設定下列欄位。

    | 欄位 | 描述 |
    |---|---|
    | 姓名 | 輸入群組名稱。 |
    | 描述 | 輸入群組說明。 |
    | 承保範疇的投保方案 | 為員工與其配偶或同居伴侶和家屬提供承保範疇的投保方案。 |
    | 員工分攤成本 | 員工負責支付的金額。 |
    | 適用第 4980H 條安全港條款 | 4980H 安全港條款或過渡期救濟法。 |
    | 計劃開始月份 | 選取您的福利計劃年份開始的月份 (日曆制)。 |
    | 群組生效日期 | 本記錄有效的第一個日期。 |
    | 群組有效截止日期 | 本記錄有效的最後一個日期。 如果沒有到期日期，請輸入 **永不**。 |

    ![建立承保範疇群組。](./media/hr-benefits-management-aca-new-group.png)

4. 選取 **儲存**。

### <a name="assign-multiple-employees-to-an-affordable-care-coverage-group"></a>將多名員工指派給平價醫療承保範疇群組

1. 請在 **福利管理** 工作區中選取 **平價醫療承保範疇群組**。
2. 選取要指派員工的群組。
3. 選取 **大量指派**。

    ![選取大量指派。](./media/hr-benefits-management-aca-mass-assignment.png)

4. 在清單中選取員工，然後選取 **指派**。

    ![指派選取的員工給群組。](./media/hr-benefits-management-aca-assign-coverage-group.png)

## <a name="maintain-multiple-versions-of-coverage-options"></a>維護承保範疇群組選項的多版本

您可以維護任何承保範疇群組的多版本。 當貴組織或提供的福利有所變更時，您可以保持群組資訊為最新狀態，不必建立新群組和重新指派員工。

待您建立平價醫療承保範疇群組後，您可以大量指派員工過去。 您也可以個別指派員工到群組，並且指出是否追蹤和回報 ACA 資訊。

如果您不必追蹤和回報某員工的 ACA 資訊，您可以設定 **回報承保範疇** 選項為 **否**。 例如，您可能會有兼職員工不需要 ACA 回報。

### <a name="override-default-values-for-an-employee"></a>覆寫員工的預設值

已指派給平價醫療保險群組的員工，您可以針對需要不同值的任何月份變更下列選項：

- 承保範疇的投保方案
- 員工分攤成本
- 適用第 4980H 條安全港條款

> [!NOTE]
> 2020 ACA 報告方面，您必須同時在 1095-C 表單上回報工作和居家的郵遞區號。 值會自動根據目前有效位置填寫。 如果任一處位置在一年當中的任何時間點不同，請務必覆寫此值。 1095-C 報告的 **郵遞區號** 欄位 (第 17 行) 只有在 **承保範疇的投保方案** 代碼包含 **1L** 到 **1Q** 才會填寫，分述如下：
>
> - **1L、1M 或 1N：** 主要居住地的郵遞區號
> - **1O、1P、1Q：** 主要工作地點的郵遞區號

若要輸入平價醫療保險群組中任一值的例外情況，請按照下列步驟進行。

1. 請在 **人事管理** 工作區中選取 **連結**，然後選取 **背景工作角色**。
2. 請選取清單中的員工。
3. 請在 **就業** 索引標籤上的 **更多資訊** 區段選取 **平價醫療承保範疇**。

    ![變更一名員工的選項。](./media/hr-benefits-management-aca-change-single-employee.png)

4. 選取 **編輯**。
5. 需要變更的每個月份，請選取 **覆寫預設值** 勾選方塊，然後根據需求變更其他值。

    ![覆寫預設值。](./media/hr-benefits-management-aca-override-default.png)

6. 選取 **儲存**。

## <a name="report-health-care-coverage"></a>回報醫療保健承保範疇

您必須追蹤全職和兼職員工的任何雇主贊助、自行投保的醫療保健承保範疇。 將每位員工與其家屬納入 1095-C 報告，包括他們被涵蓋進去的月份。

若要指出是否必須回報福利計劃，請遵照下列步驟進行。

1. 請在 **福利管理** 工作區選取 **福利計劃**。
2. 選取要回報的福利計劃。
3. 選取 **編輯**。
4. 設定 **按照平價醫療法案回報** 選項為 **是**。

    ![回報醫療保健承保範疇。](./media/hr-benefits-management-aca-report-coverage.png)

5. 選取 **儲存**。

如果員工選取家屬醫療保險承保範疇，則家屬的承保範疇期間由家屬註冊或移除的日期判定。 家屬的承保日期自動根據註冊當年度符合參加計劃資格且有效的期間計算。

## <a name="generate-1095-b-and-1095-c-forms"></a>產生 1095-B 和 1095-C 表單

您可以產生 ACA 1095-B 和 1095-C 表單，然後分發給您的每位員工。 您也可以電子產生 1095-C 表單和對應的 1094-C 傳輸檔案傳送給美國國稅局 (IRS)。

1. 請在 **福利管理** 工作區中選取 **ACA 1095-B 表單** 或 **ACA 1095-C 表單**。
2. 根據需求變更參數，然後選取 **確定**。

    > [!NOTE]
    > 如果您為 500 多名員工列印 1095-C 表單，您將收到不只一個 PDF 檔案。 我們建議您增加 **文件管理參數** 頁面的 **最大檔案大小 (MB)** 欄位值到 **150**。 (若要快速打開此頁面，請使用瀏覽列上的搜尋欄位。)
    >
    > ![變更最大檔案大小。](./media/hr-benefits-management-aca-maximum-file-size.png)

3. 若要檢查和檢視您的報告狀態，請使用瀏覽列上的搜尋欄位打開 **電子回報工作** 頁面。

    ![搜尋電子回報工作頁面。](./media/hr-benefits-management-aca-search-electronic-reporting-jobs.png)

4. 請選取要檢視的報告，然後選取 **顯示檔案**。

    ![顯示檔案。](./media/hr-benefits-management-aca-show-files.png)

5. 請選取 **打開**。

    ![打開檔案。](./media/hr-benefits-management-aca-open-file.png)

6. 請從出現在瀏覽器視窗底部的通知列打開壓縮檔，然後選取報告。 您可以檢視或列印 PDF 檔案。

    ![樣本 1095-C 表單。](./media/hr-benefits-management-aca-1095-c-form.png)

## <a name="view-aca-coverage-information"></a>檢視 ACA 覆寫資訊

**背景工作角色平價醫療承保範疇** 頁面顯示資訊如下：

- 已指派給每個承保範疇群組的員工
- 不必納入報告的員工
- 尚未指派的員工

若要檢視此項資訊，請按照下列步驟進行。

1. 請在 **福利管理** 工作區中選取 **背景工作角色平價醫療承保範疇群組**。
2. 請在 **群組名稱** 欄位中選取群組。

    ![檢視 ACA 承保範疇。](./media/hr-benefits-management-aca-view-coverage.png)

如果平價醫療承保範疇群組的任何預設值已經被覆寫，則變更值旁邊會出現星號。 如果所有 12 個月的值都相同且並且未曾被覆寫，則此值會出現在 **全部 12 個月** 欄位。

您可以檢視標記為非 ACA 回報且不需要 1095-C 表單的員工。 請在 **篩選條件** 欄位選取 **非屬 ACA 回報**。

您可以檢視並未指派給群組或已指派給到期群組的員工。 請在 **篩選條件** 欄位選取 **並未指派或已到期群組**。

### <a name="export-to-excel"></a>匯出到 Excel

若要匯出任何清單到 Microsoft Excel，請遵照這些步驟進行。

1. 選取 **在 Microsoft Office 打開** 按鈕。
2. 請選取 **供內部使用的 HCM 人力資源暫存資料表**。
3. 選取 **下載**。

### <a name="view-aca-reportable-dependents"></a>檢視 ACA 可回報的家屬

如果您因為提供自行投保的承保範疇而必須回報被保人，您可以檢視涵蓋於福利計劃之中，並且標記為 **ACA 可回報** 的任何家屬。 請在動作窗格上選取 **檢視家屬承保範疇**。

![檢視家屬承保範疇。](./media/hr-benefits-management-aca-view-dependent-coverage.png)

顯示員工家屬的承保範圍資訊。

![家屬承保範疇。](./media/hr-benefits-management-aca-dependents.png)

> [!NOTE]
> 本頁只顯示標記為 **ACA 可回報** 的福利計劃。


[!INCLUDE[footer-include](../includes/footer-banner.md)]
