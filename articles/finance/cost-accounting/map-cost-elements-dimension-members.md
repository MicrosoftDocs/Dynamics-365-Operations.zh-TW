---
title: 將成本元素維度成員測繪到維度成員常用集合
description: 憑藉測繪不同成本元素維度成員到成本元素維度成員常用集合，您將資料併入常用格式方便分析。
author: AndersGirke
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CAMDimension, CAMDimensionMember, CAMDimensionMapping
audience: Application User
ms.reviewer: roschlom
ms.custom: 223234
ms.assetid: 4c66a231-aed2-48b5-9727-b3eb4fe6e6aa
ms.search.region: global
ms.author: roschlom
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: b9ac59f305afd55edfcfb3b47bf38ddd44d92a706904f55a069a6a9fc9050825
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450273"
---
# <a name="map-cost-element-dimension-members-to-a-common-set-of-dimension-members"></a>將成本元素維度成員測繪到維度成員常用集合

[!include [banner](../includes/banner.md)]

憑藉測繪不同成本元素維度成員到成本元素維度成員常用集合，您將資料併入常用格式方便分析。

如果您是一間全球性公司並遵守法規會計要求，您可能會使用多個會計科目圖表。 當您從不同的會計科目表匯入成本元素維度成員時，您會以混合科目告終。 不過，這些帳戶實際性質可能相同，您可能希望使用常用格式分析和配置成本。

## <a name="map-cost-element-dimension-members-to-a-common-format"></a>測繪成本元素維度成員到常用格式
下列範例顯示您身為成本控制者，如何在成本會計中建立新成本元素維度，此維度測繪美國會計科目表結構和法國會計科目表結構的成本要素維度成員到成本要素維度成員常用集合。 接著您可以使用成本要素維度成員的常用集合分析成本會計分類帳中，兩間法人實體的成本資料。

| 來源：美國會計科目表                                          | 來源：法國會計科目表                                          | 新成本元素維度成員常用集合                        |
|-----------------------------------------------------------------------|---------------------------------------------------------------------------|-------------------------------------------------------------------------|
| 從美國會計科目表匯入的成本要素維度成員 | 從法國會計科目表匯入的成本要素維度成員 | 測繪美國和法國成本元素維度成員到常用集合 |
| 5001：銷售                                                           | 5001：銷售和廣告                                               | 5000：銷售和廣告                                             |
| 5030：廣告                                                     | 6390：Stock 採購\*                                                    | 7000：清潔開銷                                                 |
| 7001：清潔開銷                                               | 7001：出差開銷                                                      | 7001：出差開銷                                                   |

\*不測繪 Stock 採購法國成本要素維度成員。

## <a name="currency-conversion"></a>貨幣轉換
您使用的各類會計科目表可能設定使用不同貨幣。 此時，請務必指明貨幣換算，成本資料才能以正確貨幣處理，如使用成本要素維度成員的成本會計分類帳定義。 前例中，如果成本會計分類帳使用美元 (USD)，您必須建立從美元到歐元 (EUR) 的貨幣換算，以便處理測繪成本要素維度成員的交易。

## <a name="update-mappings-at-any-time"></a>隨時更新測繪
您可以隨時更新成本要素維度的測繪定義。 由於測繪不以有效日期為執行依據，因此更改內容會套用在您下次處理成本交易或執行的成本計算。





[!INCLUDE[footer-include](../../includes/footer-banner.md)]