---
title: 分類帳配置規則
description: 本文提供有關分類帳配置規則的資訊。 它說明這些配置規則的各種組成部分和用於它們的配置方法。
author: kweekley
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerAllocation, LedgerAllocationBasisRule, LedgerAllocationRequest, LedgerAllocationRule
audience: Application User
ms.reviewer: roschlom
ms.custom: 15402
ms.assetid: 8147e148-7c11-45ef-95c6-f9889a875b54
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 718640390cd1d4c6c2e9fb1d6bdeba21b515be4a
ms.sourcegitcommit: 4f8465729d7ae0bf5150a2785a6140c984c7030e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2021
ms.locfileid: "8451122"
---
# <a name="ledger-allocation-rules"></a>分類帳配置規則

[!include [banner](../includes/banner.md)]

本主題提供有關分類帳配置規則的資訊。 它說明這些配置規則的各種組成部分和用於它們的配置方法。

分類帳配置規則用來自動計算分類帳餘額或固定金額，並產生配置日記帳和科目分錄。 配置方法可以變動或固定。 下列配置方法可用於分類帳配置規則：

-   **基礎** – 這項變動方法用在配置取決於篩選標準的實際分類帳餘額時。 例如，可以根據各部門的銷售額與部門總銷售額的比例配置廣告開銷。
-   **固定佔比** 和 **固定權重** – 以這些方法而言，配置佔比或權重會由規則直接定義。 例如，可以配置廣告開銷，使 A 部門獲得 70% 的廣告開銷，而 B 部門獲得 30%。
-   **相等** – 此方法將金額平均配置給每個定義的目的地。 例如，如果為 A 部門和 B 部門定義目的地，可以配置廣告開銷，以便 A 部門和 B 部門都獲得 50% 的廣告開銷。

如果 Basis 要當成配置規則的配置方法，您也必須分開定義分類帳配置的基礎規則。 "處理配置申請" 流程讓使用者在過帳或刪除計算的配置額前，處理分類帳配置規則和預覽產生的配置日記帳分錄。

## <a name="components-of-ledger-allocation-rules"></a>分類帳配置規則的組成元素
每條配置規則有四個組成元素：總則、來源、目的地和沖銷。 如果 Basis 當成配置方法，會需要額外組成元件，分類帳配置基礎規則。 每個組成元素提供處理配置所需的關鍵資訊。

-   **通則** – 此組成元件是使用者指明如配置方法、公司間規則設定和規則是否有效的選項。
-   **來源** – 此組成元件是使用者指明配置來源資料的地方。 配置可依照分類帳餘額 (**資料來源** = **分類帳**) 或固定金額 (**資料來源** = **固定值**) 進行。 當 **資料來源** 設定為 **分類帳** 時，必須針對分類帳配置規則定義來源篩選標準 (例如針對廣告開銷定義)。
-   **目的地** – 此組成元件定義應該如何分佈和說明配置計算結果。 例如，各部門會有一個目的地明細。
-   **沖銷** – 此組成元件定義應如何針對平衡目的地分錄的沖銷分錄判定主科目和維度。 使用者定義的選項通常會改用在以來源為主的科目和維度。 當 **資料來源** 設定為 **固定值** 時，**來源** 不能當成選項。
-   **分類帳配置基礎規則** – 這些規則使用自己的來源篩選標準判定應該用於配置的分類帳餘額 (例如各部門營收)。 每條配置基礎規則可以搭配多條配置規則使用。






[!INCLUDE[footer-include](../../includes/footer-banner.md)]
