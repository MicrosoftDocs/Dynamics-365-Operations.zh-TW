---
title: 同步公司間價格和折扣
description: 本主題說明如何同步公司間銷售訂單和訂購單的價格和折扣
author: GalynaFedorova
ms.date: 09/01/2021
ms.topic: article
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: a9467e8d06a44cfaab9e3c8ea3944675c3eb8fb5
ms.sourcegitcommit: fcfd85a508c0de52cfe11d1986892219e39ef406
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/23/2021
ms.locfileid: "8447717"
---
# <a name="synchronize-intercompany-prices-and-discounts"></a>同步公司間價格和折扣

[!include [banner](../../includes/banner.md)]

公司間銷售訂單和公司間訂購單的折扣和價格始終保持同步。 您還可以同步原始銷售訂單的價格和折扣，如此，所有訂單都具有相同的價格和折扣。 無論是從 **銷售和市場** 或是 **採購和委外**，您可以從 **所有客戶** 清單頁面上的 **一般** 索引標籤上，存取 **公司間** 頁面進行此動作。

**價格和折扣** 欄位，會同步至公司間銷售訂單行。 這意味著，透過選擇 **允許編輯價格** 欄位，和 **允許編輯折扣** 欄位，您可以變更公司間銷售訂單和公司間訂購單。 如果您變更公司間銷售訂單上的單價、價格單位或銷售費用，公司間採購訂單行也會隨之變更。

如果已經啟用公司間銷售訂單，或是公司間訂購單上的 **允許編輯價格** 和 **允許編輯折扣** 欄位，則您可以手動變更任一訂單的價格或折扣。 否則，你不能變更。

如果沒有啟用公司間銷售訂單上的 **允許編輯價格** 和 **允許編輯折扣** 欄位，您不能手動變更價格 (或費用)，或是公司間銷售訂單上的折扣。

如果沒有啟用公司間訂購單上的 **允許編輯價格** 和 **允許編輯折扣** 欄位，您不能手動變更價格 (或費用)，或是公司間訂購單上的折扣。

如果公司間訂購單和公司間銷售訂單上 **允許編輯價格** 和 **允許編輯折扣** 欄位，兩個欄位皆已啟用，則您可以對兩種訂單進行手動變更。 但是，這可能會導致一個人做的變更，被另一間公司的另一個人在同一訂單上所做的更新所推翻。

> [!NOTE]
> 如果您在公司間訂購單和公司間銷售訂單上，同時啟用 **價格和折扣** 欄位，則您無法控制價格。

為了避免這類型的衝突，最佳做法是允許公司間銷售訂單，或是公司間訂購單的價格和折扣變更，但不能同時允許兩者。 這可以透過啟用任一個訂單的 **允許編輯價格** 和 **允許編輯折扣** 欄位完成。

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
