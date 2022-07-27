---
title: 公司間貨幣換算
description: 本主題將說明公司間交易的貨幣換算
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
ms.openlocfilehash: 540849003d532ef2f0905c18332d9cb82a04cf7c
ms.sourcegitcommit: fcfd85a508c0de52cfe11d1986892219e39ef406
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/23/2021
ms.locfileid: "8447768"
---
# <a name="intercompany-currency-conversions"></a>公司間貨幣換算

[!include [banner](../../includes/banner.md)]

當原始銷售訂單和公司間訂購單上的貨幣代碼不同時，如果啟用了同步處理作業，以下欄位將進行貨幣換算：

- **單價**
- **銷售費用** 或 **採購費用**
- **折扣**
- **多明細折扣**

這些欄位隨後會與公司間銷售訂單明細同步。

然而，由於公司間訂購單和公司間銷售訂單上的貨幣一律會同步，所以下列欄位會在不換算貨幣的情況下同步：

- **單價**
- **銷售費用** 或 **採購費用**
- **折扣**
- **折扣百分比**
- **多明細折扣**
- **多明細折扣百分比**

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
