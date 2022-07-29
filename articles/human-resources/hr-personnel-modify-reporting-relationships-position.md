---
title: 修改職位的回報關係
description: 這段程序顯示員工回報關係的變更方法。
author: twheeloc
ms.date: 10/28/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: HcmPosition, HcmPositionReportsToDialog, HcmPositionLookup, HcmPersonnelManagementWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d7996733575c2d3a23971d08eb101962c1f6bbd9
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452247"
---
# <a name="modify-reporting-relationships-for-a-position"></a>修改職位的回報關係


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



這段程序顯示員工回報關係的變更方法。 回報關係可用來路由文件走完工作流程。 本程序也顯示指派員工到額外階層架構的方法。 例如，員工可能是專案團隊的一份子，與專案主管有非正式的通報關係。 可以在職位上定義額外通報關係，以適應各類專案或矩陣方案。 用來建立此程序的示範資料公司為 USMF。

1. 請前往 **人力資源**\>**職位**\>**職位**。
2. 使用快速篩選條件尋找記錄。 例如，篩選 **職位** 欄位中的 **000091** 值。
3. 請在清單選取已選取行的連結。
4. 展開 **向職位回報** 專區。
5. 選取 **新增** 打開下拉式對話方塊。
6. 請在 **通報對象** 欄位中輸入或選取一值。
7. 選取 **建立**。
8. 展開 **關係** 專區。
9. 選取 **新增**。
10. 選取格線左側的勾選方塊。
11. 請在 **階層架構名稱** 欄位中輸入或選取一值 (例如，**專案**)。
12. 請在 **通報對象職位** 欄位中輸入或選取一值 (例如，**000437**)。
13. 選取 **儲存**。



[!INCLUDE[footer-include](../includes/footer-banner.md)]
