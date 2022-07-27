---
title: 識別和解決職責隔離中的衝突
description: 本主題說明如何識別和解決職責隔離中的衝突。
author: peakerbl
ms.date: 01/04/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SysSecSegregationOfDutiesConflict, SysSecSegregationOfDutiesRule
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0638699c0e569bbe67024a87d6c55729642557cb085ee899aa98aa0022b12840
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460538"
---
# <a name="identify-and-resolve-conflicts-in-segregation-of-duties"></a>識別和解決職責隔離中的衝突

[!include [banner](../../includes/banner.md)]

本主題說明如何識別和解決職責隔離中的衝突。 您可以設定規則來分隔必須由不同使用者執行的職責。 這個概念被命名為職責隔離。 當資訊安全角色的定義或使用者的角色指派違反規則時，將記錄衝突。 所有衝突都必須由系統管理員解決。 完成以下程序以識別和解決衝突。

新增規則後，驗證所有現有角色是否合規。 

## <a name="verify-that-existing-roles-and-duties-comply-with-new-rules-for-segregation-of-duties"></a>驗證現有角色和職責是否符合新的職責隔離規則
1. 進入 **系統管理** > **安全** > **職責隔離** > **職責隔離規則**。
3. 選取 **驗證職責與角色**。 如果任何角色違反規則，則會顯示一條訊息，其中包含規則名稱、角色和衝突職責的名稱。 必須使用 **安全設定** 修改衝突的角色，並且不能包含衝突的職責。 如果沒有角色違反所選規則，則會顯示一條訊息，指示所有角色都遵守。   

> [!NOTE]
> 僅對所選規則執行驗證。 驗證每條規則的合規性很重要。   

當您建立或修改角色時，將自動執行職責隔離規則。 您不能將相互衝突的職責指派給角色。

接下來，驗證所有現有角色指派是否合規。

## <a name="verify-that-user-role-assignments-comply-with-new-rules-for-segregation-of-duties"></a>驗證使用者角色指派是否符合職責隔離的新規則
1. 進入 **系統管理 > 安全 > 職責隔離 > 驗證使用者角色指派的合規性**。
2. 選取 **確定**。 通知會顯示驗證結果。 衝突記錄在 **職責隔離未解決的衝突** 頁面上。   

當您將使用者指派給角色時，將自動執行職責隔離規則。 如果您嘗試將使用者指派給包含衝突職責的角色，您會收到一條錯誤訊息。 然後，您必須透過拒絕或允許附加角色指派來解決衝突。 允許指派後將指派附加角色。 

> [!NOTE]
> 目前未針對根據 Active Directory 網域組指派角色的使用者驗證衝突。

## <a name="view-and-resolve-conflicting-user-role-assignments"></a>查看和解決衝突的使用者角色指派
1. 進入 **系統管理** > **安全** > **職責隔離** > **職責隔離未解決的衝突**。 
2. 選取一個衝突，然後選取以下動作之一： 

  - **否定性指派**：這將拒絕將使用者指派給其他資訊安全角色。 如果您拒絕自動指派角色，使用者將被標記為從角色中排除。 被排除的使用者不會被授予與該角色關聯的存取權限，並且在管理員刪除排除之前無法指派給該角色。 
-  **允許指派**：這將覆寫衝突並允許為使用者指派額外的安全角色。 如果您 **覆寫衝突**，則必須在覆寫原因欄位中輸入原因。 所有被覆寫的角色指派都可以在 **職責隔離衝突** 頁面上查看。  

> [!NOTE]
> 如果為同一使用者列出了多個衝突，請選取使用者記錄並在 **使用者** 頁面上評估指派的角色。 為避免此衝突，請在新增或修改每條規則後對其進行驗證。


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]