---
title: 休假類型
description: 本主題提供 Dynamics 365 Human Resources 裡休假類型實體細節和範例查詢。
author: marcelbf
ms.date: 06/25/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-06-25
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: dced58e6e9f6c20578e4582e4cf39162622713e7
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452595"
---
# <a name="leave-type"></a>休假類型


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

本主題說明 Dynamics 365 Human Resources 休假類型實體。

### <a name="description"></a>描述

本實體提供預訂休假類型的資訊。

實際名稱：mshr_essleavetypeentity。

## <a name="properties"></a>屬性

| 屬性</br>**實際名稱**</br>**_類型_** | 使用 | 描述 |
| --- | --- | --- |
| **休假類型識別碼**</br>mshr_leavetypeid</br>*字串* | 唯讀 | 休假類型識別碼。 |
| **描述**</br>mshr_description</br>*字串* | 唯讀 | 休假類型說明。 |
| **類別**</br>mshr_category</br>*mshr_LeaveTypeCategory 選項集合* | 唯讀 | 休假類型類別。 |
| **需要原因代碼**</br>mshr_isreasoncoderequired</br>*mshr_NoYes 選項集合* | 唯讀 | 定義休假類型是否需要原因代碼。 |
| **休假統一**</br>mshr_leaveamountunit</br>*mshr_LeaveAmountUnit 選項集合* | 唯讀 | 此休假類型的統一性。 |
| **啟用半天**</br>mshr_enablehalfdaydefinition</br>*mshr_NoYes 選項集合* | 定義休假類型是否啟用半天。 |
| **資料區識別碼**</br>mshr_dataareaid_id</br>*字串* | 唯讀 | 指定法人實體 (公司)。 |
| **休假類型實體**</br>mshr_essleavetypeentityid</br>*GUID* | 系統產生的 | 系統產生的 GUID 值可用來辨別唯一的休假類型。 |

## <a name="example-query"></a>範例查詢

**要求**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_essleavetypeentities?$filter=mshr_leavetypeid eq 'PTO'
```

**回應**

```json
{
    "mshr_leavetypeid": "PTO",
    "mshr_description": "Paid time off",
    "mshr_category": 200000000,
    "mshr_isreasoncoderequired": 200000000,
    "mshr_leaveamountunit": 200000000,
    "mshr_enablehalfdaydefinition": 200000000,
    "mshr_dataareaid": "usmf",
    "mshr_essleavetypeentityid": "00000a6c-0000-0000-0000-005001000000",
    "_mshr_dataareaid_id_value": null
}
```

## <a name="see-also"></a>也請參閱

[工資單整合 API 簡介](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
