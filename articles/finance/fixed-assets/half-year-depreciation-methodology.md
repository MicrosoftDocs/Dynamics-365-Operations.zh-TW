---
title: 半年折舊慣例方法論
description: 本主題說明固定資產使用半年慣例計算折舊的方法，此方法計算資產使用的第一年和最後一年的六個月折舊值。
author: moaamer
ms.date: 08/17/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2019-08-17
ms.dyn365.ops.version: 10.0.12
ms.openlocfilehash: 5e71beb316494d05a3d8ce6066f2a4c72e32a2ad3d75a4ba3560cb0aebfe4cc8
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450498"
---
# <a name="half-year-depreciation-convention-methodology"></a>半年折舊慣例方法論

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

本主題說明固定資產中使用半年慣例計算折舊的方法。 半年慣例計算資產使用第一年和最後一年的六個月折舊。 有關折舊慣例的詳細資訊，請參閱[折舊方法和慣例](Fixed-asset-depreciation-conventions.md)。 

當您使用六個月折舊慣例時，系統會使用購置年份或資產投入使用的年份，然後從該年份計算五年折舊，然後加上六個月。 為了說明這段過程，請考慮以 50,000 價格購得，並於 2020 年 4 月投入使用的資產。 也請假設資產的使用壽命為五年。

服務第一年將於 2020 年 12 月總結，意味著資產的五年使用壽命將於 2024 年 12 月結束。 半年折舊慣例將使資產的使用壽命增加六個月，意味著其使用壽命將於 2025 年 6 月結束。 

> 年折舊 50,000/5 = 10,000 月折舊 10,000/12 = 833.33 <br>
> 第一年折舊 10,000/2 = 5,000，日後月折舊 5,000/9 = 555.56

   [![半年折舊慣例的折舊時間表。](./media/half-yr-dprectn-cnvntn.png)](./media/half-yr-dprectn-cnvntn.png)

增加半年慣例的延長折舊期提供更精確的折舊分配。 六個月慣例更公平代表折舊支出，這對於損益表的編列很管用。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]