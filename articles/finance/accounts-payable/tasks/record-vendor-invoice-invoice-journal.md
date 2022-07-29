---
title: 將廠商發票記錄在發票日記帳
description: 本任務指引將顯示如何記錄與訂購單無關的廠商發票。
author: abruer
ms.date: 07/11/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: VendInvoiceWorkspace, LedgerJournalTable, LedgerJournalTransVendInvoice
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9742d8ab3e84b8f9443c7f44a5ffbabdc90a62dc19e523acd0b3b2ffa0c75880
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450216"
---
# <a name="record-a-vendor-invoice-in-the-invoice-journal"></a>將廠商發票記錄在發票日記帳

[!include [banner](../../includes/banner.md)]

本任務指引將顯示如何記錄與訂購單無關的廠商發票。 此類發票範例包括用品或服務開銷。  此錄製內容使用 USMF 示範公司。

1. 前往 **導覽窗格 > 模組 > 應付帳款 > 工作區 > 廠商發票分錄**。
2. 請在 **動作窗格** 上點選 **新發票日記帳** 。
3. 點選 **新增**。
4. 在 **名稱** 欄位，輸入日記帳名稱或點選下拉式按鈕打開查閱功能。
5. 在 **描述** 欄位中，輸入一個值。
6. 在 **動作窗格** 上，點選 **明細** 。 在 **日期** 欄位，輸入將更新總帳的過帳日期。  
7. 在 **科目** 欄位，指定 **廠商科目**。
8. 在 **發票** 欄位，輸入發票號碼。
9. 在 **描述** 欄位中，輸入一個值。
10. 在 **信用額度** 欄位，輸入數字。
11. 在 **沖銷帳戶** 欄位，輸入帳號或點選下拉式按鈕打開查閱功能
    * **營業稅群組** 預設將來自廠商帳戶。  
    * **品項銷售稅群組** 預設將來自 **沖銷帳戶** 欄位指定的主科目。  
    * **到期日** 將根據付款行件計算。  
    * **現金折扣** 預設將來自廠商帳戶。
12. 如果您已經啟用廠發票日記帳工作流程，請點選 **工作流程 > 提交**。
    * 當提交獲得核准時，如果交易過帳日期落在分類帳過帳暫停或關閉期間內，日期將提前到下一次開放期間的第一天。
12. 點選 **過帳**。
13. 關閉頁面。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]