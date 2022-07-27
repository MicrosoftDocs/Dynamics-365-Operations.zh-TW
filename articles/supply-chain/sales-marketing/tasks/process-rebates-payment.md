---
title: 處理付款回扣
description: 此程序示範如何將已核准和已處理的客戶回扣轉換為貸項通知單。
author: Henrikan
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5ce813f0f5d9aa750828b524dd9fdf9b4a9f0854
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448521"
---
# <a name="process-rebates-for-payment"></a>處理付款回扣

[!include [banner](../../includes/banner.md)]

此程序示範如何將已核准和已處理的客戶回扣轉換為貸項通知單。 您可以在 USMF 示範公司中使用本指南。 此指南的先決條件是具有一或多個狀態為「標記」的回扣要求。 如果您使用的是 USMF，您在開始此指南之前，應該先執行「產生與處理客戶回扣」指南。


## <a name="convert-rebate-claims-to-credit-note"></a>將回扣要求轉換為貸項通知單
1. 移至所有客戶。
2. 在清單中，尋找並選擇所需紀錄。
3. 在列表中，按一下所選行中的連結。
4. 在 [動作窗格] 上，按一下 [收帳]。
5. 按一下 [結算交易]。
6. 按一下 [功能]。
7. 按一下 [回扣計劃]。
    * [回扣] 頁面列出您已在客戶回扣工作台中處理且狀態為 [標記] 的回扣要求。    
8. 按一下「編輯」。
    * 在您想要包含在貸項通知單中的要求其 [標記] 欄位中設定核取記號。   
9. 按一下 [功能]。
10. 按一下 [建立貸項通知單]。
    * 將顯示一則訊息，告知您日記帳已過帳 (這是應收帳款消耗日記帳，如 [應收帳款參數] 頁面中指定)。 這會造成實際負債 (貸項) 金額移至客戶餘額。 這意味著已入帳至客戶的帳戶，而 [回扣應計帳戶] 已被扣款。  
11. 關閉頁面。
12. 按一下 [取消]。
    * 這會重新整理頁面，以便您可以看到更新。  
13. 在 [動作窗格] 上，按一下 [收帳]。
14. 按一下 [結算交易]。
    * 請注意，金額為負數 (代表總回扣金額) 且不帶發票參考的交易已新增至客戶餘額。   
15. 按一下 [取消]。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]