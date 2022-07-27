---
title: 自動登記公司間客戶發票的付款
description: 本主題說明如何自動登記公司間客戶發票的付款
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
ms.openlocfilehash: ffc5c7bf44989fbcc18e940b5a7c9df81260d770
ms.sourcegitcommit: fcfd85a508c0de52cfe11d1986892219e39ef406
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/23/2021
ms.locfileid: "8447759"
---
# <a name="register-payments-automatically-for-intercompany-customer-invoices"></a>自動登記公司間客戶發票的付款

[!include [banner](../../includes/banner.md)]

當發佈公司間客戶發票時，Microsoft Dynamics 365 Supply Chain Management 會建立客戶交易。 該客戶交易會一直是開啟狀態直到結算，意味著客戶已經支付該交易。 當對應的公司間訂購單發票更新時，將建立與廠商交易配對的客戶交易。 該廠商交易也會一直是開啟狀態，直到結算。 為了降低存在差異的風險，可以於應付帳款日誌發佈時，自動建立並發佈應收帳款的付款日誌。

1. 前往 **銷售與營銷 \> 客戶 \> 所有客戶**。
1. 在動作窗格上，於 **一般** 索引標籤，選擇 **公司間**。
1. 若要在 **公司間** 頁面上，為銷售訂單設定公司間應收帳款，請選擇 **銷售訂單原則** 連結。
1. 在 **付款日誌** 欄位中，選擇您要登記公司間廠方付款，對應的應收帳款日誌。 您將在 **應收帳款參數** 頁面中完成此設定。
1. 如果您想要自動發佈此日誌，請選擇 **自動發佈日誌** 核取方塊。

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
