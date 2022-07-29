---
title: 使用 ISO20022 付款格式建立和匯出廠商付款
description: 此程序說明如何在廠商付款日記帳中建立付款行，並使用 ISO2022 貸方轉帳範例產生廠商付款檔案。
author: mrolecki
ms.date: 01/17/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransVendPaym, SysQueryForm, VendPaymProposalEdit, BankAccountTableLookUp
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c7bd5308e7589cb280244ea85e184422cbe2aa09f1cb548a81445defbd082e42
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450546"
---
# <a name="create-and-export-vendor-payments-using-iso20022-payment-format"></a>使用 ISO20022 付款格式建立和匯出廠商付款

[!include [banner](../../includes/banner.md)]

本主題說明如何在廠商付款日記帳中建立付款行，並使用 ISO2022 貸方轉帳範例產生廠商付款檔案。

這是五個用於說明使用電子申報設定的廠商付款流程之程序中的第五個。 使用 DEMF 示範資料來完成此範例。

## <a name="example"></a>範例

1.    前往 **應付帳款 > 付款 > 付款日記帳**。
2.    點選 **新增**。
3.    在 **名稱** 欄位，輸入或選取一值。
4.    點選 **行 > 付款提案 > 建立付款提案**。
5.    展開 **預計納入的記錄** 專區。
6.    點選 **篩選**。
7.    在清單中，選擇 **廠商表** 和 **廠商帳戶欄位** 的列。
8.    在 **條件** 欄位中，輸入或選取一個值。 您可以套用任何條件來選擇要支付的廠商交易，在此範例中是使用 DE-001 作為廠商帳戶。
12.    點選 **確定**。
13.    點選 **確定**。
14.    點選 **建立付款**。
15. 產生 ISO20022 付款檔案。
    1.    點選 **產生付款**。
    2.    在 **付款方式** 欄位中，輸入或選取一個值。
    3.    在 **檔案名稱** 欄位中，輸入一個值。 對於此範例，由於用歐元付款，產生的文件將符合 SEPA。 ISO20022 貸方轉帳以及其他廠商付款格式也可用於產生其他貨幣的付款。
    4.    在 **銀行帳戶** 欄位中，輸入或選擇一個值。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]