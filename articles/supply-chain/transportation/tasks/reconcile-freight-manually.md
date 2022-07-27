---
title: 手動對帳運費
description: 此程序顯示如何手動對帳運費。
author: Henrikan
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLoadPlanningWorkbench, TMSFreightBillDetail, TMSInvoiceTable, TMSFreightBillInvoiceReconcile, TMSInvoiceJournal, LedgerJournalTable, LedgerJournalTransDaily, TMSFBDetailReconcile
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: henrikan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1342f8b26d3f629c9fe4439761ffc26372dce061
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448587"
---
# <a name="reconcile-freight-manually"></a>手動對帳運費

[!include [banner](../../includes/banner.md)]]

此程序顯示如何手動對帳運費。 這通常由運輸協調員完成。 您能在 USMF 示範資料公司中使用此程序。


## <a name="select-a-load-to-reconcile"></a>選擇要對帳的負載
1. 移至運輸管理 > 計劃 > 負載計劃工作台。
2. 清除「隱藏已裝運和已接收」核取方塊。 
3. 在清單中，選擇負載識別碼為 00006 的負載。

## <a name="create-a-carrier-invoice"></a>建立承運人發票
如果您手動對帳運費且未自動收到承運人發票，您可以根據貨運單建立發票。  
1. 按一下 [相關資訊]。
2. 按一下 [運費帳單詳細資料]。
3. 按一下 [產生運費帳單發票]。
4. 在 [發票] 欄位中輸入值。
5. 按一下 [確定]。

## <a name="reconcile-the-invoice"></a>對帳發票
當您對帳承運業者發票和運費帳單時，逐行執行。  
1. 按一下 [比對運費帳單和發票]。
2. 展開 [發票詳細資料] 區段。
3. 展開 [不相符的貨運帳單詳細資料] 區段。
4. 在清單中，標記所選資料列。
5. 按 一下 [比對]。
6. 展開 [相符的貨運帳單詳細資料] 區段。

## <a name="submit-the-invoice-for-approval"></a>提交發票以供核准
1. 按一下 [提交進行核准]。
2. 關閉頁面。
3. 清除「隱藏已核准」核取方塊。 
4. 按一下 [廠商發票日記帳]。
5. 按一下以開啟「參考日記帳編號」欄位中的連結。
6. 按一下 [明細]。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]