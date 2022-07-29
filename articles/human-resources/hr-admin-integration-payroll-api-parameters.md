---
title: 工資單整合參數
description: 本主題說明 Dynamics 365 Human Resources 工資單整合參數。
author: marcelbf
ms.date: 06/17/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-06-17
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 37d4dc52e7fe5ddd95f43d98267db819a275bd92
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452592"
---
# <a name="payroll-integration-parameters"></a>工資單整合參數


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

使用 Dynamics 365 Human Resources 工資單整合之前，您必須先設定本主題說明的參數。

## <a name="enable-payroll-address"></a>啟用工資單地址

為了能夠使用工資單地址，您必須從工資單整合索引標籤上的[共用參數表單](hr-setup-shared-parameters.md)啟用。

## <a name="define-the-identification-type"></a>定義標識類型

為了在[工資單員工實體](hr-admin-integration-payroll-api-payroll-employee.md)中揭露辨識類型識別碼，你必須針對每間公司[配置人力資源參數](hr-setup-shared-parameters.md)。

1. 請在連結下方的 **薪酬管理** 工作區選取 **人力資源參數**。 
2. 請在 **工資單整合** 索引標籤上指明下列欄位值。

| 欄位 | 描述 |
| --- | --- |
| 請在工資單處理中使用標識類型 | 選取此選項後，選取類型識別碼將在工資單員工實體中揭露。 |
| 辨識類型 | 將在 [工資單員工實體](hr-admin-integration-payroll-api-payroll-employee.md) 的 **mshr_payrollemployeeentityid** 欄位揭露的標識類型。 |

## <a name="see-also"></a>也請參閱

[工資單整合 API 簡介](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
