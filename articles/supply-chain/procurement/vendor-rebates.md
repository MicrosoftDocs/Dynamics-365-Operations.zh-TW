---
title: 廠商回扣
description: 本主題概述了您在使用廠商回扣時可能想要執行的最常見工作。 廠商回扣透過自動化管理、追蹤和索取獲得的回扣所需的工作，幫助公司更好地管理其供應商回扣計劃。
author: Henrikan
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TAMVendRebateAgreement
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 2012
ms.openlocfilehash: ec8d054d023b7e3f6611199e60f661c480d44d57
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8447957"
---
# <a name="vendor-rebates"></a>廠商回扣

[!include [banner](../includes/banner.md)]

廠商回扣透過自動化管理、追蹤和索取獲得的回扣所需的工作，幫助公司更好地管理其供應商回扣計劃。

本主題概述了您在使用廠商回扣時可能想要執行的最常見工作。 概述內容涵蓋以下工作：

- 查看回扣合約的詳細資料。
- 確定有資格獲得回扣的訂單，並產生回扣索取。
- 查看和核准索取。

## <a name="audience-and-purpose"></a>對象和目標

本主題中的資訊適用於企業公司的業務決策者，例如採購經理、首席財務長 (CFO) 和會計經理等職位，他們具有以下職責：

- 協商廠商價格、折扣和回扣合約。
- 管理處理回扣索取和收款的職員。
- 以最優惠的價格訂購庫存。

擔任這些職務的人正在尋找實現這些目標的方法： 這裡有些範例：

- 靈活適應不同類型的廠商促銷計劃和回扣條件。
- 減少與監控促銷績效和處理索賠相關的管理負擔和錯誤。
- 透過應計未來應收帳款來改進現金流預測。
- 與廠商就回扣進行的和未來的談判提供量化的基礎。

## <a name="review-details-of-a-vendor-rebate-agreement"></a>查看廠商回扣合約的詳細資料

廠商回扣合約是與廠商簽訂的合同記錄，其中規定在公司實現預設的採購目標後，向該公司授與金錢獎勵資格所依據的協商條款及條件。 廠商回扣合約記錄在 **回扣合約** 頁面。

打開 **廠商回扣合約** 頁面，選擇 **採購和資源開發** &gt; **廠商回扣** &gt; **回扣合約**。

![採購合約。](media/purchase-agreement.PNG)

在 **廠商回扣合約** 頁面，可以查看有關廠商合約協商條件的詳細資料。

該合約標題指定授與公司回扣資格的一般條件。 實際上，標題資訊指定廠商在以特定數量購買特定產品時授予回扣。 在標題上，還可以指定回扣計量單位選項和計算日期類型。

- 在 **概觀** 索引標籤上，如果將 **品項代碼** 設為 *資料表* 的行用於指定品項，則合約適用於該特定品項。 如果將 **品項代碼** 設為 *群組* 或 *所有* 的行用於指定品項，將針對具有該品項代碼的每個品項單獨處理廠商回扣合約，而不是針對具有該品項代碼的所有品項進行處理。

- 在 **一般** 索引標籤的 **回扣計量單位選項** 欄位中，可以定義計量單位是否應為訂購單行獲得索取回扣資格的條件。

    - **轉換** – 訂購單行根據回扣合約獲得廠商回扣資格。 無論在該行上套用的計量單位如何，您都將收到回扣。
    - **完全符合** – 要獲得回扣資格，採購行的計量單位必須與合約上指定的計量單位相符。

- 在 **一般** 索引標籤的 **計算日期類型** 欄位中，選擇日期以用於確定採購是否發生在回扣合約有效期內。

    - **已建立** – 使用訂購單的建立日期。
    - **要求的交貨** - 使用要求的交貨日期。

在合約行上，您可以更詳細地指定廠商回扣合約。

- 在 **採購累計方式** 欄位中，可以設定回扣索取的計算。 金額可以設定為根據期間 (週、月、年、生命週期或自訂期間)。 **發票** 值表示每次為訂購單行開立發票時都會確定回扣索取。
- 在 **取自** 欄位，您可以指定回扣計算的基礎。

    - **總金額** – 根據品項的總價計算回扣。
    - **淨金額** – 根據品項的淨價 (即套用其他折扣後的價格) 計算回扣。

- **回扣計劃應計帳戶** 和 **回扣計劃支出帳戶** 欄位指定將在核准和處理之間的中間階段收到應計回扣金額的帳號。
- 當 **需要核准** 選項設為 **是** 時，回扣索取必須獲得核准才能累計或支付。
- **回扣換行類型** 欄位指定回扣的根據。

    - **數量** – 回扣以數量為基礎。
    - **金額** – 回扣以金額為基礎。

- 在 **行** FastTab 上，您可以看到如何設定不同的數量層來授予不同的回扣。 例如，在上圖中，**起始值** 和 **結束值** 欄位表示在 10 到 19 件之間的產品數量將有資格獲得每件 15 美元的回扣。

    > [!NOTE]
    > **起始值** 值是包含該起始值，而 **結束值** 不包含該結束值。 例如，**回扣換行類型** 欄位設為 **數量**，且在 **起始值** 欄位中輸入 **1**，在 **結束值** 欄位中輸入 **3**。 在這種情況下，購買一件或兩件品項時，適用回扣金額，但購買三件商品時不適用。

- 在 **工作流核准狀態** 欄位中，**核准** 值表示合約可套用到滿足該合約條款的訂購單。

## <a name="identify-orders-that-qualify-for-rebates-and-generate-rebate-claims"></a>確定有資格獲得回扣的訂單，並產生回扣索取

