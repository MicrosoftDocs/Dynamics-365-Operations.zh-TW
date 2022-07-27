---
title: 整合資產管理與固定資產
description: 本主題說明如何整合資產管理和固定資產模組，以便您將固定資產與維護資產連結。
author: johanhoffmann
ms.date: 04/17/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-04-17
ms.dyn365.ops.version: 10.0.11
ms.openlocfilehash: 40e4fdce50b335668a53d2efe53b7cf6c66f364f
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448026"
---
# <a name="integrate-asset-management-with-fixed-assets"></a>整合資產管理與固定資產

[!include [banner](../../includes/banner.md)]

透過整合 **資產管理** 和 **固定資產** 模組，您可以將固定資產與維護資產連結。 然後，固定資產使用者可以從新的或現有固定資產建立維護資產，且資產管理使用者可以將維護資產與現有固定資產關聯。 此功能也可讓固定資產使用者輕鬆檢視從工單中為相關維護資產過帳的成本。

> [!NOTE]
> 在本主題中，*維護資產* 是指 **資產管理** 模組中的資產，而 *固定資產* 是指 **固定資產** 模組中的資產。

## <a name="set-a-default-location-for-new-maintenance-assets-that-are-created-from-fixed-assets-optional"></a>為從固定資產建立的新維護資產設定預設位置 (選擇性)

此選擇性設定可讓您為從固定資產建立的新維護資產設定預設機能位置。 如果您有完全完成此設定，則通常只需完成一次即可。

若要完成該設定，請按照以下步驟操作。

1. 前往 **資產管理 \> 設定 \> 資產管理參數**。
1. 在 **固定資產** 索引標籤的 **機能位置** 欄位中，選擇預設位置。
1. 在動作窗格上，選擇 **儲存**。

## <a name="work-with-integrated-maintenance-assets-and-fixed-assets"></a>使用整合後的維護資產和固定資產

本節提供了一系列程序，為您展示可使用整合的資產管理和固定資產功能的各種方式。

### <a name="associate-an-existing-maintenance-asset-with-a-fixed-asset"></a>將現有維護資產與固定資產關聯

如要將現有維護資產與固定資產關聯，請執行以下步驟。

1. 前往 **資產管理 \> 資產 \> 所有資產** (或 **使用中資產**)。
1. 選擇一個資產。
1. 在 **固定資產** FastTab 上的 **固定資產編號** 欄位中，選擇現有固定資產。
1. 在動作窗格上，選擇 **儲存**。

### <a name="view-the-fixed-asset-that-is-associated-with-a-selected-maintenance-asset"></a>檢視與選定維護資產關聯的固定資產

如要檢視與選定維護資產關聯的固定資產，請執行以下步驟。

1. 前往 **資產管理 \> 資產 \> 所有資產** (或 **使用中資產**)。
1. 選擇一個資產。
1. 在 **固定資產** FastTab 上的 **固定資產編號** 欄位中，選擇該連結。

    所選資產的 **固定資產** 頁面將開啟。 (通常，此頁面會位於 **固定資產 \> 固定資產 \> 固定資產**。)

### <a name="view-the-maintenance-asset-that-is-associated-with-a-selected-fixed-asset"></a>檢視與選定固定資產關聯的維護資產

如要檢視與選定固定資產關聯的維護資產，請執行以下步驟。

1. 前往 **固定資產 \> 固定資產 \> 固定資產**。
1. 選擇一個資產。
1. 在動作窗格上的 **資產管理** 索引標籤上的 **檢視** 群組中，選擇 **維護資產**。

    與所選固定資產關聯之資產的 **維護資產** 頁面已開啟。 (此頁面通常可從 **資產管理 \> 資產 \> 所有資產** 找到。)

### <a name="view-maintenance-costs-that-are-associated-with-a-fixed-asset"></a>檢視與固定資產關聯的維護成本

資產管理工單可以為維護資產進行過帳，而且這些工單中的每一個通常都有成本。 當固定資產與維護資產關聯時，您可以直接從固定資產中檢視相關成本。

如要檢視與固定資產關聯的維護成本，請執行以下步驟。

1. 前往 **固定資產 \> 固定資產 \> 固定資產**。
1. 選擇一個資產。
1. 在動作窗格上的 **資產管理** 索引標籤上的 **檢視** 群組中，選擇 **維護成本**。

    **維護成本** 頁面會開啟並顯示相關成本。

### <a name="create-a-new-maintenance-asset-for-an-existing-fixed-asset"></a><a name="new-maintenance-from-fixed"></a>為現有固定資產建立新的維護資產

如要為現有固定資產建立新的維護資產，請執行以下步驟。

1. 前往 **固定資產 \> 固定資產 \> 固定資產**。
1. 選擇一個資產。
1. 在動作窗格上的 **資產管理** 索引標籤上的 **新增** 群組中，選擇 **建立維護資產**。 (如果此選項不可用，則維護資產可能已與選定的固定資產相關聯。)
1. 按照[建立資產](../objects/create-an-object.md)中的說明完成資產建立。

### <a name="create-a-new-fixed-asset-and-add-a-new-maintenance-asset-for-it"></a>建立新的固定資產並為其新增新的維護資產

如要建立新的固定資產並為其新增新的維護資產，請執行以下步驟。

1. 前往 **固定資產 \> 固定資產 \> 固定資產**。
1. 在動作窗格上，選擇 **新增**。
1. 按照[建立固定資產](../../../finance/fixed-assets/tasks/create-fixed-asset.md)中的說明完成固定資產建立。
1. 在動作窗格上的 **資產管理** 索引標籤上的 **新增** 群組中，選擇 **建立維護資產**。
1. 按照[建立資產](../objects/create-an-object.md)中的說明完成資產建立。

### <a name="remove-the-association-between-two-assets"></a>移除兩個資產之間的關聯

在某些情況下，您可能必須解除維護資產與其固定資產間的關聯。 例如，如果您想從固定資產[建立新的維護資產](#new-maintenance-from-fixed)，您必須先刪除任何現有關聯。

如要移除維護資產與固定資產現有的關聯，請執行以下步驟。

1. 前往 **資產管理 \> 資產 \> 所有資產** (或 **使用中資產**)。
1. 查找並開啟固定資產。
1. 在 **固定資產** 的 FastTab 上，清除 **機能位置** 欄位的值。
1. 在動作窗格上，選擇 **儲存**。


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]