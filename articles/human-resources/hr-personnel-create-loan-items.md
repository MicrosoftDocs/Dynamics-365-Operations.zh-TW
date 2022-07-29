---
title: 建立借貸品項
description: 借貸品項是幫助您追蹤貴公司借給背景工作角色的實際物品記錄，例如手機或電腦。
author: twheeloc
ms.date: 10/28/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: HcmLoanType, DefaultDashboard, HcmLoanItem, HcmWorkerLookUp, HcmPersonnelManagementWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 21127c46615015c30e06465b390f67b835e746cb
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452415"
---
# <a name="create-loan-items"></a>建立借貸品項


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



借貸品項是幫助您追蹤貴公司借給背景工作角色的實際物品記錄，例如手機或電腦。 每個實際品項必須有對應的借貸品項。 每筆借貸品項記錄應說明借貸物品、負責借貸人員以及品項可以借貸的天數。 您可以同時為鑰匙、門禁卡，或制服等物品建立多筆借貸物品記錄。 用來建立此程序的示範資料公司為 USMF。


## <a name="create-loan-types"></a>建立借貸類型
1. 請前往 **人力資源** > **背景工作角色** > **借貸品項** > **借貸類型**。
2. 點選 **新增**。
3. 請在 **借貸類型** 欄位中輸入一值。
4. 在 **描述** 欄位中，輸入一個值。
5. 輸入品項指派給此借貸類型可以逾期的天數。 
6. 點選 **儲存**。
7. 關閉頁面。
8. 重新整理頁面。

## <a name="create-loan-items"></a>建立借貸品項
1. 請前往 **人力資源** > **背景工作角色** > **借貸品項** > **借貸品項**。
2. 點選 **建立借貸品項**。
3. 請在 **數量** 欄位中輸入數字。
4. 在 **描述** 欄位中，輸入一個值。
5. 請在 **借貸類型** 欄位中點選下拉式按鈕打開查閱功能。
6. 在清單中，尋找並選取所需的記錄。
7. 在清單中，點選已選取列的連結。
8. 輸入品項可以借貸的天數。
    * 借貸設備頁面上規劃的歸還欄位預設值的計算公式為目前日期加上此數字。  
9. 請在 **負責人** 欄位中點選下拉式按鈕打開查閱功能。
10. 點選 **選取**。
11. 請在 **開始值** 欄位中輸入數字。
12. 請在 **間隔** 欄位中輸入數字。
13. 請在 **格式** 欄位中輸入一值。
    * 例如，如果借貸品項的起始編號是 10，則在 **格式** 欄位輸入兩個編號符號。  
14. 點選 **確定**。
15. 重新整理頁面。



[!INCLUDE[footer-include](../includes/footer-banner.md)]
