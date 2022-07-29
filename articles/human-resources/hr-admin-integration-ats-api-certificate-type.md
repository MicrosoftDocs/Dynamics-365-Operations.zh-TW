---
title: 證書類型
description: 本主題說明 Dynamics 365 Human Resources 的證書類型實體。
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
ms.openlocfilehash: 3d01c7f01657af1501aed14f63dfb2cfbc133f8b
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452319"
---
# <a name="certificate-type"></a>證書類型


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

本主題說明 Dynamics 365 Human Resources 的證書類型實體。

實際名稱：mshr_hcmcertificatetypeentity

## <a name="description"></a>描述

本實體定義人力資源設定的專業證書類型清單。 此實體並非法人實體 (公司) 專有。

## <a name="json-representation"></a>JSON 呈現

```json
{
    "mshr_certificatetype": "String",
    "mshr_description": "String",
    "mshr_requirerenewal": Int,
    "mshr_hcmcertificatetypeentityid": "Guid"
}
```

## <a name="properties"></a>屬性

| 屬性<br>**實際名稱**<br>**_類型_** | 使用 | 描述 |
| --- | --- | --- |
| **證書類型實體 ID**<br>mshr_hcmcertificatetypeentityid<br>*GUID* | 唯讀<br>必要 
系統產生 | 唯一的證書類型主要識別碼。 |
| **證書類型**<br>mshr_certificatetype<br>*字串* | 讀/寫<br>必要 | 唯一的證書類型用戶可讀識別碼。 |
| **描述**<br>mshr_description<br>*字串* | 讀/寫<br>必要 | 證書類型的描述。 |
| **需要更新**<br>mshr_requirerenewal<br>*mshr_noyes 選項集合* | 讀/寫<br>可選項目 | 指明證書是否需要更新。 |

## <a name="see-also"></a>也請參閱

[申請人追蹤系統整合 API 簡介](hr-admin-integration-ats-api-introduction.md)<br>
[聘雇候選人的範例查詢](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
