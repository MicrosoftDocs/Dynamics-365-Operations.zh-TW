---
title: 設定彈性點數計劃
description: 您可以在 Microsoft Dynamics 365 Human Resources 中根據預定的彈性點數使用彈性點數專項在福利註冊員工。
author: andreabichsel
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitCreditPrograms, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 8f28e3fb603fde2c19669e9936ea0bdcfc866d0e
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452175"
---
# <a name="set-up-flex-credit-programs"></a>設定彈性點數計劃


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

您可以在 Microsoft Dynamics 365 Human Resources 中根據預定的彈性點數使用彈性點數專項在福利註冊員工。 員工可以選擇分配他們的彈性點數方式。 例如，如果員工涵蓋在其配偶的醫療保健計劃範圍內，他們可能希望將原本用在醫療保健的點數用在其他福利。 

1. 請在 **計劃** 下方的 **福利管理** 工作區選取 **彈性點數專項計劃**。

2. 選取 **新增**。

3. 請指定下列欄位值：

   | 欄位 | 描述 |
   | --- | --- |
   | **福利點數識別碼** | 唯一的彈性點數專項計劃識別碼。 |
   | **描述** | 彈性點數專項計劃說明。 | 
   | **開始日期** | 彈性點數專項計劃的有效日期。 |
   | **結束日期** | 彈性點數專項計劃的結束日期。 您可以保留預設值 (12/31/2154) 指出彈性點數專項計劃尚未排程的到期時間。 |
   | **總點數值** | 每位員工將用於福利的點數。 |
   | **比例規則** | 當員工在彈性點數期間中間被錄用時，用於比例分配彈性點數的規則。 </br></br><ul><li>**無** – 如果員工在彈性點數專案計劃期間開始後被錄用，不會收到彈性點數。</li><li>**全部點數** – 不論何時被錄用，員工都會收到完整彈性點數。</li><li>**按比例分配** – 員工根據他們的開始日期收到按比例分配的彈性點數。</li></ul> |
   | **彈性點數比例分配公式** | 當員工在彈性點數期間中間被錄用時，用於比例分配彈性點數的規則。 比例是以就業開始日期為基礎。 本欄位只用在您選取 **比例規則** 欄位中的 **按比例分配** 時。 </br></br><ul><li>**日常** – 將員工收到的彈性點數按每日等級比例分配。 彈性總點數除以該期間的天數。 例如，如果您的福利期間為 400 天，系統會將彈性總點數除以 400 計算員工每天獲得的彈性點數。</li><li>**當月** – 將員工收到的彈性點數按月份等級比例分配，四捨五入到當月。 彈性總點數除以該期間的月份數。 例如，如果您的福利期間為 15 個月，系統會將彈性總點數除以 15 計算員工每個月獲得的彈性點數。</li><li>**隔月** – 將員工收到的彈性點數按月份等級比例分配，四捨五入到隔月。 彈性總點數除以該期間的月份數。 例如，如果您的福利期間為 15 個月，系統會將彈性總點數除以 15 計算員工每個月獲得的彈性點數。</li></ul> |
   


[!INCLUDE[footer-include](../includes/footer-banner.md)]
