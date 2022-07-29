---
title: 為客戶建立沖銷日記帳
description: 本工作指南將說明如何從收帳頁面、打開客戶發票頁面和客戶頁面設定沖銷參數，然後沖銷交易。
author: ShivamPandey-msft
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CustParameters, CustPosting, DefaultDashboard, CustCollectionsPoolsListPage, CustWriteOff, LedgerJournalTable, LedgerJournalTransDaily, CustCollections, CustOpenInvoicesListPage, CustTable
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3e810badf9b43a3b0e57390b05247113021e26b6a0242cf29022274307c5fd56
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450780"
---
# <a name="create-a-write-off-journal-for-a-customer"></a>為客戶建立沖銷日記帳

[!include [banner](../../includes/banner.md)]

本工作指南將說明如何從收帳頁面、打開客戶發票頁面和客戶頁面設定沖銷參數，然後沖銷交易。 此工作使用 USMF 公司進行示範。


## <a name="set-up-the-write-off-parameters"></a>設定沖銷參數
1. 前往 **瀏覽窗格 > 模組 > 信用和收帳 > 設定 > 應收帳款參數**。
2. 點選 **收帳** 索引標籤。
3. 展開或摺疊 **沖銷** 區段。
    - **沖銷日記帳** 是普通日記帳，將持續您建立的沖銷交易。  
    - 您可以在每次沖銷時附加一個原因代碼。 您可以在沖銷時覆寫此預設值。  
    - 如果想在沖銷中將銷售稅與原始交易分開，請將 **獨立銷售稅** 設定為 [是]。  
4. 關閉頁面。
5. 請前往 **信用與收帳 > 設定 > 客戶過帳設定檔**。 沖銷科目將用作普通日記帳中的費用科目或準備金調整。
6. 關閉頁面。

## <a name="write-off-a-customer-balance-from-the-aged-balances-page"></a>從帳齡餘額頁面沖銷客戶餘額
1. 前往 **信用和收帳 > 收帳 > 帳齡餘額**。
2. 標記您要沖銷的客戶所在的行。 例如，標有 Birch Company 的行。
3. 在 **動作窗格** 上，點選 **收帳**。
4. 點選 **沖銷**。
5. 點選 **確定**。
6. 關閉頁面。
7. 前往 **導覽窗格 > 模組 > 總帳 > 日記帳分錄 > 總帳**。
8. 選擇包含沖銷分錄的日記帳批號。 建立一個行來沖銷客戶餘額。 建立一個或多個行以將沖銷過帳到沖銷帳戶。  
9. 關閉頁面。
10. 關閉頁面。

## <a name="write-off-transactions-from-the-collections-form"></a>從收帳表單沖銷交易。
1. 前往 **信用和收帳 > 收帳 > 帳齡餘額**。
2. 選擇要沖銷交易之客戶的名稱。 例如，選擇 Cave Wholesales (US-004)。
3. 標記第一個交易列。
4. 標記第二個交易列。
5. 選取 **沖銷**。
6. 在 **原因註解** 欄位，輸入 [壞帳]。
7. 點選 **確定**。
8. 關閉頁面。
9. 關閉頁面。
10. 前往 **總帳 > 日記帳分錄 > 普通日記帳**。
11. 選擇包含沖銷分錄的日記帳批號。 建立一個行來沖銷客戶餘額。 建立一個或多個行以將沖銷過帳到沖銷帳戶。  
12. 關閉頁面。
13. 關閉頁面。

## <a name="write-off-an-invoice-from-the-open-customers-invoices-page"></a>從未結客戶發票頁面沖銷發票
1. 前往 **瀏覽窗格 > 模組 > 應收帳款 > 發票 > 未結客戶發票**。
2. 標記發票的行。 例如，標記 CIV-000667 所在的行。
3. 在 **動作窗格** 上按一下 **發票**。
4. 選取 **沖銷**。
5. 點選 **確定**。
6. 關閉頁面。

## <a name="write-off-a-customer-balance-from-the-customer-page"></a>從客戶頁面沖銷客戶餘額
1. 前往 **應收帳款 > 客戶 > 所有客戶**。
2. 選擇客戶帳戶。 例如，選擇 US-001 (Contoso Retail San Diego)。
3. 在 **動作窗格** 上，點選 **收帳**。
4. 點選 **沖銷**。
5. 點選 **確定**。
6. 關閉頁面。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]