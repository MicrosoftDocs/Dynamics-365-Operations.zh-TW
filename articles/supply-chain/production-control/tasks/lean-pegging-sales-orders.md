---
title: 銷售訂單的精益需求追蹤
description: 此程序著重於驗證使用看板生產品項的銷售明細需求追蹤樹狀結構。
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable, LeanPeggingTree
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8eca21f8bd988ca352c07e839295b3edd9669929
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449331"
---
# <a name="lean-pegging-from-sales-orders"></a>銷售訂單的精益需求追蹤

[!include [banner](../../includes/banner.md)]

此程序著重於驗證使用看板生產品項的銷售明細需求追蹤樹狀結構。 驗證需求追蹤樹狀結構後，系統會規劃所有看板作業。 如果接單者需要確認可以立即開始生產，這個功能非常實用。 建立此程序的示範資料公司為 USMF。 此程序適用於採用精益作業的公司的進階接單者。


## <a name="create-a-sales-order-for-a-kanban-controlled-item"></a>為看板控制項目建立銷售訂單
1. 前往所有銷售訂單。
2. 按一下新增。
3. 在客戶帳戶欄位中，輸入或選擇一個值。
    * 使用 US-001。  
4. 按一下確定。
5. 在品項編號欄位中輸入「L0001」。
6. 將數量設為「30」。
    * 為了觸發事件看板規則，數量必須高於 24。  

## <a name="open-a-pegging-tree"></a>開啟需求追蹤樹狀結構 
1. 按一下產品和供應。
2. 按一下查看需求追蹤樹。
    * 請注意，需求追蹤樹狀結構顯示銷售訂單明細所需的所有需求追蹤層級。 在這種情況下，系統會提供兩個看板層級和所有必要元件。  

## <a name="plan-the-pegging-tree"></a>顯示需求追蹤樹狀結構
1. 在樹狀結構中，選取「銷售明細 000832\看板 000558」。
2. 展開看板作業區段。
    * 請注意，看板作業的作業狀態為「未規劃」。  
3. 按一下「規劃整個需求追蹤樹狀結構」。
    * 這將規劃需求追蹤樹狀結構中的所有看板作業，將作業狀態從「未規劃」更改為「已規劃」。  
4. 重新整理頁面。
    * 請注意，看板作業狀態已從「未規劃」變更為「已規劃」。  
5. 在樹狀結構中，選取「銷售明細 000832\看板 000558\L0001 問題\看板 000559」。
    * 由於整個需求追蹤樹狀結構已規劃完畢，因此第二個看板的作業也隨之完成規劃。 請注意，看板作業狀態已從「未規劃」變更為「已規劃」。  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]