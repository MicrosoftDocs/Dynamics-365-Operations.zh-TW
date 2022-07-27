---
title: 在匯入作業中同步日期和時間
description: 在匯入作業中使用 UTC 時區以避免時區轉換出現問題。
author: peakerbl
ms.date: 12/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: sericks
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2020-12-01
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c76eadc5839785ba1624ee3894ef1d0872369aa9
ms.sourcegitcommit: 7aa7d756e1e98a53da62e03c608a9597ef9893ea
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/20/2021
ms.locfileid: "8460554"
---
# <a name="synchronize-date-and-time-in-import-jobs"></a>在匯入作業中同步日期和時間

[!include [banner](../includes/banner.md)]

將匯入作業的時區設定為國際標準時間 (UTC) 很重要。 如果您使用不同的設定，您可能會在匯入的資料中看到意外的日期和時間。 如果沒有正確設定，匯入過程會將 UTC 日期轉換為本地格式，然後系統設定會再次對其進行轉換。

這種雙重轉換會導致日期在應用程式之間發生變化。 例如，由於本地時區的差異，雙重轉換可能會導致 Dynamics 365 Human Resources 和 Dynamics 365 Finance 之間的員工開始日期不同。 將匯入作業設定為 UTC 可解決此問題。

1. 在 Dynamics 365 Finance 和 Operations，選取 **資料管理**。

2. 選取 **匯入專案**，然後選取專案。

3. 在 **來源日期格式** 下方，選取 **CSV-Unicode**。

   [![將來源日期格式更改為 UTC。](./media/data-source-date-format.png)](./media/data-source-date-format.png)

4. 將 **時區** 更改至 **國際標準時間時區**，並將 **語言** 更改至 **En-US**。




[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
