---
title: 負數天數和動態負數天數
description: 本主題說明有關負數天數和動態負數天數的資訊，以及如何使用這些資訊來協助您的業務。
author: ChristianRytt
ms.date: 05/25/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2019-06-07
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d5e86cc8abd4de1e23b1a7f7217bbb1fd5ea966b988a879e663b6f393e0d1204
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447081"
---
# <a name="negative-days-and-dynamic-negative-days"></a>負數天數和動態負數天數

[!include [banner](../includes/banner.md)]

本主題說明有關負數天數和動態負數天數的資訊，以及如何使用這些資訊來協助您的業務。 *負數天數時間範圍* 代表您有負數庫存時，願意在訂購新補貨之前等待的天數。

在本主題中，您將瞭解以下資訊：

- 如何建立規劃訂單
- 負數天數時間範圍與品項前置時間之間的關聯性
- 如何計算動態負天數時間範圍，以及如何將品項前置時間納入計算
- 如何解讀與負數天數有關的[改善原料需求規劃 (MRP) (總體規劃) 執行時間的建議](https://blogs.msdn.com/b/axmfg/archive/2015/01/02/checklist-for-improving-mrp-performance-part-2-how-to-setup-planning-parameters.aspx)

本主題透過三個假設情境來協助您理解此資訊。 情境之間的區別在於您有補貨需求的時間點：在品項前置時間之前、期間或之後。

## <a name="scenario-1-you-get-demand-before-the-items-lead-time-period"></a>情境 1：您在品項前置時間前產生補貨需求

您產生補貨需求的時間可能距離品項前置時間還很久，也可能正好在前置時間開始之前。 此範例情境如下：

- DemoProduct 品項的購買前置時間為六天。
- 在第零天 (1 月 1 日)，DemoProduct 品項的庫存量為 0 (零)。
- 在第零天 (1 月 1 日)，您收到一份 DemoProduct 品項數量為 10 項的銷售訂單。
- 在第七天 (1 月 8 日)，有一份 DemoProduct 品項數量為 10 項的現有訂購單。

下方以視圖說明此情境。

![情境 1 視圖。](./media/negative-days-1.jpg)

### <a name="case-a-negative-days-are-less-than-the-items-lead-time"></a>案例 A：負數天數小於品項前置時間

如果將負數天數設為小於品項前置時間的數字，MRP 會在負數天數時間範圍內尋找 DemoProduct 品項的收據。 由於找不到任何收據，因此 MRP 建立一個新的計劃訂購單。 此計劃訂單立即延後六天 (前置時間)。 因此，品項將在 1 月 7 日送達。 由於建立新計劃訂購單後，將不再需要現有訂購單，因此該訂購單會收到 **取消** 動作訊息。

下圖顯示此案例的螢幕擷取畫面。

![情境 1 的案例 A 螢幕擷取畫面。](./media/negative-days-2.png)

下方以視圖說明此案例發生的狀況。

![情境 1 的案例 A 視圖。](./media/negative-days-3.png)

如果以 MRP 成效和計劃緊湊程度來考慮，這個案例表現不佳。 MRP 必須建立新計劃訂單，且必須計算延遲和動作。 這些工作非常耗時。 這類案例還會在您的計劃中額外增加兩項交易。 另一方面，銷售訂單僅延後了六天，而不是七天。

### <a name="case-b-negative-days-are-more-than-the-items-lead-time"></a>案例 B：負數天數超過品項前置時間

為了提高 MRP 成效，您可以將負數天數設為大於品項前置時間的數字。 由於在這種情境下您無法在前置時間內獲得供應，所以只要此搜尋合理，您就可以搜尋收據。 雖然 MRP 的執行時間會縮短，但您應該注意訂單的額外延遲時間。

### <a name="case-c-automatically-correlate-the-items-lead-time-to-the-negative-days-time-fence"></a>案例 C：自動建立負數天數時間範圍與品項交期之間的相關性

若要自動建立負數天數時間範圍與品項交期之間的相關性，您可以使用動態負數天數。 若要使用動態負數，請依序前往 **總體規劃 \> 設定 \> 總體規劃參數**，然後在 **一般** 索引標籤的 **涵蓋範圍** 區段，將 **使用動態負數天數** 選項設為 **是**。 隨後 MRP 會在動態負數天數時間範圍內尋找收據。 此時間範圍是使用以下公式計算：

動態負天數時間範圍 = 購買前置時間 + 負數天數時間範圍 + (目前日期 - 需求日期)

(如果 DemoProduct 品項的預設訂單類型是 **生產** 或 **轉移**，則前置時間為 **庫存** 前置時間。)

因此使用動態負數天數時，現在 MRP 搜尋收據的時間範圍是 6 + 2 + 0 = 8 天。 MRP 找到現有訂購單並與銷售訂單建立關聯， 並未建立新計劃訂單。 因此，MRP 的執行時間較短。 下圖顯示了 DemoProduct 品項的淨需求。

![情境 1 的案例 C 的淨需求。](./media/negative-days-4.png)

下方以視圖說明此案例發生的狀況。

![情境 1 的案例 C 視圖。](./media/negative-days-5.png)

### <a name="case-d-use-only-dynamic-negative-days"></a>案例 D：僅使用動態負數天數

如果將負數天數設為 **0** (零) 且僅使用動態負數天數時間範圍，則動態負數天數時間範圍為 6 + 0 + 0 = 6 天。 在這個案例下，結果與此情境的案例 A 結果相同。 MRP 必須建立新計劃訂單，且必須計算延遲和動作。 這些工作很耗時，也可能無法達到理想結果。 您還需處理兩個交易。 由於無法按時滿足品項送達的需求，因此這個案例會導致計劃衍生不必要的複雜性。

下圖顯示此案例的螢幕擷取畫面。

![情境 1 的案例 D 螢幕擷取畫面。](./media/negative-days-6.png)

下方以視圖說明此案例發生的狀況。

![情境 1 的案例 D 視圖。](./media/negative-days-7.png)

### <a name="case-e-use-both-negative-days-that-are-more-than-the-items-lead-time-and-the-dynamic-negative-days-time-fence"></a>案例 E：同時使用超過品項前置時間的負數天數和動態負數天數時間範圍

如果您將負數天數設為大於品項前置時間的數字，同時使用動態負數天數時間範圍，則動態負數天數時間範圍為 6 + 6 + 0 = 12 天。 這種方法可能會導致 MRP 必須在非常長的時間範圍內搜尋結果。 若需進一步瞭解案例 E 如何與負數天數設為較長時間範圍的情況相關，請參閱本主題的[結論](#conclusion)區段。

## <a name="scenario-2-you-get-demand-during-the-items-lead-time-period"></a>情境 2：您在品項前置期間內產生補貨需求

您可能會在品項前置時間內的某個時候產生補貨需求。 此範例情境如下：

- DemoProduct 品項的購買前置時間為六天。 
- 在第零天 (1 月 1 日)，DemoProduct 品項的庫存量為 0 (零)。
- 在第四天 (1 月 5 日)，也就是品項的前置時間內，您收到了 DemoProduct 品項數量為 10 項的銷售訂單。
- 在第七天 (1 月 8 日)，有一份 DemoProduct 品項數量為 10 項的訂購單。

下方以視圖說明此情境。

![情境 2 視圖。](./media/negative-days-8.png)

### <a name="case-a-negative-days-are-less-than-the-items-lead-time"></a>案例 A：負數天數小於品項前置時間

如果將負數天數設為小於品項前置時間的數字，MRP 會在負數天數時間範圍內尋找 DemoProduct 品項的收據。 因為找不到任何收據，MRP 建立了以目前日期為訂單日期的新計劃訂購單。 此計劃訂單立即延後六天 (前置時間)。 因此，品項將在 1 月 7 日送達。 由於建立新計劃訂購單後，將不再需要現有訂購單，因此該訂購單會收到 **取消** 動作訊息。

下圖顯示此案例的螢幕擷取畫面。

![情境 2 的案例 A 螢幕擷取畫面。](./media/negative-days-9.png)

下方以視圖說明此案例發生的狀況。

![情境 2 的案例 A 視圖。](./media/negative-days-10.png)

### <a name="case-b-negative-days-are-more-than-the-items-lead-time"></a>案例 B：負數天數超過品項前置時間

此案例類似於情境 1 的案例 B。 如果您將負數天數設為大於品項前置時間的數字，將不會取得新的計劃訂單。 銷售訂單會附加到現有訂購單。

### <a name="case-c-automatically-correlate-the-items-lead-time-to-the-negative-days-time-fence"></a>案例 C：自動建立負數天數時間範圍與品項交期之間的相關性

這個案例類似於情境 1 的案例 C，因為動態負數天數的執行效果與該案例一樣良好。 動態負數天數時間範圍現在是 6 + 2 - 4 = 4 天。 如果使用這種方法，MRP 會找出現有訂購單並加入銷售訂單。 因為未建立新的計劃訂單，所以 MRP 的執行時間更短。

下圖顯示此案例的螢幕擷取畫面。

![情境 2 的案例 c 螢幕擷取畫面。](./media/negative-days-11.png)

下方以視圖說明此案例發生的狀況。

![情境 2 的案例 C 視圖。](./media/negative-days-12.png)

### <a name="case-d-use-only-dynamic-negative-days"></a>案例 D：僅使用動態負數天數

如果將負數天數設為 **0** (零) 且僅使用動態負數天數時間範圍，則動態負數天數時間範圍現在為 6 + 0 - 4 = 2 天。 在這個案例下，結果與此情境的案例 A 結果相同。 有關發生情況的視圖，請查看此情境的案例 A。

### <a name="case-e-use-both-negative-days-that-are-more-than-the-items-lead-time-and-the-dynamic-negative-days-time-fence"></a>案例 E：同時使用超過品項前置時間的負數天數和動態負數天數時間範圍

如果您將負數天數設為大於品項前置時間的數字，同時使用動態負數天數時間範圍，則動態負數天數時間範圍為 6 + 6 - 4 = 8 天。 這種方法可能會導致 MRP 必須在非常長的時間範圍內搜尋結果。 若需進一步瞭解案例 E 如何與負數天數設為較長時間範圍的情況相關，請參閱本主題的[結論](#conclusion)區段。

## <a name="scenario-3-you-get-demand-after-the-items-lead-time-period"></a>情境 3：您在品項前置時間後產生補貨需求

您可能會在品項前置時間後產生補貨需求。 此範例情境如下：

- DemoProduct 品項的購買前置時間為六天。
- 在第 0 天 (1 月 1 日)，DemoProduct 品項的庫存量為 0 (零)。
- 在第七天 (1 月 8 日)，也就是品項的前置時間之外，您收到了 DemoProduct 品項數量為 10 項的銷售訂單。
- 在第十天 (1 月 11 日)，有一份 DemoProduct 品項數量為 10 項的訂購單。

下方以視圖說明此情境。

![情境 3 視圖。](./media/negative-days-13.png)

### <a name="case-a-negative-days-are-less-than-the-items-lead-time"></a>案例 A：負數天數小於品項前置時間

如果您將負數天數設為小於品項前置時間的數字，則 MRP 會比銷售訂單的需求日期提前兩天。 由於找不到任何項目，因此 MRP 會在 1 月 2 日建立一個新的計劃訂購單。 此計劃訂購單將及時裝運以滿足銷售訂單需求。 現有訂購單因不是必要項目，所以會收到 **取消** 動作訊息。

下圖顯示此案例的螢幕擷取畫面。

![情境 3 的案例 A 螢幕擷取畫面。](./media/negative-days-14.png)

下方以視圖說明此案例發生的狀況。

![情境 3 的案例 A 視圖。](./media/negative-days-15.png)

> [!NOTE]
> 在上述螢幕擷取畫面中，訂購單需求日期為 1 月 12 日。 由於該螢幕擷取畫面是在 2015 年擷取，當時 1 月 11 日是星期日，因此 MRP 將需求日期移到下個工作日，即 1 月 12 日星期一。 不過，訂購單的交貨日期為 1 月 11 日。

### <a name="case-b-negative-days-are-more-than-the-items-lead-time"></a>案例 B：負數天數超過品項前置時間

如果您將負數天數設為大於品項前置時間的數字，將不會取得新的計劃訂單。 銷售訂單會附加到現有訂購單。 因此，銷售訂單延後。 如果您建立計劃訂單，可以按時運送銷售訂單。

下圖顯示此案例的螢幕擷取畫面。

![情境 3 的案例 B 螢幕擷取畫面。](./media/negative-days-16.png)

下方以視圖說明此案例發生的狀況。

![情境 3 的案例 B 視圖。](./media/negative-days-17.png)

### <a name="case-c-automatically-correlate-the-items-lead-time-to-the-negative-days-time-fence"></a>案例 C：自動建立負數天數時間範圍與品項交期之間的相關性

這個案例類似於情境 1 的案例 C，因為動態負數天數的執行效果與此情境的案例 B 一樣良好，甚至更佳。

動態負數天數時間範圍是 6 + 2 – 7 = 1 天。 然而，在這個案例中，系統仍會考慮負數天數前置時間 (2)，因為 MRP 會考慮負數天數前置時間與動態負數天數前置時間之間的最大值。 因此，這個案例的結果與此情境的案例 A 結果相同。

下方以視圖說明此案例發生的狀況。

![情境 3 的案例 C 視圖。](./media/negative-days-18.png)

### <a name="case-d-use-only-dynamic-negative-days"></a>案例 D：僅使用動態負數天數

如果將負數天數設為 **0** (零) 且僅使用動態負數天數時間範圍，則動態負數天數時間範圍現在為 6 + 0 - 7 = -1 天。 在這個案例中，系統仍會考慮負數天數前置時間 (2)。 因此，這個案例的結果與此情境的案例 A 結果相同，也具有同樣的缺點。 有關發生情況的視圖，請查看情境 2 的案例 A。

### <a name="case-e-use-both-negative-days-that-are-more-than-the-items-lead-time-and-the-dynamic-negative-days-time-fence"></a>案例 E：同時使用超過品項前置時間的負數天數和動態負數天數時間範圍

這個案例與情境 1 和 2 的案例 E 相同。 基本上具有相同的優點和缺點。

## <a name="conclusion"></a>結論

正如本主題中的三個情境所示，您可以將負數天數設為大於涵蓋範圍群組中的品項前置時間數字。 或者，您也可以僅使用動態負數天數，並將負數天數設為有負庫存時願意在訂購新補貨前等待的天數 (也就是您願意進一步延遲需求的天數)。 此外，同一涵蓋群組中的品項應具有相似的前置時間。

如果您將負數天數設為 **0** (零) 且不使用動態負天數，MRP 會一律建立新的計劃訂單來滿足需求。 在這種情況下，請務必使用動作訊息確保不會堆積庫存。

您可能想將負數天數設為較長的時間範圍，然後搭配使用動作訊息。 這種方法可產生良好的規劃結果，但也略微耗時。 此外，由於您必須分析並套用動作訊息，因此這種方法也可能較難進行分析。 範例如下：

- DemoProduct 品項的購買前置時間為六天。
- 在第 0 天 (1 月 1 日)，DemoProduct 品項的庫存量為 0 (零)。
- 在第零天 (1 月 1 日)，您收到一份 DemoProduct 品項數量為 10 項的銷售訂單。
- 在第九天 (1 月 10 日)，您收到一份 DemoProduct 品項數量為 10 項的銷售訂單。
- 在第十一天 (1 月 12 日)，有一份 DemoProduct 品項數量為 10 項的訂購單。
- 負數天數會設為 **20**，遠多於比品項前置時間。

下方以視圖說明發生的狀況。

![範例視圖。](./media/negative-days-19.png)

MRP 會產生以下結果。

![結果範例 1。](./media/negative-days-20.png)

在先前的螢幕擷取畫面中，銷售訂單需求日期是 1 月 9 日而不是 1 月 10 日。 由於該螢幕擷取畫面是在 2015 年擷取，當時 1 月 10 日是星期六，因此訂單的需求日期應為上個工作日，即 1 月 9 日星期五。

MRP 會建立一個計劃訂購單來滿足第一個銷售訂單提出的需求，不過隨後也會建議您取消計劃訂單，因為您可以推進現有訂購單並增加其數量。

結果並非有誤，但是 MRP 的執行時間可能會更長，因為 MRP 必須建立所有延遲和建議。 此外，規劃者可能需要更多時間來瞭解 MRP 結果。 最重要的是，在這種情況下，規劃者必須瞭解並使用動作訊息。

如果您將負數天數減少到更接近品項前置時間的數字並使用動態負天數，則 MRP 會產生以下結果。

![結果範例 2。](./media/negative-days-21.png)

MRP 建立附加到第一個銷售訂單的計劃訂單。 然後一如預期，第二個銷售訂單將根據負數天數設定與現有訂購單建立關聯。 這個計劃結果也正確，且 MRP 的執行時間可能更短。 在這種情況下，您不必瞭解並知道如何使用動作訊息。

為了協助確保為業務輸入正確的值，您必須同時考慮功能和 MRP 執行時間。 因此，您可能需要經過一些嘗試和錯誤才能確定最佳值。

## <a name="see-also"></a>另請參閱

若需查看更多相關討論，請參閱原始的[更多 (動態) 負數天數相關資訊](/archive/blogs/axmfg/more-about-dynamic-negative-days)部落格文章。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
