---
title: 使用沖銷的折舊效應
description: 本文討論沖銷固定資產交易的潛在影響。
author: moaamer
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetTrans
audience: Application User
ms.reviewer: roschlom
ms.custom: 2961
ms.assetid: 63a3ac92-c321-4379-a86a-b1b14915f340
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9a8e5b1b7d468dbc37b295087815937fb49ad44f
ms.sourcegitcommit: 1707cf45217db6801df260ff60f4648bd9a4bb68
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/23/2021
ms.locfileid: "8451065"
---
# <a name="depreciation-effects-with-reversals"></a>使用沖銷的折舊效應

[!include [banner](../includes/banner.md)]

本文討論沖銷固定資產交易的潛在影響。 

您可以沖銷固定資產交易記錄，以及與某一固定資產相關聯的應付帳款和應收帳款交易。 您還可以撤銷某個已撤銷的交易。 

您可以沖銷或取消不是最近交易記錄過帳到資產的帳簿交易。 首先確定任何折舊交易是否在您沖銷的交易後過帳。 必須執行此步驟的原因在於，在您沖銷交易時並不重新計算折舊。 因此，折舊在沖銷後經常被高估或低估，如以下範例所示。 

為了在您沖銷某一交易時確保折舊正確，如果您在該過程中收到訊息，說明將不重新計算折舊，則不要繼續進行沖銷。 相反，首先沖銷在您嘗試沖銷的交易之後過帳的折舊交易記錄，然後繼續沖銷。 您不會收到有關折舊重新計算的警告，且您可以繼續沖銷。 

以下範例說明在您選擇不理警告訊息而繼續沖銷 (而不是先沖銷折舊交易) 的情況下發生的計算。

## <a name="example-1-depreciation-is-overstated"></a>範例 1：折舊被高估
一項資產的使用年限為五年，採用直線折舊法 (60 個折舊期)。 在此範例中折舊被高估。
#### <a name="asset-transaction-history"></a>資產交易歷程記錄

| 日期       | 交易類型                                                          | 金額                                    |
|------------|---------------------------------------------------------------------------|-------------------------------------------|
| 1 月 1 日  | 購置                                                               | 59,000.00                                 |
| 1 月 1 日  | 取得調整                                                    | 1,000.00                                  |
| 1 月 31 日 | 折舊 (使用針對一個折舊期間的方案建立) | 1,000.00 計算：帳面價值 (59,000 + 1,000) / 剩餘折舊期數 (60) |

#### <a name="reversal-action"></a>沖銷動作

| 日期      | 交易類型                | 金額    |
|-----------|---------------------------------|-----------|
| 1 月 1 日 | 購置調整沖銷 | –1,000.00 |

#### <a name="depreciation-effect"></a>折舊影響

| 日期        | 交易類型        | 金額                                                                                |
|-------------|-------------------------|---------------------------------------------------------------------------------------|
| 2 月 28 日 | 折舊 (提案) | 983.05 計算：帳面價值 (59,000 - 1,000 折舊) / 剩餘折舊期數 (59) |

折舊被高估 16.95 (1,000 - 983.05)。

## <a name="example-2-depreciation-is-understated"></a>範例 2：折舊被低估
一項資產的使用年限為五年，採用直線折舊法 (60 個折舊期)。 在此範例中折舊被低估。
#### <a name="asset-transaction-history"></a>資產交易歷程記錄

| 日期       | 交易類型                                                          | 金額                                      |
|------------|---------------------------------------------------------------------------|---------------------------------------------|
| 1 月 1 日  | 購置                                                               | 59,000.00                                   |
| 1 月 1 日  | 減值調整                                                     | 1,000.00                                    |
| 1 月 31 日 | 折舊 (使用針對一個折舊期間的方案建立) | 966.67 計算：帳面價值 (59,000 - 1,000) / 剩餘折舊期數 (60) |

#### <a name="reversal-action"></a>沖銷動作

| 日期      | 交易類型               | 金額    |
|-----------|--------------------------------|-----------|
| 1 月 1 日 | 減值調整沖銷 | –1,000.00 |

#### <a name="depreciation-effect"></a>折舊影響

| 日期        | 交易類型        | 金額                                                                                       |
|-------------|-------------------------|----------------------------------------------------------------------------------------------|
| 2 月 28 日 | 折舊 (提案) | 983.62 計算：帳面價值 (59,000 - 966.67 折舊) / 剩餘折舊期數 (59) |

折舊被低估 16.95 (983.62 - 966.67)。



## <a name="additional-resources"></a>其他資源

[固定資產折舊](fixed-asset-depreciation.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]