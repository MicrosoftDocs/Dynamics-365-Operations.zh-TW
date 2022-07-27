---
title: 生產設定要求
description: 本文提供使用生產控制之前的設定要求的相關資訊。
author: johanhoffmann
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ProdParameters, RouteOpr, RouteOprTable, WorkCalendarTable, WorkTimeTable, WrkCtrTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 55561
ms.assetid: 1953059f-478d-4706-b461-25b89ace5fc3
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bfde8b40927ceaa216878d58ef72c5d91e9ebe01
ms.sourcegitcommit: 133aa728b8a795eaeaef22544f76478da2bd1df9
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/13/2022
ms.locfileid: "8449619"
---
# <a name="production-setup-requirements"></a>生產設定要求

[!include [banner](../includes/banner.md)]

本文提供使用生產控制之前的設定要求的相關資訊。 

生產控制已與其他模組中的功能整合。 這種互連性讓您可以變更生產訂單，並確保生產訂單在系統中的所有其他相關流程和計算中自動更新。 以下設定過程按照您應完成的順序列出。

## <a name="required-baseline-setup-in-other-modules"></a>其他模組中所需的基準設定
您必須先設定其他模組中的資訊，才能夠使用生產控制。 這項設定包括以下任務：

-   設定一般公司資訊。
-   設定總帳。
-   定義項目群組。
-   為項目群組設定分類帳。
-   在庫存管理中設定庫存品項表。
-   在產品資訊管理中建立物料清單 (BOM) 和 BOM 版本。

## <a name="required-calendar-and-resource-setup"></a>所需的日曆和資源設定
在使用生產控制之前，請開啟組織管理，並按以下順序建立和定義日曆和營運資源：

1.  **工作時間範本** – 設定工作時間範本，以定義可用於生產排程的時間。
2.  **日曆** – 設定工作時間日曆，以定義一年中可用於生產計劃的天數。
3.  **資源群組** – 設定資源群組將營運資源分組，以便您在執行排程時可以概覽任何可用產能。 您不需要在設定營運資源之前設定資源群組。 但是，我們建議您在設定生產控制時瞭解如何將資源分組。
4.  **資源** – 設定營運資源以定義用於完成生產流程和產能計劃的資源。

## <a name="required-production-parameters-setup"></a>所需的生產參數設定
**生產控制參數** – 設定基本生產參數以定義系統如何反應及處理生產訂單。 定義如何建立、估算、排程和消耗生產訂單。 您也可以選擇想要的意見反應以及成本核算方式。

## <a name="required-journal-name-identification"></a>必需的日記帳名稱識別資訊
**生產日記帳名稱** – 指定用於記錄和過帳交易的生產日記帳名稱。

## <a name="setup-if-you-use-operations"></a>如果您使用作業，請設定
作業是指為生產產品而完成的特定活動。 **注意：** 您必須了解生產項目所需的活動類型，以及這些活動的次序和優先順序。 您還必須知道涉及哪些資源，以及相關數量。

1.  **運營** – 設定作業以表示生產成品必須完成的任務。
2.  **關係** – 設定作業關係以建立詳細的屬性。 若要定義操作關係，請按一下 **運營** 頁面上的 **關係**。

## <a name="setup-if-you-use-routes"></a>如果您使用途程，請設定
如果您使用途程，則必須為設定的每個生產路線定義作業。 路線表示項目從作業到作業，從生產過程開始到結束所採用的路徑。

1.  **成本類別** – 設定成本類別以定義指定流程和設定時間的每小時成本。
2.  **成本群組** – 設定成本群組以建立和維護不同類型的成本核算。
3.  **途程群組** – 設置途程群組以定義與途程群組相關的參數。 您必須先設定途程，才能建立生產路線。
4.  **途程** – 設定生產路線，並定義控管排程、花費和途程作業價格的預設設定，同時控制進度報告。
5.  **途程版本** – 設定途程版本以啟用生產中的項目變型。

## <a name="optional-advanced-settings"></a>選用的進階設定
1.  **生產群組** – 設定生產群組以建立生產訂單和分類帳之間的關係。 分類帳適用於過帳或分組訂單以進行報告。
2.  **生產集區** – 建立生產集區以對生產訂單進行分組，以便您可以處理緊急產生訂單，或刪除和過帳訂單群組。
3.  **屬性** – 定義屬性以建立特別屬性，讓您可以指派資源來控制生產順序。 這些屬性會連結工作時間範本。






[!INCLUDE[footer-include](../../includes/footer-banner.md)]
