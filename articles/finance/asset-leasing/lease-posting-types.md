---
title: 租賃過帳類型
description: 本主題說明資產租賃交易使用的過帳類型。
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeasePostingAccounts
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 721463000c05eb1774335ccce1af39468c2aed9f179e5e88d8725f4d265d6870
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450171"
---
# <a name="lease-posting-types"></a>租賃過帳類型

[!include [banner](../includes/banner.md)]

本主題說明資產租賃交易使用的過帳類型。

## <a name="lease-asset"></a>租賃資產

與使用權 (ROU) 資產有關聯的科目。 當資產初步按照新租賃會計準則、會計準則編纂主題 842 (ASC 842) 和國際財務報告準則第 16 號 (IFRS 16) 認列時，此科目將借記計入。 以修改後的租賃而言，此科目可依照修改會增加或減少租賃負債的情況借記或貸記。

**日記帳分錄範例：** 初步認列<br>
**借方：** 租賃資產 XXX<br>
**貸方：** 租賃負債 XXX

## <a name="lease-liability"></a>租賃負債

此科目與貼現時按照新 IFRS 16 和 ASC 842 標準發生的租賃負債有關。 此科目在按照新準則初步認列租賃時記入貸方。 它會借記為租賃付款，貸記為應計利息。

**日記帳分錄範例：** 初步認列<br>
**借方：** 租賃資產 XXX<br>
**貸方：** 租賃負債 XXX

**日記帳分錄範例：** 應計利息<br>
**借記：** 應計開銷 XXX<br>
**貸方：** 租賃負債 XXX

**日記帳分錄範例：** 租賃付款<br>
**借方：** 租賃負債 XXX<br>
**貸方：** 廠商應付/租賃付款 XXX

## <a name="short-term-lease-liability"></a>短期租賃負債

過帳短期租賃負債重分類日記帳分錄時，此科目與短期租賃負債有關。 此科目在當月最後一天的攤銷期程貸記短期負債。 不過，下個月第一天會借記相同金額。

**日記帳分錄範例：** 短期租賃負債重分類<br>
**借方：** 租賃負債 XXX<br>
**貸方：** 短期租賃負債 XXX<br>
**借方：** 短期租賃負債 XXX<br>
**貸方：** 租賃負債 XXX

## <a name="depreciation-expense"></a>折舊費用

此科目與按照 IFRS 16、ASC 842 的使用權資產折舊相關費用和按照 IAS 17 和 ASC 840 的融資租賃費用有關。 當 ROU 資產每個月折舊時，將借記此科目。

**日記帳分錄範例：** 應計折舊<br>
**借方：** 折舊費用 XXX<br>
**貸方：** 累計折舊 XXX

## <a name="gainloss-on-lease-modification"></a>租賃修改的損/益

此科目與租賃修改產生的任何收益或損失有關。 如果修改減少租賃負債的金額超過 ROU 資產的帳面價值，則租賃修改期間可能產生收益。

例如，租賃負債的目前帳面價值為 $150,000，而 ROU 資產的帳面價值為 $100,000。 租賃被修改，而此修改產生 $40,000 的未來最低租賃付款 (PVFMLP) 新現值。 因此，租賃負債將借記 $110,000 ($150,000 – $40,000)。 因為 ROU 資產只有 $100,000，減少 $110,000 會將資產減為 0 (零) 甚至負值。 因此，會計指引明文規定應將剩餘部分記入收益科。 此時，最終日記帳分錄將借記 $110,000 的租賃負債、貸記 $100,000 的租賃資產，和貸記 $10,000 的收益科。

**日記帳分錄範例：** 租賃修改<br>
**借方：** 租賃負債 XXX<br>
**貸方：** 租賃資產 XXX<br>
**貸方：** 獲得 XXX

## <a name="accumulated-depreciation"></a>累計折舊

此科目與 ROU 資產的反資產帳戶有關。 過帳折舊費用時，貸記此科。

**日記帳分錄範例：** 應計折舊<br>
**借方：** 折舊費用 XXX<br>
**貸方：** 累計折舊 XXX

## <a name="variable-payment"></a>變動付款

此科目與按照 ASC 842、ASC 840 和 IAS 17 租賃的指數重估產生的變動租賃付款有關。 租賃付款期程中的變動付款納入 **變動付款** 欄位。 當發票按照含有變動付款的付款期程開立時，將借記此科目。

**日記帳分錄範例：** 租賃付款<br>
**借方：** 租賃負債 XXX<br>
**貸方：** 變動付款 XXX<br>
**貸方：** 廠商應付/租賃付款 XXX

## <a name="deferred-rent-asset-liability"></a>遞延的租金資產 (負債)

此科目與遞延租金處理租賃產生的遞延租金資產或負債有關。 如果租賃付款金額超過當期的直線租金費用，則按照遞延租金處理租賃過帳發票時借記此科目。 如果租賃付款金額少於當期直線租金費用，則計入貸方。

**日記帳分錄範例：** 租金付款 (遞延租金處理租賃)<br>
**借方：** 租賃費用 XXX<br>
**貸方：** 遞延的租金負債 XXX<br>
**貸方：** 廠商應付/租賃付款 XXX

## <a name="lease-expense"></a>租賃費用

如果租賃歸類為遞延租金處理租賃，則此科目與租賃費用有關。 當發票按照遞延租金處理租賃過帳時，將借記此科目。

**日記帳分錄範例：** 租金付款 (遞延租金處理租賃)<br>
**借方：** 租賃費用 XXX<br>
**貸方：** 遞延的租金負債 XXX<br>
**貸方：** 廠商應付/租賃付款 XXX

## <a name="impairment-expense"></a>減值費用

此科目在租賃減值時按其過帳。 借記此科目，而直接貸記 ROU 資產科目。

**日記帳分錄範例：** 租賃付款<br>
**借方：** 減值費用 XXX<br>
**貸方：** ROU 資產 XXX

## <a name="lease-payment"></a>租賃付款

如果 **支付廠商** 參數關閉，此科目按其過帳。 如果此參數關閉，則貸記此科目而不是廠商應付。

**日記帳分錄範例：** 租賃付款<br>
**借方：** 租賃負債 XXX<br>
**貸方：** 租賃付款 XXX

## <a name="expense-type-postings"></a>費用類型過帳

針對每種費用類型選取的科目在產生該費用類型的付款時記入借方。 例如，針對 **保險** 費用類型指明的科目，每當從保險費用的執行成本期程開立發票或付款日記帳分錄時，都會記入借方。

**日記帳分錄範例：** 保險付款<br>
**借方：** 保險費用類型科目 XXX<br>
**貸方：** 沖銷科目 XXX

> [!NOTE]
> 沖銷科目會以執行成本支付期程明細上的租賃等級選取。 此抵銷科目會與廠商或分類帳科目有關。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
