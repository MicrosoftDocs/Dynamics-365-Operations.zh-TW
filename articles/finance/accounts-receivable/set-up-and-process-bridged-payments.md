---
title: 設定和處理橋接付款
description: 本主題說明如何設定和處理橋接式客戶付款。 橋接付款是分兩步驟過帳到總帳的付款。
author: rachel-profitt
ms.date: 12/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustPaymMode, VendPaymMode, LedgerJournalTable, LedgerJournalTransCustPaym, LedgerJournalTransVendPaym, LedgerJournalTransDaily
audience: Application User
ms.reviewer: roschlom
ms.custom: ''
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2022-01-03
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5e1418e573f34fadcf0bebc7232d847ee7e9768b
ms.sourcegitcommit: 5bfd6511d710deb539b4030eb0e9c48d25513595
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/19/2022
ms.locfileid: "8451476"
---
# <a name="set-up-and-process-bridged-payments"></a>設定和處理橋接付款

[!include [banner](../includes/banner.md)]

橋接付款是分兩步驟過帳到總帳的付款。 通常，當付款方式設定為 **銀行**，並且您必須僅在交易清除銀行後才將交易過帳到銀行帳戶時，才會使用此方法。 但是，您也可以將其用於分類帳科目。 在這種情況下，系統會在處理橋接過帳時將金額從一個主科目轉移到另一個主科目。

您可以從應付帳款或應收帳款建立橋接付款。 儘管本主題說明如何為應收帳款設定橋接過帳，但應付帳款交易的步驟是相似的。

## <a name="set-up-bridging-posting"></a>設定橋接過帳

若要使用橋接過帳，您必須設定一種或多種付款方式，以便它們使用 **橋接過帳** 方法。 然後，您必須選擇橋接帳戶。

1. 前往 **應收帳款 &gt; 付款設定 &gt; 付款方式**。
2. 選擇現有付款方式以啟用橋接過帳。 或者，建立新付款方式。
3. 選擇 **橋接過帳** 核取方塊。
4. 在 **橋接帳戶** 欄位中，選擇要將付款清算到銀行帳戶之前應將其過帳到的主科目。
5. 關閉頁面。

## <a name="process-and-transfer-bridging-posting"></a>處理和轉移橋接過帳

若要建立和處理橋接過帳，請按照以下步驟操作。

1. 前往 **應收帳款 &gt; 付款 &gt; 客戶付款日記帳**。
2. 選取 **新增** 以建立日記帳。
3. 在 **名稱** 欄位中，選擇名稱。
4. 將明細加入客戶付款日記帳，並選擇為橋接過帳設定的付款方式。
5. 過帳日記帳。 交易將過帳到您在上一個程序中 **橋接帳戶** 欄位內選擇的主科目。

當交易已清除銀行，並且您希望將付款從橋接帳戶轉移到為付款方式指定的付款帳戶時，請按照以下步驟進行操作。

1. 前往 **總帳 &gt; 日記帳分錄 &gt; 普通日記帳**。
2. 選取 **新增** 以建立日記帳。
3. 在 **名稱** 欄位中，選擇名稱。
4. 選擇 **明細** 已開啟日記帳詳細資料。
5. 選擇 **功能 &gt; 選擇橋接交易**。
6. 標記每筆已結清的付款，然後選擇 **接受**。
7. 過帳日記帳。
