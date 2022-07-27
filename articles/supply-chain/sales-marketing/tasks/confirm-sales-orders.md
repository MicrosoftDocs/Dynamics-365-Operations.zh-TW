---
title: 確認銷售訂單
description: 此程序示範如何確認銷售訂單。
author: Henrikan
ms.date: 06/26/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SalesTableListPage, SalesTable, SalesEditLines,  SrsReportViewerForm, CustConfirmJournal, SysQueryForm, SysQueryFieldLookUp, SysLookup, SalesParmIdLookup, SalesUnconfirmedOrdersPart
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 30396c121b67d1b7095a175d85399ed664f68557
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448530"
---
# <a name="confirm-sales-orders"></a>確認銷售訂單

[!include [banner](../../includes/banner.md)]

此程序示範如何確認銷售訂單。 將為您示範如何確認單一訂單，以及如何一次同時確認多個訂單。 這些工作通常由銷售訂單處理器執行。 您可用示範資料公司 USMF 或自己的資料來使用此程序。 在開始之前，請確認同一客戶有多個未結銷售訂單。 如果您使用 USMF，則可以使用客戶 US-027。


## <a name="confirm-a-single-sales-order"></a>確認單一銷售訂單
1. 前往 **瀏覽窗格 > 模組 > 銷售和行銷 > 銷售訂單 > 所有銷售訂單**。
2. 在清單中，找到並選擇您要確認的訂單。
3. 按一下銷售訂單編號上的連結，以開啟所選訂單。
4. 在 **動作窗格** 上，按一下 **販售**。
5. 按一下 **確認銷售訂單**。
6. 展開 **參數** 部分。 確認 **過帳** 選項設為「是」。  
7. 將 **列印確認選項** 設為「是」。 **檢查信用額度** 欄位指定用於計算客戶剩餘信用額度的方法。 預設情況下，此設定從應收帳款參數頁面複製。 如果您想在確認特定銷售訂單時跳過信用額度檢查，請將 **檢查信用額度** 設為「無」。 但您應該知道，即使此欄位設為「無」，如果在客戶主資料上選擇了 **強制信用額度** 選項，仍將執行信用額度檢查。 
8. 按一下 **確定**。
9. 按一下 **是**。
10. 關閉頁面。
11. 在 **動作窗格** 上，按一下 **選項**。
12. 按一下 **變更檢視**。
13. 按一下 **標頭檢視**。 確認訂單後，**文件狀態** 將設為「確認」。 
14. 在 **動作窗格** 上，按一下 **販售**。
15. 按一下 **銷售訂單確認**。
16. 關閉頁面。

## <a name="confirm-multiple-sales-orders-at-once"></a>一次確認多個銷售訂單
1. 移至 **銷售和行銷 > 銷售訂單 > 訂單確認 > 確認銷售訂單**。
2. 按一下 **選擇**。
3. 在 **範圍** 索引標籤上的名單中，尋找並選擇參考 **客戶帳戶** 欄位的記錄。
4. 在 **條件** 欄位中，按一下下拉式按鈕開啟查詢。
5. 在清單中，尋找並選擇您要整批確認的有多個訂單的客戶帳戶。 如果您使用 USMF，則可以選擇帳戶 US-027。  
6. 按一下 **確定**。
    - **概觀** 索引標籤顯示與查詢條件匹配的訂單清單。 這些將包含在確認中。  
    - **參數** 區段中的 **摘要更新** 欄位指定將多個訂單匯總到一個確認文件中的參數。 預設情況下，將從 **應收帳款參數** 頁面的 **摘要更新設定的預設值** 複製選項。  
7. 在 **摘要更新** 欄位中，選擇「訂單」。 建立摘要更新所需的最小參數是 **發票帳戶** 和 **貨幣**。 這意味著不允許包含不同發票帳戶和不同貨幣的摘要更新。 其他參數可在從 **應收帳款參數** 頁面存取的 **摘要更新參數** 頁面上設定。 
8. 在 **銷售訂單** 欄位中，按一下下拉式按鈕開啟查詢。
9. 在清單中，選擇要作為摘要順序的訂單編號。
10. 按一下 **排列**。
11. 按一下 **確定**。
12. 按一下 **確定**。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]