---
title: 消耗折舊
description: 本文概述了折舊的消耗方法。
author: moaamer
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: roschlom
ms.custom: 13751
ms.assetid: d25a681f-49a5-4bfc-aa76-1c6373e35dd8
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d9b97caefcb650f289e7f29f14473e0a22aa5d88
ms.sourcegitcommit: 1707cf45217db6801df260ff60f4648bd9a4bb68
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/23/2021
ms.locfileid: "8451053"
---
# <a name="consumption-depreciation"></a>消耗折舊

[!include [banner](../includes/banner.md)]

本文概述了折舊的消耗方法。

如果您為固定資產設定折舊範本，並在 **折舊設定檔** 頁面上的 **方法** 欄位選擇 **消耗**，則會根據使用情況將固定資產分配到折舊設定檔。 您不必在 **折舊設定檔** 頁面上設定百分比和間隔。 建立使用消耗方法的折舊設定檔後，您可以透過多種方式設定該方法。

## <a name="set-up-and-use-consumption-depreciation"></a>設定和使用消耗折舊
1.  在 **折舊設定檔** 頁面，建立折舊設定檔。 對於消耗計算，折舊設定檔必須具有識別碼和名稱，並且必須在 **方法** 欄位中選擇 **消耗**。
2.  在 **消耗係數** 頁面，設定消耗係數。 每個消耗係數必須具有識別碼和名稱，以及指定為數量或百分比的消耗係數。
3.  在 **消耗單位** 頁面，設定消耗單位。 每個消耗單元必須具有識別碼和名稱。 折舊單位用於計算 **消耗折舊** 頁面上的消耗折舊。 單位的範例是公里 (km)、公斤 (kg) 和小時。
4.  在 **固定資產** 頁面，設定各個固定資產。 對於每個固定資產，選擇具有折舊設定檔的值模型和折舊帳簿。 如果您的任何固定資產使用基於消耗方法的折舊設定檔，您必須為消耗折舊設定值模型或折舊帳簿。 此設定是在 **值模型** 頁面的 **折舊** 索引標籤或 **折舊設定檔** 頁面的 **一般** FastTab 上完成。 您可以對多個固定資產使用相同的值模型。 對於每個固定資產，選擇具有折舊設定檔的值模型和折舊帳簿。 您不能直接在 **固定資產** 頁面上新增或修改折舊設定檔。 您只能在 **折舊帳簿** 頁面上修改折舊範本。
5.  在 **值模型** 頁面或 **折舊帳簿** 頁面上，在 **消耗折舊** 欄位群組，在以下欄位中輸入資訊：
    -   消耗係數
    -   單位
    -   單位折舊
    -   估計消耗

    **已過帳的消耗** 欄位按單位顯示已為固定資產和值模型組合或固定資產折舊帳簿過帳的消耗折舊。 不能在此欄位中手動更新值。

## <a name="examples"></a>範例
### <a name="example-1"></a>範例 1

為 1 月 31 日設定了以下消耗係數：

-   數量為 1,000。
-   為固定資產指定的單位折舊價格為 1.5。

1 月 31 日的折舊提案如下：數量 × 單位折舊 1,000 × 1.5 = 1,500。如果為固定資產指定的係數是百分比係數，則在 **估計消耗** 欄位中為固定資產的值模型估計的數量會乘以為所選結束日期設定的百分比。 然後將產生的數量建議做為該期間的折舊數量。

### <a name="example-2"></a>範例 2

為 1 月 31 日設定了以下消耗折舊係數：

-   百分比為 10%。
-   為固定資產指定的單位折舊價格為 1.5。
-   固定資產的估計數量為 2,000。

1 月 31 日的折舊提案如下：預計數量 × 百分比 × 單位折舊 2,000 × .10 × 1.5 = 300





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
