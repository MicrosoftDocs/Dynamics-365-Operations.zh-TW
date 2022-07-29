---
title: 定義廠商付款期限
description: 本主題說明如何設定廠商發票的付款期限。
author: abruer
ms.date: 02/11/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PaymTerm, CashDisc
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2199c12e92d631d3eb058637c48b53335d779f2d
ms.sourcegitcommit: 3105642fca2392edef574b60b4748a82cda0a386
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/12/2022
ms.locfileid: "8451545"
---
# <a name="define-vendor-payment-terms"></a>定義廠商付款期限

[!include [banner](../../includes/banner.md)]

本主題說明如何設定廠商發票的付款期限。 此工作使用 USMF 公司進行示範。

1. 進入 **瀏覽窗格 > 模組 > 應付帳款 > 付款設置 > 付款條件**。
2. 選取 **新增**。 **支付期限** 頁面用於定義如何計算到期日。 並非用於定義如何計算現金折扣日期。  
3. 在 **付款期限** 欄位，輸入一個值。
4. 在 **描述欄位** 中，輸入一個值。
5. 在 **天數** 欄位中，輸入數字。 此處輸入的數字將用於新增到到期日，或新增到 **付款方式** 所規定的結束日期。 例如，如果您選擇 **淨額**，該數字將新增到到期日。 如果選擇 **本月**，數字將新增到本月的最後一天來計算到期日。  
6. 選擇 **儲存**。
7. 關閉頁面。
8. 前往 **應付帳款 > 付款設定 > 現金折扣**。
9. 選取 **新增**。
10. 在裡面 **現金折扣** 欄位，輸入一個 ID。
11. 在 **描述** 欄位中，輸入一個值。
12. 如果廠商提供分級折扣，請選擇目前折扣到期後的下一個現金折扣。
13. 關閉頁面。
14. 在 **天數** 欄位中，輸入數字。 在 **天數** 欄位中輸入的數字，將根據 **淨額/目前** 欄位中的選項，用於計算 **現金折扣日期**。 如果選擇 **淨額**，則數字將新增到發票日期以確定現金折扣日期。 如果選擇 **本月**，則天數將新增到本月的最後日期以確定現金折扣日期。  
15. 在 **折扣** 欄位，輸入現金折扣的百分比。 
16. 輸入客戶發票的現金折扣將過帳到的主科目，然後輸入廠商發票的現金折扣將過帳到的主科目。 如果將 **貼現沖銷帳戶** 設定為 **使用廠商折扣的主科目**，則應使用該 [主科目]。 如果該選項設定為 **發票行上的科目**，現金折扣將過帳到發票行上的資產/費用帳戶。  
17. 選擇 **儲存**。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
