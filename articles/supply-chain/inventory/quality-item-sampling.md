---
title: 品質管理品項取樣
description: 本主題說明如何設定品項取樣。
author: yufeihuang
ms.date: 03/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventItemSampling
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ea749c470ab1d80f1f3974596a2cd4a1f5b7b32d
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449118"
---
# <a name="quality-management-item-sampling"></a>品質管理品項取樣

[!include [banner](../includes/banner.md)]

品項取樣是品質關聯的一部分。 其定義目前必須檢查的實物庫存量。 取樣可以根據固定數量、百分比或完整牌照。

## <a name="set-up-item-sampling"></a>設定品項取樣

若要設定品項取樣，請按照以下步驟操作：

1. 前往 **庫存管理 \> 設定 \> 品質控制 \> 品項取樣**。
1. 選取 **新增**。
1. 在 **品項取樣** 欄位中，輸入一個值。
1. 在 **說明** 欄位中輸入一個值。
1. 在 **值** 欄位中，輸入一個值。 此值與在相鄰欄位中選擇的數量規格值相關。
1. 在 **流程** 區段，如果測試失敗，而應封鎖整個批次或訂單明細數量，請選擇 **完全封鎖** 核取方塊。 如果清除此核取方塊，則如果測試失敗，將只會封鎖品質檢驗訂單中的品項。
1. 選擇 **儲存**。
1. 關閉頁面。

> [!NOTE]
> *倉庫流程的品質管理* 功能提供額外的品項取樣功能。 其加入了 *品項取樣範圍* 的概念，並允許您將完整牌照定義為數量規格。 如果您已開啟此功能，請參閱[倉庫流程的品質管理](quality-management-for-warehouses-processes.md)。

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
