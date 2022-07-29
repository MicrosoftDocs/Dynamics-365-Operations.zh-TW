---
title: 設定租賃核准工作流程
description: 本主題說明如何設定在建立新租賃時將執行的核准工作流程。
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WorkflowTableListPageRnr
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 2f99bb480e6ee2314852965ab9559bae2ad348fb92514d791fca127d91558348
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450336"
---
# <a name="set-up-lease-approval-workflows"></a>設定租賃核准工作流程

[!include [banner](../includes/banner.md)]

本主題說明如何設定在建立新租賃時將執行的核准工作流程。 如需有關如何使用工作流程的資訊，請參閱[使用租賃核准工作流程](use-create-lease-wrkflw.md)。 

1. 前往 **資產租賃 \> 設定 \> 租賃工作流程**。
2. 在 **租賃工作流程** 頁面選取 **新增**。
3. 在顯示的對話方塊中，在 **工作流程** 下方，選取 **租賃工作流程** 連結。

    隨即開啟應用程式。 執行後，登入待重新導向至工作流程應用程式的 Azure Active Directory(Azure AD)。

4. 將 **租賃工作流程核准** 元素拖曳至工作流程。
5. 從 **開始** 將一個節點連接到 **租賃工作流程核准**。 然後將 **租賃工作流程核准** 連接 **結束**，
6. 連按兩下 **租賃工作流程核准**。
7. 選取 **屬性**，然後在 **基本設定** 下方輸入工作流程的名稱。

    在此頁面上，您還可以為工作流程設定更多參數。 如果您已開啟 **自動動作**，系統會自動採取特定的動作。 如果已在 **通知** 索引標籤上指定通知，便會傳送通知。在 **進階設定** 索引標籤上，您可以指定最終核准者、設定時間限制，然後指定必須完成的特定動作。

8. 完成工作流參數設定後，選取 **關閉**。
9. 選取 **步驟 1**，然後選取 **屬性**。
10. 在 **基本設定** 下方輸入步驟名稱，建立核准主旨行，並指定核准指示。
11. 在 **指派** 頁面，選取指派類型。
12. 若要將特定使用者指派給核准，請選取 **使用者**，然後選取核准租賃的使用者，再選取 **關閉**。
13. 選取 **儲存並關閉** 以建立工作流程。 然後當系統提示您時，選取 **確定**。
14. 在 **建立工作流程** 頁面上選取 **關閉**。
14. 選取新的工作流程，然後選取 **版本**。 接著選取 **使它生效** 以確保工作流程處於使用中狀態。
15. 選取 **關閉**。 隨即顯示新的使用中版本。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
