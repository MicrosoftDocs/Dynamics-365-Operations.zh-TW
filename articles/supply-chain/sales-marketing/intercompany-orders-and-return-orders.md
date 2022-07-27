---
title: 公司間訂單和退貨單
description: 本主題將說明公司間訂單和退貨單
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
ms.openlocfilehash: 103225595e82bdedec6d97e5ebe5b61498377065
ms.sourcegitcommit: fcfd85a508c0de52cfe11d1986892219e39ef406
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/23/2021
ms.locfileid: "8447765"
---
# <a name="intercompany-orders-and-return-orders"></a>公司間訂單和退貨單

[!include [banner](../../includes/banner.md)]

本主題將介紹如何建立及更新公司間訂購單、銷售訂單、退貨單、購買合約與銷售合約。

## <a name="about-intercompany-orders"></a>關於公司間訂單

建立公司間銷售訂單時，Microsoft Dynamics 365 Supply Chain Management 會自動建立相應的訂購單。 同樣地，建立公司間訂購單代表系統會自動建立相應的公司間銷售訂單。

這適用於雙方訂單 (兩個相關公司之間的交易) 和大多數三方公司間訂單 (當公司間交易來自外部客戶的銷售訂單時)。

## <a name="intercompany-order-example"></a>公司間訂單範例

您有兩家相關的公司。 A 公司是銷售子公司，B 公司是經銷單位。 系統在以下情況中會自動建立公司間銷售訂單和訂購單：

- 當 A 公司建立訂購單且供應商為 B 公司時，B 公司會自動建立公司間銷售訂單。雙方訂單鏈由 A 公司的訂購單和 B 公司的公司間銷售訂單組成。
- 當 B 公司建立銷售訂單且客戶為 A 公司時，A 公司會自動建立公司間訂購單。雙方訂單鏈由 B 公司的銷售訂單和 A 公司的公司間訂購單組成。
- 當 A 公司首次為外部客戶建立銷售訂單時，系統會在 A 公司內自動建立訂購單；這反過來又促使系統在 B 公司中自動建立公司間銷售訂單。三方訂單鏈由 A 公司中的銷售訂單和訂購單，以及 B 公司中的公司間銷售訂單組成。

## <a name="about-intercompany-return-orders"></a>關於公司間退貨單

您可以像一般退貨一樣退回公司間交易品項。 然而，外部客戶針對公司間品項提出的退貨單會建立公司間訂購單。 這反過來會導致自動建立公司間銷售退貨單。 您也可以在沒有外部客戶退貨單的情況下退回公司間品項。

與一般退貨單類似，請在 **建立退貨單** 頁面建立公司間退貨單。

Microsoft Dynamics 365 Supply Chain Management 會自動更新公司間銷售和購買合約，以反映退回的品項。 該品項的銷售或購買合約承諾用量會自動調整，以反映退回品項時的數量或金額變化。

## <a name="intercompany-return-order-example"></a>公司間退貨單範例

A 公司建立一個連結至公司間品項購買合約的訂購單。 B 公司自動建立與相應銷售合約相關聯的公司間銷售訂單。 購買合約與銷售合約做為公司間協議相互關聯。

A 公司將公司間品項退回 B 公司，B 公司為該品項建立退貨單，然後 A 公司自動建立訂購退貨單。原始訂單相關購買合約與和銷售合約的承諾用量會自動調整，以反映數量或金額的變化。

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
