---
title: 評等級別
description: 本主題說明 Dynamics 365 Human Resources 的評等級別實體。
author: jaredha
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: a821e3cd90e85571da4a09f5dd564beb2de35989
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452475"
---
# <a name="rating-level"></a>評等級別


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

本主題說明 Dynamics 365 Human Resources 的評等級別實體。

實際名稱：mshr_hcmratinglevelentity

## <a name="description"></a>描述

本實體提供可用的技能評等級別。 評等級別適用所有法人實體。

## <a name="json-representation"></a>JSON 呈現

```json
{
    "mshr_description": "String",
    "mshr_factor": Int,
    "mshr_note": "String",
    "mshr_ratinglevelid": "String",
    "mshr_ratingmodelid": "String",
    "mshr_primaryfield": "String",
    "_mshr_fk_ratingmodelentity_id_value": "Guid",
    "mshr_hcmratinglevelentityid": "Guid"
}
```

## <a name="properties"></a>屬性

| 屬性<br>**實際名稱**<br>**_類型_** | 使用 | 描述 |
| --- | --- | --- |
| **評等級別實體 ID**<br>mshr_hcmratinglevelentityid<br>*GUID* | 唯讀<br>必要<br>系統產生 | 系統產生的唯一級別識別碼。 |
| **評等級別 ID**<br>mshr_ratinglevelid<br>*字串* | 讀/寫<br>必要 | 使用者可讀的唯一級別識別碼。 |
| **評等模型 ID**<br>mshr_ratingmodelid<br>*字串* | 讀/寫<br>必要 | 評等級別所屬的評等模型。 |
| **評等模型實體 ID**<br>_mshr_fk_ratingmodelentity_id_value<br>*GUID* | 唯讀<br>必要<br>外部金鑰：mshr_hcmratingmodelentity 的 mshr_hcmratingmodelentityid | 系統產生評等級別所屬的評等模型識別碼。 |
| **描述**<br>mshr_description<br>*字串* | 讀/寫<br>必要 | 評等級別說明。 |
| **因素**<br>mshr_factor<br>*整數* | 讀/寫<br>必要 | 評等級別因素。 當您比較評等級別不同的項目時，因素會用來標準化分數。 值必須為 0 到 9 的整數。 |
| **附註**<br>mshr_note<br>*字串* | 讀/寫<br>可選項目 | 與評等級別關聯的任何注釋。 |
| **主要領域**<br>mshr_primaryfield<br>*字串* | 唯讀<br>必要 | 預計當作實體記錄識別碼的欄位。 評等級別 ID 和評等模型 ID 組合。 |

## <a name="see-also"></a>也請參閱

[申請人追蹤系統整合 API 簡介](hr-admin-integration-ats-api-introduction.md)<br>
[聘雇候選人的範例查詢](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
