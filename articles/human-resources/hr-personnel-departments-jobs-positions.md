---
title: 憑藉部門、工作和職位來整理您的人力陣容
description: 本主題說明有關部門、工作和職位的概念性資訊，它們是在人力資源維護的組織元素。
author: twheeloc
ms.date: 01/03/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmJob, HcmPosition, OMOperatingUnit, HcmPersonnelManagementWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 87933
ms.assetid: eb5dcacb-a5fe-451d-b30a-7ef14da65d81
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 2b4c1efac249b315de25348a104f00a613c32df9
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452331"
---
# <a name="organize-your-workforce-by-using-departments-jobs-and-positions"></a>憑藉部門、工作和職位來整理您的人力陣容


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

部門、工作和職位是在人力資源內維護的組織元素。 本主題說明有關這些元素的概念性資訊。 

下列範例用來圖說本文描述的概念。

|**部門**|**職位**|**工作**|
|---|---|---|
|**銷售**|銷售經理 (東方)|銷售經理|
|**銷售**|銷售經理 (西方)|銷售經理|
|**銷售**|銷售經理 (中部)|銷售經理|
|**會計**|會計主管|會計經理|
|**會計**|會計 - A|會計|
|**人力資源**|人力資源經理 (東方)|人力資源經理|
|**人力資源**|人力資源經理 (西方)|人力資源經理|
|**人力資源**|人力資源經理 (中部)|人力資源經理|


##  <a name="departments"></a>部門

部門是代表組織類別或職能領域的營運單位，負責組織的特定領域，例如銷售或會計。 部門用來回報職能領域，並可能承擔盈虧責任。 部門也可能包括一組成本中心。 銷售、會計和人力資源是組織內一些部門範例。

## <a name="jobs-and-positions"></a>工作和職位
工作是工作執行者必備的任務和責任集合。 職位是工作的個別執行個體。 工作必備的責任範圍、工作任務、工作職能、技能、教育資訊和證書也是工作關聯職位的必備元素。

### <a name="job-tasks"></a>工作任務

您可以建立工作任務，說明任職該工作崗位的背景工作角色必須完成的基本任務。 相同的工作任務可以新增到多項工作，而這些工作職位將承襲那些工作任務。 工作任務範例如下列資料表所列。

| 工作           | 工作任務                                                |
|---------------|-------------------------------------------------------------|
| 銷售經理 | 績效審核 – 審核每位銷售人員的工作績效。    |
| 會計    | 絕對審核 – 核准或駁回每位銷售人員的缺席要求或註冊。 |


### <a name="job-functions"></a>工作職能

工作職能就像工作任務。 工作職能說明指派給工作的一項或多項任務、職責或責任。 工作職能可以指派給工作並用來設定和落實薪酬計劃的資格規則。 工作職能範例如下列資料表所列。

| 工作           | 職務                                                |
|---------------|-------------------------------------------------------------|
| 銷售經理 | Mng-people – 管理下屬。               |
| 會計    | FIN-Review – 維護一套帳戶的財務資料。 |

### <a name="job-types"></a>工作類型

使用工作類型將類似工作分成各類別。 工作類型，就像工作職能，可以指派給工作並用來設定和落實薪酬計劃的資格規則。 一些工作類型範例如下列清單所示：
-   全職
-   兼職
-   薪資
-   時薪

### <a name="areas-of-responsibility"></a>責任範圍

使用責任範圍指出任職該工作的背景工作角色，會負責的工作角色、流程和產品。 例如，職銜為 "會計" 的責任範圍可能是 "A 產品的財務報表"。

## <a name="positions"></a>職位

職位是組織階層架構中，等級較低的重要元素。 職位是工作的個別執行個體。 例如，“銷售經理 (東部)“ 職位只是與 “銷售經理” 工作有關聯的職位之一。 職位存在於部門，指派給背景工作角。
### <a name="position-creation-and-maintenance"></a>職位建立和維護

-   您可以在存取容易的清單頁面檢視職位相關系統變更的歷程。
-   您可以建立使用者在建立或修改職位時，可以選取的原因代碼。
-   您可以建立人事動作類型並將編號順序指派給人事動作。
-   您可以設定工作流程，職位新增和變更因此需要事先核准。

### <a name="position-duration"></a>職位持續期間
每個職位都有職位有效的時間長度。 這個時間長度簡稱為持續間。 例如，暑假職位的持續期間可能是 2015 年五月 1 日到 2015 年八月 31 日。

### <a name="worker-assignments"></a>背景工作角色指派
當您指派背景工作角色給某個職位時，等於您填補該職位的空缺。 您可以指派背景工作角色給多個職位，但同時只能指派一名背景工作角色給某個職位。

### <a name="reporting-relationships"></a>回報關係
職位是組織階層架構中，較低等級的重要元素。 您可以在 **職位** 頁面上指明職位回報的職位。 當您指派背景工作角色到另一個主管職位時，等於您在被指派給兩個職位的背景工作角色之間建立回報關係。 例如，“會計 - A” 職位向 “會計主管” 職位回報。 Ana Bowman 被指派到 “會計主管” 職位，而 Felix Henderson 被指派到 “會計 - A” 職位。 這意味著 Felix Henderson 向 Ana Bowman 回報。 

如果貴組織使用矩陣階層架構或另一個自訂階層架構，您可以設定職位階層架構類型，然後新增回報關係到您設定每個階層架構類型的職位。 例如，Olivia Wilson 是 Adventure Works 的總經理，被指派到 "總經理" 職位。 Olivia 平日管理用來清理小程式的產品開發。 Olivia 需要會計幫助她產品開發的財務工作。 因此，她已經招募 Felix Henderson 擔任會計一職。 Felix 直接向 Ana Bowman 回報，但也搭配 Olivia Wilson 小程式清潔器開發的財務相關工作。 

以前例而言，您會完成下列任務才能設定 Felix Henderson 和 Ana Bowman 之間的工作關係：
1.  建立名為 "小程式" 的自訂職位階層架構類型就等於建立包括負責處理小程式清理產品職位的階層架構。
2.  指派總經理職位為 Widget 階層架構中，會計 - A 職位要回報的職位。

使用 **職位階層架構** 頁面檢視職位的回報架構。 如果您有多個職位階層架構，您可以檢視 **職位階層架構** 中，每種類型的階層架構。 您也可以按照職位識別碼或指派給該職位的背景工作角色姓名搜尋職位。 **職位階層架構** 是組織階層架構。

## <a name="date-effective-records"></a>日期生效記錄
某些記錄，您可以指明記錄未來將變更的內容。 下列資訊依生效日期決定效期。

<table>
<thead>
<tr class="header">
<th>記錄</th>
<th>生效日期資訊</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>工作</td>
<td><ul>
<li>一些詳細的工作資訊</li>
<li>工作分類資訊</li>
<li>薪酬資訊</li>
</ul></td>
</tr>
<tr class="even">
<td>職位</td>
<td><ul>
<li>一些詳細的職位資訊</li>
<li>背景工作角色指派</li>
<li>職位持續期間</li>
<li>職位階層架構</li>
</ul></td>
</tr>
</tbody>
</table>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
