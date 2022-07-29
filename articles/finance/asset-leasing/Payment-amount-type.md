---
title: 新增付款金額類型
description: 本主題說明如何在「資產租賃」中設定付款金額類型。
author: moaamer
ms.date: 01/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeaseIndexRevaluation
audience: Application User
ms.reviewer: twheeloc
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 037afa458277a3a07bcb937c6ec4d961d0dd5ca9
ms.sourcegitcommit: 7adf9ad53b4e6d1c4d5d612ce0977b76c61ec173
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/13/2022
ms.locfileid: "8451347"
---
# <a name="add-payment-amount-types"></a>新增付款金額類型

[!include [banner](../includes/banner.md)]

本主題說明如何在「資產租賃」中設定付款金額類型。 您可以藉此逐項列出租賃付款金額，而不是新增總金額到付款期程明細。

若要新增付款金額類型，請按照下列步驟操作。

1. 前往 **資產租賃\>設定\>付款金額類型**。
2. 選取 **新增**。
3. 輸入新付款類型和說明。

> [!NOTE]
> IFRS 16 索引重估方面，您必須建立一種付款金額類型並標示為 **適用 IRFS 16 的索引重估**。 此付款金額類型將用在按照 IFRS 16 帳冊執行索引重估的流程，將一併考慮因索引重估流程發生的變化。
>
> 當租賃中的 **付款明細** 選項設定為 **是**，如果執行 IFRS 16 的索引重估，但沒有對應 IFRS 16 的付款類型，則流程將無法完成。

只有一筆記錄可標示為 **適用 IFRS 16 的索引重估**。

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
