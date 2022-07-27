---
title: 覆寫生產中材料的預設保留原則
description: 本主題介紹如何為每個項目模型群組設定預設保留原則，以便可以為作為生產物料清單 (BOM) 或批次訂單公式一部分的每個項目自動應用不同的保留原則。
author: johanhoffmann
ms.date: 12/10/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventModelGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-12-10
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: b12740e58b2bf8667bee8a2c51917d69771779f2
ms.sourcegitcommit: fcb8a3419e3597fe855cae9eb21333698518c2c7
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/09/2022
ms.locfileid: "8449985"
---
# <a name="override-the-default-reservation-principle-for-materials-in-production"></a>覆寫生產中材料的預設保留原則

[!include [banner](../includes/banner.md)]

這 *覆寫預設生產保留* 功能允許您為每個項目模型群組設定預設保留原則。 因此，可以為作為生產物料清單 (BOM) 或批次訂單公式一部分的每個項目自動應用不同的保留原則。 您可以選擇每個項目模型群組是否應該覆寫為訂單設定的預設保留原則，以及應該使用何種保留原則（*手動*,*估算*,*排程*,*發佈*，或是 *開始*）。

當您創建新的生產訂單或批次訂單時，系統會提示您選擇應該用於該訂單及其所有 BOM 行或公式行的保留原則。 使用 *覆寫預設生產保留* 功能時，部分或全部 BOM 或公式行可以覆寫該保留原則，轉而使用為相關項目模型群組設定的保留原則。

例如，如果您有需要揀選工作的原材料或成分，則為那些產品創建的 BOM或公式行需要進行實際保留，因為實際保留是產生倉庫工作的先決條件。 通常，如果您希望自動進行保留，您可以選擇以下其中一項保留原則：*估算*,*排程*,*發佈*，或是 *開始*。 另一方面，如果您有不需要揀選工作的材料或成分，由於它們是直接從某個地點消費的，您通常會選擇 *手動* 保留原則，不進行任何實際保留或產生任何揀選工作。

## <a name="turn-the-override-default-production-reservation-feature-on-or-off"></a>打開或關閉覆寫預設生產保留功能

從 Supply Chain Management 版本 10.0.25 開始，此功能預設開啟。 管理員可以通過搜索打開或關閉 *覆寫預設生產保留* 功能，其位在[功能管理](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)工作區。

## <a name="assign-a-production-reservation-policy-to-an-item-model-group"></a>將生產保留原則指派給項目模型群組

1. 移至 **成本管理\>庫存會計原則設定\>項目模型群組**.
1. 建立或選擇項目模型群組。
1. 在 **庫存原則** FastTab，選擇 **覆寫項目生產保留** 核取方塊。
1. 在 **保留** 欄位，選擇屬於所選模型群組項目的保留原則。 （那些項目包括 BOM 或公式行上的項目。）

    - **手動**–模型群組中的項目不會自動為生產進行實際保留。 但是，它們仍然可以根據需要手動保留。
    - **估算**–模型群組中的項目將在估算生產訂單期間進行實際保留。
    - **排程**–模型群組中的項目將在安排生產訂單期間進行實際保留。
    - **發佈**–模型群組中的項目在發佈生產訂單時將會進行實際保留。
    - **開始**–模型群組中的項目將在生產訂單開始時進行實際保留。

## <a name="example-using-reservation-principles-in-a-bulkpack-scenario"></a>示例：在散裝/包裝情況使用保留原則

在 1,000 升混合器中生產散裝潤滑劑材料。 在該散裝材料準備好後，會被泵送到數個灌裝站，在那裡灌裝不同大小的瓶子。 灌裝完成後，將瓶子裝入盒內。 接著將那些盒子裝至貨板上。

在此狀況下，將創建一個生產 1,000 升散裝材料的批次訂單。 （此訂單為大宗訂單。）此批訂單完成後，便會到灌裝站的進料位置報告完成。 然後建立用於填充和包裝每個瓶子大小的批次訂單。 （這些訂單是包裝訂單。）包裝訂單有一個由散裝材料、空瓶、標籤和其他包裝材料組成的公式。 由於散裝材料直接從混和槽流向灌裝站，因此無需倉庫工作即可挑選這種材料，散裝材料直接從輸入位置取用。 因此，保留原則設定為 *手動*。 其他材料會透過揀選工作送到灌裝站。 因此，舉例來說，這些行的保留原則設定為 *發佈*，這樣便能在發佈包裝訂單時自動進行保留。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]