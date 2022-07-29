---
title: 大規模錄用專案
description: 本主題說明大規模錄用項目，允許人力資源專家建立多個職位並有效地錄用背景工作角色進入這些職位工作。
author: twheeloc
ms.date: 10/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HRMMassHireProject, HcmPersonnelManagementWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7481
ms.assetid: 5f5eb271-76eb-4305-bd1c-5d171dafccc9
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fcfc973dc9acea624336f059d68562fa5eb41353
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452610"
---
# <a name="mass-hire-projects"></a>大規模錄用專案


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



大規模錄用專案允許人力資源專家建立多個職位並有效地錄用背景工作角色進入這些職位工作。

## <a name="overview"></a>概觀

當您一次錄用多名背景工作角色時，例如當您錄用以便滿足季節性需求時，請使用大規模錄用專案。 建立大規模錄用專案很實用，因為您可以針對職位同時建立職位記錄、背景工作角色記錄和背景工作角色指派。 當您為大規模錄用專案建立職位時，您可以指明的資訊如下：

- 預計建立的職位數目
- 您將針對這些職位錄用人員的背景工作角類型
- 與職位關聯的部門和工作
- 職位的全職等效值

## <a name="example"></a>範例

夏季，您通常會僱用 15-20 名兼職大學生填補貴公司的實習職缺。 今年，您想錄用五名會計師、五名訂單處理員和五名收銀員。 有別於分開建立每筆職位記錄和背景工作角色記錄，您反而是建立一個名為 “SummerInterns” 的大規模招募專案。 專案開始日期和結束日期攸關您針對大規模錄用專案建立職位持續時間的開始日期和結束日期。

請在 **大規模錄用專案** 頁面上選取 **SummerInterns** 專案，然後選取 **打開專案**。 請在大規模開放式錄用專案中選取 **建立職位**，並輸入有關會計職位的資訊。 您可以指明應該建立的五個會計職位，以及每個職位應使用的相同資訊。 然後選取 **確定**。 針對訂單處理器和收銀員職位重覆這段流程。

待您選取預計錄用實習職缺的學生後，您將在錄用職位的細節中輸入每位學生的資訊。 當您已經輸入所有職位細節後，請在 **大規模錄用專案** 頁面上選取職位和 **錄用**。 職位記錄將針對每個職位建立，也將建立背景工作角色記錄並指派給您錄用每個人的正確職位。

## <a name="mass-hire-project-statuses"></a>大規模錄用專案狀態

大規模錄用專案狀態如下。

- 已建立
- 開啟
- 已結案

請在 **大規模錄用專案** 頁面上選取 **打開專案** 或 **關閉項目**，以變更大規模錄用專案的狀態。 下表說明您可以根據狀態對專案執行的動作。

<table>
<thead>
<tr>
<th>狀態</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr>
<td>已建立</td>
<td>您可以建立和修改資訊，但不能針對專案建立職位。 這是新專案的預設狀態。</td>
</tr>
<tr>
<td>開啟</td>
<td>您可以修改專案細節、針對大規模錄用專案建立職位，並為職位錄用人員。 這是有效專案的狀態。</td>
</tr>
<tr>
<td>已結案</td>
<td><p>您不能新增職位到專案中。 若要新增職位到大規模錄用專案，請再打開一次專案。 這是已完成專案的狀態。</p>
<p><strong>註記：</strong>在您可以關閉大規模錄用專案之前，專案中的所有職位狀態必須是<b>已建立</b>或<b>已關閉</b>。</p>
</td>
</tr>
</tbody>
</table>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
