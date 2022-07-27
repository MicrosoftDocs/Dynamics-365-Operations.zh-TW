---
title: 成本計算等級
description: 本主題介紹名為成本計算等級的物料清單 (BOM) 等級。 此 BOM 等級的計算不包括生產和批次訂單。
author: AndersGirke
ms.date: 04/23/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2020-04-23
ms.dyn365.ops.version: 10.0.12
ms.openlocfilehash: e08d11c8e9d98e56c5ef076cbab7bb68bedea62a
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449376"
---
# <a name="cost-calculation-level"></a>成本計算等級

[!include [banner](../includes/banner.md)]

名稱為 **成本計算等級** 的物料清單 (BOM) 等級在計算中排除生產訂單和批次訂單。 系統在成本計算版本中執行成本計算時使用此等級。 在重新計算和庫存結轉等過程中，系統則是使用 **成本核算等級** BOM 等級。

以下的簡單案例顯示 **成本計算等級** BOM 等級與 **成本核算等級** BOM 等級兩者之間的差異。

您有三種產品：A、B 和 C。產品 C 是產品 B 的元件，產品 B 是產品 A 的元件。

- **成本核算等級** 分配以下的 BOM 等級：

    - **產品 A：** 0
    - **產品 B：** 1
    - **產品 C：** 2

- **成本計算等級** 分配以下的 BOM 等級：

    - **產品 A：** 0
    - **產品 B：** 1
    - **產品 C：** 2

然後建立產品 C 的生產訂單，並將產品 A 加入生產訂單 BOM。 估計訂單後，BOM 等級按以下方式更新：

- **成本核算等級** 分配以下的 BOM 等級：

    - **產品 B：** 1
    - **產品 C：** 2
    - **產品 A：** 3

- **成本計算等級** 分配以下的 BOM 等級：

    - **產品 A：** 0
    - **產品 B：** 1
    - **產品 C：** 2

此行為可確保對生產訂單 BOM 的變更不會影響後續成本計算。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]