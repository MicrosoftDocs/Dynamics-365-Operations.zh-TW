---
title: 內部公司交易的 TDS 計算
description: 本主題說明了用於分階段計算內部公司交易的從源頭扣除稅款 (TDS) 的流程。
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: c978c84891a0c1ce5a079484eec24590283027c4
ms.sourcegitcommit: 6dc2b877cf8ea9185a07964ec05c5ddb7a78471b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/12/2022
ms.locfileid: "8451806"
---
# <a name="tds-calculation-on-intercompany-transactions"></a>內部公司交易的 TDS 計算

[!include [banner](../includes/banner.md)]

本主題說明了用於分階段計算內部公司交易的從源頭扣除稅款 (TDS) 的流程。

建立內部公司訂購單或銷售訂單時，將使用為客戶或廠商定義的預設 TDS 群組計算 TDS 金額。 過帳發票後，TDS 金額將過帳到可退稅帳戶或應付帳款。

將為原始訂購單或銷售訂單自動建立內部公司銷售訂單或訂購單。 預設 TDS 群組顯示在內部公司訂單上，以便可以計算 TDS。 您可以變更 TDS 群組。 僅當自動建立的內部公司訂單上的淨發票金額與原始訂單上的淨發票金額相符時，才可以過帳發票。 (淨額為扣除 TDS 後的發票金額。)

例如，為 50,000 建立了一張銷售發票，並向其附加 **10%** TDS 群組。 過帳的發票金額為 45,000，銷售發票的已過帳 TDS 金額為 5,000。 將為內部公司銷售訂單自動建立訂購單，並向其附加 **10%** TDS 群組。 如果將 TDS 群組變更為 **15%**，則無法過帳發票，因為自動建立的內部公司銷售訂單的淨發票金額與原始銷售訂單的淨發票金額不相符。

將為內部公司發票建立的付款日記帳會自動過帳。 僅當付款日記帳上的淨付款金額與原始付款日記帳上的淨付款金額相符時，才能過帳該付款日記帳。
