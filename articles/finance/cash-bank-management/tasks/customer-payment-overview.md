---
title: 客戶付款概觀
description: 此流程將介紹用於輸入客戶付款的各種方法。
author: kweekley
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTable, CustPaymEntry, CustTableLookup, LedgerJournalTransCustPaym, CustOpenTrans, BankAccountTableLookUp
audience: Application User
ms.reviewer: roschlom
ms.custom: intro-internal
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f3782c1dd5e326bfc8ae5c005b58d4039f32b021
ms.sourcegitcommit: 03f53980a4bc67b73ac2be76a3b3e7331d0db705
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/18/2021
ms.locfileid: "8450915"
---
# <a name="customer-payment-overview"></a>客戶付款概觀

[!include [banner](../../includes/banner.md)]

此流程將介紹用於輸入客戶付款的各種方法。 此工作使用 USMF 公司進行示範。

1. 前往 **瀏覽窗格 > 模組 > 應收帳款 > 付款 > 付款日記帳**。
2. 點選 **新增**。
3. 選擇將儲存客戶付款的付款日記帳。
4. 選取或手動輸入日記帳。
5. 在 **動作窗格** 中，點選 **輸入客戶付款**。 輸入客戶付款用於一次記錄一個客戶付款。 您在頂端輸入付款資訊，然後標記該付款支付的發票，全部在同一個頁面操作。  
6. 輸入您接收其付款的客戶。 如果您不知道客戶，但知道已付款的交易，則可以使用 [交易] 欄位來輸入付款。 在 [交易] 欄位中輸入或選擇發票。 選擇交易後，客戶將自動預設填入。
7. 在 **付款參考** 欄位中，輸入付款參考。 付款參考可以是客戶的支票號碼或客戶的電子付款參考。 僅當您在存款單上標記為包含付款時，才需要付款參考。  
8. 在 **存款單** 欄位，選擇是否將付款包含在存款單中。 
9. 在 **金額** 欄位中，輸入客戶付款金額。 付款金額不會預設填入。 必須手動輸入。 
10. 標記客戶已支付的發票。 如果付款為預付款，您無需標記任何結算發票。 付款仍然可以儲存和過帳。 發票結算可以在稍後進行。
11. 輸入應結算到標記發票的付款金額。 當付款是部分付款時，可以使用該欄位。 如果您不輸入金額，將自動為您確定要結算的金額。
12. 點選 **儲存在日記帳**。 在將付款儲存到日記帳之前，請確保已定義沖銷科目。 使用 **儲存在日記中** 將儲存付款並將其移至日記帳。 然後您可以繼續輸入下一筆付款。
13. 關閉頁面。
14. 在 **動作窗格** 點選 [行]。 打開 [行] 時，您會看到在 **輸入客戶付款** 頁面記錄並儲存到日誌中的所有付款。 您還可以使用此頁面輸入新的客戶付款，或在現有客戶付款過帳之前對其進行編輯。
15. 點選 **新增** 以建立另一筆付款。 
16. 選取您接收其付款的客戶。 如果您不知道客戶，但知道付款支付的發票，請使用 [發票] 欄位手動輸入或選擇發票。 選擇發票後客戶將預設填入。  
17. 點選 **結算交易** 以標記已支付的發票。 您無需結算付款，以開具發票。 如果這是預付款，或您不知道支付了哪張發票，您可以輸入並過帳付款。 付款可以在稍後結算到發票。  
18. 標記付款已支付的發票。 
19. 在 **金額** 欄位中，輸入將結算以標記發票的付款金額。
20. 點選 **確定**。
21. 在 **付款參考** 欄位中，輸入付款參考。 僅當您在存款單上標記為包含付款時，才需要付款參考。  
22. 在 **動作窗格** 中，點選 **過帳** 以過帳客戶付款。 



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
