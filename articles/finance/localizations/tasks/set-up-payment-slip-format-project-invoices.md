---
title: 設定專案發票的付款單格式
description: 本主題說明如何將紙本付款單附加到專案發票，並為過帳和結算提供付款參考。
author: EvgenyPopovMBS
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: OMLegalEntity, CustFormletterParameters
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 88bdce7697e47fc49b6ffb2fe6a8a468860f41f3
ms.sourcegitcommit: 2fba4f2ef7e513357366fc640befe0d2f7bc31f5
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/05/2021
ms.locfileid: "8451044"
---
# <a name="set-up-payment-slip-format-for-project-invoices"></a>設定專案發票的付款單格式

[!include [banner](../../includes/banner.md)]

公司通常會將紙本付款單附加到發票來協助客戶，並為過帳和結算提供付款參考。 除了銷售發票和普通發票外，付款單還可用於專案或服務發票、催收帳款信函、利息票據和帳戶對帳單。 若要處理付款單，請先設定您的債權人識別號碼和付款單附件格式。

此程序使用的是 DEMF 示範公司。 

此功能適用於主要地址在丹麥的法律實體。


## <a name="set-up-a-creditor-id-number"></a>設定債權人識別號碼
1. 前往 [組織管理] > [組織] > [法律實體]。
2. 展開或摺疊 [銀行帳戶資料] 區段。
3. 點選編輯。
4. 在「FI-債權人識別碼」欄位中，輸入一個值。
5. 點選儲存。
6. 關閉頁面。

## <a name="set-up-a-payment-slip-format-for-invoices-notes-letters-and-statements"></a>為發票、票據、信函與對帳單設定付款單格式
1. 前往 \[應收帳款\] > \[設定\] > \[表單\] > \[表單設定\]。
2. 按一下 \[發票\] 索引標籤。
3. 在 \[客戶發票上的相關付款附件\] 欄位中選擇一個選項。
    * 無 – 不列印付款單。 如果付款金額採用丹麥克朗 (DKK) 以外的貨幣，請選擇此選項。   FIK 751 – 如果您打算在付款單上手動寫入付款金額和到期日，請列印 FIK 751 付款單。   FIK 752 – 如果您打算使用電腦產生的付款單，並預先列印付款金額和到期日，請印列 FIK 752 付款單。  
4. 點選儲存。
5. 按一下 \[普通發票\] 索引標籤。
6. 在 \[普通發票上的相關付款附件\] 欄位中選擇一個選項。
    * 無 – 不列印付款單。 如果付款金額採用丹麥克朗 (DKK) 以外的貨幣，請選擇此選項。   FIK 751 – 如果您打算在付款單上手動寫入付款金額和到期日，請列印 FIK 751 付款單。   FIK 752 – 如果您打算使用電腦產生的付款單，並預先列印付款金額和到期日，請印列 FIK 752 付款單。  
7. 點選儲存。
8. 按一下 \[利息票據\] 索引標籤。
9. 在 \[利息票據上的相關付款附件\] 欄位中選擇一個選項。
    * 無 – 不列印付款單。 如果付款金額採用丹麥克朗 (DKK) 以外的貨幣，請選擇此選項。   FIK 751 – 如果您打算在付款單上手動寫入付款金額和到期日，請列印 FIK 751 付款單。   FIK 752 – 如果您打算使用電腦產生的付款單，並預先列印付款金額和到期日，請印列 FIK 752 付款單。  
10. 點選儲存。
11. 按一下 \[催收帳款信函\] 索引標籤。
12. 在 \[催收帳款信函上的相關付款附件\] 欄位中選擇一個選項。
    * 無 – 不列印付款單。 如果付款金額採用丹麥克朗 (DKK) 以外的貨幣，請選擇此選項。   FIK 751 – 如果您打算在付款單上手動寫入付款金額和到期日，請列印 FIK 751 付款單。   FIK 752 – 如果您打算使用電腦產生的付款單，並預先列印付款金額和到期日，請印列 FIK 752 付款單。  
13. 點選儲存。
14. 按一下 \[帳戶對帳單] 索引標籤。
15. 在 \[帳戶對帳單上的相關付款附件\] 欄位中選擇一個選項。
    * 無 – 不列印付款單。 如果付款金額採用丹麥克朗 (DKK) 以外的貨幣，請選擇此選項。   FIK 751 – 如果您打算在付款單上手動寫入付款金額和到期日，請列印 FIK 751 付款單。   FIK 752 – 如果您打算使用電腦產生的付款單，並預先列印付款金額和到期日，請印列 FIK 752 付款單。  
16. 點選儲存。
17. 關閉頁面。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
