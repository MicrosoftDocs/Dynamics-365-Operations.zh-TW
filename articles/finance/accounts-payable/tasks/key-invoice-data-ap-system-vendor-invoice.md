---
title: 使用廠商發票將發票資料鍵入 AP 系統
description: 本任務指引將幫助您從採購訂單建立廠商發票，並檢視採購訂單、收據和發票的相符結果 (3 種符合方)。
author: abruer
ms.date: 07/22/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PurchTable, PurchCreateOrder, InventItemIdLookupPurchase, PurchEditLines, VendEditInvoice, InventItemIdLookupSimple, VendInvoiceMatchingDetails
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b3e27ed41ff1fa44d5e8779cb5e81e45d02110eb3b37be3a3b9938cabfc395bd
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450843"
---
# <a name="key-invoice-data-in-ap-using-a-vendor-invoice"></a>使用廠商發票將發票資料鍵入 AP 系統

[!include [banner](../../includes/banner.md)]

本任務指引將幫助您從採購訂單建立廠商發票，並檢視採購訂單、收據和發票的相符結果 (3 種符合方)。


## <a name="create-a-purchase-order"></a>建立採購訂單
1. 在瀏覽窗格前往 **模組 > 應付帳款 > 採購訂單 > 所有採購訂單**。
2. 點選 **新增**。
3. 在 **廠商科目** 欄位，點選下拉式按鈕打開查閱功能。
4. 尋找要選取的廠商 例如，捲軸向下滾動到 US-104。
5. 選取廠商 US-104。
6. 點選 **確定**。
7. 在 **品項編號** 欄位中，點選下拉式按鈕開啟查詢。
8. 選取庫存品項。 例如，選取品項編號 1000。
9. 展開 **行項詳細資料** fastTab。
10. 點選 **設定** 索引標籤。您可以覆寫相符政策為使用不相符、雙向符合或三向符合。  
11. 在「動作窗格」上，按一下 **採購**。
12. 點選 **確認**。

## <a name="receive-the-products"></a>收到產品
1. 在動作窗格上，點選 **收件**。
2. 點選 **產品收據**。
3. 在 **產品收據** 欄位，輸入產品收據號碼。 例如，輸入 PR123。
4. 點選 **確定** 過帳產品收據。
5. 關閉頁面。

## <a name="create-a-vendor-invoice"></a>建立廠商發票
1. 在瀏覽窗格前往 **模組 > 應付帳款 > 採購訂單 > 採購訂單已收到但未開立發票**。
2. 選取您建立的採購訂單。
3. 請在動作窗格上點選 **發票** 。
4. 點選 **發票**。
5. 在 **編號** 欄位，輸入發票號碼。
6. 在 **發票說明** 欄位，輸入一值。
7. 在 **發票日期** 欄位，輸入日期。
8. 在 **單價** 欄位，輸入 1200。
9. 點選 **新增明細**。
10. 在 **品項編號** 欄位中，點選下拉式按鈕開啟查詢。
11. 在清單尋找安裝收費項目編號。 例如，S0001 
12. 選取安裝收費項目編號。 請注意，自從您更改之後，尚未執行比對。  
13. 點選 **更新比對狀態**。
14. 在動作窗格上，按一下 **審核**。
15. 點選 **比對細節**。 新服務明細不需要比對，所以狀態保持為 "未執行"。  
16. 選取您已經收到的庫存品項產品收據。 產品收據明細已經比對，但數量或價格不比對，因此失敗。  
17. 在 **單價** 欄位中，輸入一個數字。 現在單價比對，狀態更新為通過。 如果您的政策允許出入或比對是否只是警告，您都仍然可以過帳發票。  
18. 關閉頁面。
19. 點選 **過帳**。
20. 關閉表單。 請注意，採購訂單不再列為已收到但未開立發票。  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]