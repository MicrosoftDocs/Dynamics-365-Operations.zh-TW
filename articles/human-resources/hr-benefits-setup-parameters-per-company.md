---
title: 配置各間公司福利管理參數
description: 本主題說明在 Microsoft Dynamics 365 Human Resources 中配置各間個公司福利管理參數的方式。
author: twheeloc
ms.date: 8/24/2021
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
ms.search.validFrom: 2020-12-07
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: f6b3f068c9d3198afa8cd10aaa14bbc7ec9ef3c4
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452160"
---
# <a name="configure-benefits-management-parameters-per-company"></a>配置各間公司福利管理參數


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

對於每個提供福利的組織，您必須配置福利確認電子郵件的設定。

## <a name="configure-confirmation-email-settings"></a>配置確認電子郵件設定

1. 請在 **設定** 下方的 **福利管理** 工作區選取 **人力資源參數**。

2. 請在 **福利管理** 索引標籤中指定下列欄位值： 

   | 欄位 | 描述 |
   | --- | --- |
   | **傳送確認電子郵件** | 啟用此項功能後，當員工從 **員工自助服務** 的福利註冊歷程離開時，確認電子郵件會傳送給員工。 |
   | **確認電子郵件範本** | 選取傳送註冊確認時要使用的組織電子郵件範本。 如果您不選取範本，將傳送通用電子郵件如下：<br><br>%EmployeeFirstName%，<br><br>恭喜! 您已成功完成福利註冊。<br><br>謝謝您。<br><Company/Org name> 福利。 |
   | **預設電子郵件寄件人地址** | 當傳送確認電子郵件時要使用的電子郵件地址。 |

3. 選取 **儲存**。

[!INCLUDE[footer-include](../includes/footer-banner.md)]
