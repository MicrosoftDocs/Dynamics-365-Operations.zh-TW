---
title: 在固定薪酬計劃中註冊員工
description: 薪酬和福利經理可以將員工指派給固定薪酬計劃以管理他們的基本工資。
author: twheeloc
ms.date: 08/25/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: HRMCompFixedEmpl, HRMCompFixedEmplActionDialog, HcmPositionLookup, HRMCompRefPointLookup, HcmCompensationWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b7c2423faa4a0c50d9d319a9e6f489e2946c36a7
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452556"
---
# <a name="enroll-an-employee-in-a-fixed-compensation-plan"></a>在固定薪酬計劃中註冊員工


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

薪酬和福利經理可以將員工指派給固定薪酬計劃以管理他們的基本工資。 這段程序假設固定計劃已經建立並且生效，而此計劃的資格規則已經設定。 用來建立此程序的示範資料公司為 USMF。 若要開始這段程序，請前往 **人力資源** > **背景工作角色** > **員工** > **薪酬** > **固定計劃**。

1. 點選 **新增**。
2. 請在 **動作** 欄位中選取 **錄用/重新錄用** 的固定薪酬動作以說明員工薪酬的變動情況。
3. 在清單中，點選已選取列的連結。
4. 請在 **職位** 欄位點選下拉式按鈕開啟查閱功能。
5. 在清單中，點選已選取列的連結。
    * 顯示的等級來自指派給 **職位** 的 **工作** 中，**薪酬** FastTab >**等級** 欄位。 等級必須在薪酬可以指派給員工前在工作上設定。  
6. 請在 **計劃** 欄位選取員工的固定薪酬計劃。 **計劃** 查閱功能已經篩選過只顯示根據 **資格規則**，具備資格的員工。
7. 在清單中，尋找並選取所需的記錄。
    * 薪酬 **生效** 和 **到期** 日期預設為背景工作角色職位指派的開始日期和結束日期。 您可以按照需求調整這些日期。  
    * 如果固定薪酬計劃是級距式計劃，請選取包含員工正確工資費率的級距。 如果固定薪酬計劃是分級式或分段式計劃，請輸入員工的工資費率。 工資費率將按照計劃的容差設定和工作薪酬等級的最小和最大參考點驗證。  
8. 點選 **確定**。



[!INCLUDE[footer-include](../includes/footer-banner.md)]
