---
title: 產品訂單生命週期概觀
description: 建立生產訂單時，會啟動開始生產項目請求。 生產訂單包含將生產什麼、生產數量和計劃完成日期的資訊。 還包含有關使用哪些物料，以及生產該項目要遵循的流程資訊。
author: johanhoffmann
ms.date: 07/25/2019
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: ProdTable, ProdTableCreate
audience: Application User
ms.reviewer: kamaybac
ms.custom:
- "19741"
- intro-internal
ms.assetid: bbb6e69d-479c-45fc-a0a8-66da5df16c7f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c4c3632d644070f064ec70d3dd7c0d480927eafe
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/15/2022
ms.locfileid: "8449670"
---
# <a name="production-order-lifecycle-overview"></a>產品訂單生命週期概觀

[!include [banner](../includes/banner.md)]

建立生產訂單時，會啟動開始生產項目請求。 生產訂單包含將生產什麼、生產數量和計劃完成日期的資訊。 還包含有關使用哪些物料，以及生產該項目要遵循的流程資訊。

生產訂單會經過生產生命週期的各個階段。 建立訂單時，其狀態分配為 **已建立**。 訂單完成時，其狀態分配為 **已結束**。 每個階段的參數設定，可允許使用者設定每個步驟。 可以為單一使用者，或所有使用者設定該設定。

生產物料清單和生產路徑，是生產訂單的主要實體。 會根據要生產的所選項目和數量，複製到生產訂單中。 生產訂單開始之前，可以編輯生產物料清單和路徑。

可以在以下情況下建立生產訂單：

-   由主計畫執行根據物料需求建立。
-   直接從銷售訂單行建立，或更高等級的生產訂單建立和預估時建立 (分頁供應)。
-   手動建立。






[!INCLUDE[footer-include](../../includes/footer-banner.md)]