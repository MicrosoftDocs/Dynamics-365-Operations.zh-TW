---
title: 跨公司批次和序號
description: 本主題說明跨公司訂單註冊批次號碼與序號時會有何影響
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
ms.openlocfilehash: 4da936263bb57c24eeb7021ac61b3945bb2777fb
ms.sourcegitcommit: fcfd85a508c0de52cfe11d1986892219e39ef406
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/23/2021
ms.locfileid: "8447774"
---
# <a name="intercompany-batch-and-serial-numbers"></a>跨公司批次和序號

[!include [banner](../../includes/banner.md)]

公司使用序號或批次號碼來追蹤項目，必須同時追蹤揀選項目的序號與批次號碼。 跨公司功能可自動在兩家公司間推送/拉進序號與批次號碼。 公司間銷售訂單的項目註冊批次號碼與序號時，您可設定此程式，將這些號碼自動推送至相對應公司的訂購單與原始的銷售訂單。 相關參數可於銷售訂單的 **公司間** 頁面設定：

- 若於 **銷售訂單政策** 頁面選擇 **批次號碼** 欄位，當您張貼該公司間銷售訂單的裝箱單時，此批次號碼會同步至公司間訂購單明細的庫存交易。
- 若選擇 **序號** 欄位，當您張貼該公司間銷售訂單的裝箱單時，此序號會同步至公司間訂購單明細的庫存交易。

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
