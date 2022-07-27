---
title: 讓使用者能夠接收與工作流程相關的電子郵件
description: 您可以將系統設定為在發生與工作流程相關的事件時向使用者發送電子郵件。
author: jasongre
ms.date: 06/01/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SysUserManagement, SysUserSetup
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 368fe2fbf1f8a1adcabe37ced5ed942f9fb86fc8
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8460186"
---
# <a name="enable-users-to-receive-workflow-related-email-messages"></a>讓使用者能夠接收與工作流程相關的電子郵件

[!include [banner](../../includes/banner.md)]


[!INCLUDE [PEAP](../../../../includes/peap-1.md)]

您可以將系統設定為在發生與工作流程相關的事件時向使用者發送電子郵件。 例如，當將文件指派給使用者以供核准時，可以將電子郵件訊息發送給使用者。 用來建立此程序的示範資料公司為 USMF。

1. 前往 **瀏覽窗格 > 模組 > 系統管理 > 使用者 > 使用者**。
2. 在清單中，尋找並選取所需的記錄。
3. 在 **動作窗格** 上，點選 **使用者選項**。
4. 點選 **工作流程** 索引標籤。確保 **通知** 區塊已展開。 在 **通知** 區塊，您可以指定希望使用者如何收到有關工作流程相關事件的通知。  
5. 在 **訂單項工作流程通知類型** 欄位，選取一個選項。
    - 分組 - 訂單項的通知被分組到單個電子郵件訊息中。
    - 個人 – 為每個訂單項發送一封電子郵件。  
    - 如果您希望使用者在客戶端中接收通知，請選取 **在電子郵件中發送通知** 核取方塊。  
6. 選取 **儲存**。
7. 關閉頁面。

> [!NOTE]
> 工作流程電子郵件範本將來自系統電子郵件範本或組織電子郵件範本，具體取決於工作流程是系統級 (非公司特定) 還是組織級 (公司特定) 工作流程。


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]