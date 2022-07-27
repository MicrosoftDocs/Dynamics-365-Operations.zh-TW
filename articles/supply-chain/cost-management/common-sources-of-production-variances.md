---
title: 生產差異的常見來源
description: 本文闡述每種生產差異的各種典型來源。
author: AndersGirke
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventCostTrans, ProdCalcVarianceTrans
audience: Application User
ms.reviewer: kamaybac
ms.custom: 79753
ms.assetid: 14ac7db4-fb40-43c1-bb0d-1d51fc91d24f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ce352db56fe41264562fd11260f9fa91931babeeb62d352327a588fb622492d0
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447165"
---
# <a name="common-sources-of-production-variances"></a>生產差異的常見來源

[!include [banner](../includes/banner.md)]

本文闡述每種生產差異的各種典型來源。 

以下是一些典型的 **批量** 差異來源：

-   生產訂單的合格數量不同於標準成本計算中使用的計算數量。 數量是攤銷固定成本的基礎。
-   生產訂單的固定成本值不同於標準成本計算中使用的固定成本。 生產訂單的固定成本可能因多種原因而不同。 例如，固定成本可能反映以下因素：
    -   手動更改生產物料清單 (BOM) 或途程
    -   建立生產訂單時選擇不同的 BOM 版本或途程版本
    -   指派給品項的 BOM 版本或途程版本上，存在計劃工程變更

以下是一些典型的 **生產價格** 差異來源：

-   途程規劃作業報告耗用的成本類別 (和成本類別價格) 不同於標準成本計算中使用的成本類別。
-   成本類別價格的現有成本不同於標準成本計算中使用的成本類別價格。

以下是一些典型的 **生產數量** 差異來源：

-   對於重要組成部分，出現過度出貨或出貨不足的狀況。
-   您多報或少報路線規劃作業的時間。
-   相對於訂單數量，您多收或少收上層品項的良好數量。 但是，您完全根據生產訂單的訂單數量發出組件和報告作業。

以下是一些典型的 **生產替代** 差異來源：

-   您發出不在生產 BOM 上的物料組件。
-   您手動將組件新增到生產 BOM 並將該組件報告為已耗用。
-   您將品項報告為已耗用，但不手動將其新增到生產 BOM。
-   您手動將作業新增到生產途程並將該作業報告為已耗用。
-   建立生產訂單時，您選取的 BOM 版本與標準成本計算中使用的 BOM 版本不同。
-   建立生產訂單時，您選擇的途程版本與標準成本計算中使用的途程版本不同。






[!INCLUDE[footer-include](../../includes/footer-banner.md)]