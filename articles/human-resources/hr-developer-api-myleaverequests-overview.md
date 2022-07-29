---
title: MyLeaveRequests 概觀
description: Microsoft Dynamics 365 Human Resources 中的 MyLeaveRequests 實體在系統提供請假要求清單，範疇 (限制) 限縮到目前查詢實體的使用者可存取的要求。
author: andreabichsel
ms.date: 02/03/2020
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 41ef8c6fc0e896e7f2cefd94801abab610083b81
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452664"
---
# <a name="myleaverequests-overview"></a>MyLeaveRequests 概觀


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Microsoft Dynamics 365 Human Resources 中的 MyLeaveRequests 實體在系統提供請假要求清單，範疇 (限制) 限縮到目前查詢實體的使用者可存取的要求。

## <a name="key"></a>機碼

  | 屬性名稱 | 資料類型 |
  |---------------|-----------|
  | dataAreaId    | 字串    |
  | RequestId     | 字串    |
  | LeaveType     | 字串    |
  | LeaveDate     | 日期      |
  
## <a name="properties"></a>屬性

  | 屬性名稱     | 資料類型 | 必要 |
  |-------------------|-----------|----------|
  | dataAreaId        | 字串    | X        |
  | RequestId         | 字串    | X        |
  | LeaveType         | 字串    | X        |
  | LeaveDate         | 日期      | X        |
  | ReasonCodeId      | 字串    |          |
  | PersonnelNumber   | 字串    | X        |
  | RequestDate       | 日期      | X        |
  | 註解           | 字串    |          |
  | 狀態            | 列舉      | X        |
  | 金額            | 里耳      |          |
  | HalfDayDefinition | 列舉      |          |

## <a name="actions"></a>動作

 | 動作名稱                               | 描述                                     |
 |-------------------------------------------|-------------------------------------------------|
 | [提交](hr-developer-api-myleaverequests-submit.md)   | 提交由工作流程處理的要求。 |

## <a name="see-also"></a>也請參閱

- [提交請假要求到工作流程](hr-developer-api-myleaverequests-submit.md)
- [驗證](hr-developer-api-authentication.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
