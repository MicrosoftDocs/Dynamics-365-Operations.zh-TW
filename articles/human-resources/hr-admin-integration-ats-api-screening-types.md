---
title: 篩選類型
description: 本主題說明 Dynamics 365 Human Resources 的篩選類型實體。
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
ms.openlocfilehash: bcbf22aac78f1ff96edb7dd927721453f8d10fa5
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452391"
---
# <a name="screening-types"></a>篩選類型


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

本主題說明 Dynamics 365 Human Resources 的篩選類型實體。

實際名稱：mshr_hcmscreeningtypeentity

## <a name="description"></a>描述

本實體說明公司針對就業前和正在進行的員工篩選流程設定的篩選類型。

## <a name="json-representation"></a>JSON 呈現

```json
{
    "mshr_description": "String",
    "mshr_frequencyunit": Int,
    "mshr_generatefrom": Int,
    "mshr_frequencyinterval": Int,
    "mshr_screeningtypeid": "String",
    "mshr_hcmscreeningtypeentityid": "Guid"
}
```

## <a name="properties"></a>屬性

| 屬性<br>**實際名稱**<br>**_類型_** | 使用 | 描述 |
| --- | --- | --- |
| **篩選類型實體 ID**<br>mshr_hcmscreeningtypeentityid<br>*GUID* | 唯讀<br>必要<br>系統產生 | 唯一的篩選類型記錄主要識別碼。 |
| **篩選類型 ID**<br>mshr_screeningtypeid<br>*字串* | 讀/寫<br>必要 | 使用者定義的唯一篩選類型識別碼。 |
| **描述**<br>mshr_description<br>*字串* | 讀/寫<br>必要 | 篩選類型說明。 |
| **頻率單位**<br>mshr_frequencyunit<br>*mshr_hcmfrequencyunit 選項集合* | 讀/寫<br>必要 | 描述須為指派人員完成篩選的頻率。 |
| **產生來源**<br>mshr_generatefrom<br>*mshr_hcmfrequencygeneratefrom 選項集合* | 讀-寫<br>必要 | 如果頻率值是 “一次性” 以外的任何值，則 GenerateFrom 值會判定計算下次篩選事件的日期。 |
| **頻率間隔**<br>mshr_frequencyinterval<br>*整數* | 讀-寫<br>必要 | 如果頻率值是 “一次性” 以外的任何值，您必須針對每個篩選事件之間的時間單位定義間隔。 |

## <a name="see-also"></a>也請參閱

[申請人追蹤系統整合 API 簡介](hr-admin-integration-ats-api-introduction.md)<br>
[聘雇候選人的範例查詢](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
