---
title: 財務維度集
description: 本主題描述財務維度集並提供一些最佳化其使用的技巧。
author: yukonpeegs
ms.date: 03/07/2022
ms.topic: article
ems.prod: ''
ms.technology: ''
ms.search.form: DimensionFocus, LedgerTrialBalanceListPage
audience: Application User
ms.reviewer: roschlom
ms.custom: 25871
ms.search.region: Global
ms.author: epegors
ms.search.validFrom: 2021-03-23
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 9274e7f85005ab27d9f2b35fbb0be42e216941c9
ms.sourcegitcommit: 411874545d7c326fc4aa877948a059371f0ccb3c
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/07/2022
ms.locfileid: "8451746"
---
# <a name="financial-dimension-sets"></a>財務維度集

[!include [banner](../includes/banner.md)]

本主題描述財務維度集並提供一些最佳化其使用的技巧。

維度集是財務維度的有序列表，可用於以用戶定義的方式匯總總帳資料。 維度集的主要用途是定義試算表。

唯一的標準維度集是僅包含主科目的維度集。

您使用 **財務維度集** 頁面來創建和管理財務維度集。

## <a name="dimension-set-balances"></a>維度集餘額

維度集可以具有基於其財務維度的餘額。 餘額存在於總帳中並且基於維度集定義。 餘額從總帳資料中匯總，以幫助提高檢索時的性能 (例如，生成試算表時)。

## <a name="create-balances"></a>建立餘額

使用 **創建餘額** 按鈕為當前沒有餘額的維度集初始化餘額。

> [!NOTE]
> 我們建議您限制具有餘額的維度集的數量，因為餘額更新會影響所有總帳過帳活動。

## <a name="update-balances"></a>更新餘額

使用 **更新餘額** 按鈕以在餘額中包含最新的總帳過帳活動。 餘額更新是輕量級的操作。 他們必須只處理自上次更新以來發生的總帳過帳活動。

> [!NOTE]
> 試算表的顯示強制更新，以確保顯示的餘額是最新的。 考慮使用重複的批處理作業，以便快速更新最常用的維度集。 通過這種方式，您可以幫助最大限度地減少試算表用戶必須等待的時間。

## <a name="rebuild-balances"></a>重建餘額

使用 **重建餘額** 按鈕從頭開始重新創建餘額。 通過這種方式，您可以幫助確保它們與總帳中的資料相匹配。 天平的重建需要大量處理，通常不需要。

> [!NOTE]
> 如果您遇到需要定期重建餘額的情況，我們建議您連絡客戶支援。 客戶支援可以幫助您確定餘額與總帳中的資料不匹配的原因。

## <a name="clear-balances"></a>清除餘額

使用 **清除餘額** 按鈕刪除餘額並停止任何進一步的更新。 維度集將不再對總帳過帳活動產生影響。

## <a name="delete-a-dimension-set"></a>刪除維度集

別 **刪除並重新創建** 維度集作為解決特定維度集餘額資料潛在問題的任何形式的變通方法。 重新創建維度集的成本很高。 如需有關問題的進一步幫助，請連絡客戶支援。 


如需詳細資訊，請參閱[財務維度](financial-dimensions.md)。

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
