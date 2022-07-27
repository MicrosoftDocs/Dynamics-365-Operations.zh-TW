---
title: 匯入需求預測的歷史資料
description: 要獲得準確的需求預測，您需要每個項目或項目分配金鑰的歷史需求資料。 本主題介紹如何使用資料實體從任何系統匯入歷史需求資料，以便您擁有更長的需求預測資料記錄。
author: ChristianRytt
ms.date: 05/10/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqDemPlanCreateForecastDialog
audience: Application User
ms.reviewer: kamaybac
ms.assetid: 59c0d269-9db0-48e7-b8c7-9a388781a9ca
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6dba31279541c20949dd1e86236103045c48b701
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449238"
---
# <a name="import-historical-data-for-demand-forecasts"></a>匯入需求預測的歷史資料

[!include [banner](../includes/banner.md)]

為了幫助保證需求預測的正確性，您必須取得每個項目或項目分配金鑰盡可能多的歷史需求資料。 如果尚未匯入歷史需求資料，請使用 Dynamics 365 Supply Chain Management 之中的 **歷史外部需求** (ReqDemPlanHistoricalExternalDemandEntity) 資料實體匯入。

在 **資料管理** 工作區，您可以看到實體中所有欄位的概覽。

1. 打開 **資料管理** 工作區。
2. 選擇 **資料實體** 磚。
3. 在實體清單中搜尋 **歷史外部需求**。
4. 選擇 **目標欄位**。 以下實體欄位是必填的：站點 (**DeliveringSiteId**)、日期 (**DemandDate**)、數量 (**DemandQuantity**) 以及品項編號 (**ItemNumber**) 或項目分配金鑰 (**ProductAllocationKeyId**)。

要使用資料實體，您必須擁有包含歷史需求資料的 Microsoft Excel 檔案或逗號分隔值 (CSV) 檔案。 以下範例顯示如何從 CSV 檔案匯入資料。

有關如何匯入資料的更多資訊，包括如何在匯入後清理資料，請參閱[資料匯入和匯出工作概述](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md)及其相關主題。

也請參閱[產生統計基線預測](generate-statistical-baseline-forecast.md)。

[!INCLUDE[footer-include](../../includes/footer-banner.md)]