---
title: 將產品生命週期狀態指派給已發佈的基準產品
description: 此程序顯示如何將產品生命週期狀態指派給已發佈的基準產品和其變體。
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
ms.openlocfilehash: 217bab38544c2794d2e57410f8c2a979605106b0
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8447972"
---
# <a name="assign-a-product-lifecycle-state-to-a-released-product-master"></a>將產品生命週期狀態指派給已發佈的基準產品

[!include [banner](../../includes/banner.md)]

此程序顯示如何將產品生命週期狀態指派給已發佈的基準產品和其變體。 先決條件：您需要先播放工作指南“建立新的產品生命週期狀態”，確保在您能播放該工作指南前，您至少有一個已建立的產品生命週期狀態。


## <a name="find-a-released-product-master"></a>尋找已發佈的基準產品
1. 請前往產品資訊管理 >產品 > 已發佈產品。
2. 在清單中，尋找並選擇所需紀錄。

> [!NOTE]
> 基準產品具有產品子類型基準產品。  

## <a name="update-the-lifecycle-state"></a>更新生命週期狀態
1. 按一下「編輯」。
2. 在 [產品生命週期狀態] 欄位中，輸入或選取一個值。
3. 按一下「儲存」。
4. 按一下「是」。

> [!NOTE]
> 如果選擇“是”，則與已發佈的基準產品具有相同原始狀態的所有相關已發佈的產品變型也將更新為新的產品生命週期狀態。 如果選擇否，則所有變體都保持其實際狀態。 與已發佈的基準產品具有不同產品生命週期狀態的變體不會更新。  

## <a name="verify-the-lifecycle-state-of-the-variants"></a>驗證變體的生命週期狀態
1. 按一下已發佈的產品變型。

> [!NOTE]
> 請注意，所有變體都從已發佈的基準產品繼承了選定的生命週期狀態。  

2. 在清單中，標記所選資料列。
3. 在 [產品生命週期狀態] 欄位中，輸入或選取一個值。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]