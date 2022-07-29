---
title: 拆分後減少餘額折舊
description: 本主題說明用來計算固定資產中，減少餘額法拆分資產後的折舊方法。
author: moaamer
ms.date: 11/17/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-11-17
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 8e59ff1ef2b06a7203c1023bade7f06019479f3929dfbd582860f102c46b49f0
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450396"
---
# <a name="reduce-balance-depreciation-after-a-split"></a>拆分後減少餘額折舊

[!include [banner](../includes/banner.md)]

本主題說明用來計算固定資產中，減少餘額法拆分資產到另一筆資產後的折舊方法。 資產帳冊配置的折舊年度為會計年度。 更多資訊，請參閱[減少餘額折舊](reduce-balance-depreciation.md)和[拆分固定資產](tasks/split-fixed-asset.md)。

如果您在取得資產後的會計期間拆分固定資產，減少的餘額折舊將計入上一年的資產帳面淨值 (NBV)。 它也將解釋從拆分資產交易產生的取得和折舊調整交易。 此行為假設資產是在一個會計年度取得，而在稍晚的會計年度拆分。 拆分後原始資產必須折舊的金額反映出資產拆分前的資產 NBV，以及取得和拆分過帳的折舊調整交易。

例如，下列行件已生效：

- 會計期間為六月 30 日到七月 1 日。
- 減少餘額佔比 18%，資產於 2019 年六月以 $10,000 的取得價格取得。
- 第一個會計年度的折舊等於$18,000，每月折舊等於$150，接著資產折舊到 2019 年十一月，金額 $738.75。
- 2019 年十一月，80% 的資產拆分到另一筆固定資產。

[![拆分後減少餘額折舊。](./media/reduce-balance-depreciation-after-split.png)](./media/reduce-balance-depreciation-after-split.png)

原始資產的折舊金額為 $1,822.25。 此金額等於過帳拆分交易前的 NBV ($9,111.25)，加上過帳拆分交易期間產生的取得調整 (-$8,000)，加上拆分交易期間產生的折舊調整 ($711)。 因此，第二年折舊為 (1,822.25 × 18%) ÷ 12 = $27.33。

第一年新固定資產的折舊金額為 (8,000 × 18%) ÷ 12 = $120。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]