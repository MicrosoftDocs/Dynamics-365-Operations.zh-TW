---
title: 建立預設產品生命週期狀態
description: 此程序說明如何建立預設產品生命週期狀態，以及如何將預設狀態與已發布的產品建立關聯。
author: t-benebo
ms.date: 12/05/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a628ed2b609f48c22076f409889c212e4d9463ac
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449082"
---
# <a name="create-a-default-product-lifecycle-state"></a>建立預設產品生命週期狀態

[!include [banner](../../includes/banner.md)]

此程序說明如何建立預設產品生命週期狀態，以及如何將預設狀態與已發布的產品建立關聯。


## <a name="create-a-default-lifecycle-state"></a>建立預設生命週期狀態
1. 前往產品資訊管理 > 設定 > 產品生命週期狀態。
2. 按一下新增。
3. 在狀態欄位中，輸入一個值。
4. 發布到法律時提欄位時，選擇預設的是。
5. 在 [描述] 欄位中輸入一個值。
6. 選擇是否對計畫欄位有效的否。

> [!NOTE]
> 如果新發布的產品不應包含在主計畫中，請選擇否。 如果它應該包含在主計劃中，請將控制保持為其預設值，是。  

## <a name="create-a-new-released-product"></a>建立新的已發布產品
1. 關閉頁面。
2. 請前往產品資訊管理 >產品 > 已發佈產品。
3. 按一下新增。
4. 在產品編號欄位中，輸入一個值。
5. 在產品名稱欄位中，輸入一個值。
6. 在搜尋名稱欄位中，輸入一個值。
7. 在項目型號群組欄位中，輸入或選擇一個值。
8. 在項目群組欄位中，輸入或選擇一個值。
9. 在儲存維度群組欄位中，輸入或選擇一個值。
10. 在追蹤維度群組欄位中，輸入或選擇一個值。
11. 按一下確定。

> [!NOTE]
> 預設產品生命週期狀態是全局定義。  

## <a name="change-the-product-to-an-active-state"></a>將產品變更為有效狀態
1. 在 [產品生命週期狀態] 欄位中，輸入或選取一個值。

> [!NOTE]
> 假設您已設定活動狀態，您現在可以選擇活動狀態以允許產品用於主計畫和 BOM 等級的計算。 顯然，這只有在所有產品細節。都需要一致性的指定計畫時，才顯得有意義。  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]