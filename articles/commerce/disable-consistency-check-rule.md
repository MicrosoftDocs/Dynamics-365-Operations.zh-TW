---
title: 停用交易驗證程序中所使用的規則
description: 本文章描述在 Microsoft Dynamics 365 Commerce 中停用交易驗證規則的功能。
author: analpert
ms.date: 12/11/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: ''
ms.openlocfilehash: 7d566aa3b829dad281528925a341382f9637fdba
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/03/2022
ms.locfileid: "8884868"
---
# <a name="disable-rules-used-in-the-transaction-validation-process"></a>停用交易驗證程序中所使用的規則

[!include [banner](../includes/banner.md)]

零售商可能會有其獨特的商務案例和程序。 因此，在 Commerce 交易驗證程序中所包含的規則並非全部適用於所有零售商。 為了因應差異，Microsoft Dynamics 365 Commerce 提供可用於停用不適用規則的功能。

若要檢視適用於您環境中交易驗證程序的規則清單，並查看每個規則的狀態，請前往 **Retail 和 Commerce \> 總部設定 \> 參數 \> Commerce 參數**，然後選取 **交易驗證** 索引標籤。所有啟用的規則都會在 **驗證存放區交易** 過程中用於驗證交易，而且必須通過，才能將交易收集和過帳到交易對帳單上。

根據預設，每個規則的狀態會設定為 **啟用**。 因此，會使用所有規則驗證交易，然後才能將其提取到 Commerce 交易對帳單中。 若要停用規則，請將其狀態變更為 **停用**。 在 **驗證存放區交易** 過程中驗證交易時，不會考慮已停用的規則。

[!INCLUDE[footer-include](../includes/footer-banner.md)]
