---
title: 其他州廠商產品的 ICMS-DIF 基本納稅計算變動
description: 本主題說明巴西南里奧格蘭德州 (RS) 或聖保羅 (SP) 州收到財務文件時，對 ICMS-DIF 課稅類型計算的配置。
author: Kai-Cloud
ms.date: 1/20/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2022-1-17
ms.dyn365.ops.version: 10.0.26
ms.openlocfilehash: 16f78b85567e6d08c588e621119513ff070bf618
ms.sourcegitcommit: 68655c5673aef9892063e5913ffee6bfc3817387
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/21/2022
ms.locfileid: "8451491"
---
# <a name="basis-change-in-icms-dif-tax-calculations-for-products-from-suppliers-in-other-states"></a>其他州廠商產品的 ICMS-DIF 基本納稅計算變動

本主題說明巴西南里奧格蘭德州 (RS) 或聖保羅 (SP) 州收到財務文件時，對 **ICMS-DIF** 課稅類型計算的配置。

根據州法律定義，收齊的 Imposto sobre Circulação de Mercadorias e Serviços (ICMS) 必須遵照規則如下：

*ICMS 收款*= ([(*操作金額*–*來源 ICMS*) ÷ (1–*內部 ICMS %*)] ×*內部 ICMS %*) –*來源 ICMS 金額*

## <a name="example"></a>範例

位於 RS 州的一間巴西公司收到 SP 州廠商的採購財務文件。 公司必須收集 RS 州 (18%) 與 SP 州 (12%) 之間的 ICMS 佔比差異。 不過，基數必須根據前規則計算。

- **操作金額：** 1,000.00 巴西里耳 (R$1,000.00)
- **ICMS 州際公路：** 120.00 里耳
- **RS 州的 ICMS 佔比：** 18%
- **RS 州收集的 ICMS：**(\[(1,000–120) ÷ (1–0.18)\] × 0.18) – 120 = 73.17 里耳 

## <a name="resolution"></a>解決方案

若要根據 RS 州規則計算 ICMS 差異 (ICMS-DIF)，您必須以下列方式設定銷售稅代碼和銷售稅群組：

1. 建立銷售稅代碼，以便收取 12% ICMS (其他州)。 此代碼用來登記廠商的應收稅賦金額。
2. 建立銷售稅代碼收集 ICMS-DIF。 此銷售稅代碼應有 18% 的佔比金額 (您所在州境)，以便定義 18% 和 12% 之間的差異。 設定稅賦類型為 **ICMS-DIF**。 此銷售稅代碼必須在計算參數中以下列方式定義：

    - 在 **產地** 欄位，選取 **總額佔比**。
    - 在 **保證金基數** 欄位，選取 **每行淨額** 或 **發票淨餘額**。
    - 定義稅賦代碼才能有 **3** 的財務值。 如此一來，調整交易將在 **財務帳冊** 模組啟用時自動建立。
    - 在銷售稅群組配置中，選取 **ICMS-DIF** 銷售稅代碼的 **使用稅** 選項。
