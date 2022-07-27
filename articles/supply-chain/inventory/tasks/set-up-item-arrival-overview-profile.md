---
title: 設定品項到貨概覽設定檔
description: 本主題重點介紹到貨概覽設定檔的設定。
author: yufeihuang
ms.date: 07/30/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WMSArrivalOverviewProfile
audience: Application User
ms.reviewer: kamaybac
ms.custom: intro-internal
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a9a98c84c0dcc86e58b74f53a9061c4a0518ecbf
ms.sourcegitcommit: 27475081f3d2d96cf655b6afdc97be9fb719c04d
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2022
ms.locfileid: "8449616"
---
# <a name="set-up-an-item-arrival-overview-profile"></a>設定品項到貨概覽設定檔

[!include [banner](../../includes/banner.md)]

本主題重點介紹到貨概覽設定檔的設定。 到貨概覽設定檔是在使用者打開到貨概覽頁面時套用的規則集合。 您可以在 USMF 示範公司資料中使用此程序。 此程序通常由收貨員執行。

1. 在瀏覽窗格中，前往 **模組> 庫存管理> 設定> 配送> 到貨概觀設定檔**。
2. 選取 **新增**。 因為您幾乎都是在同一個倉庫卸載整車貨物，所以您應該建立一個到貨概覽設定檔以簡化登記接收品項的流程。  
3. 在 **到貨概觀設定檔名稱** 欄位中，輸入一個值。
4. 在 **顯示行** 欄位中，選擇一個選項。 選擇要為收貨顯示哪些行：  

    - **全部** - 不考慮狀態顯示所有行。   
    - **進行中** – 顯示進度為 [完成] 或 [部分] 的收據行。 這代表對於每一行，全部數量或部分數量都已在到貨日記帳中登記。   
    - **未完成** – 顯示進度為 [無] 或 [部分] 的收據行。 這代表對於每一行，沒有或僅部分數量登記在到貨日記帳中。  

5. 展開或摺疊 **到貨選項** 區段。
6. 在 **提前天數** 欄位中，輸入一個值。 這將設定篩選以顯示預計在接下來的幾天內收到的收據行 (根據您設定的數量而定)。  
7. 在 **延遲天數** 欄位中，輸入一個值。 這將設定篩選以顯示預計在今天之前的幾天內收到的收據行。  
8. 在 **倉庫** 欄位中，輸入一個值。 篩選一個或多個倉庫。  
9. 在 **交貨方式** 欄位中，選擇一個值。 這會設定篩選以僅顯示具有此交貨方式的收據行。  
10. 在 **名稱** 欄位中，選取 WHS。
11. 請在 **倉庫** 欄位中，選取倉庫 24。 這是將用於使用此設定檔的已登記收據行的預設倉庫。  
12. 在 **位置** 欄位中，選擇 **Baydoor**。 這是將用於使用此設定檔的已登記收據行的預設位置。  
13. 展開或摺疊 **到貨查詢詳細資料** 區段。
14. 在 **限制到站點** 欄位中，選擇站點 2。 這會設定篩選以僅顯示具有此站點的收據行。  
15. 將 **訂購單** 選項設定為 **是**。 選擇訂購單中的收據行。  
16. 將 **轉移單** 選項設定為 **是**。 選擇轉移單中的收據行。  
17. 選取 **儲存**。
18. 關閉頁面。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
