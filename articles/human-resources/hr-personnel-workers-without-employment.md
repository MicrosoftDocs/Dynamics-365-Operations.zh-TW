---
title: 待業中的背景工作角色
description: 貴組織未來不會雇用、非現職或無雇用歷程的背景工作角色會出現在待業中的背景工作角色頁面。
author: twheeloc
ms.date: 11/03/2021
ms.topic: ''
ms.prod: ''
ms.technology: ''
ms.search.form: HcmWorkerV2, HRMMassHireProject, HRMMassHireLine, HcmPersonnelManagementWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2021-04-06
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d0b8fe7dd0818fa1c3cc4224e73035849f9dadfe
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452634"
---
# <a name="workers-without-employment"></a>待業中的背景工作角色


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

貴組織未來不會雇用、非現職或無雇用歷程的背景工作角色會出現在 **待業中的背景工作角色** 頁面。 當您匯入沒有雇用記錄的背景工作角色，或當您透過 **背景工作角色\>工作歷程** 刪除背景工作角色的雇用狀態。

**待業中的背景工作角色** 頁面預設會開放下列角色使用：

- 人力資源助理
- 人力資源經理
- 招募人員
- 薪酬和福利經理
- 工資單管理員
- 工資單經理
- 訓練經理

您可以在 **待業中的背景工作角色** 清單刪除列入其中的個人。 本項權限預設是給人力資源助理角色。 您可以按照下列步驟給其他角色本項權限：

1. 選取 **系統管理**，然後 **安全配置**。

2. 請在 **權限** 索引標籤篩選 **權限** 清單到 **維護背景工作角色**。

   [![篩選權限清單。](./media/hr-personnel-workers-without-employment-filter.png)](./media/hr-personnel-workers-without-employment-filter.png)

3. 請在 **參考** 欄位選取 **顯示功能表項目**。

4. 請在 **顯示功能表項目** 選取 **HcmWorkersWithoutEmployment**。

   [![選取表單。](./media/hr-personnel-workers-without-employment-select.png)](./media/hr-personnel-workers-without-employment-select.png)

5. 設定 **刪除** 使用權限為 **授予**。

6. 選取 **未公開對象** 索引標籤。

7. 選取 **公開全部**。

   [![公開更改。](./media/hr-personnel-workers-without-employment-publish.png)](./media/hr-personnel-workers-without-employment-publish.png)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
