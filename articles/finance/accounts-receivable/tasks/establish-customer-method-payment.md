---
title: 建立客戶付款方式
description: 本主題說明如何為客戶付款創建付款方式。
author: ShivamPandey-msft
ms.date: 07/31/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CustPaymMode, BankAccountTableLookUp
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0dd9fb37c733730360c78b702c62adadfdc6bd476ba4c436da08c86a9ad7ff55
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450651"
---
# <a name="establish-customer-method-of-payment"></a>建立客戶付款方式

[!include [banner](../../includes/banner.md)]

本主題說明如何為客戶付款創建付款方式。 此工作使用 USMF 公司進行示範。

1. 在瀏覽窗格中，進入 **模組 > 應收帳款 > 付款設定 > 付款方式**。
2. 選取 **新增**。
3. 在 **付款方式** 欄位中，輸入付款方式的識別碼。 付款方式 ID 顯示在發票和付款上，因此請使其具有足夠的描述性，以便了解記錄的付款類型以及銀行帳戶。  
4. 在 **描述** 欄位中，輸入描述。
5. 選擇要過帳付款所需的付款狀態。 創建客戶付款時，僅當付款狀態與您在此處定義的付款狀態匹配時才能過帳。  
6. 選擇應如何為發票創建客戶付款。 此選項僅在運行付款建議時使用。 在進行直接借記和從客戶的銀行帳戶中提取資金時，付款建議可用於客戶付款。  
7. 選取付款類型。 付款類型將有助於確定付款是否會進行某些驗證。  
8. 選擇將過帳到的帳戶類型。 通常，會為此選項選擇銀行。  
9. 選擇將記錄此付款的銀行帳戶。
10. 輸入銀行交易類型以識別您的銀行使用的付款類型。 銀行交易類型在銀行對帳過程中使用，可以使對帳更容易。  
11. 選擇此付款是否會暫時過帳到過渡帳戶。 如果您想嘗試支付的浮動時間以清算銀行，請使用橋接功能。 付款將暫時過帳到分類帳帳戶，直到它清算銀行，此時付款將轉移到您在此處定義的銀行帳戶。  
12. 輸入用於過帳的主科目。 如果使用橋接，這是付款將暫時過帳的主帳戶。  
13. 使用 **文件格式** 索引標籤來定義電子支付的設置。
14. 使用 **支付控制** 索引標籤來定義必填字段。 例如，如果您要求以這種付款方式存入所有付款，您可以在此索引標籤上選擇該選項。  
15. 使用 **支付屬性** 索引標籤以定義您要用於此付款方式的付款屬性。
16. 選擇 **儲存**。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]