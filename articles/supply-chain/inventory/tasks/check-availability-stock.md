---
title: 檢查庫存的可用數量
description: 此過程向您展示對特定品項編號檢查其現有和實際現有庫存的方法。
author: yufeihuang
ms.date: 06/25/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventOnHandItemListPage, SysQueryForm, InventDimParmFixed, InventSupply, DefaultDashboard, WHSInventPhysicalOnhand, WHSOnHand, InventOnhandItem
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5c1533dc677c53e90d73077e06a67c71cebc1b7e
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448740"
---
# <a name="check-the-availability-of-stock"></a>檢查庫存的可用數量

[!include [banner](../../includes/banner.md)]

此過程向您展示對特定品項編號檢查其現有和實際現有庫存的方法。 並向您展示如何取得品項相關的供應資訊。 實際現有庫存是可用的現有庫存，即完成購買、接收和登記的。 現有庫存包括可用的現有庫存，還包括已訂購和預期但尚未收到或登記的庫存。 您能以示範資料公司 USMF 或自己的資料走完這段程序。 如果您使用的是 USMF，您可以使用顯示的範例值。 這些工作通常由倉庫工作人員執行。


## <a name="check-on-hand-inventory-for-an-item"></a>檢查品項的現有庫存
1. 請前往 **功能窗格 > 模組 > 庫存管理 > 查詢和報告 > 現有庫存**。
2. 選取 **品項編號** 列。 若要依品項編號查詢現有庫存，找到資料表設定為 **現有庫存** 且欄位設定為 **品項** 編號的列，選取該列。
3. 在 **準則** 欄位，選取您要查詢的品項。 如果您使用的是 USMF 示範資料公司，則可以選擇「M9201」。  
4. 按一下 **確定**。
5. 在 **動作窗格** 上，按一下 **維度**。 **維度** 索引標籤允許您選取想要查看現有庫存的哪些詳細資料。 如果您需要與保留相關的資料，則必須對於使用進階倉庫 (WMS) 流程的品項，顯示所有庫存維度。
6. 按一下 **確定**。
7. 在 **動作窗格**，按一下 **相關資訊**。 如果您沒有看到此選項，您可能需要按一下省略號按鈕 (...) 以查看其他動作窗格選項。
8. 按一下 **供應摘要**。 **供應摘要** 索引標籤提供特定品項的供應資訊，例如現有數量、前置期和供應商資訊。  
9. 展開 **現有** 區段。
10. 展開 **供應商** 區段。
11. 關閉頁面。
12. 關閉頁面。

## <a name="check-physical-on-hand-inventory"></a>檢查實際現有庫存
1. 請前往 **功能窗格 > 模組 > 倉庫管理 > 查詢和報告 > 實際現有庫存**。
2. 在 **項目編號** 欄位中，輸入一個值。 您可以使用站點和倉庫欄位來篩選品項清單。 
3. 重新整理頁面。
4. 在 **動作窗格** 上，按一下 **顯示維度**。 維度顯示索引標籤允許您選取想要查看現有庫存的哪些詳細資料。
5. 按一下 **確定**。
6. 關閉頁面。

## <a name="check-on-hand-inventory-by-location"></a>按位置檢查現有庫存
1. 請前往 **功能窗格 > 模組 > 倉庫管理 > 查詢和報告 > 按位置排序現有庫存**。
2. 在 **Warehouse** 欄位中輸入值。 如果您使用的是 USMF 示範資料公司，則可以選擇「51」。  
3. 重新整理頁面。
4. 按一下 **顯示維度**。
5. 按一下 **確定**。
6. 關閉頁面。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]