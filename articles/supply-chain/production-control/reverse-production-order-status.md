---
title: 反轉生產訂單狀態
description: 本主題介紹如何反轉生產訂單狀態。
author: johanhoffmann
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ProdParmStatusDecrease, ProdSetupStatusDecrease
audience: Application User
ms.reviewer: kamaybac
ms.custom: 70131
ms.assetid: b1e0df43-b388-4326-8fb7-501f30c89776
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0dd17bc48bfb6c78e1baca4faf78d6bc5b3ce426c5f0530174eccd95536a5859
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447123"
---
# <a name="reverse-the-production-order-status"></a>反轉生產訂單狀態

[!include [banner](../includes/banner.md)]

本主題介紹如何反轉生產訂單狀態。 

如果您反轉生產訂單的狀態，則與途程關聯的訂單和所有作業將恢復到生產生命週期中的上一個步驟。 例如，生產訂單的狀態為 **已排程**，然後您將狀態變更回 **已建立**。 在這種情況下，系統必須先將狀態變更為 **已估計**，這是 **已排程** 的上一個狀態。 然後它才能將狀態變更為您想要的 **已建立** 狀態。 **附註：** 如果您的訂單已達到 **報告為完成** 狀態，您仍然可以將其回復為較早的狀態。 但是，您必須重新執行估計和作業排程、工作排程或兩種類型的排程，以更新訂單資訊。 此步驟是必需的，因為還必須重設剩餘項目消用和作業資源耗用的任何保留。 本文接下來將說明當您透過以下方式反轉生產訂單狀態時會發生什麼：

-   從 **已估計** 到 **已建立**
-   從 **已排程** 到 **已估計**
-   從 **已發放** 到 **已排程**
-   從 **已開始** 到 **已發放**

## <a name="from-estimated-to-created"></a>從已估計到已建立
當您將生產訂單的狀態從 **已估計** 反轉到 **已建立** 時，將刪除為物料清單 (BOM) 中的品項計算的品項耗用。 生產線上的庫存交易刪除，且生產訂單 BOM 細項上的 **保持狀態** 欄位重設為 **已結束**。 當選擇 **衍生採購** 和 **衍生生產** 選項後，將刪除任何基礎訂購單或生產訂單。 如果您估計了生產訂單的成本，或者如果您手動保留品項以便它們可以在生產中使用，則會刪除這些交易。

## <a name="from-scheduled-to-estimated"></a>從已排程到已估計
當您將生產訂單的狀態從 **已排程** 反轉到 **已估計** 時，將刪除計劃的開始和結束日期和時間。 將刪除在排程期間進行的產能預留，將刪除在工作排程期間建立的作業。 **生產訂單詳細資料** 頁面上記錄的有關作業排程和工作排程的所有資訊將重設。

## <a name="from-released-to-scheduled"></a>從已發放到已排程
當您將生產訂單的狀態從 **已發放** 反轉到 **已排程** 時，只有狀態欄位中的值會發生變化。

## <a name="from-started-to-released"></a>從已開始到已發放
當您將生產訂單的狀態從 **已開始** 反轉到 **已發放**，所有報告為已完成的項目都將撤銷。 如果物料已揀貨，或者已將入庫和出庫交付到生產，則這些設定將撤銷。 生產訂單 BOM 細項上的 **保持狀態** 欄位從 **已結束** 變更為 **物料耗用**。 如果已登記時間，或已將生產途程中作業的數量報告為已完成，則這些設定將撤銷。 生產途程中的 **保持狀態** 欄位從 **已結束** 變更為 **路程耗用**。 所有過帳為在製品或在製品的品項的設定都會撤銷。 在 **生產訂單詳細資料** 頁面中，顯示已開始數量或報告為已完成數量的欄位將重設。 這些交易的日期也會重設。





[!INCLUDE[footer-include](../../includes/footer-banner.md)]