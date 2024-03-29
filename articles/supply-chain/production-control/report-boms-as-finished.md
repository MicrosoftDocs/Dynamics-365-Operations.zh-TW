---
title: 將 BOM 報告為完工入庫
description: 本文提供有關將 BOM 報告為完工入庫的資訊。
author: johanhoffmann
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BOMReportFinish, BOMReportFinishMax, BOMSetupReportFinish
audience: Application User
ms.reviewer: kamaybac
ms.custom: 53251
ms.assetid: 510d05a3-0073-438d-b0c4-b6a6df1882ea
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ff88622c2cbbdcff6130fb8c500ea12a1e454ecb5f33834bc0a69718038c9e89
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447174"
---
# <a name="report-boms-as-finished"></a>將 BOM 報告為完工入庫

[!include [banner](../includes/banner.md)]

本文提供有關將 BOM 報告為完工入庫的資訊。

**報告為完成** 和 **報告為完成的最大量** 頁面用於將物料清單 (BOM) 報告為完工入庫。 從概念上來說，將 BOM 報告為已完工入庫的流程和將生產訂單報告為已完工入庫的流程相同。 例如，此流程可用於不需要更進階生產訂單功能的簡單裝配和配套流程。 **報告為完成** 頁面允許您批量地將多個 BOM 報告為已完工入庫。 **報告為完成的最大量** 頁面允許您一次僅將一個 BOM 報告為已完工入庫。 可從庫存管理中的功能表項目存取 **報告為完成** 頁面，並且這兩個頁面在 **已發行的產品** 頁面中都有提供。

## <a name="report-as-finished-page"></a>「報告為完成」頁面
如果從已發行的產品中開啟 **報告為完成** 頁面，該頁會建議您將標準庫存預設數量報告為已完工入庫。 預設情況下會顯示使用中的 BOM 版本，但如果有其他已核准的版本，您可以更改 BOM 版本。 該頁面還允許您刪除記錄，並為應報告為已完工入庫的已發行的產品建立新記錄。 若要使用查詢來選擇產品，則按一下 **選擇** 功能表項目。 您可以透過按一下 **確定**，手動確認所選產品已完工入庫。 或者，您可以批量設定要執行的流程。 在確認完工入庫流程後，系統將產生 BOM 日記帳，其中已處理過帳到庫存。 此日記帳包含一個用於成品的明細項目，以及一個用於每個 BOM 明細的明細項目。 您可以控制日記帳是自動過帳還是保持開放狀態以進行其他調整。

## <a name="max-report-as-finished-page"></a>「報告為 完成的最大量」頁面
在 **報告為完成的最大量** 頁面中，每個 BOM 明細表示可以報告為完成的產品件數。 此計算基於每個材料明細的實際現有庫存量。 在以下範例中，一件品項編號 FG 消耗兩件原物料 RM10 和一件原物料 RM20。 因為 RM10 的現有量只有 10 件，可以報告為已完工入庫的最大 FG 數量是五件。 此值顯示在 **報告為完成的最大量** 欄位中。

| 等級 | 品項編號 | 數量 | 現有量 | 報告為 完成的最大量 |
|-------|-------------|----------|---------|-------------------------|
| 0     | FG          |  1       | 0       | 5                       |
| 1     | RM10        | -2       | 10      | 5                       |
| 1     | RM20        | -1       |  8      | 8                       |

## <a name="boms-that-have-multiple-levels"></a>具有多個層級的 BOM
當 BOM 具有多個層級時，您可以透過使用 **分解** 欄位，來控制如何在所有層級計算物料。 在 **報告為完成** 頁面和 **報告為完成的最大量** 頁面中可以使用此欄位。 可以使用以下選項：

-   **永不** – 如果有材料物料，則不會分解基礎 BOM。
-   **一律** – 全面分解所有基礎 BOM。 因此，不使用任何半成品組件品項的現有庫存量。
-   **短缺** – 如果所需物料數量並不全部可用，則只分解到基礎物料清單。

### <a name="example"></a>範例

在本範例中，三件成品 (品項編號 FG) 做好報告為已完工入庫的準備。 有一個兩層級的 BOM，顯示如下。

| 等級 | 品項編號 | BOM 明細數量 | 現有量 |
|-------|-------------|-------------------|---------|
| 0     | FG          |                   |         |
| 1     | COMP        | 1                 | 2       |
| 1     | RM          | 1                 |         |

下表顯示 **分解** 欄位的設定如何影響 BOM 日記帳明細的產生方式。 **分解：永不**

| 等級 | 品項編號 | 數量 |
|-------|-------------|----------|
| 0     | FG          | 3        |
| 1     | COMP        | -3       |

如前表所示，只有品項編號 COMP 被視為在日記帳中扣除。 作為 COMP 其中一部分的品項編號 RM 不會分解到日記帳明細，並且不考慮現有的兩個 COMP。 **分解：一律**

| 等級 | 品項編號 | 數量 |
|-------|-------------|----------|
| 0     | FG          | 3        |
| 1     | RM          | -3       |

在這種情況下，品項編號 COMP 分解到其原物料品項編號 RM 中。 兩件現有 COMP 不計入消耗的 RM 數量中。 **分解：短缺**

| 等級 | 品項編號 | 數量 |
|-------|-------------|----------|
| 0     | FG          | 3        |
| 1     | COMP        | -2       |
| 1     | RM          | -1       |

在這種情況下，則考慮兩件現有品項編號 COMP。 然而，因為需要三件品項編號 FG，所以還需要一件品項編號 RM 才能多製作一件 COMP。





[!INCLUDE[footer-include](../../includes/footer-banner.md)]