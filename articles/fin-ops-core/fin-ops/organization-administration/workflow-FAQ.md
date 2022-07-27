---
title: 工作流程常見問題
description: 本主題回答有關工作流程系統的常見問題。
author: ChrisGarty
ms.date: 03/01/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0e9e2000684081035f35ea55e1c773a4f6976d74
ms.sourcegitcommit: 967b93bb42413b5b38b817f924015468312a93a0
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/01/2022
ms.locfileid: "8460184"
---
# <a name="workflow-faq"></a>工作流程常見問題

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

本主題回答有關工作流程系統的常見問題。

## <a name="why-are-multiple-notifications-received-when-a-work-item-is-rejected"></a>當一個工作項被拒絕時，為什麼會收到多個通知？
當一個工作項被拒絕時，該工作項作為被拒絕完成。 另一個工作項被建立並指派給發起者。 這代表對於被拒絕的工作項會向發起者發出通知，並向指派給新的「更改請求」工作項的使用者發出單獨的通知。 

每個通知都針對不同的工作項，但相似性可能會導致混淆。 我們正在尋找在未來版本中改進這一點的方法。

## <a name="why-are-my-workflow-exports-failing"></a>為什麼我的工作流程匯出失敗？
目前工作流程匯出功能存在限制，阻止工作流程名稱超過 48 個字元。 使用長度超過 48 個字元的名稱可能會導致「伺服器無法驗證請求」錯誤和/或阻止在沒有檔案類型的情況下匯出檔案。 以下部落格文章提供了更多詳情，[工作流程匯出疑難排解](https://community.dynamics.com/365/financeandoperations/b/elandaxdynamicsaxupgradesanddevelopment/posts/workflow-export-troubleshooting)。

## <a name="can-the-submitter-of-a-workflow-also-approve-the-workflow"></a>工作流程的送出者也可以核准工作流程嗎？
是，如果以這種方式設定，工作流程的送出者也可以核准工作流程。 為了防止這種行為，將 **系統管理 > 工作流程 > 工作流程參數 > 一般 > 核准者 > 不允許送出者核准** 設定到 **是**。

## <a name="can-i-add-alerts-to-workflows-to-provide-notifications-to-users"></a>我可以向工作流程新增警示以向使用者提供通知嗎？
以下是有關向工作流程新增警示以提供通知的幾個關鍵領域：
- 警示與工作流程通知機制
    - 可以為記錄更改設定警示。 工作流程更改記錄，因此可以設定與工作流程引起的記錄更改相關的警示。 但是，由於工作流程具有不同的內建通知選項，因此使用警示並不理想。
- 來自工作流程的標準通知 
    - 工作流程內建了電子郵件通知。 客戶可以設定通知，以便向使用者發送電子郵件。 這些通知不會為使用者產生動作中心訊息。
    - 在未來的更新中，我們將新增一個動作中心訊息，以便為使用者指派一個工作流程工作項。 
- 向工作流程新增通知
    - 可以為特定使用者建立動作中心訊息，例如從 X++ 中的工作流程建立的訊息。
    - [工作流程有商務事件](../../dev-itpro/business-events/business-events-workflow.md)客戶可以用來觸發流程有他們正在尋找的通知。   

總之，如果使用者在指派工作流程工作項時沒有從動作中心收到正確的通知，則可以利用 Microsoft Power Automate 的[工作流程商務事件](../../dev-itpro/business-events/business-events-workflow.md)來提供其他或不同的通知。

## <a name="why-is-workflow-editor-not-able-to-start-under-ad-fs"></a>為什麼工作流程編輯器無法在 AD FS 下啟動？
在升級環境中的 Active Directory 同盟服務 (AD FS) 下執行階段，工作流程編輯器可能無法啟動。 如果是，請確保將 URL「https://dynamicsaxworkfloweditor/」新增到 ADFS 設定中的 **Microsoft Dynamics 365 for Operations 內部 - 工作流程 - 本機應用程式** 屬性。

## <a name="why-am-i-getting-sql-deadlocks-on-workflow-processing"></a>為什麼我在工作流程處理中遇到 SQL 死鎖？ 
**工作流程參數** 頁面中 **每批次的工作流程項目數** 的預設欄位值為 0。 值 0 會導致預設值更改為每批 20 個項目。 調整此值時要小心，因為每個批次的大量項目 (> 40) 會導致 SQL 死鎖。

## <a name="what-is-the-workflow-enhanced-error-feature"></a>什麼是工作流程增強錯誤功能？
版本 10.0.13 中的工作流程增強錯誤功能新增了錯誤代碼以區分不同類別的工作流程錯誤。 報表的錯誤訊息將大體相似，略有不同，以使它們更清晰。


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