向與公司簽訂了回扣合約的廠商下達訂購單時，該程序標識未來的所有廠商貸記付款。 如果訂購單有資格獲得回扣，則一旦過帳採購發票，就會為每個訂單行產生回扣索取。 此流程會自動執行。 稍後，您可以查看預期回扣，以及這些回扣對產品成本和利潤率的影響。

### <a name="view-details-of-rebates-that-are-applied-to-a-purchase-order-line-per-the-vendor-rebate-agreement"></a>查看套用於每個廠商回扣合約的訂購單行的回扣詳細資料

1. 在 **訂購單** 頁面選擇訂單行，然後選擇 **訂購單行** &gt; **查看** &gt; **價格詳細資料**。
2. 在 **價格詳細資料** 頁面上，選擇 **回扣** FastTab。

回扣資訊也會顯示在 **價格詳細資料** 頁面中 **保證金估計** 部分的 **廠商回扣** 欄位中。

> [!NOTE]
> 在 **採購和資源開發參數** 頁面的 **價格** 索引標籤上，驗證 **啟用價格詳細資料** 選項設為 **是**。 如果此選項設為 **否**，則無法查看回扣。

## <a name="review-and-approve-claims"></a>查看和核准索取

產生的回扣索取代表預期將來可從廠商獲得的付款。 將貸方通知單簽發給場商之前，合約所有者通常要審查並核准索取。 但請注意，索取的狀態會決定索取是否已準備好進入核准流程。

### <a name="the-status-of-claims-and-the-effect-on-the-approval-process"></a>索取的狀態和對核准流程的影響

產生索取時，如果以累計為基礎授予回扣，則索取狀態設為 **待計算**，如果按發票授予回扣，則索取狀態設為 **已計算**。 如果索取的狀態是 **待計算**，則索取必須進入計算流程並由累計函數進行處理。 僅狀態為 **已計算** 的索取才能納入核准流程。

> [!NOTE]
> 如果廠商回扣合約上的 **需要核准** 選項設為 **否**，則產生的任何索取狀態將為 **已核准**。 對於累計基礎授予的索取必須進行核准。

### <a name="approve-claims-and-view-postings-and-invoice-details"></a>核准索取並查看過帳和發票詳細資料

核准索取後，可透過應付帳款 (A/P) 處理。 回扣索取金額的貸項通知單 (廠商發票) 是自動產生的。 然後可以將貸項新增到廠商餘額中，且 A/P 團隊可以將其包含在定期結算流程中。

1. 選擇 **採購和資源開發** &gt; **廠商回扣** &gt; **回扣索取** 以打開回扣索取。
2. 關閉回扣索取。
3. 標記索取，請在動作窗格上，選擇 **核准**。
4. 在要求頁面的 **廠商** 欄位，選擇您有權收取其回扣的廠商，然後選擇 **確定**。

    為索取金額過帳回扣應計日記帳。 此過帳將應計廠商回扣應收帳款借記為預期的廠商貸記，並將期中應計廠商回扣收款帳戶貸記為預期收益。

    ![訊息。](media/message.png)

5. 在回扣清單中選擇行，然後在動作窗格中，選擇 **回扣交易** 以查看並瀏覽到此回扣應計過帳的日記帳批號。

    若要將索取移動到定期應付帳款流程，應付帳款職員現在必須執行 [處理] 函數以完成回扣索取處理。

6. 在動作窗格上，選擇 **處理**，接著選擇 **篩選**。 在 **廠商帳戶** 欄位的 **準則** 欄位，選擇要處理其回扣索取的廠商，選擇其他相關篩選，然後選擇 **確定**。

    消息列和狀態已變更為 **已完成** 表示發生了以下事件：

    - 回扣應計日記帳過帳已沖銷應計應收帳款和支出帳戶上的期中金額。
    - 已建立回扣金額的廠商發票 (貸方通知單)。

        > [!NOTE]
        > **採購和資源開發參數** 頁面 **回扣計劃** 索引標籤上的 **手動發票過帳** 的設定決定是否對廠商發票手動過帳，或作為索取處理的一部分自動過帳。

    - 自動或手動過帳廠商發票時，已借記廠商的應付帳款，並貸記已收到的折扣和折讓金額。

        > [!NOTE] 
        > 已收折扣和折讓帳號針對在回扣的採購發票行上使用的採購類別進行指定。 反過來，採購類別在 **採購和資源開發參數** 頁面上的 **回扣計劃** 索引標籤上進行設定。

7. 在回扣清單中選擇行，然後在動作窗格中，選擇 **回扣交易** 以查看並瀏覽到此回扣應計過帳的日記帳批號，和廠商發票編號。
8. 選擇廠商發票交易記錄的行，然後在動作窗格中選擇 **廠商發票**。 如果廠商發票已過帳，您將看到發票日記帳。 否則，您將看到廠商發票為需要手動過帳的待定廠商發票。

    發票行指定 **佣金和回扣** 採購類別的廠商發票詳細資料。

9. 在 **所有廠商** 頁面選擇已收到其回扣的廠商，然後在動作窗格中選擇 **交易**。 找到發票的行。 回扣金額現已新增到廠商餘額中。

## <a name="summary"></a>摘要

處理廠商回扣的流程涉及多個手動追蹤工作，這些工作通常很繁瑣。 透過自動化這些工作，廠商回扣管理功能可以幫助您完成以下流程：

- 產生準確的回扣索取
- 在總帳中應記預期應收帳款和期中收益
- 使用到期的折讓更新廠商餘額和損益表


[!INCLUDE[footer-include](../../includes/footer-banner.md)]