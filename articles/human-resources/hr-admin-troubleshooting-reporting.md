---
title: 報表選項
description: 本主題說明如何客製化 Microsoft Dynamics 365 Human Resources 報表或建立新報表。
author: twheeloc
ms.date: 08/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 3c82f3d4f040f680cab68228f1aa8ab16f548961
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452517"
---
# <a name="reporting-options"></a>報表選項


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



**環境細節**

此問題適用所有環境。

**徵兆**

客戶希望客製化 Microsoft Dynamics 365 Human Resources 報表或建立新報表。

**問題**

使用者無法客製化嵌入式 Microsoft Power BI 報表。

**解決方案**

- 流向 Dataverse 的人力資源資料可以透過 Power Apps Dataverse 連接器向 Power BI Desktop 回報。 須注意 Dataverse 包含人力資源資料子集合。 更多有關 Power BI 和儀表板的資訊，請參閱[使用 Power Apps Common Data Service 建立 Power BI 報表和儀表板](https://powerapps.microsoft.com/blog/cdsconnectortopowerbi)。
- 電子報表 (ER) 可用於人力資源的某些報表。 客戶導向的客製化可透過 ER 組態選項完成。
- 資料可藉由人力資源部透過 Microsoft Office 整合提供的各種資料實體匯出到 Microsoft Excel 或 Microsoft Word。

**長期解決方案**

Power BI 額外選項將可使用，更多資料和實體將是 Dataverse 的一部份。


[!INCLUDE[footer-include](../includes/footer-banner.md)]
