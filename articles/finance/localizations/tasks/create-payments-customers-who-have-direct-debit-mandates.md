---
title: 為有直接借記要求的客戶建立付款
description: 此程序說明如何為已設定直接借記和要支付發票的客戶產生 ISO20022 直接借記付款檔案。
author: mrolecki
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CustFreeInvoice, CustTableLookup, CustPostInvoiceJob, LedgerJournalTable, LedgerJournalTransCustPaym, SysQueryForm, CustPaymProposalEdit, BankAccountTableLookUp
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0ecc28cb11b8c34a438bb47b1cfa9a37e17297e421020b32030261af95b86a49
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450600"
---
# <a name="create-payments-for-a-customer-who-have-direct-debit-mandates"></a>為有直接借記要求的客戶建立付款

[!include [banner](../../includes/banner.md)]

此程序說明如何為已設定直接借記和要支付發票的客戶產生 ISO20022 直接借記付款檔案。 建立和過帳發票是選擇性的。 您可以在產生付款檔案之前在日記帳中選擇授權，而不是建立要付款的發票，為客戶預付款案例提供支援。



用來建立此程序的示範資料公司為 DEMF。



這是五個使用電子報表組態的客戶付款流程示範程序中第五個。 必須先完成前面的工作，才能完成此工作。 您必須先匯入客戶付款電子報表設定，設定付款方式，和設定您的公司和客戶資訊。 


## <a name="post-a-free-text-invoice-with-direct-debit-information"></a>過帳具有直接借記資訊的普通發票
1. 前往 [應收帳款] > [發票] > [所有普通發票]。
2. 點選 [新增]。
3. 在客戶帳戶欄位中，輸入或選取一個值。
    * 例如，選擇 DE-010。  
4. 在 [付款方式] 欄位中，輸入或選取一個值。
    * 例如： 選擇 [電子]。  
5. 在 [直接借記授權識別碼] 欄位，輸入或選擇一個值。
6. 點選 [新增行]。
7. 在 [描述] 欄位中，輸入一個值。
8. 在 [主科目] 欄位中，指定所需值。
9. 在 [單價] 欄位中，輸入一個數字。
10. 點選 [過帳]。
11. 點選 [確定]。

## <a name="create-a-payment"></a>建立付款
1. 前往 [應收帳款] > [付款] > [付款日記帳]。
2. 點選 [新增]。
3. 在 [名稱] 欄位，輸入或選取一值。
4. 點選 [行]。
5. 點選 [付款提案]。
6. 點選 [建立付款提案]。
7. 展開 [要包括的記錄] 區段。
8. 點選 [篩選]。
9. 在清單中，選擇 [客戶交易表] 和 [付款方式] 欄位的列。
    * 您可以套用任何條件來選擇要支付的客戶交易。 在本例中，請使用 [電子] 做為支付方式篩選交易。  
10. 在 [條件] 欄位中，輸入或選取一個值。
11. 點選 [確定]。
12. 點選 [確定]。
13. 點選 [建立付款]。


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]