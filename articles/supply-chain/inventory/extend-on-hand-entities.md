---
title: 擴充庫存現有資料實體
description: 本主題將透過範例，說明如何在 INVENTORSITEONHANDENTITY 和 INVENTWAREHOUSEONHANDENTITY 檢視中新增擴充欄位，以便庫存現有資料實體能與擴充項目搭配運作。
author: yufeihuang
ms.date: 07/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2020-07-27
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 8161d951c3296b63476c4e7b527efca163a4f4b3
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449034"
---
# <a name="extend-inventory-on-hand-data-entities"></a>擴充庫存現有資料實體

[!include [banner](../includes/banner.md)]

Microsoft Dynamics 365 Supply Chain Management 的[擴充性](../../fin-ops-core/dev-itpro/extensibility/extensibility-home-page.md)功能可讓您[透過擴充新增資料表欄位](../../fin-ops-core/dev-itpro/extensibility/add-field-extension.md)。 本主題將透過範例，說明如何在 `INVENTORSITEONHANDENTITY` 和 `INVENTWAREHOUSEONHANDENTITY` 檢視中新增擴充欄位，以便庫存現有資料實體能與擴充項目搭配運作。 如需有關資料實體的詳細資訊，請參閱[資料管理概述](../../fin-ops-core/dev-itpro/data-entities/data-entities-data-packages.md)。

> [!NOTE]
> 以下是一些庫存現有資料實體的清單：
>
> - 現有庫存 (按地點)
> - 現有庫存 (按地點) V2
> - 現有庫存 (按倉庫)
> - 現有庫存 (按倉庫) v2

將欄位新增至 `inventSiteOnHandView` 檢視使用的資料表時，您必須同步處理引擎，系統才能正確識別擴充項目。

1. 新增「擴充項目」欄位，擴充 `InventSiteOnHandView` 檢視。
1. 以「擴充項目」欄位擴充 `InventSiteOnHandAggregatedView` 檢視。
1. 修改 `getExtensionFields()` 方法來擴充「`InventSiteOnHandAggregatedViewBuilder`」viewBuilder 類別。 這個方式可讓您在執行 viewBuilder 同步處理程序時，將舊檢視欄位對應至新檢視欄位。

例如，您已透過擴充將以下四個欄位新增至 `InventTable` 資料表：

- 自訂欄位 1
- 自訂欄位 2
- 自訂欄位 3
- 自訂欄位 4

在這種情況下，您必須按照以下方式修改 `getExtensionFields()` 方法。

```xpp
[ExtensionOf(classStr(InventSiteOnHandAggregatedViewBuilder))]
public final class InventOnHandAggregatedViewBuilder\_Extension
{
    protected Map getExtensionFields()
    {
        next getExtensionFields();
        Map extensionFields = new Map(Types::Int64, Types::Int64);
        extensionFields.insert(fieldNum(InventSiteOnHandView, Custom field 1), fieldNum(InventSiteOnHandAggregatedView, Custom field 1));
        extensionFields.insert(fieldNum(InventSiteOnHandView, Custom field 2), fieldNum(InventSiteOnHandAggregatedView, Custom field 2));
        extensionFields.insert(fieldNum(InventSiteOnHandView, Custom field 3), fieldNum(InventSiteOnHandAggregatedView, Custom field 3));
        extensionFields.insert(fieldNum(InventSiteOnHandView, Custom field 4), fieldNum(InventSiteOnHandAggregatedView, Custom field 4));
        return extensionFields;
    }
}
```

完成這些步驟後，您可以加入新欄位來擴充「現有倉庫 (按地點)」和「現有庫存 (按倉庫)」資料實體。 這個方式可確保在使用這些資料實體的資料移轉期間識別並納入擴充欄位。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]