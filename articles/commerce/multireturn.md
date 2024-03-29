---
title: 跨多筆客戶訂單和發票退回商品
description: 本文章描述在 Dynamics 365 Commerce 中跨多筆客戶訂單和發票啟用退貨的功能。
author: josaw1
ms.date: 08/27/2020
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-01-15
ms.dyn365.ops.version: 10
ms.openlocfilehash: 65ef700db5a81c49a962fd388af54e7811c088d2
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/03/2022
ms.locfileid: "8890313"
---
# <a name="return-items-across-multiple-customer-orders-and-invoices"></a>跨多筆客戶訂單和發票退回商品

[!include [banner](includes/banner.md)]


您可以跨多筆訂單和發票辦理退貨。 

## <a name="configure-commerce-to-support-returns-across-multiple-customer-order-and-invoices"></a>設定 Commerce 以支援跨多筆客戶訂單和發票辦理退貨

1. 移至 **Commerce 參數 \> 客戶訂單**。
1. 開啟 **啟用多筆客戶訂單的退貨** 參數。 

## <a name="process-returns"></a>處理退貨

開啟該參數並將變更同步到商店後，商店收銀員即可選取某位客戶的多筆銷售訂單進行退貨。

選取訂單後，隨即顯示這些訂單所有發票的全部可退貨產品清單。 接著，收銀員可以選取要退貨的產品。 系統會為所有選取的產品建立單一退貨單。
