---
title: 建立使用 RFQ 的申請
description: 本主題說明如何從 RFQ 流程將價格和供應商資訊新增到採購申請。
author: Henrikan
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PurchReqTableListPage, PurchReqCreate, PurchReqTable, PurchReqLineRelatedDocuments, EcoResCategorySingleLookup, PurchReqWorkflowDropDialog, WorkflowSubmitDialog, WorkflowStatus, WorkflowWorkItemActionDialog, WorkflowUserListLookup, PurchReqCopyRFQ, SysDataAreaSelectLookup, PurchRFQCaseTable, PurchRFQEditLines, PurchRFQReplyTable, UnitOfMeasureLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f88d50c24e84b94128aa3fd567562f3240832910
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449070"
---
# <a name="create-a-requisition-that-uses-an-rfq"></a>建立使用 RFQ 的申請

[!include [banner](../../includes/banner.md)]

本主題說明如何從 RFQ 流程將價格和供應商資訊新增到採購申請。 本指南中的範例可用於 USMF 示範資料公司，您必須以管理員身份登入才能完成所有步驟。 本指南中的工作通常由採購專業人員完成。


## <a name="create-a-requisition"></a>建立請購單
1. 在功能窗格中，前往 **模組 > 採購及開源 > 採購需求 > 我所準備的採購申請**。
2. 選擇 **新增**。
3. 在 **名稱** 欄位中，輸入一個值。
4. 在 **要求日期** 欄位中，輸入日期。
5. 在 **會計日期** 欄位中，輸入日期。
6. 選擇 **確定**。
7. 在 **原因** 欄位中，輸入或選擇一個值。
8. 選擇 **新增明細**。
9. 在 **採購類別** 欄位中，在樹狀圖中選擇一個類別，然後選擇 **確定**。
10. 在 **產品名稱** 欄位中，輸入一個值。
11. 在 **數量** 欄位中，輸入一個數字。
12. 在 **單位** 欄位中，輸入或選擇一個值。
13. 選擇 **儲存**。
14. 選擇 **工作流程** 打開下拉對話框。
15. 選擇 **提交**。
16. 關閉頁面。
17. 選擇 **提交**。

## <a name="reassign-a-workflow-task"></a>重新指派工作流程工作
下一個工作是建立 RFQ 以從供應商處取得產品的出價。 在 USMF 示範資料中，申請工作流程有規則設定，以便如果未選擇供應商，或者明細的單價為 0 時，則將工作指派給特定工作人員以建立 RFQ。 要繼續本指南，您需要將該工作重新指派給另一個使用者 (您自己)。 僅當您以管理員身份登入時才能執行此操作。  

1. 選擇 **工作流程** 打開下拉對話框。
2. 選擇 **檢視記錄**。
3. 重新整理頁面。
4. 展開 **追蹤詳細資訊** 區段。
5. 在樹狀檢視中，選擇以「Line workflow activated on」為開頭的明細。
6. 選擇 **檢視工作流程詳細資訊**。
7. 展開 **工作項目** 區段。
8. 選擇 **重新指派**。
9. 在 **使用者** 欄位中，選擇 **管理員**。
10. 選擇 **重新指派**。
11. 關閉這兩個頁面。

## <a name="create-an-rfq"></a>建立一個 RFQ

1. 重新整理頁面。
2. 選擇 **詢價**。
3. 在 **購買法律實體** 欄位中，選擇 **USMF**。 您必須選擇申請行上的同一法人。  
4. 在清單中，標記所選資料列。 如果您的採購申請中有多個行，請選擇要添加到 RFQ 的所有行。  
5. 選擇 **確定**。
6. 重新整理頁面。
7. 確保 FactBox 已開啟，然後展開 **相關文件** 區段。
8. 選擇 **詢價** 欄位中的連結，以打開剛才建立的 RFQ。
9. 選擇 **標題**。
10. 選擇 **新增**。
11. 在 **廠商帳戶** 欄位中，輸入或選擇一個值。
12. 選擇 **新增**。
13. 在 **廠商帳戶** 欄位中，輸入或選擇一個值。
14. 選擇 **傳送**。
15. 選擇 **確定**。
16. 選擇 **輸入回覆**。
17. 在動作窗格上，選取 **回覆**。
18. 選擇 **複製資料以回覆**。 這會將數量和日期等資料從 RFQ 複製到回覆。  
19. 在 **單價** 欄位中，輸入一個數字。 這是您從供應商處收到的價格。 您可能也想輸入來自供應商的附加資訊。  
20. 選擇 **接受**。
21. 選擇 **確定**。

## <a name="verify-that-vendor-and-price-have-been-transferred-to-the-requisition"></a>驗證供應商和價格是否已轉移到申請
1. 關閉頁面。
2. 選擇 **明細**。
3. 選擇 **相關資訊**。
4. 選擇 **採購申請**。
5. 選擇轉移至該 RFQ 的明細。 驗證價格和供應商是否已複製到申請。  
6. 選擇 **工作流程** 打開下拉對話框。
7. 選擇完成。
8. 選擇該頁面。
9. 選擇完成。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]