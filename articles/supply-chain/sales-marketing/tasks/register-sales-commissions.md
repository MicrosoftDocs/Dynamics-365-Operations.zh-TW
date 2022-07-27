---
title: 登記銷售佣金
description: 本主題介紹如何計算和登記銷售佣金。
author: Henrikan
ms.date: 08/06/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable, SalesEditLines,  CustInvoiceJournal, CommissionTrans, LedgerTransVoucher, CustClassificationGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f4aca37350938d54d4acf283093365bfcab64f70
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448815"
---
# <a name="register-sales-commissions"></a>登記銷售佣金

[!include [banner](../../includes/banner.md)]

本主題介紹如何計算和登記銷售佣金。 您可使用示範資料公司 USMF 或自己的資料來執行此程序。 在開始本指南之前，執行名為「設定銷售佣金規則」的指南，以確保您已完成所有必要的佣金計算設定。

記錄為佣金流程選擇的客戶和品項編號，並在建立本指南中的銷售訂單時使用。


## <a name="invoice-a-sales-order-that-qualifies-a-salesperson-for-a-commission"></a>為銷售人員符合佣金資格的銷售訂單開立發票
1. 在瀏覽窗格中，移至 **模組 > 銷售和行銷 > 銷售訂單 > 所有銷售訂單**。
2. 選取 **新增**。
3. 在 **客戶帳戶** 欄位中，從下拉式功能表選取所需的記錄。
4. 選取 **確定**。
5. 在 [動作窗格] 上，選擇 **選項**。
6. 選取 **更改檢視**。
7. 選擇 **標題檢視**。
8. 展開 **設定** 區段。

    - **銷售群組** 欄位中的值代表有一名或多名指派銷售代表的群組。 群組中的人員是在訂單開立發票時以預定義的比率和分配規則接受佣金的人員。   
    - 該值是從客戶卡中複製的，但您可以視需要更改。  
    - 銷售群組也可以複製到銷售訂單明細。 您可以更改它，使其與標題和/或明細之間的名稱不同。  
    - **佣金群組** 欄位的值代表您出於追蹤佣金目的為一個或多個客戶建立的群組。   
    - 該值是從客戶卡中複製的，但您可以視需要更改。   

9. 在 [動作窗格] 上，選擇 **選項**。
10. 選取 **更改檢視**。
11. 選取 **明細檢視**。
12. 在 **品項編號** 欄位的下拉式選單中，選擇已為其設定佣金的品項。 
13. 在 **數量** 欄位中，輸入一個數字。 記錄明細的淨額。 它代表銷售收入，在本範例中它是佣金計算的基礎。  
14. 選擇 **儲存**。
15. 在動作窗格上，選取 **發票**。
16. 選擇 **發票**。
17. 展開 **參數** 部分。
18. 在 **數量** 欄位中，選取 **全部**。
19. 在 **過帳** 欄位中選擇 **是**。
20. 選擇 **確定**，然後在下一個窗格中選擇 **確定**。 過帳交易可能需要大概一分鐘。 處理完成前不要關閉頁面。  

## <a name="review-the-registered-sales-commissions"></a>查看登記的銷售佣金
1. 在動作窗格上，選擇 **發票**，再次選擇 **發票**。
2. 在動作窗格上，選擇 **發票**，接著選擇 **佣金交易**。

    - **概覽** 索引標籤顯示的是與應付給與開票銷售訂單關聯的銷售代表之佣金金額明細。 開始查看詳細資料。  
    - 如果您使用「設定銷售佣金規則」指南來設定 **佣金銷售** 群組，將有兩位銷售人員接受銷售佣金，並且兩人平分佣金。  
    - 在此範例中，佣金的總金額計算為銷售收入百分比 (訂單明細的淨額)。  
3. 關閉頁面。
4. 選擇 **憑單**。 您可以在憑證交易中查看已過帳到預定義佣金費用和佣金應付帳戶的佣金金額。  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]