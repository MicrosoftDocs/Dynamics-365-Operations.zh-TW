---
title: 建立承保範疇選項
description: 本主題說明參與者在福利計劃或專項計劃中，挑選的 Microsoft Dynamics 365 Human Resources 承保範疇選項。
author: twheeloc
ms.date: 08/24/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 01eb0c56578cf6f6b070c4a05768ec5361993555
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452169"
---
# <a name="create-coverage-options"></a>建立承保範疇選項


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

承保範疇選項判定應投保的對象，或者保險計劃中的承保範疇規模。 例如，醫療計劃方面，您可能會有 **限員工** 選項、**員工 + 1** 選項和 **全家** 選項。 而人壽保險方面，您可能會劃定 **1 x 薪資** 或 **2 x 薪資** 在承保範疇內。

定義福利涵蓋選項後，您可以重複使用。 您可以將選項與一項或多項計劃產生關聯。

> [!IMPORTANT]
> 定義承保範疇選項後，將它們附加到福利計劃類型。 接著計劃類型與福利計劃或專項計劃產生關聯。 與計劃類型關聯的承保範疇選項開放給已建立該類型的所有計劃使用。

## <a name="create-coverage-options"></a>建立承保範疇選項
1. 請在 **設定** 下方的 **福利管理** 工作區選取 **承保範疇選項**。

2. 選取 **新增**。

3. 請指定下列欄位值：

   | 欄位 | 描述 |
   | --- | --- |
   | **承保範疇選項** | 唯一的承保範疇選項名稱。 |
   | **描述** | 承保範疇說明。 |
   | **承保範疇代碼** | 承保範疇為每個具備資格的被保人類型指派最低和最高金額。 承保範疇代碼指出被保人或計劃類型允許的承保範疇金額。 您可以用美元金額或百分比表示承保範疇金額。 例如： <ul><li>**Emp+1** – 若要通過資格審查，員工必須選取一名家屬 (如果選取一名以上，他們不再符合資格)。</li><li>**員工+全家**– 若要通過資格審查，員工必須至少選取兩名家屬。</li></ul> |
   | **最多人數** | 最多家屬人數。 |
   | **狀態** | 承保範疇選項的狀態。 如果承保範疇選項狀態設定為 **無效**，即無法在計劃類型上選取承保範疇選項。 |
   | **百分比** | 百分比金額。 本欄位只有在承保範疇代碼欄位中選取 % x 薪資才有效。 |
   | **除數** | 當您選取承保範疇代碼 % x 薪資時，預計在計算中使用的除數。 |
   | **最低百分比** | 當您選取百分比承保範疇代碼時的最低百分比。 |
   | **最高百分比** | 當您選取百分比承保範疇代碼時的最高百分比。 |

4. 請在 **個人聯絡人資格選項** 下方，將適當的個人聯絡人資格選項附到每個承保範疇選項。

5. **自助服務** 下方的指定欄位值如下：

   | 欄位 | 描述 |
   | --- | --- |
   | **允許員工提撥金額** | 指定是否允許員工在選取福利時修改福利自助服務的提撥金額。 如果您選取這個勾選方塊，系統會根據員工在福利自助服務中輸入的提撥金額計算福利計劃參數。 |
   | **允許員工的承保範疇金額** | 指明是否允許員工在選取福利時修改福利自助服務的承保範疇金額。 如果您選取這個勾選方塊，系統會根據員工在員工自助服務中輸入的承保範疇金額計算福利計劃參數。 |

6. 選取 **儲存**。 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
