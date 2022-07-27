---
title: 追蹤各庫存維度的執行平均成本
description: 庫存維度組會附加至各庫存品項。 因此，品項的執行平均成本價格是根據財務追蹤的所選庫存維度計算。
author: AndersGirke
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventOnhandItem
audience: Application User
ms.reviewer: kamaybac
ms.custom: 75053
ms.assetid: 68cc00f4-0f7a-4a7d-be90-8f2e0d0563d3
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9ed1ced17eb25bdc10994b1e9e74c90a1d4ec95227bb1ddb072bae88e9255c0d
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447327"
---
# <a name="track-running-average-cost-per-inventory-dimension"></a>追蹤各庫存維度的執行平均成本

[!include [banner](../includes/banner.md)]

庫存維度組會附加至各庫存品項。 因此，品項的執行平均成本價格是根據財務追蹤的所選庫存維度計算。

庫存維度分為三種類型：產品、存貨和追蹤。 產品維度 (尺寸、顏色、款式或設定)。 產品維度永遠會在財務上進行追蹤。 存貨和追蹤維度包括站點、倉庫、位置、庫存狀態、車牌、批號和序號。 您可以決定對哪些存貨和追蹤維度進行財務追蹤。 

**範例 1** 

如果附加到物料的儲存尺寸會依照倉庫進行財務追蹤，則會依照倉庫計算執行平均成本價。 以下訂購單已開票：

-   已為倉庫 GW 開立了成本價為 USD 10.00、數量為 2 的訂購單。
-   已為倉庫 GW 開立了成本價為 USD 12.00、數量為 3 的訂購單。
-   已為倉庫 MW 開立了成本價為 USD 15.00、數量為 5 的訂購單。

倉庫 GW 的執行平均成本價格為 USD 11.20，倉庫 MW 的執行平均成本價格為 USD 15.00。 為倉庫 GW 過帳銷售訂單發票。 庫存價值和已售商品成本 (在執行庫存關閉且未標記前) 為 USD 11.20。 為倉庫 MW 過帳另一個銷售訂單。 庫存價值和已售商品成本 (在執行庫存關閉且未標記前) 為 USD 15.00。 

**範例 2** 如果附加到物料的儲存尺寸組依照倉庫進行財務追蹤，且追蹤維度組按批次編號進行財務追蹤，則計算每個批次的執行平均成本價。 

**注意：** 我們建議您隨時查看正在追蹤的所有財務維度的成本價。 以下訂購單已開票：

-   已為倉庫 GW 和批次 AAA 開立了成本價為 USD 10.00、數量為 2 的訂購單。
-   已為倉庫 GW 和批次 AAA 開立了成本價為 USD 12.00、數量為 3 的訂購單。
-   已為倉庫 GW 和批次 BBB 開立了成本價為 USD 15.00、數量為 2 的訂購單。

倉庫 GW 和批次 AAA 的執行平均成本價格為 USD 11.20，倉庫 GW 和批次 BBB 的執行平均成本價格為 USD 15.00。





[!INCLUDE[footer-include](../../includes/footer-banner.md)]