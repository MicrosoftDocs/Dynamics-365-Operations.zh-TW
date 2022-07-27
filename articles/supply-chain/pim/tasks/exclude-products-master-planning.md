---
title: 建立產品生命週期狀態以從總規劃中排除產品
description: 此程序說明如何建立新的產品生命週期狀態，並將產品排除在主計劃和 BOM 層級計算之外。
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
ms.openlocfilehash: c7f72be341b81515b7c5540d66f61647df93af41
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8447975"
---
# <a name="create-a-product-lifecycle-state-to-exclude-products-from-master-planning"></a>建立產品生命週期狀態以從總規劃中排除產品

[!include [banner](../../includes/banner.md)]

此程序說明如何建立新的產品生命週期狀態，並將產品排除在主計劃和 BOM 層級計算之外。


## <a name="create-an-obsolete-state"></a>建立一個過時的狀態
1. 前往產品資訊管理 > 設定 > 產品生命週期狀態。
2. 按一下新增。
3. 在狀態欄位中，輸入一個值。
4. 選擇是否對計畫欄位有效的否。
5. 在 [描述] 欄位中輸入一個值。

## <a name="associate-the-obsolete-state-to-a-released-product"></a>將過時狀態與已發布產品建立關聯
1. 關閉頁面。
2. 請前往產品資訊管理 >產品 > 已發佈產品。
3. 使用快速篩選器尋找記錄。 例如，以「M00」這個值來搜尋名稱欄位。
4. 按一下編輯。
5. 在清單中，標記所選資料列。
6. 在 [產品生命週期狀態] 欄位中，輸入或選取一個值。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]