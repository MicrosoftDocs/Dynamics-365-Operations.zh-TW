---
title: 從交易帳戶和總帳戶建立預算
description: 本文概述了根據總帳戶建立預算的過程。 如果需要預算控制，還說明如何為總帳戶啟用預算控制。
author: panolte
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BudgetControlConfiguration, BudgetPlanGenerate
audience: Application User
ms.reviewer: roschlom
ms.custom: 13051
ms.assetid: fb1bb2d3-445c-402f-a9a3-aa6503eed78e
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 09c9fc38360dcf82ceb317edc7195d826f56d86f
ms.sourcegitcommit: e40a9fac5bac9f57a6dcfe73a1f21856eab9b6a9
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/02/2021
ms.locfileid: "8451005"
---
# <a name="create-a-budget-from-transaction-accounts-and-total-accounts"></a>從交易帳戶和總帳戶建立預算

[!include [banner](../includes/banner.md)]

本文概述了根據總帳戶建立預算的過程。 如果需要預算控制，還說明如何為總帳戶啟用預算控制。

預算計劃和預算登記分錄文件都允許對具有 **總計** 主科目類型的主科目編制預算。 實際資料只能過帳到交易主科目。 

對於 **從總帳產生預算計劃** 定期流程，可在 **來源** 索引標籤指定 **總計** 主科目類型作為條件。 在這種情況下，每個總計主科目都將包含在目標預算計劃中，金額將等於所選主科目範圍的總金額。 

您可以啟用 **總計** 類型主科目的預算控制。 透過使用預算群組支援此功能。 對於每個總計主科目，必須在**預算控制設定**頁面上建立應為預算群組控制的預算。 您指定的條件必須包括總計主科目和科目範圍。 為了加快建立預算群組的流程，您可以利用預算控制群組資料實體。 

在報表中 (例如財務報表) 使用預算時，總計科目的預算總額包括以下金額：

-   在總計科目間隔內的每個交易分類帳科目建立的預算。
-   直接在總計科目中輸入的預算金額。

因此，您可以為總計科目間隔中最重要的交易科目建立單獨的預算，然後將可用預算金額新增到總計科目中。





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
