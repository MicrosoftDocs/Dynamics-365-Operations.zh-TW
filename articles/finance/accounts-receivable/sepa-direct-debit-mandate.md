---
title: 設定 SEPA 直接借記授權
description: 在客戶授予債權人已簽署授權的前提下，單一歐元支付區 (SEPA) 直接借記允許債權人從客戶的銀行帳戶中收取資金。
author: ShivamPandey-msft
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustParameters
audience: Application User
ms.reviewer: roschlom
ms.custom: 59491
ms.assetid: 653a135f-c515-4ae3-9da2-82b5e1f103b5
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a4f63f88daf65676104384a2d612aa415ae6533044ea52ce85947f75ad876ced
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450621"
---
# <a name="set-up-sepa-direct-debit-mandate"></a>設定 SEPA 直接借記授權

[!include [banner](../includes/banner.md)]

在客戶授予債權人已簽署授權的前提下，單一歐元支付區 (SEPA) 直接借記允許債權人從客戶的銀行帳戶中收取資金。 客戶簽署授權允許債權人收取付款並指示客戶的銀行支付該款項。 本主題旨在顯示設定 SEPA 直接借記授權的流程。

## <a name="prerequisites"></a>先決條件
下表顯示開始前必須具備的先決行件。

| 類別       | 先決條件                                                                                                                                              |
|----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|
| 國家/地區 | 法律實體的主要地址必須位於以下國家/地區：奧地利、比利時、德國、西班牙、法國、義大利或荷蘭。 |

1. 設定直接借記授權的數字序列。每個直接借記授權必須具有一組唯一的編號。 使用 **數字序列** 頁面建立直接借記授權的數字序列。 在 **應收帳款參數** 頁面中，使用該識別碼將數字序列指派給直接借記授權系統。

2. 設定直接借記授權的應收帳款參數。使用 **應收帳款參數** 頁面可以設定直接借記授權的參數。 若要設定參數，則在 **直接借記** 索引標籤中，根據需要更改預設參數。 然後，在 **數字序列** 索引標籤中，使用先前設定的數字序列更新 **直接借記授權識別碼** 欄位。

3. 設定直接借記授權的付款方式。您必須設定直接借記授權的付款方式。 使用此付款方式查詢發票以產生直接借記付款。 使用 **付款方式** 頁面可設定付款方式。 若要設定直接借記授權的付款方式，您必須按照以下付款方式的附加步驟操作：

-   在 **付款類型** 欄位中，選擇 **電子支付**。
-   選擇性：如果您希望每位客戶都有多個授權，則在 **期間** 欄位中選擇 **發票**。 將會建立每張發票的單獨付款，而每筆付款都會使用發票指定的授權。
-   透過使用直接借記授權，選擇 **需要授權** 選項建立付款。 只當在 **付款類型** 欄位中選擇 **電子支付** 時，才可使用 **需要授權** 選項。

其他資源

[SEPA 直接借記概觀](sepa-direct-debit-overview.md) 

[建立客戶直接借記授權](tasks/create-direct-debit-mandate-customer.md) 



[!INCLUDE[footer-include](../../includes/footer-banner.md)]