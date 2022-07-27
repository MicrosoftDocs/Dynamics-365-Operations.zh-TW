---
title: 初始化倉庫中的庫存量
description: 此過程會向您展示如何使用庫存移動日記帳手動更新現有庫存。
author: yufeihuang
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventJournalMovement, InventJournalCreate, InventItemIdLookupSimple, InventLocationIdLookup, WMSLocationIdLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 264dabf9c1c10c3d2cee3e0c942abbfa249f21f5
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8447864"
---
# <a name="initialize-stock-levels-in-the-warehouse"></a>初始化倉庫中的庫存量

[!include [banner](../../includes/banner.md)]

此過程會向您展示如何使用庫存移動日記帳手動更新現有庫存。 (也可以透過在資料實體中匯入交易來更新現有庫存。) 您可以在示範資料公司 USMF 中執行本指南，其中所有先決條件 (如日記帳名稱、項目設定、過帳設定檔和帳戶) 都可使用。 該指南建議了項目的特定值和使用的維度。 如果您選取了不同的項目，您可能需要輸入不同維度的值。

1. 前往庫存管理 > 日記帳項目 > 品項 > 移動。
2. 按一下新增。
3. 在名稱欄位中，按一下下拉式按鈕開啟查詢。
4. 選擇 IMov。
    * 為不同的業務目的使用不同的日記帳名稱範本是一種很好的做法。  
5. 在列表中，按一下所選行中的連結。
6. 在沖銷帳戶欄位中，指定值「140200」。
    * 這是將成為日記帳明細上預設帳戶的沖銷帳戶。 預設設定可以被覆寫，以為每個明細指派不同的沖銷帳戶。  
7. 按一下確定。
8. 按一下新增。
9. 在品項編號欄位中，按一下下拉式按鈕開啟查詢。
10. 選擇品項 A0001。
11. 在列表中，按一下所選行中的連結。
12. 按一下庫存維度索引標籤。
13. 在站點欄位中，按一下下拉式按鈕開啟查詢。
14. 選擇站點 1。
15. 在倉庫欄位中，按一下下拉式按鈕開啟查詢。
16. 選擇倉庫 13。
17. 在列表中，按一下所選行中的連結。
18. 在位置欄位中，按一下下拉式按鈕以開啟查詢。
19. 選擇位置 13。
20. 在數量欄位中，輸入一個數字。
21. 按一下儲存。
22. 按一下過帳。
23. 勾選或取消勾選將所有過帳錯誤移轉到新的日記帳核取方塊。
    * 如果您啟用此選項，任何無法過帳的明細都將被複製到新的日記帳中。 您可以使用日誌中的資訊來更正問題，然後重新過帳明細。  
24. 按一下確定。
25. 關閉頁面。
26. 關閉頁面。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]