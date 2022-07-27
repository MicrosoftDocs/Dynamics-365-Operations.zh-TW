---
title: 解除安裝雙重寫入應用程式協調流程解決流程
description: 本主題介紹如何解除安裝雙重寫入應用協調流程解決方案。
author: RamaKrishnamoorthy
ms.date: 03/16/2022
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2022-01-21
ms.openlocfilehash: 781b2cb19a563d5712fa65718c93bfdc242f0c4a
ms.sourcegitcommit: abfaef124c8747827d6f297821f01f1f6fbca6b7
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/17/2022
ms.locfileid: "8460598"
---
# <a name="uninstall-dual-write-application-orchestration-solutions"></a>解除安裝雙重寫入應用程式協調流程解決流程

[!include [banner](../../includes/banner.md)]

本主題介紹如何解除安裝雙重寫入應用協調流程解決方案。

有些客戶無意中安裝了在其 Microsoft Dataverse 環境中安裝多個解決方案的雙重寫入應用程式協調流程套件。 在軟體套件中安裝無關解決方案可能會導致意外和不良問題。

若要修復與安裝雙重寫入應用協調流程套件相關的問題，請按以下順序解除安裝不需要的雙重寫入解決方案：

1. Dynamics365FinanceAndOperationsAnchor_managed
1. msdyn_OneFSSCM_managed (如果存在)
1. Dynamics365FinanceAndOperationsDualWriteEntityMaps_managed
1. Dynamics365Notes_managed (若要解除安裝此解決方案，您必須向 Microsoft 開具支援票證。)
1. DualWriteCore_managed
1. Dynamics365AssetManagementApp_managed
1. Dynamics365AssetManagement_managed
1. Dynamics365SupplyChainExtended_managed
1. Dynamics365FinanceExtended_managed
1. HCMCommon_managed
1. Dynamics365FinanceAndOperationsCommon_managed
1. Dynamics365Company_managed
1. CurrencyExchangeRates_managed
1. msdyn_AssetCommon_managed
1. FieldServiceCommon_managed

如果安裝了合作對象和全球通訊錄解決方案，請按以下順序解除安裝解決方案：

1. Dynamics365FinanceAndOperationsAnchor
1. Dynamics365FinanceAndOperationsDualWriteEntityMaps
1. msdyn_DualWriteCore
1. Dynamics365AssetManagementApp
1. Dynamics365AssetManagement
1. Dynamics365SupplyChainExtended
1. Dynamics365FinanceExtended
1. HCMCommon
1. Dynamics365FinanceAndOperationsCommon
1. 當事人
1. Dynamics365Company_managed
1. CurrencyExchangeRates
1. msdyn_AssetCommon
1. FieldServiceCommon
