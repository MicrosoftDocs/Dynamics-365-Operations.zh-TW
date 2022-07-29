---
title: 銷售交易中的扣繳稅款
description: 本主題列出了避免計算選定客戶扣繳稅款的步驟。 對於在支付給您的款項中指定扣繳稅款的客戶，您可以指派預設扣繳稅款組。
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
ms.openlocfilehash: b221fc04ef82f148846fc0c282f6c8601f0eb4759d99a8dee02256cc0d42417f
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450504"
---
# <a name="withholding-tax-in-sales-transactions"></a>銷售交易中的扣繳稅款

本主題列出了避免計算選定客戶扣繳稅款的步驟。 對於在支付給您的款項中指定扣繳稅款的客戶，您可以指派 **客戶** 頁面上的預設 **扣繳稅款組**。 

1. 前往 **瀏覽窗格 > 模組 > 應收帳款 > 客戶 > 所有客戶**。

2. 點選相應的客戶帳戶，點選 **編輯**。

3. 在 **發票和交貨** 索引標籤，將 **計算扣繳稅款** 欄位設定為 **是的**。

   > [!NOTE] 
   > 如果 **計算扣繳稅款** 沒有為主資料中的客戶打開，則不計算扣繳稅款。

4. 在 **扣繳稅款組** 中選取扣繳稅款組。

5. 點選 **儲存**。

對於需要扣繳稅款的項目/服務，您可以在 **已發佈產品** 中指派預設 **項目扣繳稅款組**。

1. 前往 **瀏覽窗格 > 模組 > 產品資訊管理 > 產品 > 已發佈產品**。

2. 點選相應的項目號碼，點選 **編輯**。

3. 在 **銷售** 索引標籤中，點選 **計算扣繳稅款**。

   > [!NOTE] 
   > 如果在 **已發佈產品** 頁面的 **銷售** 索引標籤中，沒有將此項目的 **計算扣繳稅款** 設定為 **是**，則不會計算扣繳稅款。

4. 在 **項目扣繳稅款組** 清單中選取項目扣繳稅款組。

5. 點選 **儲存**。

扣繳稅款組和項目扣繳稅款稅組可以使用 **銷售訂單** 頁面來指派。 

當您建立新的銷售訂單時，預設扣繳稅款組和項目扣繳稅款組將用於銷售訂單明細的預設分錄。

扣繳稅款已按 **客戶付款日記帳** 計算和過帳。 您可以手動調整適用的扣繳稅款代碼以及 **結算交易** 頁面上 **扣繳稅款** 索引標籤中的實際扣繳稅款金額。

計算出的扣繳稅款金額將從客戶付款中扣除，並在相關憑證中過帳至 **扣繳稅款沖銷** 帳戶。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]