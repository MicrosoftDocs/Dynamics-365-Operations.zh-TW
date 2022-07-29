---
title: 資產租賃慣例
description: 本主題說明租賃資產的慣例。
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLease
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2021-1-28
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: afc432d448f3b013dd8732120d7e8a50a9169343c705a75465e669156fd5e052
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450414"
---
# <a name="asset-leasing-conventions"></a>資產租賃慣例

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

本主題說明租賃資產的慣例。 租賃慣例用於確定租賃帳簿的開始日期。 如果租賃慣例設為 **無**，則開始日期與租賃的開始日期相同 (即 **租賃開始日期** 欄位的值)。 如果租賃慣例設為 **整月**，則開始日期為租賃開始日期所屬月份的第一天。

開始日期決定了負債攤銷和資產折舊計劃期間的開始日期。 利息費用和折舊費用在相應計劃的期間結束日期過帳。 初始確認和調整日記帳分錄在開始日期過帳。

> [!NOTE]
> 租賃慣例功能必須透過「功能管理」開啟。 在 **功能管理** 工作區中，找到並選擇名為 **資產租賃的租賃慣例** 功能，然後選擇 **立即啟用**。

租賃慣例分配給租賃資產帳簿的設定。

要查看或分配租賃慣例，請執行以下步驟。

1. 前往 **資產租賃\>設定\>租賃帳簿**。
2. 在 **租賃慣例** 欄位，選擇以下值之一。

    | 租賃慣例 | 描述 |
    |--------------------|-------------|
    | 無               | 負債攤銷和資產折舊計劃從租賃的開始日期開始，因為開始日期等於租賃開始日期。 結束日期是一個月後。 此租賃慣例不保證利息將在每個月的最後一天過帳。 |
    | 整個月         | 對於開始日期在當月任何時間發生的租賃，負債攤銷和資產折舊計劃在該月的第一天開始計提費用。 此租賃慣例可確保在整個月的每個月的最後一天計算利息。 |

3. 選擇 **儲存**。

建立租賃後，會根據為租賃輸入的開始日期和為帳簿指定的租賃慣例自動輸入每個帳簿的開始日期。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
