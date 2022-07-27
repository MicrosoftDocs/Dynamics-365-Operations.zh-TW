---
title: 主規劃和多站點功能概觀
description: 總體規劃會將位置設定和倉庫庫存維度納入考量。
author: ChristianRytt
ms.date: 07/25/2019
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: InventLocation, InventSite
audience: Application User
ms.reviewer: kamaybac
ms.custom:
- "2434"
- intro-internal
ms.assetid: 7f05c031-a446-4168-8cce-03a6305f5c4d
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e594cfd71201c6a629c04d5557c117649e6b19b0
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/15/2022
ms.locfileid: "8449637"
---
# <a name="master-planning-and-multisite-functionality-overview"></a>主規劃和多站點功能概觀

[!include [banner](../includes/banner.md)]

總體規劃會將位置設定和倉庫庫存維度納入考量。 

位置維度是強制性的，而您可以將倉庫維度設定為強制性的。

如果是強制性的維度，則必須在所有庫存交易記錄中輸入維度值。 因此，在總體規劃期間，初始需求的位置和倉庫就會是已知的。 位置維度也會一致，因此較低等級的需求擴展時，位置的值不會發生變化。

當倉庫沒有設定為強制性時，可能無法得知初始需求。 計劃引擎必須根據項目、個別倉庫和訂單行的詳細資訊定義的設定，來決定要使用的倉庫。

下列主題說明不同的定義設定時，計劃引擎決定要使用倉庫的工作方式。

[場地及倉庫涵蓋範圍總體規劃、倉庫強制](master-plan-site-warehouse-coverage-warehouse-mandatory.md)

[場地涵蓋範圍總體規劃、強制倉庫](master-plan-site-coverage-warehouse-mandatory.md)

[場地及倉庫涵蓋範圍總體規劃、倉庫非強制](master-plan-site-warehouse-coverage-warehouse-not-mandatory.md)

[場地涵蓋範圍總體規劃、倉庫非強制](master-plan-site-coverage-warehouse-not-mandatory.md)

[確定 BOM 版本](master-plan-bom-version-determined.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]