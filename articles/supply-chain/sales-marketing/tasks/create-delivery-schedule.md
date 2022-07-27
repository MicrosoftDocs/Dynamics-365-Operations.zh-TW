---
title: 建立交貨排程
description: 此程序示範如何為銷售訂單建立交貨排程。
author: Henrikan
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable, SalesDeliverySchedule, SalesEditLines,  SrsReportViewerForm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 97dbbcc7173dcece9aea833551e8f985246bdbb2
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449166"
---
# <a name="create-delivery-schedule"></a>建立交貨排程

[!include [banner](../../includes/banner.md)]

此程序示範如何為銷售訂單建立交貨排程。 訂單或報價單上的數量要求分多次裝運交貨時，即可使用交貨排程。 您可使用示範資料公司 USMF 或自己的資料來執行此程序。


## <a name="create-delivery-schedule"></a>建立交貨排程
1. 前往所有銷售訂單。
2. 按一下新增。
3. 在客戶帳戶欄位中，輸入或選擇一個值。
4. 按一下確定。
5. 在品項編號欄位中，輸入或選擇一個值。
6. 在數量欄位中，輸入大於 1 的數字。
7. 按一下銷售訂單明細。
8. 按一下交貨排程。
    * 您可於交貨排程頁面指定訂單明細總數量交貨給客戶的裝運次數。    
    * 系統預設會將原始銷售明細的總數量和其他交貨詳細資料，複製到第一條交貨排程明細。 在此範例中，我們將建立兩次裝運的排程，其中第二次裝運日期是第一次的一週後。  
9. 在數量欄位中，輸入小於總數量的數字。
10. 按一下新增。
11. 在數量欄位中，輸入剩餘的數量。
12. 在要求出貨日期欄位中，輸入第一條交貨明細日期前一週的日期。
    * 在原始訂單明細指派費用後，即可運用費用轉換 FastTab 的兩個選項來指定費用在各個交貨排程明細間的分配方式。 若您選擇複製總額，則會將相同的費用金額複製到每一條明細。 分攤至交貨明細選項會在所有交貨明細間平均分配費用。  
    * 只能分配固定費用，若是變動費用，則會複製到明細中。  
13. 將滑鼠移開第二條交貨明細以更新頁面。
    * 您可檢視總數和剩餘欄位，追蹤分配至交貨排程明細的總數。 剩餘數量為零，代表原始明細的總數量已完全分配至排程中。   
14. 按一下確定。
    * 交貨排程現已複製到訂單明細。   
    * 原始訂單明細 (稱為商業明細) 已轉換為具多次交貨的訂單明細。 在此標有特殊圖示，作為交貨明細的標題。  
    * 這兩條新明細 (稱為交貨明細) 即構成一個交貨排程。 訂單將依據這些明細處理，而非原始明細。 若列印確認單、揀料單、裝箱單或發票等文件，則只會顯示交貨明細。   
    * 交貨明細可有不同交貨日期、數量、交貨模式和儲存維度，例如站點和倉庫。 然而，產品維度必須與商業明細上的內容相符，而且不能變更。  
15. 在數量欄位中，輸入大於目前顯示的數字。
16. 選擇商業明細，查看數量重新計算的效果。
17. 在動作窗格上按一下揀貨並裝箱。
18. 按一下過帳裝箱單。
19. 展開參數區段。
20. 在數量欄位中，選擇「全部」。
    * 請注意，裝箱單會依據兩條交貨排程明細來建立，而非根據原始訂單明細。  
21. 在列印裝箱單欄位中選擇是。
22. 按一下確定。
23. 按一下是。
24. 關閉頁面。


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]