---
title: 結算廠商的遠期支票
description: 當銀行已在支票逾期並由銀行清算後清算支票交易時，結算簽發給廠商的遠期支票。
author: kweekley
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: VendPostDatedChecks, LedgerJournalTable, LedgerJournalTransDaily, LedgerTransVoucher
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6b7755c3c3d092692dde6582a8d4ba74f00b10a95ba82a2782e3dad34d28e7b9
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450276"
---
# <a name="settle-a-postdated-check-for-a-vendor"></a>結算廠商的遠期支票

[!include [banner](../../includes/banner.md)]

當銀行已在支票逾期並由銀行清算後清算支票交易時，結算簽發給廠商的遠期支票。 

開始此作業之前必須先完成下列程序。

1) 設定遠期支票

2) 登記並過帳廠商的遠期支票



此程序的角色是 Treasurer。 此程序使用的是 USMF 示範公司。

1. 前往 \[應收帳款\] > \[付款\] > \[廠商遠期支票\]。
2. 按一下 \[結算\]。
3. 按一下 \[結算清算分錄\]。
    * 為支票交易結算廠商帳戶。  
4. 關閉頁面。
5. 前往總帳 > 日記帳分錄 > 普通日記帳。
6. 在 \[顯示\] 欄位中，選取 \[全部\]。
7. 選取或清除 \[僅顯示使用者建立\] 核取方塊。
8. 在清單中，標示選取的列。
9. 點選行項。
10. 點選憑證。
11. 關閉頁面。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]