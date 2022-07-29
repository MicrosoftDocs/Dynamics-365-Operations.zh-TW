---
title: 存入多筆客戶付款
description: 存入多筆客戶付款。
author: ShivamPandey-msft
ms.date: 07/18/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransCustPaym, CustTableLookup
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 776871aad417d26486ec109f8b0b7f51db32d065d801e51459584c82269f9ac7
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450777"
---
# <a name="deposit-customer-payments"></a>存入多筆客戶付款

[!include [banner](../../includes/banner.md)]

存入多筆客戶付款。 此工作使用 USMF 公司進行示範。

1. 前往 **瀏覽窗格 > 模組 > 應收帳款 > 付款 > 付款日記帳**。
2. 選取 **新增**。
3. 在 **名稱** 欄位的下拉式選單中選取 **CustPay**。
4. 選取 **行**。
5. 在 **帳戶** 欄位，選擇記錄付款的客戶。
6. 在 **信用** 欄位中，輸入付款的金額。 您可以選擇將金額留空，並讓系統透過選擇已支付的發票計算出金額。  
7. 在 **付款參考** 欄位，輸入一個值。 付款參考可以是您輸入的付款的支票號碼。 填寫付款參考是為了在存款單上新增付款。  
8. 標記 [使用存款單] 方塊。 如果付款應包含在存款中，請將此設定變更為 [是]。  
9. 選取 **新增**。
10. 在 **帳戶** 欄位，選擇下一個付款的客戶。
11. 在 **信用** 欄位中，輸入付款金額。
12. 在 **付款參考** 欄位，輸入一個值。
13. 標記 **使用存款單** 方塊。
14. 選取 **過帳**。 必須在產生存款單之前過帳付款。 這是為了確保在產生存款單後付款不會發生變化。  
15. 選取 **功能**。
16. 選取 **存款單**。
17. 選取 **確定**。 第一頁用於建立存款單。  
18. 選取 **確定**。 第二步是列印存款單，但此步驟不是必須的。  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]