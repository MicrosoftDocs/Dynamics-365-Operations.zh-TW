---
title: 建立銷售訂單
description: 此程序說明如何建立銷售訂單。
author: Henrikan
ms.date: 06/25/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable, InventDimParmFixed, InventProductDimensionLookup, SalesTotals
audience: Application User, SalesTableDelete, SalesTableListPagePreviewPage, SalesUpdateRemain
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5746fa0ab9fd7ef3e288adc88a755324309a27c0
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8447906"
---
# <a name="create-sales-orders"></a>建立銷售訂單

[!include [banner](../../includes/banner.md)]

此程序說明如何建立銷售訂單。 您可以在 USMF 示範公司資料中使用該程序。 銷售訂單通常由銷售訂單處理器建立。 

## <a name="enter-sales-order-header-details"></a>輸入銷售訂單標題詳細資訊
1. 前往 **瀏覽窗格 > 模組 > 銷售和行銷 > 銷售訂單 > 所有銷售訂單**。
2. 選擇 **新增**。
3. 在 **客戶帳戶** 欄位中，選擇下拉式按鈕開啟查詢。
4. 在清單中，尋找並選擇客戶紀錄。
    - 在本範例中，選擇客戶編號 US-004。  
5. 選擇 **確定**。

## <a name="enter-sales-order-line-details"></a>輸入銷售訂單行詳細資訊
    
您組織銷售的產品可能有不同尺寸的變體，例如設定、顏色、尺寸和樣式。 此外，產品可以設定為使用儲存尺寸，例如站點、倉庫和貨板，以及追蹤維度，例如批次和序號。 指派這些維度時，您必須在訂單明細上選擇這些維度的值。 為了提高訂單輸入效率，您可能希望將相應的維度欄位新增到訂單網格。
    
1. 在 **銷售訂單明細** 部分下方，選擇 **銷售訂單明細**。
2. 選擇 **維度**。
    
    在此範例中，選擇顏色、站點和倉庫維度。 您在此選擇的維度將出現在銷售訂單網格中。 如果您希望選擇保持不變，請將 **儲存設定** 選項設為是。
    
3. 選擇 **確定**。
4. 在 **項目編號** 欄位中，選擇下拉式按鈕開啟查詢。
5. 在此範例中，選擇項目編號 T0004。
    - 如果該項目是銷售類別的一部分，則項目名稱將自動出現在銷售類別欄位中。  
    - 如果產品尺寸欄位已包含一個值，這是因為該值是從定義為預設產品尺寸的產品記錄中複製的。 您可以隨時更改該預設值。   
6. 在 **顏色** 欄位中，打開下拉式按鈕以開啟查詢。
7. 在清單中，尋找並選擇所需紀錄。
8. 在 **數量** 欄位中，輸入一個數字。
    - 如果商品的銷售單位與購買、生產和儲存時不同，並且在產品記錄中設定了銷售測量單位，則該值將顯示在 **單元** 欄位中。 您可以隨時更改該值。   
    - 如果 **站點** 欄位已包含一個值，該值是從訂單標題或與產品關聯的訂單設定中複製的。 您可以隨時更改該值。 如果該欄位為空，請選擇一個值。   
    - 如果 **單價** 欄位已包含一個值，則該值是從有效的貿易合約或產品記錄中複製的。 (單價也可以來自銷售合約，但從銷售合約建立銷售訂單的過程與此處顯示的不同。) 如果該欄位為空，請輸入一個值。   
    - **折扣** 欄位包含每個產品單位的折扣金額。 要計算總行折扣金額，請將折扣值乘以行的數量。 如果 **折扣** 欄位已包含一個值，則該值是從有效的貿易合約中複製的。 如果該欄位為空，並且您想為客戶提供行折扣，請輸入一個值。  
    - 此 **折扣百分比** 欄位包含會一個百分比值，總行毛額將按該百分比值減少。  如果 **折扣百分比** 欄位已包含一個值，則該值是從有效的貿易合約中複製的。 如果該欄位為空，並且您想為客戶提供行折扣，請輸入一個值。 
    - 該 **淨額** 欄位會包含一個值，該值是根據折扣調整後的行的數量和單價計算得出的。  您可以將計算值覆寫為其他值。  

## <a name="review-the-order-totals"></a>檢閱訂單總額
1. 在 **動作窗格** 上，選擇 **銷售訂單**。
2. 選擇 **總計**。
    
    該 **總計** 頁面會顯示有關整體訂單的詳細資訊。 這包括小計金額，它是針對最終行折扣調整的所有行淨額的總和、發票總金額，即針對最終訂單層級折扣、費用和銷售稅調整的小計金額、客戶信用額度情況等資訊。 發票金額是顯示在客戶發票文件上的金額。  
    
3. 選擇 **確定**。


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]