---
title: 建立和編輯銷售報價
description: 此程序示範如何建立和更新銷售報價。
author: Henrikan
ms.date: 06/26/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SalesQuotationListPage, SalesCreateQuotation, SalesQuotationTable, SalesQuotationTotals, SalesQuotationPriceSimulation, SalesQuotationEditLines, SrsReportViewerForm, smmSetNumSeqIfManual, CustTable, SalesTable, CustQuotationConfirmationJournal, CustQuotationJournal, CustSalesLines, SalesQuotationCopying, SalesQuotationDeleteQuotations, SalesQuotationListPagePreviewPane, SalesQuotationTypeGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1c409d294565f89eac95e42f6207573d22859100
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449163"
---
# <a name="create-and-edit-sales-quotations"></a>建立和編輯銷售報價

[!include [banner](../../includes/banner.md)]

此程序示範如何建立和更新銷售報價。 您可使用自己的資料或 USMF 示範資料公司來執行此程序。


## <a name="create-a-sales-quotation"></a>建立銷售報價
1. 移至 **導覽窗格 > 模組 > 銷售和行銷 > 銷售報價 > 所有報價**。
2. 按一下 **新增**。
3. 請在 **帳戶類型** 欄位，選擇「潛在客戶」。
4. 在 **潛在客戶** 欄位中，輸入或選擇一個值。
5. 展開 **一般** 區段。 由於您是從銷售和行銷區段建立報價，因此類型會自動設為「銷售報價」。 若要針對專案建立報價，您必須從 **專案管理和會計** 模組來進行。
6. 按一下 **確定**。 報價明細上的欄位和動作與銷售訂單明細的非常類似。   如同銷售訂單，報價的建立可針對特定項目、編號未知或報價建立時不存在的項目，另也可針對銷售類別建立報價。     
7. 在 **項目** 欄位中，輸入或選擇一個值。
8. 在 **站點** 欄位中，輸入一個值。
9. 在 **數量** 欄位中，輸入一個數字。 若明細所選項目適用於有效的貿易合約，則適用價格和折扣會自動複製進報價明細。 請確認單價欄位內有一個值，也可視需要輸入折扣值。 
10. 按一下 **儲存**。
11. 在 **動作窗格** 上按一下 **銷售報價**。
12. 按一下 **總計**。
13. 按一下 **確定**。
14. 選擇銷售報價明細。
15. 在 **動作窗格** 上按一下 **報價**。
16. 按一下 **價格模擬**。
    - 在 **執行價格模擬** 頁面中，您可依據想要的單價、折扣金額、折扣百分比、總金額、利潤或貢獻率，嘗試調整該報價的預期收入或獲利能力。 對目標數字感到滿意後，即可將該建議套用至報價明細，之後就會自動更新價格相關欄位。  
    - 您可以盡情建立價格模擬。 按一下 **新增** 時，目前報價明細的價格條件會複製到此頁面。 之後再修改價格相關欄位的值，使之更接近目標數字。 調整一個欄位的值，將會使所有其他欄位重新計算。 為了讓系統計算銷售利潤和貢獻率，必須提供產品的單位成本。 在模擬價格索引標籤檢視原始價格、建議變更的詳細資料，以及報價總額會受到的影響。 一般而言，設成不同金額的模擬作業套用至報價明細後，系統會重新計算單價並輸入新的值。 若模擬作業僅針對不同的利潤或貢獻率調整，則只會更新淨額欄位，單價則為空白。 上述兩種情況中，報價明細上模擬前的任何折扣都會被刪除。
17. 在 **動作窗格** 上按一下 **報價**。
18. 按一下 **傳送報價**。
19. 在 **列印報價** 欄位中選擇「是」。
20. 按一下 **確定**。 製作報告可能需要一分鐘。 報告完成前請勿關閉頁面。

## <a name="update-a-sales-quotation"></a>更新銷售報價
1. 移至 **導覽窗格 > 模組 > 銷售和行銷 > 銷售報價 > 所有報價**。
2. 在 **動作窗格** 上按一下 **跟進**。
3. 按一下 **轉換為客戶**。
4. 在 **客戶帳戶** 欄位中，輸入一個值。
5. 按一下 **檢查**。 確認系統出現您輸入的帳戶號碼可供使用的訊息。  
6. 按一下 **確定**。 系統現已針對報價上的潛在客戶，建立新的客戶帳戶。  
7. 關閉頁面。
8. 在 **動作窗格** 上按一下 **跟進**。
9. 按一下 **確認**。
10. 在 **原因** 欄位中，輸入或選擇一個值。
11. 按一下 **確定**。
12. 在 **動作窗格** 上按一下 **一般**。
13. 按一下 **銷售訂單**。
14. 關閉頁面。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]