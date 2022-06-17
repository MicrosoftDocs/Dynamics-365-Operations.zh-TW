---
title: 財務報表常見問題
description: 本主題提供有關財務報表的一些常見問題解答。
author: jiwo
ms.date: 07/07/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2021-01-13
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 3690a541b503281f204221a72bfb5a371984d9e4
ms.sourcegitcommit: 25b3dd639e41d040c2714f56deadaa0906e4b493
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/06/2021
ms.locfileid: "8452901"
---
# <a name="financial-reporting-faq"></a>財務報表常見問題

本主題提供有關財務報表的常見問題解答。

## <a name="how-do-i-restrict-access-to-a-report-by-using-tree-security"></a>如何使用樹狀結構安全性限制對報表的存取？

以下範例示範如何使用樹狀結構安全性限制對報表的存取。

USMF 示範公司有一份並非所有財務報表使用者都有存取權的 **資產負債表** 報表。 您可以使用樹狀結構安全性限制對單一報表的存取，僅限特定使用者可以存取。

1. 登入 Financial Reporter Report Designer。
2. 選取 **檔案 \> 新增 \> 樹狀結構** 建立新的樹狀結構定義。
3. 點選兩下 (或按兩下) **單位安全性** 欄中的 **摘要** 行。
4. 選取 **使用者與群組**。
5. 選取需要存取該報表的使用者或群組。
6. 選擇 **儲存**。
7. 在報告定義中，新增您的新樹狀結構定義。
8. 在樹狀結構定義中，選取 **設定**。 然後，選取 **選擇報告單位** 下的 **包含所有單位**。

## <a name="how-do-i-identify-which-accounts-dont-match-my-balances"></a>如何識別餘額不符的帳戶？

如果有餘額不符的報告，請使用下列程序找出每個帳戶和差異。

### <a name="in-financial-reporter-report-designer"></a>在 Financial Reporter Report Designer 中

1. 建立新的列定義。
2. 選取 **編輯 \> 從維度插入列**。
3. 選取 **主科目**。
4. 選擇 **確定**。
5. 儲存列定義。
6. 建立新的欄定義。
7. 建立新的報告定義。
8. 選取 **設定** 並取消標記此選項。
9. 產生報告。 
10. 將報告匯出到 Microsoft Excel。

### <a name="in-dynamics-365-finance"></a>在 Dynamics 365 Finance 中

1. 前往 **總帳 \> 查詢和報告 \> 試算表**。
2. 設定下列欄位：

    - **開始日期** – 輸入會計年度的開始日期。
    - **結束日期** – 輸入要產生報告的日期。
    - **財務維度** – 將此欄位設為 **主科目集**。

3. 選取 **計算**。
4. 將報告匯出到 Excel。

您現在應該可以將資料從 Financial Reporter Excel 複製到 **試算表** 報告，以便比較 **期末餘額** 各欄。

## <a name="when-i-design-a-report-in-report-designer-or-when-i-generate-a-financial-report-i-received-the-following-message-the-operation-could-not-be-completed-due-to-a-problem-in-the-data-provider-framework-how-should-i-respond"></a>使用 Report Designer 設計報告或要產生財務報表時，收到以下訊息：「因為資料提供者架構的問題，作業無法完成。」 我該如何回應？

此訊息指出在您使用財務報表時，系統嘗試從資料超市擷取財務中繼資料發生問題。 有兩種方法可以處理這個問題：

- 前往 Report Designer 的 **工具 \> 整合狀態**，檢查資料的整合狀態。 如果整合未完成，請待其完成。 然後重試收到訊息時正在執行的作業。
- 聯繫支援以識別並解決問題。 系統中可能存在不一致的資料。 支援工程師可以幫助您識別伺服器的問題，並找到可能需要更新的特定資料。

## <a name="how-does-the-selection-of-historical-rate-translation-affect-report-performance"></a>選擇歷史匯率換算對報告效能有何影響？

歷史匯率通常用在保留盈餘、不動產、廠房設備及權益帳戶。 根據美國財務會計準則委員會 (FASB) 或公認會計原則 (GAAP) 的指導方針，可能需要歷史匯率。 如需詳細資訊，請參閱[財務報表中的貨幣功能](financial-reporting-currency-capability.md)。

## <a name="how-many-types-of-currency-rate-are-there"></a>貨幣匯率有幾種？

有三種：

- **現行匯率** – 這種類型通常用於資產負債表帳目。 通常被稱為 *即期匯率*，可以是當月最後一天或其他預定日期的匯率。
- **平均匯率** – 這種類型通常用於損益表 (損益) 科目。 您可以設定平均匯率以計算簡單平均或加權平均。
- **歷史匯率** – 這種類型通常用於保留盈餘、不動產、廠房設備及權益帳戶。 根據 FASB 或 GAAP 指導方針，可能需要這些科目。

## <a name="how-does-historical-currency-translation-work"></a>歷史貨幣換算如何運作？

匯率是特定於交易日期的。 因此，每筆交易都是根據最接近的匯率單獨換算。

歷史貨幣換算可以使用預先計算的期間餘額，而不是使用個別的交易詳細資料。 此行為不同於現行匯率換算行為。

## <a name="how-does-historical-currency-translation-affect-performance"></a>歷史貨幣換算如何影響效能？

更新報告顯示資料時，因為必須檢查交易詳細資料重新計算金額，所以可能會出現延遲。 每次更新匯率或過帳很多交易時都會觸發延遲。 例如，如果設定每天多次數千個科目的歷史換算，則延遲可能長達一個小時才會更新報告的資料。 另一方面，如果是較少量的特定科目，則更新報告資料的處理時間可減少到幾分鐘或更短。

同樣地，當使用歷史類型科目的貨幣換算產生報告時，會有額外的逐筆交易計算。 視科目數量而定，報告產生時間可能會增加一倍以上。

## <a name="what-are-the-estimated-data-mart-integration-intervals"></a>預估的資料超市整合間隔為何？

Financial Reporter 使用 16 項工作將資料從 Dynamics 365 Finance 複製到 Financial Reporter 資料庫。 下表列出這 16 項工作，並顯示每項工作執行頻率的指定間隔。 間隔不能改變。

| 名稱                                                       | 間隔 | 間隔計時 |
|------------------------------------------------------------|----------|-----------------|
| AX 2012 科目類別到科目類別            | 41       | 分鐘         |
| AX 2012 科目到科目                                | 7        | 分鐘         |
| AX 2012 公司到公司                               | 300      | 秒         |
| AX 2012 公司到組織                          | 23       | 分鐘         |
| AX 2012 維度組合到維度組合    | 1        | 分鐘         |
| AX 2012 維度值到維度值                | 11       | 分鐘         |
| AX 2012 維度到維度                            | 31       | 分鐘         |
| AX 2012 匯率到匯率                    | 17       | 分鐘         |
| AX 2012 會計年度到會計年度                        | 13       | 分鐘         |
| AX 2012 總帳交易到事實                | 1        | 分鐘         |
| AX 2012 組織階層到樹狀結構                   | 3,600    | 秒         |
| AX 2012 案例到案例                              | 29       | 分鐘         |
| AX 2012 交易類型限定詞到事實類型限定詞 | 19       | 分鐘         |
| 維護工作                                           | 1        | 分鐘         |
| MR 報告定義到 AX7 財務報表             | 45       | 秒         |
| MR 報告版本到 AX 財務報表版本         | 45       | 秒         |

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
