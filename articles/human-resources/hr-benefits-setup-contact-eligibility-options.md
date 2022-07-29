---
title: 配置個人聯絡人資格選項
description: 本主題說明在 Microsoft Dynamics 365 Human Resources 中配置個人聯絡人資格選項的方式。
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
ms.openlocfilehash: ad9dc9d12bcc419c3925b0f78566d9f3eb0a1e35
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452625"
---
# <a name="configure-personal-contact-eligibility-options"></a>配置個人聯絡人資格選項


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

本主題說明如何配置可在 Microsoft Dynamics 365 Human Resources 福利使用的個人聯絡人類型。 個人聯絡人是將涵蓋於您的計劃之下的個人 (家屬) 或將從您的計劃受益的個人 (受益人)。 典型家屬是配偶或子女。 受益人則是配偶、子女、受託人或父母。

1. 請在 **設定** 下的 **福利管理** 工作區選 **個人聯絡人資格選項**。

2. 選取 **新增**。

3. 請指定下列欄位值：

   | 欄位 | 描述 |
   | --- | --- |
   | **資格選項** | 用來辨別資格選項的唯一資格選項名稱或代碼。 |
   | **描述** | 資格選項的簡要說明。 |
   | **聯絡人資格代碼** | 最能說明個人資格選項的系統代碼。 您可以從下方選擇： <ul><li>關聯</li><li>學生</li><li>超額家屬</li><li>超齡失能家屬</li></ul> |
   | **狀態** | 資格選項的狀態。 如果資格選項的狀態設定為無效，則您無法為個人聯絡人選取個人聯絡人資格選項。 |
   | **關聯** | 指定個人聯絡人和員工之間的關係。 唯有聯絡人資格代碼設定為關係時，本欄位才有效。 |
   | **年齡** | 福利計劃的具備資格個人聯絡人的最大年齡。 本欄位只在您選取關係時才有效。 將此年齡比較個人聯絡人的計算年齡。 計算的年齡為：(承保範疇的日期 - 個人聯絡人出生日期/ 365)。 此數字始終是整數。 |

4. 選取 **儲存**。 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
