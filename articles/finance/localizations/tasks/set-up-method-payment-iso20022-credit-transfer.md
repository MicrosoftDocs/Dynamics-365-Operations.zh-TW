---
title: 設置 ISO20022 貸記轉帳的付款方式
description: 此程序顯示如何使用電子報告產生檔案，來設定 ISO20022 匯款轉帳或任何其他付款類型的廠商付款方式。
author: mrolecki
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: VendPaymMode
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7f87cc0dfa47295f047ef97732f60733c362ca4066d9070418322b34934e3ce3
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450795"
---
# <a name="set-up-method-of-payment-for-iso20022-credit-transfer"></a>設置 ISO20022 貸記轉帳的付款方式

[!include [banner](../../includes/banner.md)]

此程序顯示如何使用電子報告產生檔案，來設定 ISO20022 匯款轉帳或任何其他付款類型的廠商付款方式。 

在完成此工作之前，您必須匯出格式組態並設定付款帳戶。

用於建立此任務的示範資料公司是 DEMF。

這是五個用於說明使用電子申報設定的廠商付款流程之程序中的第二個。 此程序是 Dynamics 365 for Operations 版本 1611 中增加的功能。

1. 進入應付帳款 > 付款安裝 > 付款方式。
2. 使用快速篩選條件尋找記錄。 例如，篩選其值為 'SEPA CT' 的 \[付款方式\] 欄位。
3. 點選編輯。
4. 在 \[期間\] 欄位中選擇 \[總計\]。
5. 在 \[付款類型\] 欄位中，選擇 \[電子支付\]。
6. 展開檔案格式區段。
7. 在 \[一般電子報表\] 欄位中選取 \[是\]。
8. 在 \[匯出格式組態\] 欄位中輸入或選擇一個值。
    * 在清單中，選擇 \[ISO20022 匯款轉帳 (DE)\]。 如果清單是空白的，則尚未匯入與啟用廠商付款匯出格式組態。  
9. 在 \[帳戶類型\] 欄位中，選取 \[銀行\]。
10. 在 \[付款帳戶\] 欄位中，指定 'DEMF OPER' 值。
11. 點選儲存。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]