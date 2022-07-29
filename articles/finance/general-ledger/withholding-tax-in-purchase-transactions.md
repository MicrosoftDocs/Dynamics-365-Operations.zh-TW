---
title: 購買交易中的扣繳稅款
description: 對於有義務扣繳稅款的廠商，您可以在 **所有廠商** 頁面上指派 **預設扣繳稅款組**。
author: roschlom
ms.date: 01/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2020-01-12
ms.dyn365.ops.version: AX 10.0.16
ms.openlocfilehash: a1d1ddf108e5e79ca7684ecc26df1c016a0362bbec43868c7dfed6970a097a76
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450318"
---
# <a name="withholding-tax-in-purchase-transactions"></a>購買交易中的扣繳稅款

對於有義務扣繳稅款的廠商，您可以在 **所有廠商** 頁面上指派 **預設扣繳稅款組**。

1. 前往 **瀏覽窗格 > 模組 > 應付帳款 > 廠商 > 所有廠商**。

2. 點選相應的廠商帳戶，點選 **編輯**。

3. 在 **發票和交貨** 索引標籤，將 **計算扣繳稅款** 欄位設定為 **是的**。

   > [!NOTE] 
   > 如果 **計算扣繳稅款** 沒有為資料中的廠商打開，則不計算扣繳稅款。

4. 在 **扣繳稅款組** 中選取扣繳稅款組。

5. 點選 **儲存**。

對於需要扣繳稅款的項目/服務，您可以在 **已發佈產品** 中指派預設 **項目扣繳稅款組**。

1. 前往 **瀏覽窗格 > 模組 > 產品資訊管理 > 產品 > 已發佈產品**。

2. 點選相應的項目號碼，點選 **編輯**。

3. 在 **購買** 索引標籤中，點選 **計算扣繳稅款**。

   > [!NOTE] 
   > 如果在 **已發佈產品** 頁面的 **購買** 索引標籤中，沒有將此項目的 **計算扣繳稅款** 設定為 **是**，則不會計算扣繳稅款。

4. 在 **項目扣繳稅款組** 清單中選取項目扣繳稅款組。

5. 點選 **儲存**。

扣繳稅款組和項目扣繳稅款稅組可以在頁面中指派： 

- **訂購單**
- **廠商發票**
- **發票日記帳**

預設扣繳稅款組和項目扣繳稅款組將在建立 **訂購單** 和/或 **待處理的廠商發票** 時帶入明細中。 如需 **廠商發票日記帳**，您可以打開 **計算扣繳稅款** 並選取在日記帳中 **一般** 索引標籤的 **項目扣繳稅款組**。

扣繳稅款的暫扣稅額可在 **訂購單** 頁面上 **總額** 索引標籤中的 **調整扣繳稅款** 欄位中找到。

![扣繳稅款已包含在訂購單中。](media/withholding-tax-adjusted.png)

扣繳稅款是根據 **廠商付款日記帳** 計算。 您可以手動調整適用的扣繳稅款代碼以及 **結算交易** 頁面上 **扣繳稅款** 索引標籤中的實際扣繳稅款金額。

![可以在結算交易頁面上手動調整扣繳稅款。](media/withholding-tax-vendor-payment-tab.png)

計算出的扣繳稅款金額將從廠商付款中扣除，並在相關憑證中過帳至 **扣繳稅款帳戶**。

![顯示相關憑證的扣繳稅款帳戶。](media/withholding-tax-adjusted.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]