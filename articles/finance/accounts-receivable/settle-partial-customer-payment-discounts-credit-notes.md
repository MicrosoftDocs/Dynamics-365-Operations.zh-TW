---
title: 結算其貸項通知單有折扣的部分客戶付款
description: 本文將引導您完成當原始發票也有現金折扣時，會在貸項通知單上採用現金折扣的案例。
author: ShivamPandey-msft
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustOpenTrans, LedgerJournalTransCustPaym
audience: Application User
ms.reviewer: roschlom
ms.custom: 14564
ms.assetid: d9984cef-ddcf-46bd-816d-c01b8cc5cf48
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6476fed0ac10888c51266128f950fc0e1418b13c743894ab0992d051e733c4e1
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450426"
---
# <a name="settle-a-partial-customer-payment-that-has-discounts-on-credit-notes"></a>結算其貸項通知單有折扣的部分客戶付款

[!include [banner](../includes/banner.md)]

本文將引導您完成當原始發票也有現金折扣時，會在貸項通知單上採用現金折扣的案例。 

Fabrikam 允許客戶對部分付款採用現金折扣，也允許對折讓單 (貸項通知單) 採用現金折扣。 當為客戶得到現金折扣的發票開立折讓單時，可以對折讓單採用現金折扣。 您可以將不包含客戶所得到現金折扣百分比的金額記入客戶餘額，而不是全額記入。 結算參數位於 **應收帳款參數** 頁面。

## <a name="invoice-and-credit-note"></a>發票與折讓單
客戶 4035 有一張面額為 1,000.00 的發票，及一張面額為 100.00 的折讓單。 如果在 14 天內付款，則每份文件都有 1% 的折扣。 Arnie 可以在 **客戶交易** 頁面上檢視此資訊。

| 憑單    | 交易類型 | 日期      | 發票  | 以交易貨幣扣款的金額 | 以交易貨幣入帳的金額 | 餘額  | 貨幣 |
|------------|------------------|-----------|----------|--------------------------------------|---------------------------------------|----------|----------|
| FTI-10050  | 發票          | 6/28/2015 | 10050    | 1,000.00                             |                                       | 1,000.00 | 美元      |
| CCRN-10050 | 折讓單      | 6/28/2015 | CR-10050 |                                      | 100.00                                | -100.00  | 美元      |

## <a name="settle-a-credit-note-with-an-invoice"></a>使用發票結算折讓單
在 **客戶交易** 頁面上，Arnie 開啟 **結算交易** 頁面。 Arnie 可以使用 **結算交易** 頁面來結算發票與折讓單。 在結算流程進行的過程中，Arnie 檢視現金折扣日期和金額。 Arnie 標記了兩個文件，然後按一下 **過帳** 以結算交易。 折讓單有 -1.00 的折扣，因為 Fabrikam 允許在折讓單上採用折扣。

| 標記     | 使用現金折扣 | 憑單    | 客戶 | 日期      | 到期日  | 發票  | 以交易貨幣計價的金額 | 貨幣 | 結算金額 |
|----------|-------------------|------------|---------|-----------|-----------|----------|--------------------------------|----------|------------------|
| 已選取 | 標準            | FTI-10050  | 4035    | 6/28/2015 | 7/28/2015 | 10050    | 1,000.00                       | 美元      | 990.00           |
| 已選取 | 標準            | CCRN-10050 | 4035    | 6/28/2015 | 7/28/2015 | CR-10050 | -100.00                        | 美元      | -99.00           |

折扣資訊顯示在 **結算交易** 頁面底部。

- **現金折扣日期**: 7/12/2015 
- **現金折扣金額**: -1.00     
- **使用現金折扣**: 標準    
- **享有的現金折扣**: 0.00      
- **現金折扣金額**: -1.00     

結算金額為 100.00，其中包括 99.00 的付款和 1.00 的折扣。





[!INCLUDE[footer-include](../../includes/footer-banner.md)]