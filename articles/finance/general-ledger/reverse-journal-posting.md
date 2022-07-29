---
title: 沖銷日記帳過帳
description: 本主題介紹能夠從憑單交易清單或財務日記帳沖銷憑單的功能。
author: kweekley
ms.date: 10/08/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerTransVoucher, LedgerJournalTable
audience: Application User
ms.reviewer: roschloma
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fb1615312e9fd1786a5a0050dda3e9e9b20fe710
ms.sourcegitcommit: 408786b164b44bee4e16ae7c3d956034d54c3f80
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/05/2021
ms.locfileid: "8451152"
---
# <a name="reverse-journal-posting"></a>沖銷日記帳過帳

[!include [banner](../includes/banner.md)]

本主題介紹用於沖銷整個日記帳或沖銷憑單交易清單中的一個或多個憑單 (而不考慮其來源) 的 Microsoft Dynamics 365 Finance 功能。 

在使用本主題介紹的任一個功能之前，必須在系統中將其開啟。 管理員可以使用 **功能管理** 工作區來檢查該功能的狀態，並視需要開啟該功能。 在此，功能會以下方式列出：
 - 模組：總帳
 - 功能名稱：**批量沖銷多張單據**

## <a name="reversing-journals"></a>沖銷日記帳

可分別沖銷日記帳明細。 使用沖銷日記帳過帳，也可以沖銷整個財務日記帳。 若要沖銷日記帳： 

- 篩選已過帳的日記帳，然後開啟日記帳的 **明細** 檢視。
- 選擇頁面頂部的 **沖銷** 選單。
- 將看到憑單總數和憑單明細，以及正在沖銷的明細總量。
- 選擇 **是**，以使用現有的交易日期，或選擇 **否**，以輸入新交易日期。 在某些情況下，原始交易的期間可能已關閉，您必須為沖銷輸入新的交易日期。
- 如果選擇 **否**，請輸入沖銷的交易日期。 
- 輸入要加到沖銷交易的註解。
- 選取 **沖銷** 按鈕。

交易將被沖銷。 

如果憑單超過 100 行，則將使用批次處理流程執行沖銷流程。 可透過查看批次處理作業中的註解來查看結果。 無法沖銷的交易都將列在批次處理作業歷史記錄中。

如果憑單等於或少於 100 行，將立即執行沖銷流程。 結果將出現在對話方塊中，其中顯示不能沖銷的所有憑單，以及不能沖銷的原因。 選擇 **確定** 關閉對話方塊。

## <a name="reversing-vouchers-from-the-voucher-transaction-list"></a>沖銷憑單交易清單中的憑單。 

也可以沖銷所有子分類帳中 **憑單交易清單** 的憑單。 此外，還可以同時沖銷多個憑單。 

若要沖銷一個或多個憑單： 

- 選擇頁面頂部的 **沖銷整個日記帳下拉式選單** 的選單。
- 將顯示憑單總數和憑單明細，以及正在沖銷的明細總量。
- 選擇 **是**，以使用現有的交易日期，或選擇 **否**，以輸入新交易日期。 在某些情況下，原始交易的期間可能已關閉，您必須輸入新的交易日期來沖銷它。
- 如果選擇 **否**，請輸入沖銷的交易日期。 
- 輸入說明沖銷交易的註解。
- 選取 **沖銷** 按鈕。

交易將被沖銷。 

如果超過 100 行憑單明細，則將使用批次處理流程執行沖銷流程。 可透過查看批次處理作業中的註解來查看結果。 無法沖銷的交易都將記錄在批次處理作業歷史記錄中。

如果等於或少於 100 行憑單明細，將立即執行沖銷流程。 結果將顯示在對話方塊中，其中顯示不能沖銷的所有憑單，以及不能沖銷的原因。 選擇 **確定** 關閉對話方塊。

僅當交易符合沖銷的業務準則時，才可以沖銷交易。 使用本主題中介紹的功能無法沖銷廠商付款。 廠商付款必須按照[沖銷廠商付款](../accounts-payable/reverse-vendor-payment.md)中列出的步驟進行沖銷。



[!INCLUDE[footer-include](../../includes/footer-banner.md)]
