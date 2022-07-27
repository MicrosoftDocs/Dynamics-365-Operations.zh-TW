---
title: Dataverse 中的組織階層
description: 本主題介紹財務和營運應用程式與 Dataverse 之間的組織資料整合。
author: RamaKrishnamoorthy
ms.date: 07/15/2019
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 9174612743c68595d12dd223f0932ace1857c0fb
ms.sourcegitcommit: 9cbff8a2cdeaf606488fb0044b3de4ab4409c9dc
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/26/2022
ms.locfileid: "8460520"
---
# <a name="organization-hierarchy-in-dataverse"></a>Dataverse 中的組織階層

[!include [banner](../../includes/banner.md)]



因為 Dynamics 365 Finance 是一個財務系統，*組織* 是一個核心概念，系統設定從組織階層的設定開始。 然後可以在組織級別以及組織階層中的任何級別追蹤業務財務。

雖然 Dataverse 沒有組織階層的概念，它確實有一些鬆散的概念，例如總銷售收入。 作為 Dataverse 整合的一部分，組織階層資料結構被新增到 Dataverse。

## <a name="data-flow"></a>資料流程

由財務和營運應用程式和 Dataverse 組成的業務生態系統將繼續具有組織階層。 此組織階層基於財務和營運應用程式構建，但出於提供資訊和可擴展性目的而在 Dataverse 中公開。 下圖顯示了在 Dataverse 中作為從財務和營運應用程式到 Dataverse 的單向資料流程公開的組織階層資訊。

![架構影像。](media/dual-write-data-flow.png)

組織階層表對應可用於將資料從財務和營運應用程式單向同步到 Dataverse。

## <a name="templates"></a>範本

組織是一起工作以執行業務流程或實現目標的一群人。 組織階層表示組成企業的組織之間的關係。 您可以定義以下類型的內部組織：法律實體、營運單位和團隊。 如下表所示，建立了一組表對應以同步法律實體、營運單位和相關的組織階層資訊。

財務和營運應用程式 | Customer Engagement 應用程式     | 描述
-----------------------|--------------------------------|---
[法律實體](mapping-reference.md#102) | cdm_companies | 
[法律實體](mapping-reference.md#142) | msdyn_internalorganizations |
[營運單位](mapping-reference.md#143) | msdyn_internalorganizations |
[組織階層 - 已發佈](mapping-reference.md#139) | msdyn_internalorganizationhierarchies | 此範本提供組織階層已發佈表的單向同步。
[組織階層目的](mapping-reference.md#140) | msdyn_internalorganizationhierarchypurposes | 此範本提供組織階層目的表的單向同步。
[組織階層類型](mapping-reference.md#141) | msdyn_internalorganizationhierarchytypes | 此範本提供組織階層類型表的單向同步。

## <a name="internal-organization"></a>內部組織

Dataverse 中的內部組織資訊來自兩個資料表、**營運單位** 和 **法律實體**。

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
