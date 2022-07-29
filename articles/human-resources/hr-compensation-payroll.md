---
title: 準備支付
description: 本主題顥示如何在 Dynamics 365 Human Resources 標示員工為準備支付。
author: marcelbf
ms.date: 08/25/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-07-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 825aa327cc1530675fad57be6fc1b4313f0cf998
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452508"
---
# <a name="ready-to-pay"></a>準備支付


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

> [!NOTE]
> 如果您希望標示員工為準備支付，您必須先在功能管理中啟用 **(預覽) 工資單整合** 功能。 更多有關啟用預覽功能的資訊，請參閱[管理功能](hr-admin-manage-features.md)。

本項功能促使人力資源專業人員理解已經準備好工資單處理的員工，以及由第三方工資單提供商使用之前需要採取行動的員工。

## <a name="mark-employee-as-ready-to-pay"></a>標示員工為準備支付

收集和驗證員工資訊既耗時又容易出錯。 借助為人力資源專業人員提供審查和輕鬆更新員工資訊的方式，Dynamics 365 Human Resources 有助於減少準備處理工資單所花費的時間。

標示員工為準備支付：

1. 打開 **薪酬管理**。 工作區有兩個圖格： 
    - **員工準備支付**
    - **員工尚未準備支付**
    ![薪酬管理工作區。](./media/hr-ready-to-pay-1-workspace.png)

2. 請選取 **員工尚未準備支付** 圖格。

3. 請選取要驗證的員工。 請在 **準備支付** 群組的 **工資單索引標籤** 選取 **驗證**。
    ![驗證員工。](./media/hr-ready-to-pay-2-validate.png)

4. 若要審查結果，請在 **準備支付** 群組的 **工資單索引標籤** 選取 **結果**。

## <a name="validation"></a>驗證

標示員工為準備支付之前，將驗證員工的訂定檔是否完整。

![驗證結果。](./media/hr-ready-to-pay-3-results.png)

| 驗證 | 詳細資料​​ |
| --- | --- |
| **地址用途參數** | 確認已選取 **使用工資單地址用途** 參數。 |
| **工資單地址** | 確認工作人員設定檔至少有一個地址的用途是 **工資單居住位置** 或 **工資單工作位置**，並且每個用途只有一個地址。 |
| **雇用** | 確認背景工作角色至少已經就業一份工作 (現職、以前或未來)。 |
| **身份識別號碼** | 確認 **人力資源參數** 頁面上的 **在工資單處理中使用識別類型** 欄位為 **是**，以及參數中指示的識別類型是否填寫在背景工作角色設定檔。 |
| **名字和姓氏** | 確認已填寫 **名字** 和 **姓氏** 欄位。|
| **職位** | 確認背景工作角色的職位已經指派。 |
| **生日** | 確認已經填寫 **生日** 欄位。 |
| **薪酬** | 確認背景工作角色已註冊固定薪酬計劃。 |

如果其中一項驗證失敗，您就無法標示員工為準備支付。

如果 **準備支付** 欄位為 **否**，指出您必須執行動作以確保背景工作角色設定檔完整無缺。 這將不會阻止資料在任何資料實體中公開。 

## <a name="process-automation"></a>流程自動化

您可以藉由使用[流程自動化](/dynamics365/fin-ops-core/dev-itpro/sysadmin/process-automation) 自動驗證所有員工。 請在 **薪酬管理** 工作區中，前往 **連結**\>**參數**\>**流程自動化**。

## <a name="see-also"></a>也請參閱

[工資單整合 API 簡介](hr-admin-integration-payroll-api-introduction.md)<br>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
