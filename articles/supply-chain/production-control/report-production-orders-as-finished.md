---
title: 將生產訂單報告為完成
description: 報告為完成是生產階段 在此階段將報告成品，並將其從生產訂單移至庫存。
author: johanhoffmann
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ProdJournalTransJob, ProdJournalTransProd, ProdJournalTransRoute, ProdParmReportFinished, ProdRouteOprOverview
audience: Application User
ms.reviewer: kamaybac
ms.custom: 27061
ms.assetid: 1c2dfc54-a293-49f2-9b96-5a912ac5762c
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d509f0f732c1255a87bf810ab9a3bba3f61e2061f9a761ee0797b3fec45e45a3
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446667"
---
# <a name="report-production-orders-as-finished"></a>將生產訂單報告為完成

[!include [banner](../includes/banner.md)]

報告為完成是生產階段 在此階段將報告成品，並將其從生產訂單移至庫存。

當生產訂單上的成品數量報告為完成時，此數量會在庫存中更新為現有數量。 原計劃訂單數量的部分數量可以報告為完成。 也可以在將數量報告為完成時報告具有相關錯誤原因的錯誤數量。 當生產訂單到達「報告為完成」階段時，代表生產訂單上不再報告其他數量。
以下特性也與 **報告為完成** 程序相關聯：
-   可以設定與報告數量成比例的原材料耗用量和時間 (反排清)
-   可為已為倉庫程序啟用的物料產生儲存工作。
-   成品的計劃或標準成本值可設定為報告到分類帳科目。
-   可以根據品質關聯的設定為報告的數量建立品質檢驗訂單。

報告數量到輸出位置。 然後產生倉庫工作以將數量從輸出位置移動到由儲存工作的位置指令定義的最終目的地。

-   如果已設定品質關聯，則生產訂單報告為完成時，可以建立品質檢驗訂單。

## <a name="set-a-production-order-to-reporting-as-finished"></a>將生產訂單設定為「報告為完成」
您可以透過標準生產訂單更新功能、途程日記帳和作業卡日記帳，或日記帳 **報告為完成**，將生產訂單設定為 **報告為完成**。 您還可以在報告生產訂單的最後一個作業時，透過作業卡片終端和作業卡裝置頁面將階段更新為 **報告為完成**。 最後，您可以啟用 **報告為完成** 選項作為手持式倉庫裝置解決方案的流程。  





[!INCLUDE[footer-include](../../includes/footer-banner.md)]