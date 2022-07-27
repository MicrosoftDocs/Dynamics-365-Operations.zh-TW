---
title: 同步公司間費用
description: 本主題說明如何同步公司間費用
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
ms.openlocfilehash: c4854b698c8046fc603454c4d9d7059c938c70b3
ms.sourcegitcommit: fcfd85a508c0de52cfe11d1986892219e39ef406
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/23/2021
ms.locfileid: "8447750"
---
# <a name="synchronize-intercompany-charges"></a>同步公司間費用

[!include [banner](../../includes/banner.md)]

費用只會於公司間銷售訂單和公司間訂購單之間同步，並且始終保持同步。

如果已經選擇公司間訂購單，或是公司間銷售訂單上的 **允許編輯價格** 欄位，則您可以手動將費用新增至公司間銷售訂單或公司間訂購單。 否則，你不能新增。

如果沒有選擇公司間銷售訂單上的 **允許編輯價格** 欄位，則您無法手動將費用新增至公司間銷售訂單。

如果沒有選擇公司間訂購單上的 **允許編輯價格** 欄位，則您無法在公司間訂購單上，手動新增費用。

如果公司間訂購單和公司間銷售訂單，兩者的 **允許編輯價格** 欄位都已啟用，則您可以手動將費用新增至訂單。 但是，這可能會導致新增許多錯誤的費用。

為了避免這類型的衝突，最佳做法是允許費用新增至公司間銷售訂單，或是公司間訂購單，但不能同時允許兩者。

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
