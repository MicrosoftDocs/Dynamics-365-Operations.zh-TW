---
title: 計算和調整廠商發票上的銷售稅
description: 本主題說明如何在 Dynamics 365 Finance 中調整廠商發票上的銷售稅。
author: twheeloc
ms.date: 07/31/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransVendInvoice, VendTableLookup, TaxTmpWorkTrans
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 648d94e895a4941f5f3148134130b3ffa693a9d57e0bb4e236f5d5fb33aca48f
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450870"
---
# <a name="calculate-and-adjust-sales-tax-on-a-vendor-invoice"></a>計算和調整廠商發票上的銷售稅

[!include [banner](../../includes/banner.md)]

本主題說明如何調整廠商發票上的銷售稅。 如果原始單據顯示不同的計算稅額，您可以在過帳前調整這些金額。 此工作使用 DEMF 公司進行示範。

1. 在瀏覽窗格中，前往 **模組 > 應付帳款 > 發票 > 發票日記帳**。
2. 選取 **新增**。
3. 在新行的 **名稱** 欄位中，在下拉式功能表中選擇一個選項。
4. 在動作窗格中，選取 **明細**。
5. 在 **科目** 欄位中，指定所需值。
6. 在 **發票** 欄位，鍵入一值。
7. 在 **信用額度** 欄位，輸入數字。
8. 在 **沖銷科目** 欄位中，指定所需值。
9. 選取 **銷售稅**。
10. 在 **實際銷售稅總額** 欄位，輸入一個數字。
11. 在 **調整** 索引標籤中，可以調整每個銷售稅代碼的銷售稅金額。
12. 選取 **透過計算得出的金額重設實際金額**。
13. 選取 **確定**。
14. 選取 **儲存**。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]