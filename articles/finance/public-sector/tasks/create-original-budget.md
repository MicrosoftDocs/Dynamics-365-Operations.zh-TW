---
title: 建立原始預算，然後沖銷公共部門的初步預算分錄
description: 本主題提供有關如何使用具有初步預算金額的預算模型和維度值，建立和沖銷原始預算分錄的資訊。
author: twheeloc
ms.date: 02/14/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: BudgetTransaction, BudgetAccountStructureLookup, BudgetTransactionMultiPost
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.search.industry: Service industries
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7758a1c9edfa129ba8b63a146b38ed3f119fd051
ms.sourcegitcommit: 6a269db08e8bb3bb3405c9f4a512091d13c80faa
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2022
ms.locfileid: "8451569"
---
# <a name="create-an-original-budget-and-then-reverse-preliminary-budget-entries-in-the-public-sector"></a>建立原始預算，然後沖銷公共部門的初步預算分錄

[!include [banner](../../includes/banner.md)]

當您建立原始預算分錄並使用包含初步預算金額的預算模型和維度值時，可以沖銷初步預算金額。 透過使用 PSUS 示範公司資料的公共部門分區建立該程序。

1. 前往 **預算 > 預算登記分錄**。
2. 點選 **新增**。
3. 在 **預算模型** 欄位中，點選下拉式按鈕以開啟查詢。
4. 在清單中，尋找並選取所需的記錄。
5. 在 **預算代碼** 欄位中，點選下拉式按鈕以開啟查詢。
6. 在清單中，點選 **原始預算**。
7. 點選 **儲存**。
8. 點選 **新增行**。
9. 選用：如果要變更標題中的日期，請輸入新日期。 此日期決定預算將記錄到的會計期間。
10. 在 **科目結構** 欄位，點選下拉式按鈕打開查閱功能。
11. 在清單中，尋找並選取所需的記錄。
12. 在 **維度值** 欄位中，指定所需值。
13. 在 **金額** 欄位中，輸入數字。
14. 在 **貨幣** 欄位中，按一下下拉式按鈕開啟查詢。
15. 在清單中，點選已選取列的連結。
16. 點選 **儲存**。
17. 點選 **更新預算餘額**。
    * 選用：您可以選擇 **沖銷初步預算** 選項。 請注意，您可以沖銷所有初步預算分錄，或只沖銷具有您指定預算代碼的初步預算分錄。  
    * 要進行選擇性選項，請點選頁面頂端的 **解除鎖定** 圖示。  
18. 點選 **更新**。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
