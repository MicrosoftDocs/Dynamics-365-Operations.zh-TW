---
title: 設定指數利率
description: 本主題說明如何設定指數利率。 如果您的組織將租賃付款金額與一組指數利率相關聯，則需要使用指數利率。
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeaseIndexRateType
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 9d1c9fd1ebabce628bbd7d0b0b03daaec11b2cd9d54157ba0ccbf0a7c89bdd07
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450459"
---
# <a name="set-up-index-rates"></a>設定指數利率

[!include [banner](../includes/banner.md)]

如果租賃付款取決於指數，則可以在系統中加入並維護指數利率類型。 為了從 **指數利率類型** 頁面重估租賃付款，指數利率重估流程使用自重估之日起的最新指數利率。

若要加入指數利率類型和指數利率，請執行下列步驟。

1. 前往 **資產租賃\>設定\>指數利率類型**。
2. 選擇 **新建**。
3. 在相應的欄位中，輸入指數利率的利率類型和名稱。
4. 若要加入新的指數利率值，則選擇指數利率類型，然後選擇 **新增**。
5. 選擇利率的生效日期，然後選擇利率值。

您必須選擇 **指數利率值差** 或 **指數利率值** 作為指數利率方法。

- 根據開始日期的指數利率與最近指數利率之間的差異，選擇用於計算新租賃付款的 **指數利率值差** 方法。 指數利率在 **指數利率 (%)** 欄位中定義。
- 透過選擇 **指數利率 (%)** 欄位中指定的百分比，選擇用於計算租賃付款的 **指數利率值** 方法。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
