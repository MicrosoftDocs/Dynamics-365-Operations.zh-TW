---
title: 運輸管理狀態
description: 本主題說明如何建立運輸狀態，並將該狀態對應到承運人狀態。
author: Henrikan
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2020-09-08
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 9c5570d3b5b436a35bb57d051bc06cde8b78934e
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448251"
---
# <a name="transportation-management-statuses"></a>運輸管理狀態

[!include [banner](../includes/banner.md)]

設定運輸狀態的主代碼以說明裝運承運人提供的代碼。 這可讓您與裝運承運人整合以提供狀態。 您為運輸主狀態代碼提供的運輸狀態可以幫助您追蹤裝載、裝運或集裝箱的狀態。 負載、裝運或集裝箱的特定運輸狀態只能透過資料整合來更新，而不能透過使用者介面手動更新。

## <a name="create-a-transportation-status"></a>建立運輸狀態

若要建立運輸狀態，請執行以下步驟：

1. 移至 **運輸管理** \> 設定 \> 運輸狀態主資料。
1. 選擇 **新增** 以建立運輸狀態主資料。
1. 在 **運輸狀態主資料** 欄位，輸入運輸狀態的唯一代碼。
1. 在 **運輸類型** 欄位，選擇 *裝運承運人* 或 *中樞* 作為運輸工具。
1. 輸入名稱和運輸狀態。
1. 關閉頁面。

## <a name="map-a-transportation-status-to-a-carrier-status"></a>將運輸狀態對應到承運人狀態

若要將運輸狀態對應到承運人狀態，請按照以下步驟作業：

1. 移至 **運輸管理 \> 設定 \> 承運人 \> 承運人運輸狀態**。
1. 選擇 **新增** 將裝運承運人的代碼對應到運輸狀態主代碼。
1. 選擇裝運承運人和承運人服務的唯一識別碼。
1. 選擇要對應到所選裝運承運人代碼的運輸狀態代碼。
1. 輸入裝運承運人使用的外部代碼。
1. 關閉頁面。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]