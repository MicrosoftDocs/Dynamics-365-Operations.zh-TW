---
title: 管理訂單保留
description: 此程序示範如何保留客戶銷售訂單、如何使用訂單保留結帳，以及如何移除訂單保留。
author: Henrikan
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: MCRHoldCodeTable, SalesTableListPage, SalesCreateOrder, SalesTable, MCRHoldCodeTrans, MCRHoldCheckOutOverride, MCRHoldCodeTable, MCRItemListCopying, MCRItemListTable, MCROMHoldList
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 938b21b66b7b61452be104936877278a3bc120f2
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8447909"
---
# <a name="manage-order-holds"></a>管理訂單保留

[!include [banner](../../includes/banner.md)]

此程序示範如何保留客戶銷售訂單、如何使用訂單保留結帳，以及如何移除訂單保留。 訂單可能會因各種原因被保留。 例如，在客戶地址或付款方式通過驗證，或者經理可以檢閱客戶的信用額度之前，您可能會保留訂單。 訂單被保留時，倉庫便無法處理該訂單的送貨作業。 

您可使用示範資料公司 USMF 或自己的資料來執行此程序。


## <a name="set-up-order-holds"></a>設定訂單保留
1. 前往 **瀏覽窗格 > 模組 > 銷售和行銷 > 設定 > 銷售訂單 > 訂單保留代碼**。
2. 按一下 **新增**。
3. 在 **保留代碼** 欄位中，輸入一個值。 例如，輸入「Call back」。  
4. 在 **描述** 欄位中，輸入一個值。
    - 例如，因等待客戶回撥而保留訂單。  
    - 或者，選擇 **刪除預訂** 核取方塊，以在新增此保留代碼時，從訂單中刪除任何實際保留。  
5. 按一下 **儲存**。

## <a name="place-order-on-hold"></a>將訂單設為保留中
1. 前往 **瀏覽窗格 > 模組 > 銷售和行銷 > 銷售訂單 > 所有銷售訂單**。
2. 按一下 **新增**。
3. 在 **客戶帳戶** 欄位中，輸入或選取一個值。
4. 按一下 **確定**。
5. 在 **項目號碼** 欄位中，輸入或選擇一個值。
6. 在 **數量** 欄位中，輸入一個數字。
7. 在 **動作窗格** 上，按一下 **銷售訂單**。
8. 按一下 **訂單保留**。
9. 按一下 **新增**。
10. 在 **保留代碼** 欄位中，選擇您在上一個子任務中建立的代碼。
11. 按一下 **儲存**。
12. 關閉頁面。
13. 前往 **銷售和行銷 > 銷售訂單 > 所有銷售訂單**。
14. 在清單中，標記所選資料列。 目前被保留的訂單標有「不處理」和「保留」欄位。
15. 在動作窗格上按一下 **揀貨並裝箱**。

## <a name="manage-order-holds"></a>管理訂單保留
1. 前往 **銷售和行銷 > 銷售訂單 > 開啟訂單 > 訂單保留**。 **訂單保留** 頁面的功能是作為工作台使用，您可以在其中概覽所有目前和已處理的保留，並處理它們和相關的銷售訂單。     
2. 在清單中，標記所選資料列。
3. 在 **動作窗格** 上，按一下 **保留結帳**。
4. 按一下 **結帳**。
5. 在清單中，取消標記所選資料列。 **結帳至** 欄位現在顯示您的用戶識別碼。   
6. 按一下 **清除結帳**。
7. 在 **動作窗格** 上，按一下 **清除保留**。
    - 在您準備好移除保留並允許訂單進入下一個履行步驟時，您必須解除保留。 如果訂單不需變更，您可以執行解除保留動作。 但是，如果在解除保留時必須更新訂單，則您可以使用解除和修改動作。      
    - **解除並提交** 動作僅適用於您使用呼叫中心功能時。  
8. 按一下 **解除保留**。 保留現在已從訂單中解除，並從使用中保留清單中移除。 如要根據特定狀態查看所有保留或其子集，請變更顯示欄位中的值。     



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]