---
title: 生產過帳
description: 本文提供有關生產流程中不同過帳類型的資訊。
author: AndersGirke
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventItemGroup, ProjCategory, WrkCtrResourceGroup, WrkCtrTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 54591
ms.assetid: 0917fe64-f643-46ae-98ff-5013b266a067
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ee3eaf11f5d77861e7abd29bb428f67b57a3e0e3
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8447873"
---
# <a name="production-posting"></a>生產過帳

[!include [banner](../includes/banner.md)]

本文提供有關生產流程中不同過帳類型的資訊。

生產過帳活動會遵循下列篇章中說明的生產流程。

## <a name="material-consumption"></a>材料消耗
生產揀料單日記帳過帳時，材料會在生產期間登記為已消耗。 這項流程會產生扣除現有庫存的發貨交易記錄。 在生產參數中，您可以指定正在處理中 (在製品 \[WIP\]) 之原料的值是否應在分類帳中過帳。 接著，將在製品 (WIP) 的原料價值過帳到專用的揀料單帳戶和專用的揀料單沖銷帳戶。

## <a name="time-consumption"></a>時間消耗
工作人員在生產工作上花費的時間會記錄在途程卡日記帳或工作卡日記帳中。 過帳這些日記帳時，系統會處理過帳到處理中 (WIP) 資源之專用帳戶的分類帳。 此過帳表示用於生產訂單的時間價值。 生產訂單登記結束後，系統會結算 WIP 帳戶。

## <a name="reporting-finished-goods-and-error-quantities"></a>報告成品和錯誤數量
生產訂單報告為已完成時，已完成的成品數量會透過「報告為完成的日記帳」在庫存管理中更新。 如果您使用 WIP 會計 (可在生產參數中設定)，系統會產生分類帳日記帳以減少 WIP 帳戶並增加成品庫存。 日記帳使用為產品定義的標準成本。

## <a name="ending-the-production-order"></a>結束生產訂單
在生產訂單結束之前，系統會針對生產的數量計算實際成本。 材料、人力和間接費用的所有估計成本都會沖銷並替換為實際成本。 成品的總成本會從庫存收貨帳戶中借記，並貸記到庫存發貨帳戶中。 如果您在執行成本計算時選取 **結束工作** 核取方塊，生產訂單狀態會變更為 **已結束**。 此狀態可防止將任何附加成本過帳到已完成的生產訂單。 您可以指定在報告為已完成期間回報的錯誤數量，應分配至報告為已完成的良品數量。 或者，您可以指定錯誤數量值應過帳到專用的報廢帳戶。

## <a name="controlling-the-level-of-ledger-posting"></a>控制分類帳過帳的級別
在 **生產控制參數** 中，您可以使用 **分類帳過帳** 欄位設定生產流程的分類帳過帳級別。 以下是可供使用的值：

-   **項目和資源** – 使用為原料和成品的項目群組設定的分類帳帳戶。 WIP 的時間消耗取自途程作業中的資源或資源群組。
-   **項目和類別** – 使用為原料和成品之項目群組設定的分類帳帳戶。 WIP 的時間消耗取自途程中作業資源或資源群組。
-   **生產群組** – 使用在材料和時間消耗皆適用的產品群組上設定的分類帳帳戶。 生產群組會與已發佈的產品建立關聯，並在建立這些訂單時復製到生產訂單。 然後，生產訂單上的過帳將遵循與生產訂單相關聯的生產群組。

**注意：** 如果使用計算成品成本的標準方法，最終交易會反映這一事實。 如果實際成本與使用標準方法計算的成本不同，系統會將差額過帳到顯示收益或損失的帳戶。





[!INCLUDE[footer-include](../../includes/footer-banner.md)]