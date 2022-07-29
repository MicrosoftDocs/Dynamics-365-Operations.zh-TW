---
title: 因不平衡導致日記帳過帳失敗
description: 本主題解釋憑單交易的借方和貸方可能不平衡，進而無法過帳交易的原因。 本主題也包括修正問題的步驟。
author: kweekley
ms.date: 08/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2021-8-03
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 0f1f49a7da2f015d90987587fc251a36cfe82d49
ms.sourcegitcommit: cd7f1c63f48542a8ebcace7b3d512eb810d4b56e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/10/2021
ms.locfileid: "8451302"
---
# <a name="journal-posting-failure-because-of-imbalance"></a>因不平衡導致日記帳過帳失敗

[!include [banner](../includes/banner.md)]

本主題解釋憑單交易的借方和貸方可能不平衡，進而無法過帳交易的原因。 本主題也包括修正問題的步驟。

## <a name="symptom"></a>異常徵兆

某些案例無法過帳日記帳，並顯示下列訊息："特定憑單交易截至特定日期前不平衡 (會計貨幣：0.01 - 報表貨幣：0.06)。" 日記帳為何無法過帳？

## <a name="resolution"></a>解決方法

過帳到總帳期間，如果每張憑單的交易貨幣、會計貨幣和報表貨幣已在 **分類帳設定** 頁定義，計入的金額就必須平衡。 (當總借記金額等於總貸記金額時，憑單金額即平衡無誤。)

總計金額以會計貨幣和報表貨幣顯示在日記帳明細頁的底部。 他們 **不** 以外幣顯示外幣交易。 此外，使用者在模擬或過帳期間收到的錯誤訊息只顯示會計貨幣和報表貨幣的差異。 它不以交易貨幣顯示，因為單一憑單會有一個以上的交易貨幣，而日記帳可包括以不同交易貨幣列示的憑單。 因此，手動驗證每張只有一種交易貨幣的憑單金額是否平衡很重要。

### <a name="transaction-currency"></a>交易貨幣

模擬和過帳期間，系統會驗證每張只有一種交易貨幣的憑單在交易貨幣上是否平衡。 每張已經輸入的憑單，其交易貨幣會有一種或多種貨幣。 例如，當現金從使用歐元 (EUR) 的銀行帳戶轉移到使用加幣 (CAD) 的銀行帳戶時，在普通日記帳輸入的憑單可能會有兩種交易貨幣。

如果憑單只有一種交易貨幣，則借記總額必須等於憑單交易貨幣的貸記總額。 客戶曾遭遇下列因為交易貨幣金額不平衡導致正確過帳失敗的情況：

- 交易貨幣計入的總借記和總貸記金額 **不** 平衡，但會計貨幣和報表貨幣卻是平衡的。 客戶會假定憑單仍然可以過帳。 火過，這個假設並不正確。 **當憑單的所有明細交易貨幣都相同時，憑單上的交易貨幣金額必須始終平衡。**
- 憑單是透過資料管理框架 (DMF) 連同資料實體一同匯入，使用者會認為交易貨幣金額是平衡的。 匯入檔案的部分金額有兩位數的小數點，匯入時會全部匯入。 因此，借記不等於貸記，因為它們會捨去一分錢的一部份。 日記帳不會在憑單明細上反映這項差異，因為顯示的金額只有兩位小數。
- 憑單是透過 DMF 連同資料實體一同匯入，使用者會認為交易貨幣金額是平衡的。 雖然 **憑單** 金額平衡，但某些明細的交易日期不同。 如果您按照 **憑單和交易日期** 新增交易貨幣的總借記和總貸記金額，他們會不平衡。 當您透過系統的總帳輸入憑單時，這項要求會強制執行。 不過當憑單透過 DMF 連同資料實體一同匯入時，不會強制執行這項要求。

在一種支援的情況中，憑單會有多個交易貨幣。 此時系統 **不會** 驗證借記是否等於交易貨幣計入的貸計，因為貨幣不相配。 系統反而會驗證會計貨幣和報表貨幣的金額是否平衡。

### <a name="accounting-currency"></a>會計貨幣

如果憑單的所有明細交易貨幣相同，並且交易貨幣金額平衡，則系統會驗證會計貨幣金額是否平衡。 如果憑單以外幣輸入，則憑單明細上的匯率用來將交易貨幣換算為會計貨幣。 憑單的每行明細會先經過換算和四捨五入到小數點後兩位。 接著加總判定總借記和總貸記。 因為每行明細都會換算，所以總借記和總貸記可能不平衡。 不管如何，如果差額的絕對值在 **總帳參數** 頁面上定義的 **最大分錢差額** 值以內，憑單就會過帳，而差額會自動過帳到 Penny 差額的科目。

如果憑單的交易貨幣不只一種，則憑單的每行明細會換算成會計貨幣並且四捨五入到小數點後兩位，接著加總，判定總借記和總貸記。 若希望認定是平衡的，以會計貨幣計入的借記和貸記金額必須平衡。  分錢差額科目絕對不為了讓借記和貨記平衡，而新增到以會計貨幣計入的憑單。 

### <a name="reporting-currency"></a>報表貨幣

如果憑單的所有明細交易貨幣相同，並且交易貨幣金額平衡，則系統會驗證報表貨幣金額是否平衡。 如果憑單以外幣輸入，則憑單明細上的匯率用來將交易貨幣換算為報表貨幣。 憑單的每行明細會先經過換算和四捨五入到小數點後兩位。 接著加總判定總借記和總貸記。 因為每行明細都會換算，所以總借記和總貸記可能不平衡。 不管如何，如果差額的絕對值在 **總帳參數** 頁面上定義的 **最大報表貨幣的分錢進位** 值以內，憑單就會過帳，而差額會自動過帳到 Penny 差額的科目。

如果憑單的交易貨幣不只一種，則憑單的每行明細會換算成報表貨幣並且四捨五入到小數點後兩位，接著加總，判定總借記和總貸記。 若希望認定是平衡的，以報表貨幣計入的借記和貸記金額必須平衡。  分錢差額科目絕對不為了讓借記和貨記平衡，而新增到以報表貨幣計入的憑單。

### <a name="example-for-an-accounting-currency-imbalance"></a>會計貨幣失衡範例

> [!NOTE]
> 報表貨幣金額是按照與會計貨幣相同的方式從交易貨幣金額計算。

匯率：1.5

| 行 | 憑單 | 客戶 | 貨幣 | 借記 (交易) | 貸記 (交易) | 借記 (會計) | 貸記 (會計) |
|---|---|---|---|---|---|---|---|
| 1 | 001 | 1101-01 | 歐元 | 3.33 | | 5.00 (4.995) | |
| 2 | 001 | 1101-02 | 歐元 | 3.33 | | 5.00 (4.995) | |
| 3 | 001 | 1101-03 | 歐元 | 3.34 | | 5.01 | |
| 4 | 001 | 4101- | 歐元 | | 10.00 | | 15.00 |
| **總計** | | | | **10.00** | **10.00** | **15.01** | **15.00** |

會計貨幣餘額不足 0.01。  不過，只要會計貨幣的最大美分進位值至少 0.01，差額就會自動過帳到 Penny 差額科目，憑單將過帳成功。