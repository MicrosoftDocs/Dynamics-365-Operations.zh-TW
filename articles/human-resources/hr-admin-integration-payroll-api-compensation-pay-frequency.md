---
title: 薪酬支付頻率
description: 本主題提供 Dynamics 365 Human Resources 裡薪酬支付頻率實體細節和範例查詢。
author: marcelbf
ms.date: 09/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 171b7fb7b361bd1fe2e7e637cd555c88a81a8bcf
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452202"
---
# <a name="compensation-pay-frequency"></a>薪酬支付頻率


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

本主題說明 Dynamics 365 Human Resources 中的薪酬支付頻率實體。

實際名稱：mshr_hcmpayrateconversionentity。

### <a name="description"></a>描述

本實體提供有關預訂定薪酬支付頻率的工資率轉換資訊。

## <a name="properties"></a>屬性

| 屬性</br>**實際名稱**</br>**_類型_** | 使用 | 描述 |
| --- | --- | --- |
| **年薪支付率轉換**</br>mshr_annualconversionfactor</br>*十進位* | 唯讀 | 支付頻率的年轉換因子。 |
| **描述**</br>mshr_description</br>*字串* | 唯讀 | 轉換率說明。 |
| **時薪支付率轉換**</br>mshr_hourlyconversionfactor</br>*十進位* | 唯讀 | 支付頻率的小時換算因子。 |
| **月薪支付率轉換**</br>mshr_monthlyconversionfactor</br>*十進位* | 唯讀 | 付款頻率的月轉換因子。 |
| **支付率轉換**</br>mshr_payrateconversion</br>*字串* | 唯讀 | 用來辨別轉換率的唯一字串。 |
| **期間**</br>mshr_period</br>*期間選項集合* | 唯讀 | 預設支付率轉換的主要期間。 |
| **週薪支付率轉換**</br>mshr_weeklyconversionfactor</br>*十進位* | 唯讀 | 支付頻率的週轉換因子。 |
| **資料區識別碼**</br>mshr_dataareaid</br>*字串* | 唯讀 | 法人實體 (公司)。 |
| **薪酬支付頻率實體 ID**</br>mshr_dirpersonnamehistoricalentityid</br>*GUID* | 系統產生的 | 系統產生的全域唯一識別碼 (GUID) 值用來辨別唯一的記錄。 |

## <a name="example-query-for-payroll-employee"></a>工資單員工的範例查詢

**要求**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_hcmpayrateconversionentities?$filter=mshr_payrateconversion eq 'Annual' and mshr_dataareaid eq 'usmf'
```

**回應**

```json
{
    "mshr_annualconversionfactor": 1,
    "mshr_description": "Annual",
    "mshr_hourlyconversionfactor": 0.0004807692,
    "mshr_monthlyconversionfactor": 0.0833333333,
    "mshr_payrateconversion": "Annual",
    "mshr_period": 200000000,
    "mshr_weeklyconversionfactor": 0.0192307692,
    "mshr_dataareaid": "usmf",
    "mshr_hcmpayrateconversionentityid": "0000056e-0000-0000-b027-fef003000000",
    "_mshr_dataareaid_id_value": null
}
```

## <a name="see-also"></a>也請參閱

[工資單整合 API 簡介](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
