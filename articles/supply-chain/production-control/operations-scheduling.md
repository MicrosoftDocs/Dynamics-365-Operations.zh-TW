---
title: 操作排程
description: 本主題提供有關操作排程的資訊。 您可以使用作業排程提供生產過程隨時間變化的一般估計。
author: johanhoffmann
ms.date: 06/20/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ProdSchedule
audience: Application User
ms.reviewer: kamaybac
ms.custom: 198073
ms.assetid: 12c28b11-80aa-4668-b15b-724cb24890bd
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e3c380297b56f615a6b285ef7daf1ecbd7bb420f
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448734"
---
# <a name="operations-scheduling"></a>操作排程

[!include [banner](../includes/banner.md)]

本主題提供有關操作排程的資訊。 您可以使用作業排程提供生產過程隨時間變化的一般估計。

您可以在作業層級和工作層級排程生產。 與作業排程不同，操作排程不會將生產路線的操作展開為作業。 如果您想在排程中包含更多詳細資訊，例如有關當前產能的資訊，您可以在執行操作排程後執行作業排程。 您也僅能執行作業排程。 作業排程通常用於在工廠安排單個作業的即時或短期時間範圍。

## <a name="components-of-operations-scheduling"></a>操作排程的組成部分
操作排程的主要組成部分是排程導向、資源產能和材料優化。 透過使用操作排程，您可以實現以下目標：

-   透過從給定日期向前或向後安排來控制計劃方法。
-   透過根據資源的產能安排生產來優化資源的使用。 這種方法還有助於確定何時應使用替代資源。
-   透過根據所需材料的可用性安排生產來優化材料的使用。
-   安排和同步參考生產。 當生產訂單的排程更改時，參考生產的日期也會隨之調整。

您必須先估算生產訂單的成本，然後才能執行操作排程。 如果您尚未執行估算，它會在操作排程開始之前自動執行。 操作排程指定以下資訊：

-   計劃生產的產品
-   產品設定
-   參與生產的數量
-   生產開始和結束的日期
-   執行生產活動資源的產能預留

為生產操作設置設定時間、處理時間和執行時間。 執行操作排程後，生產訂單的狀態為 **已排程**，且所有操作都按照生產路線指定的順序進行安排。 但是，只考慮操作的持續時間。 沒有安排開始時間和結束時間。

## <a name="scheduling-direction-and-date"></a>排程導向及日期
排程導向對排程程序而言相當重要。 可從任一日期向前或向後排定生產，這取決於時間和排程需求。

-   **從排程日期往前推**–您可以儘早排定開始生產。 生產可以在今天、明天或將來的任何特定日期開始。 生產將及時往前安排到最早可行的結束日期。
-   **從排程日期往後推**–您可以儘可能晚一點排定開始生產。 後推排程基於必須完成生產的日期。 排程從該日期倒數計時至可以開始並仍按時完成生產的最晚可行日期。

## <a name="resource-scheduling"></a>資源排程
當您執行操作排程時，生產路線中的每項操作都為操作指定的資源進行安排。 此外，每個操作的持續時間都在生產路線上指定。 如果為操作指定了資源群組，則排程會為該群組預留產能。 但是，與作業排程不同，操作排程不會選擇群組中的特定資源。 若您使用有限產能，則排程取決於完成生產所需資源的可用性。 操作排程遵循生產路線上指定的操作順序。 該操作排程根據生產路線上所定的操作時間為資源群組預留產能。 參與資源的可用產能總和決定資源群組的產能。 資源已存在的產能預留被視為不可用產能。 若該生產無足夠的可用產能，則生產訂單可能會延遲甚至停止。 您還可以指定您期望從參與生產資源中獲得的效率。 您將效率指定為資源的百分比。 效率百分比調整資源的輸送量。 此調整會影響為資源預留的時間。 使用資源操作的前置重疊時間也會相應調整。

## <a name="operations-scheduling-and-master-planning"></a>操作排程和總規劃
操作排程還推動總規劃並確定材料需求的計算。 操作排程考慮以下資訊：

-   **待處理的生產**–計劃、發佈或啟動的產品
-   **材料可用性**–庫存、附屬生產、供應商和廠商
-   **產能可用性**–生產所需的資源

> [!NOTE]
> 如果您使用多執行緒總規劃和操作排程，將不考慮有限產能。 

## <a name="cancellations"></a>取消
當您執行操作排程時，您可以取消路由的特定部分。 這些部分包括佇列時間、設定時間、處理時間、重疊時間和運輸時間。

## <a name="finite-materials"></a>有限材料
如果您使用有限材料，排程還取決於生產所需材料的可用性。 如果沒有足夠的可用元件進行生產，生產可能會延遲。 透過指定必須可用於生產的材料，您能以材料的使用為基礎進行排程。 當您同時優化資源產能和材料可用性時，將根據這些限制計算產量。 在產能和材料同時可用且數量達到要求之前，無法安排開始生產訂單。

## <a name="additional-resources"></a>其他資源

[操作排程選項](operation-scheduling-options.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]