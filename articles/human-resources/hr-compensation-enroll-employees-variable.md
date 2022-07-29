---
title: 在變動薪酬計劃中註冊員工
description: 薪酬和福利經理可以將員工註冊到變動薪酬計劃，方便計算員工的現金和非現金獎勵。
author: twheeloc
ms.date: 08/25/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: HRMCompVarEnrollEmpl, HcmCompensationWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 49a64407778fba5669ad13f239363bffd4b0c7d6
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452421"
---
# <a name="enroll-an-employee-in-a-variable-compensation-plan"></a>在變動薪酬計劃中註冊員工


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

薪酬和福利經理可以將員工註冊到變動薪酬計劃，方便計算員工的現金和非現金獎勵。 這段程序假設 **啟用註冊** 欄位已設定為 **是**，藉此建立變動薪酬計劃，並且已針對變動薪酬計劃建立資格規則。 用來建立此程序的示範資料公司為 USMF。 為了開始這段程序，請前往 **人力資源** > **背景工作角色** > **員工** > **薪酬** > **變動計劃註冊**。

1. 點選 **新增**。
2. 請在 **計劃** 欄位中點選下拉式按鈕開啟查閱功能。
    * 計劃查閱功能將只篩選顯示根據資格規則，員工具備資格的變動薪酬計劃。  
3. 在清單中，點選已選取列的連結。
4. 切換展開 **一般** 專區。
5. 請在 **有效日期** 欄位中，輸入日期。
6. 點選 **儲存**。
7. 切換展開 **覆寫** 專區。
    * 或者，當選取變數計劃指明的錄用規則為百分比時，可以設定錄用規則日期覆寫員工錄用日期。  
    * 如果變數計劃是基礎計劃的佔比，可以覆寫員工的獎勵佔比。 如果變數薪酬計劃是單位計劃數，可以覆寫員工的單位數。  
    * 如果員工應享有固定金額的獎勵，這裡可以設定金額。  
8. 切換展開 **組織覆寫** 專區。
    * 如果員工績效是考量的因素，不同部門績效或指派員工職位以外的部門績效，可以將部門覆寫。 **佔比** 欄位總計應為 100。  



[!INCLUDE[footer-include](../includes/footer-banner.md)]
