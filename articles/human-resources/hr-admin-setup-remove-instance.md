---
title: 移除執行個體
description: 本主題帶您完成移除 Microsoft Dynamics 365 Human Resources 的試用產品或實際執行環境的流程。
author: twheeloc
ms.date: 08/11/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SystemAdministrationWorkspaceForm
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: e32058280d0cb1eab436bc25bd29bc3e39fabc92
ms.sourcegitcommit: 49f7528d3268abe15e40f719956e1ec8696a6f4e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/18/2021
ms.locfileid: "8451938"
---
# <a name="remove-an-instance"></a>移除執行個體

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

本主題說明移除 Microsoft Dynamics 365 Human Resources 的試用產品或實際執行環境的流程。

## <a name="remove-a-test-drive-environment"></a>移除試用產品環境

人力資源試用產品佈建 60 天的到期政策。 然而試用產品環境的所有人可以選擇完成下列步驟提早結束試用。 

1. 導航到 [Power Apps 管理中心](https://admin.businessplatform.microsoft.com/)。
2. 選取 **環境**。
3. 選取試用產品環境，命名型態類似：TestDrive - alias@domain
4. 選取 **刪除** 並確認此決策。 

將移除既有的試用產品環境。 移除後，您就可以註冊新試用產品環境。 

## <a name="remove-a-production-environment"></a>移除實際執行環境

本主題假定您已經透過雲端解決方案提供者 (CSP) 或企業架構 (EA) 協議購買人力資源。 

既然單一人力資源環境包含在單一 Power Apps 環境裡，目前有兩個考量選項。 第一個選項涉及移除整個 Power Apps 環境；第二個選項涉及只移除人力資源。 當您已經建立 Power Apps 環境明確用於佈建人力資源目的，並且才剛開始落實或者尚未建立任何整合時，第一個選項是首選。 第二個選項適合用在您已經使用在 Power Apps 和 Power Automate 有效率調控填滿的豐富資料所建立的 Power Apps。

> [!Important]
> 移除 Power Apps 環境之前，確保它不用在人力資源範圍的豐富資料整合。 同時也要注意無法移除預設的 Power Apps 環境。 

若要移除整個 Power Apps 環境，包括人力資源和相關應用程式與流程：

1. 導航到 [Power Apps 管理中心](https://admin.businessplatform.microsoft.com/)。
2. 選取 **環境**。
3. 選取要移除的環境。
4. 選取 **刪除** 並確認此決策。 
5. 等到移除完成為止。
6. 使用您用來訂閱人力資源的帳戶登入 [Lifecycle Services](https://lcs.dynamics.com/Logon/Index) (LCS)。 
7. 選取包含環境的人力資源專案。 
8. 請在您的 LCS 專案選取 **人力資源 App 管理** 圖格。 
9. 選取要移除的執行個體。 
10. 選取 **移除執行個體** 並確認您的決定。  

若要從既有的 Power Apps 環境移除人力資源環境，請完成下列步驟。 須注意的是，直接在 LCS 啟用本功能之前，必須暫時支援與聯絡人力資源 DevOps 團隊。

1. 聯絡支援團隊發起移除要求。
2. 支援團隊將向人力資源 DevOps 團隊發起移除要求。 
3. 獲知環境已經移除的消息後繼續。
4. 使用您用來訂閱人力資源的帳戶登入 LCS。 
5. 選取包含環境的人力資源專案。 
6. 請在您的 LCS 專案選取 **人力資源 App 管理** 圖格。 
7. 選取您希望移除的執行個體，此個體應標示為 **已刪除** 的部署狀態。
8. 選取 **移除執行個體** 並確認您的決定。 

## <a name="recover-a-soft-deleted-environment"></a>恢復軟刪除的環境

如果您刪除人力資源環境連接的 Power Apps 環境，Lifecycle Services 裡的人力資源環境狀態將為 **軟刪除**。 此時使用者無法連接人力資源。

若要恢復環境：

1. 請按照[恢復 Power Apps 環境](/power-platform/admin/recover-environment.md) 的說明操作。

2. 聯絡支援團隊恢復人力資源環境。 更多資訊，請參閱[取得支援](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md)。

> [!Warning]
> Power Apps 環境只能在刪除後儲存七日。 您必須在七日內恢復環境。


[!INCLUDE[footer-include](../includes/footer-banner.md)]
