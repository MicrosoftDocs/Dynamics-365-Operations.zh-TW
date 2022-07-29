---
title: 篩選頻率來源
description: 本主題說明 Dynamics 365 Human Resources 選項集合產生的篩選頻率。
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
ms.openlocfilehash: 27c6c62f3ac312ee502df969f25f1b16761cba03
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452397"
---
# <a name="screening-frequency-generate-from"></a>篩選頻率來源


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

本主題說明 Dynamics 365 Human Resources 選項集合產生的篩選頻率。

實際名稱：mshr_hcmfrequencygeneratefrom

此列舉項目提供判定下次篩選時，計算開始日期所需的選項值集合。

| 值 | 標籤 | 描述 |
| --- | --- | --- |
| 未選取 200000000 | 尚未選取任何值。 |
| 200000001 完成日期 | 從前次篩選完成之日起計算。 |
| 200000002 要求日期 | 從前次要求篩選完成之日起計算。 |

## <a name="see-also"></a>也請參閱

[申請人追蹤系統整合 API 簡介](hr-admin-integration-ats-api-introduction.md)<br>
[聘雇候選人的範例查詢](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
