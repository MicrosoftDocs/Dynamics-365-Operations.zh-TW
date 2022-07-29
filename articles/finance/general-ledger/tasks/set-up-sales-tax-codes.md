---
title: 設定銷售稅代碼
description: 本主題說明如何在 Dynamics 365 Finance 設定銷售稅代碼。
author: twheeloc
ms.date: 09/27/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TaxTable, TaxData
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2539d701dda4ef5e1484d095b2d86d1f68a0dc98
ms.sourcegitcommit: 86f0574363fb869482ef73ff294f345f81d17c5b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8450996"
---
# <a name="set-up-sales-tax-codes"></a>設定銷售稅代碼

[!include [banner](../../includes/banner.md)]

本主題說明如何設定銷售稅代碼。 銷售稅代碼是針對法律實體有義務計算、徵收和支付給銷售稅務機關的每筆間接稅或關稅所建立的。

此工作使用 USMF 公司進行示範。

1. 前往 **瀏覽窗格 > 稅金 > 間接稅 > 銷售稅 > 銷售稅代碼**。
2. 選取 **新增**。
3. 在 **銷售稅代碼** 欄位中，輸入一個值。
4. 在 **名稱** 欄位中，輸入一個值。
5. 開啟下拉式清單選取一個 **結算期間**，以指定此銷售稅需要向哪一個銷售稅務機關申報與支付及其間隔時間。
6. 選擇 **分類帳過帳群組** 以指定要將銷售稅過帳到總分類帳的主科目。
7. 展開 **計算** FastTab。 這包括多個可控制如何計算銷售稅金額的欄位。 視需要填寫這些欄位。  
8. 在介面頂端的 **動作窗格** 上，選擇 **銷售稅代碼**。
9. 選擇 **值**。
10. 在 **值** 欄中輸入此稅代碼的值。

    如果選取 **每單位金額**，則在 **計算** FastTab 上的 **來源** 欄位中，此值將乘以交易上的數量，以計算銷售稅金額。  如果稅代碼不是以單位為基礎的稅，則該值是套用到此稅代碼來源的百分比，以計算銷售稅金額。     

11. 選擇 **儲存**。
12. 關閉頁面。
13. 選擇 **儲存**。

自 Microsoft Dynamics 365 Finance 10.0.22 版起，如果您使用 [稅務服務](../../localizations/global-tax-calcuation-service-overview.md)，且 **功能管理** 工作區中的 [**支援多個增值稅註冊編號**](../../localizations/emea-multiple-vat-registration-numbers.md)功能已啟用，則您可以使用 **稅務類型** 欄位來指定稅代碼的類型。 以下是可供使用的值: 

- 標準增值稅
- 減少的增值稅
- 增值稅 0%
- 消費稅
- 其他

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
