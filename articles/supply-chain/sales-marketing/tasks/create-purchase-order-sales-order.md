---
title: 從銷售訂單建立訂購單
description: 此程序說明如何根據銷售訂單建立訂購單。
author: Henrikan
ms.date: 06/26/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable, PurchCreateFromSalesOrder, VendAccountItemLookup, SalesTableReferences, PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4ca91f17c13e210a4df6c22e0ed12370179bb866
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448527"
---
# <a name="create-a-purchase-order-from-a-sales-order"></a>從銷售訂單建立訂購單

[!include [banner](../../includes/banner.md)]

此程序說明如何根據銷售訂單建立訂購單。 訂購單上的產品數量，是為了滿足原始銷售訂單的需求。 以這種方式滿足銷售需求，是更全面且優化的經銷需求計畫的替代方法。 您可使用示範資料公司 USMF 或自己的資料來執行此程序。


## <a name="create-a-purchase-order-from-a-sales-order"></a>從銷售訂單建立訂購單
1. 前往 **瀏覽窗格 > 模組 > 銷售和行銷 > 銷售訂單 > 所有銷售訂單**。
2. 按一下 **新增**。
3. 在 **客戶帳戶** 欄位中，按一下下拉式按鈕開啟查詢。
4. 在清單中，尋找並選擇所需紀錄。
5. 按一下 **確定**。
6. 在 **項目編號** 欄位中，按一下下拉式按鈕開啟查詢。
7. 在清單中，尋找並選擇所需紀錄。 如果您是使用 USMF，則可以選擇 D0001。  
8. 在 **數量** 欄位中，輸入一個數字。
9. 按一下 **新增明細**。
10. 在 **項目編號** 欄位中，按一下下拉式按鈕開啟查詢。
11. 在清單中，尋找並選擇所需紀錄。 如果您是使用 USMF，則可以選擇 T0020。  
12. 在列表中，按一下所選行中的連結。
13. 在 **數量** 欄位中，輸入一個數字。
14. 按一下 **儲存**。
15. 在 **動作窗格** 上，按一下 **銷售訂單**。
16. 按一下 **訂購單**。 **創建訂購單** 頁面，列出所有從銷售訂單複制的未結銷售訂單明細。 您可以查看訂單詳細資訊，如果需要，您可以在創建訂購單前修改選定的詳細資訊，例如：購買數量和價格條款。 
17. 選擇 **包括所有選項**。
    - 如果您只要為銷售訂單明細的子項目生成採購單，請單獨選擇。  
    - **廠商帳戶** 欄位可能已經填入或可能尚未填入廠商編號。 如果產品已設定預設廠商 (在相關的項目覆蓋範圍內)，則該供應商將被複製到該明細。 否則，您必須手動輸入廠商。  在本指南中，無論 **廠商帳戶** 欄位是否已包含值，以下步驟會指導您為每個明細選擇不同的新廠商。  
18. 在 **廠商帳戶** 欄位中，按一下下拉式按鈕開啟查詢。
19. 在清單中，尋找並選擇所需紀錄。
20. 在列表中，按一下所選行中的連結。
21. 選擇第二個訂單明細。
22. 在 **廠商帳戶** 欄位中，按一下下拉式按鈕開啟查詢。
23. 在清單中，尋找並選擇所需紀錄。
24. 在列表中，按一下所選行中的連結。
25. 按一下 **驗證**。
26. 按一下 **確定**。 訊息通知您以創建一個或多個訂購單。 系統會根據您指定的銷售訂單明細，為每個廠商生成單獨的訂購單。 這意味著，如果同一廠商供應多個銷售訂單明細，會生成一個包含多個明細的訂購單。  

## <a name="review-purchase-orders-created-from-sales-orders"></a>查看從銷售訂單創建的訂購單
1. 在 **動作窗格** 上按一下 **一般**。
2. 按一下 **相關訂單**。 **相關訂單** 頁面列出所有從銷售訂單創建的訂單。 在此範例中，分別生產兩個訂購單，對應兩個不同的廠商。 
3. 按一下，以跟隨 **訂購單** 欄位中的連結。 每個訂單明細都與導致購買的銷售訂單明細關聯。 與銷售訂單的關係說明，在 **明細詳細資料** Fasttab 的 **產品索引標籤** 上、**參考類型** 中、**參考編號**，和 **參考區域** 欄位。  
4. 展開或摺疊 **明細詳細資料** 部分。
5. 按一下 **產品** 索引標籤。
    - **參考區域** 保證當前購買的成本，會從附加的銷售訂單上收取。  
    - 您可以透過打開 **參考編號** 欄位的連結，前往原始銷售訂單。  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]