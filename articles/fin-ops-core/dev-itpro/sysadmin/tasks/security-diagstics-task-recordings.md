---
title: 工作記錄的安全診斷
description: 本主題提供有關如何根據工作記錄分析和管理安全權限要求的資訊。
author: Peakerbl
ms.date: 05/05/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: ''
ms.dyn365.ops.version: Version 10.0.9
ms.openlocfilehash: 44af35f16f6e9ff89b30bc10eef3f16ecdfaf907c4c6e22aa5775d1941fb6a5d
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460536"
---
# <a name="security-diagnostics-for-task-recordings"></a>工作記錄的安全診斷

[!include [banner](../../includes/banner.md)]

## <a name="before-you-begin"></a>在您開始之前

本主題提供有關如何根據工作記錄分析和管理安全權限要求的資訊。 在完成本主題中的步驟之前，您必須擁有要分析的業務流程的工作記錄。 若要記錄商業流程，請參閱[工作記錄器資源](../../user-interface/task-recorder.md)。 

## <a name="manage-security-for-a-task-recording"></a>管理工作記錄的安全性

1. 進入 **系統管理** > **安全性** > **工作記錄的安全診斷**。
2. 從其位置打開工作記錄。 選取 **從這台電腦開啟** 或 **從 Lifecycle Services 開啟**，然後選取 **關閉**。
3. 這將開啟 **安全選單項詳情** 頁面，其中列出了該過程所需的安全對象。

 > [!NOTE]
 > **動作** 和 **輸出** 選單項不包含在清單中。

4. 在 **使用者識別碼** 欄位中，選取一個使用者。 如果使用者對某些選單項沒有權限，則 **缺少權限** 欄位將更新為 **是**。
  
  ![安全選單項詳情頁面。](../media/Security-Menu-Item-Details.png)

5. 選取 **新增參考** 查看安全物件清單，包括授予缺失權限的角色、職責和特權。
6. 從清單中選取一個安全物件：

    - 如果已選取 **角色**，選取 **為使用者新增角色**。 這將開啟 **將使用者指派給角色** 頁。 如需相關資訊，請參閱[為使用者指派資訊安全角色](assign-users-security-roles.md)頁面。
    - 如果已選取 **職責**，選取 **為角色新增職責**，選取應新增職責的角色，然後選取 **確定**。
    - 如果已選取 **權限**，選取 **為職責新增權限**，選取應新增職責的角色，然後選取 **確定**。


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]