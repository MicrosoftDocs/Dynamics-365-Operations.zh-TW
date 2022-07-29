---
title: 設定銷售稅結算期間
description: 本主題說明如何在 Dynamics 365 Finance 設定銷售稅結算期。
author: twheeloc
ms.date: 08/05/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TaxPeriod
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1f57cd2b5b0f8f86d67500086403c5f484a263f76601453c00f59ede901b01a8
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450330"
---
# <a name="set-up-sales-tax-settlement-periods"></a>設定銷售稅結算期間

[!include [banner](../../includes/banner.md)]

本主題說明如何設定銷售稅結算期。 銷售稅結算期包含與必須申報和繳納銷售稅的期間間隔相關資訊。 結算流程可以在特定日期間隔執行達一段結算期。 與結算期相關的所有稅代碼都將被結算。 根據相關銷售稅務機關的設定，將納稅義務過帳到廠商或總分類帳科目。

此工作使用 USMF 公司進行示範。

1. 在瀏覽窗格中，前往 **模組 > 稅金 > 間接稅 > 銷售稅 > 銷售稅結算期間**。
2. 選取 **新增**。
3. 在 **結算期間** 欄位中輸入一個值。
4. 在 **描述** 欄位中，輸入一個值。
5. 在 **機關** 欄位中，選取受理針對該結算期所建立申報與繳納的銷售稅務機關。
6. 在清單中，尋找並選取所需的記錄。
7. 在 **付款期限** 欄位中，從下拉功能表中選擇需要的記錄。 相關的銷售稅務機關可以設定為廠商，銷售稅結算將建立一個未結的廠商發票。 付款期限定義未結廠商發票的到期日。  
8. 選取結算期間隔的類型。
9. 輸入每個期間的期間間隔單位數。 例如，一季有 3 個月。
10. 選取或清除 **使用批次處理執行銷售稅結算** 核取方塊。 結算期的結算流程可以在背景中作為批次工作處理。 若在一個期間間隔內有大量的稅交易，則建議採用此設定。
11. 選取或清除 **防止產生沖銷稅交易** 核取方塊。 預設情況下，系統在結算流程期間會產生沖銷稅交易，若在期間間隔內有大量稅交易的話，這會造成發生效能問題。 選取此核取方塊可防止產生沖銷稅交易。
12. 展開 **期間間隔** 索引標籤。
13. 選取 **新增**。
14. 在 **開始日期** 欄位中輸入日期。
15. 請在 **截止日期** 欄位中輸入日期。
16. 選取 **新期間間隔**。 輸入第一個期間間隔後，系統會自動建立新期間。 您可以返回並視需要新增新的期間間隔。  
17. 關閉頁面。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
