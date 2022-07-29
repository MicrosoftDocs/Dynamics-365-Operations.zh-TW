---
title: 設定薪酬格線
description: 薪酬格線用來定義和維護固定薪酬計劃的支付結構。
author: twheeloc
ms.date: 01/03/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: HRCCompGrid, HRCCompGridView, HcmCompensationWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 51b98320eac539e49787d352f32683efadc11f41
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452151"
---
# <a name="set-up-compensation-grids"></a>設定薪酬格線


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

薪酬格線用來定義和維護固定薪酬計劃的支付結構。 薪酬格線可以在多項計劃之間共用或建立新薪酬計劃時複製。  建立薪酬格線之前必須先設定等級和參考點。 本範例將使用等級和參考點的示範資料建立新級別類型的薪酬格線。 用來建立此程序的示範資料公司為 USMF。


## <a name="set-up-information-about-the-compensation-grid"></a>設定有關薪酬格線的資訊
1. 前往 **人力資源** > **薪酬** > **固定薪酬** > **薪酬格線**。
2. 點選 **新增**。
3. 請在 **格線** 欄位中鍵入一值。
4. 在 **描述** 欄位中，輸入一個值。
5. 請在 **類型** 欄位中選取一個選項。
6. 請在 **參考** 設定欄位中輸入或選取一值。
7. 請在 **貨幣** 欄位中輸入或選取一值。
8. 請在 **有效日期** 欄位中，輸入日期。

## <a name="add-levels-to-the-compensation-structure"></a>新增等級到薪酬結構
1. 點選 **薪酬結構**。
2. 在清單中，標示選取的列。
3. 請在 **等級** 欄位中輸入或選取一值。
4. 點選 **新增**。
5. 在清單中，標示選取的列。
6. 請在 **等級** 欄位中輸入或選取一值。
7. 點選 **新增**。
8. 在清單中，標示選取的列。
9. 請在 **等級** 欄位中輸入或選取一值。
10. 點選 **新增**。
11. 在清單中，標示選取的列。
12. 請在 **等級** 欄位中輸入或選取一值。
13. 點選 **新增**。
14. 在清單中，標示選取的列。
15. 請在 **等級** 欄位中輸入或選取一值。

## <a name="fill-in-the-compensation-structure-with-values"></a>請用數值填寫薪酬結構
1. 在清單中，標示選取的列。
    * 此時，可以手動輸入薪酬值到資料表的每個欄位，或者可以使用質量變化函數輕鬆填寫多欄位並執行基本計算。  
2. 請點選 **質量變化**。
    * 格線方面，我們會先將第一級的中點值套用到資料表的所有欄位。 這將是薪酬矩陣基礎。  
3. 請在 **調整類型** 欄位中選取一個選項。
4. 請在 **調整金額** 欄位中輸入數字。
5. 在清單中，標記或取消標記所有列。
6. 點選 **套用到格線**。
    * 現在我們將使用質量變化函數將每個後續等級中的金額遞增特定佔比或金額。 本範例中，各級別中點之間會有 12.5% 的差額。  
7. 請在 **調整類型** 欄位中選取一個選項。
8. 請在 **調整金額** 欄位中輸入數字。
9. 在清單中，尋找並選取所需的記錄。
10. 點選 **套用到格線**。
    * 現在我們將使用質量變化函數來調整各等級的最小和最大參考點。 本範例將使用 50% 的差額，如此一來最小參考點將調整 -20%，而最大值將調整 +20%。  
11. 請在 **調整金額** 欄位中輸入數字。
12. 請在 **參考點** 欄位中輸入或選取一值。
13. 在清單中，標記或取消標記所有列。
14. 點選 **套用到格線**。
15. 請在 **調整金額** 欄位中輸入數字。
16. 請在 **參考點** 欄位中輸入或選取一值。
17. 在清單中，標記或取消標記所有列。
18. 點選 **套用到格線**。



[!INCLUDE[footer-include](../includes/footer-banner.md)]
