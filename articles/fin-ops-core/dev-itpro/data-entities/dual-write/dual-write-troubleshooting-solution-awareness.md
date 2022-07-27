---
title: 疑難排解與解決方案意識相關的問題
description: 本主題提供疑難排解信息，可幫助您解決與解決方案意識相關的問題。
author: RamaKrishnamoorthy
ms.date: 03/16/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: f83a064bfc8896bdf76bcd38f9187ed0e1ea56cf
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8460200"
---
# <a name="troubleshoot-issues-related-to-solution-awareness"></a>疑難排解與解決方案意識相關的問題

[!include [banner](../../includes/banner.md)]





本主題提供有關財務和營運應用程式與 Dataverse 之間的雙重寫入整合的疑難排解信息。 具體來說，它提供的信息可幫助您解決與解決方案意識相關的問題。

> [!IMPORTANT]
> 本主題解決的一些問題可能需要系統管理員角色或 Microsoft Azure Active Directory (Azure AD) 租使用者管理員認證。 每個問題的部分說明是否需要特定角色或認證。

## <a name="error-on-the-dual-write-page"></a>雙重寫入頁面上的錯誤

在 **雙重寫入** 頁面上，您可能會收到類似於以下範例的錯誤訊息：

*名稱為「msdyn」的實體\_在 MetadataCache 中找不到具有 namemapping='Logical' 的 dualwriteentitymap'。*

若要解決此問題，請確保雙重寫入核心解決方案安裝在 Dataverse。 雙重寫入核心方案是解決方案意識的前提。


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]