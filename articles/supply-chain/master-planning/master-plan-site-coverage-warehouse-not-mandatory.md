---
title: 場地涵蓋範圍總體規劃、倉庫非強制
description: 本主題說明如何規劃將場地維度設定為涵蓋範圍的品項。
author: ChristianRytt
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResStorageDimensionGroup, ReqItemTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2474
ms.assetid: 316da918-67ae-43c5-baea-00ae559e29b0
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 484b178f3ac43f727fd6acb5deb40b7907c931ec
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449235"
---
# <a name="master-planning-for-site-coverage-warehouse-not-mandatory"></a>場地涵蓋範圍總體規劃、倉庫非強制

[!include [banner](../includes/banner.md)]

本主題說明如何規劃將場地維度設定為涵蓋範圍的品項。

此總體規劃情境涉及以下條件：

-   場地維度設定為強制，並且必須在需求交易輸入。
-   倉庫維度並未設定為強制。 倉庫可能是已知的，但不用於總體規劃計算。
-   場地維度設定用於涵蓋範圍規劃。
-   倉庫維度並未設定用於涵蓋範圍規劃。 因此，供應和需求是按場地所彙總，也許還有其他涵蓋範圍計劃的維度。

下圖說明總體規劃是如何進行的。 圖中引用的參數及其位置如下：
-   為品項定義品項涵蓋範圍。 按一下 **產品資訊管理 &gt; 產品 &gt; 已發佈的產品**。 選擇品項，然後按一下 **計劃 &gt; 品項涵蓋範圍**。
-   為倉庫定義了補貨關係。 按一下 **庫存管理 &gt; 設定 &gt; 庫存明細 &gt; 倉庫**。 在 **總體規劃** 索引標籤，請參閱 **主倉庫** 欄位群組。
-   預設訂單類型設定為生產、訂購單或看板。 按一下 **產品資訊管理 &gt; 產品 &gt; 已發佈的產品**。 選擇品項，然後按一下 **計劃 &gt; 預設順序設定**。 在 **預設訂單設定** 表單，請參閱 **預設訂單類型** 欄位。

![要求場地涵蓋範圍倉庫非強制。](./media/multisitedemandexplosionscenarioforsitecoveragewarehousenotmandatory.jpg)



## <a name="additional-resources"></a>其他資源

[主規劃和多站點功能概觀](master-plan-multisite-functionality.md)

[場地及倉庫涵蓋範圍總體規劃、倉庫強制](master-plan-site-coverage-warehouse-mandatory.md)

[場地涵蓋範圍總體規劃、強制倉庫](master-plan-site-warehouse-coverage-warehouse-not-mandatory.md)

[場地涵蓋範圍總體規劃、倉庫非強制](master-plan-site-warehouse-coverage-warehouse-mandatory.md)

[確定 BOM 版本](master-plan-bom-version-determined.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]