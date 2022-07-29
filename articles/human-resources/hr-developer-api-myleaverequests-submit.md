---
title: 提交請假要求到工作流程
description: 您可以在 Microsoft Dynamics 365 Human Resources 使用 MyLeaveRequests submit() 應用程式的撰寫程式介面 (API) 提交請求要求到工作流程。
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: f9ca716f37b90e22983b2dddc2c426a2b4e251ec
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452361"
---
# <a name="submit-a-leave-request-to-workflow"></a>提交請假要求到工作流程


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

您可以在 Microsoft Dynamics 365 Human Resources 使用 MyLeaveRequests submit() 應用程式的撰寫程式介面 (API) 提交請求要求到工作流程。 在 MyLeaveRequests OData 實體上，此 API 會以動作形式公開。

## <a name="prerequisites"></a>先決條件

請假要求必須在資料庫儲存，並且必須可透過 MyLeaveRequests 實體檢索。

## <a name="permissions"></a>權限

呼叫此 API 需要下列其中一個權限。 更多有關權限以及選取方式的資訊，請參閱[驗證](hr-developer-api-authentication.md)。

| 權限類型                    | 權限 (從最少權限到最多權限) |
|------------------------------------|--------------------------------------------------------|
| 已委託 (工作或學校帳戶) | 使用者\_冒名頂替                                    |

## <a name="https-request"></a>HTTPS 要求

<!-- { "blockType": "ignored" } -->
```HTTP
POST https://{cluster}.hr.talent.dynamics.com/namespaces/{namespace_guid}/data/MyLeaveRequests(RequestId='{requestId}', LeaveType='{leaveType}', LeaveDate={leaveDate}, dataAreaId={dataArea})/Microsoft.Dynamics.DataEntities.submit?cross-company=true
```

此項要求遵守 OData 標準。 {requestId}、{leaveType}；{leaveDate}，和 {dataArea} 參數指的是組成 MyLeaveRequests 實體的合成自然鍵欄位。

> [!NOTE]
> 由於 MyLeaveRequests 實體欄位指的是請假要求中的個別行項，但呼叫提交 API 會將整個請假要求 (所有行項) 提交到工作流程。

### <a name="request-headers"></a>要求標頭

| 頁首         | 值                     |
|----------------|---------------------------|
| 授權  | 持有人 {token} (必要) |
| 內容-類型   | 應用程式/json          |

### <a name="request-body"></a>要求本文

不提供此方法的要求本文。

### <a name="response"></a>回應

成功的回應總是 **204 無內容** 回應。

未經授權的來電者將收到 **401 未授權** 或 **403 禁止** 回應。

如果提交不成功 (例如因為驗證緣故)，回應將是 **500 伺服器錯誤**，並且回應本文將包括含有進一步細節的 JSON 對象。

## <a name="example"></a>範例

```http
POST https://aos-rts-sf-550e5c091f6-prod-westus2.hr.talent.dynamics.com/namespaces/b2eb8003-334f-4a84-ab63-edbe23569090/data/MyLeaveRequests(RequestId='USMF-000065', LeaveType='Vacation', LeaveDate=2019-10-04T12:00:00Z, dataAreaId='USMF')/Microsoft.Dynamics.DataEntities.submit
```

```json
{
  "error": {
    "code": "",
    "message": "An error has occurred.",
    "innererror": {
      "message": "Exception occurred while executing action submit on Entity MyLeaveRequest: The request would put the 'Vacation' balance below the allowed minimum balance on 9/10/2019.",
      "type": "System.InvalidOperationException",
      "stacktrace": "   at Microsoft.Dynamics.Platform.Integration.Services.OData.Action.ActionInvokable.Invoke()   at Microsoft.Dynamics.Platform.Integration.Services.OData.Update.UpdateProcessor.ActionInvocation(ChangeOperationContext context, ActionInvokable action)   at Microsoft.Dynamics.Platform.Integration.Services.OData.Update.UpdateManager.<>c__DisplayClass13_0.<ScheduleInvokable>b__0(ChangeOperationContext context)   at Microsoft.Dynamics.Platform.Integration.Services.OData.Update.ChangeInfo.ExecuteActionsInCompanyContext(IEnumerable`1 actionList, ChangeOperationContext operationContext)\r\n   at Microsoft.Dynamics.Platform.Integration.Services.OData.Update.ChangeInfo.ExecuteActions(ChangeOperationContext context)   at Microsoft.Dynamics.Platform.Integration.Services.OData.Update.UpdateManager.SaveChanges()   at Microsoft.Dynamics.Platform.Integration.Services.OData.AxODataDelegatingHandler.<SaveChangesAsync>d__3.MoveNext()"
    }
  }
}
```

## <a name="validation-and-error-messages"></a>驗證與錯誤訊息

作為呼叫提交 API 的一部分，人力資源部會在提交之前執行業務邏輯驗證，確保請假要求在有效提交的狀態。 如果驗證失敗，您可能在回應中收到可能的錯誤訊息如下：

 - 要求會把 '{LeaveTypeId}' 餘額放置在 {date} 當天允許的最低餘額。
 - 無法提交在已完成狀態的休假要求。
 - 由於尚未進行任何更改，因此無法提交或儲存要求。 新增或更新金額或請假類型，並且再試一次。
 - 輸入的休假要求包含與既有待核准要求相同日期和請假類型的一日或多日。 請重新叫用既有的更改要求。
 - 原因代碼 '{ReasonCodeId}' 不適用要求中的任何請假類型。
 - 請假類型 '{LeaveTypeId}' 需要原因代碼。 選取適當類型和原因代碼。
 - 休假提交不成功。 休假已儲存為草稿要求。

## <a name="see-also"></a>也請參閱

- [MyLeaveRequests 概觀](hr-developer-api-myleaverequests-overview.md)
- [驗證](hr-developer-api-authentication.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
