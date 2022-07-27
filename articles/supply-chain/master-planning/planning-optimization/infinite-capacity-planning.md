---
title: 以無限產能進行排程
description: 本主題提供有關規劃最佳化的無限產能排程資訊。 它也說明目前的功能限制。
author: ChristianRytt
ms.date: 09/21/2021
ms.topic: article
ms.search.form: RouteInventProd
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-06-09
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 6ea27f4e38697d517b1520176eb5dfeee651a598
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/15/2022
ms.locfileid: "8449625"
---
# <a name="scheduling-with-infinite-capacity"></a>以無限產能進行排程

[!include [banner](../../includes/banner.md)]

*規劃最佳化的無限產能排程* 功能導入了以途程資訊為基礎的排程作業。 它可讓您根據各種途程設定來安排作業。 規劃最佳化排程涵蓋了常用的途程設定，包括途程運作順序或對途程運作資源的要求。

## <a name="turn-on-the-infinite-capacity-scheduling-feature"></a>開啟無限產能的排程功能

使用此功能之前，您必須先在系統中開啟。 管理員可利用[功能管理](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)設定檢查功能狀態，並開啟該功能。 在 **功能管理** 工作區，該功能會依以下方式列出：

- **模組：** *主計劃*
- **功能名稱：** *規劃最佳化的無限產能排程*

如需此功能的更多資訊，請參閱[以產能為基礎的資源選擇排程](capability-based-scheduling.md)。

## <a name="added-functionality"></a>新增的功能性

*規劃最佳化的無限產能排程* 功能實現了以途程資訊為基礎的工作排程。 因此，途程設定可用於安排生產過程。 儘管此功能有一些內建主計劃所沒有的限制，但它支援製造案例所需的最常見功能。

該功能同時將 *簡單途程* 和 *途程網路* 納入考量。 透過使用途程作業的 **下一步** 欄位，您可以設定具有多個起點和多個平行執行作業的複雜途程。 系統在排程時會考慮這種類型的複雜途程結構。

此外，該功能支援途程中的 *平行作業*。 透過在途程作業的 **優先等級** 欄位中使用 *主要* 和 *次要* 選項，您可以定義一個途程結構，其中一個途程作業是主要作業，而另一個途程是次要作業。 在這種情況下，系統將在排程時考慮途程結構。

在排程過程中，系統也會考慮為作業所指定的 *資源需求*。 本系統使用資源需求來判斷執行作業需要哪些資源。 目前，*規劃最佳化的無限產能排程* 功能支援以下類型的資源需求：

- 資源類型
- 資源
- 資源群組
- 功能 (如需更多資訊，請參閱[以產能為基礎的資源選擇排程](capability-based-scheduling.md)。)

> [!NOTE]
>
> - 如果資源和/或資源群組設定為無限產能，則主計劃會將它們視為無限產能。
> - 目前尚不支援與人力資源相關的要求，例如技能或憑證要求。

該功能也支援 **設定時間** 和 **執行時間** 作業屬性。 當您在途程作業上設定這些屬性時，排程流程將會建立適當的設定和流程作業。

總之，規劃最佳化的排程支援最常用的方案。 您可以建立途程、新增主要和次要作業、定義下一步作業、新增資源需求，以及新增設定時間和執行時間。 然後系統將在排程期間考慮此資訊。

## <a name="limitations"></a>限制

在您使用計劃最佳化排程時，將適用以下限制：

- 該功能僅支援無限產能。
- 該功能不支援資源負載功能。
- 該功能不考慮途程報廢。
- 該功能支援 *持續時間* 僅作為主要資源選擇。

請注意，*規劃最佳化的無限產能排程* 功能正在日趨完善。 Microsoft 預計將在未來的版本中導入對其他排程設定的支援。
