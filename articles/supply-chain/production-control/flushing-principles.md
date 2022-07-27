---
title: 耗用原則
description: 本主題描述用於原物料耗用的四種耗用原則。
author: johanhoffmann
ms.date: 04/04/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: JmgShopSupervisorReleaseOrders
audience: Application User
ms.reviewer: kamaybac
ms.custom: 221264
ms.assetid: dde49743-1541-4353-a030-63ca3069cd7d
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 7f644f26098bf7ac7d13292d6fbabb09a488d61e29fcd5fbd3cf0d261f0529bc
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447192"
---
# <a name="flushing-principles"></a>耗用原則

[!include [banner](../includes/banner.md)]

耗用原則反映了生產過程中使用的原物料的不同耗用策略。 耗用是從現有庫存中扣除材料，並將耗用材料的值設為生產訂單和批次訂單的 **在製品** (WIP) 的過程。 原物料的耗用，通常會從耗用材料的流程設定的位置進行。 此位置稱為生產輸入位置。

在材料耗用之前，該材料會被移動到輸入位置。 以下為流程說明。

[![scenario4a.](./media/scenario4a.png)](./media/scenario4a.png)

1. 材料倉庫
2. 原物料挑選
3. 生產輸入位置
4. 原物料消耗
5. 生產程序

材料耗用由以下四個耗用原則控制：

- 手動
- 開始
- 完成
- 可在地點使用

耗用原則會在預設值階層中進行設定。 階層會從發佈的產品開始，其中耗用原則的值為 **Start**。 在物料清單 (BOM) 或配方明細上，可以覆寫產品的耗用原則。 生產 BOM 明細或批次訂單配方明細上的預設耗用原則，是取自產品或 BOM 或配方上的覆寫值。

## <a name="description-of-the-flushing-principles"></a>耗用原則描述

### <a name="manual"></a>手動
手動耗用原則表示材料耗用的登錄是由手動操作。 例如，如果您想追蹤時間，並且必須考慮耗用批號或序號的數量以進行追蹤，則此原則是相關的。 手工耗用的登錄會在生產揀料單日記帳中進行。 對於為進階倉庫流程啟用的項目，可以套用手持流程。

### <a name="start"></a>開始
啟動耗用原則代表生產訂單啟動時會自動耗用材料。 耗用的材料量與開始的數量成正比。 啟動耗用原則與製造執行系統搭配使用時，也可用於操作或處理作業啟動時的材料耗用。 例如，如果耗用差異小、該材料是低價值材料、沒有追蹤需求或作業執行時間短，則此原則是相關的。 

### <a name="finish"></a>完成
完成耗用原則表示當生產訂單報告為完成時，或者設定為耗用材料的作業登錄為完成時，該材料將自動進行耗用。 耗用的材料量與報告為完成的數量成正比。 完成耗用原則與製造執行系統搭配使用時，也可用於操作或處理作業已完成時的材料耗用。 此原則在與啟動原則相同的情況下是相關的。 但是，完成原則適用於執行時間較長的作業，在作業完成之前不應將材料設定為 WIP。 

### <a name="available-at-location"></a>可在地點使用
可在地點使用耗用原則表示材料在登錄為生產揀貨時將自動被耗用。 當原物料揀選作業完成時，或者當生產輸入地點的材料可使用，且材料明細發佈到倉庫時，該材料會被登錄為從位置進行揀選。 在此過程中產生的揀料單會在批次作業中進行過帳。 例如，如果您針對一個生產訂單有許多揀貨活動，則此原則是相關的。 在此情況下，您不必手動更新揀料單，並且可以取得 WIP 餘額的目前檢視表。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]