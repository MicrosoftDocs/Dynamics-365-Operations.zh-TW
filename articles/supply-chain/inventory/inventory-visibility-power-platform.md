---
title: 庫存能見度應用程式
description: 本主題將說明如何使用庫存能見度應用程式。
author: yufeihuang
ms.date: 08/02/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 359f89f98ca6954a0bbafd63fffa1d505a43f0c8
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8449808"
---
# <a name="use-the-inventory-visibility-app"></a>使用庫存能見度應用程式

[!include [banner](../includes/banner.md)]


本主題將說明如何使用庫存能見度應用程式。

庫存能見度是一項以視覺效果呈現庫存的模型導向應用程式。 此應用程式包含三個頁面：**設定**、**營運能見度**，和 **庫存摘要**。 具備的功能如下：

- 提供現有庫存設定和未確認保留庫存設定的使用者介面 (UI)。
- 支援各種維度組合的即時現有庫存查詢。
- 提供過帳保留要求的 UI。
- 提供產品現有庫存的自訂視圖以及所有維度。

## <a name="prerequisites"></a>先決條件

在開始之前，請按照[安裝及設定庫存能見度](inventory-visibility-setup.md)的說明，安裝並設定庫存能見度增益集。

## <a name="open-the-inventory-visibility-app"></a>開啟庫存能見度應用程式

若要開啟庫存能見度應用程式，請登入您的 Power Apps 環境，然後開啟 **庫存能見度**。

## <a name="configuration"></a><a name="configuration"></a>組態

庫存能見度應用程式的 **設定** 頁面可協助您設置現有庫存設定和未確認保留庫存設定。 安裝增益集後，預設設定包括 Microsoft Dynamics 365 Supply Chain Management 預設設定 (`fno` 資料來源)。 您可以檢閱預設設定。 之後，您可以根據業務需求和外部系統的庫存過帳需求修改設定，將庫存變更的跨系統過帳、整理和查詢方式標準化。

有關如何設定解決方案的完整詳細資訊，請參閱[設定庫存能見度](inventory-visibility-configuration.md)。

## <a name="operational-visibility"></a>營運能見度

**營運能見度** 頁面提供基於各種維度組合的即時庫存查詢結果。 *OnHandReservation* 功能開啟時，您也可以從 **營運能見度** 頁面過帳保留要求。

### <a name="on-hand-query"></a>現有庫存查詢

**現有庫存查詢** 索引標籤顯示即時現有庫存查詢的結果。

當您選取 **現有庫存查詢** 索引標籤時，系統會要求您的認證，以便取得查詢庫存能見度服務所需的持有人權杖。 您只需將持有人權杖貼入 **持有人權杖** 欄位並關閉對話方塊， 然後即可過帳現有庫存查詢要求。

如果持有人權杖無效或已過期，則必須將新權杖貼入 **持有人權杖** 欄位。 輸入正確的 **用戶端識別碼**、**租用戶識別碼**、**用戶端密碼** 值，然後選取 **重新整理**。 系統將自動取得有效的新持有人權杖。

若要過帳現有庫存查詢，請在要求本文中輸入查詢。 運用[使用 post 方法查詢](inventory-visibility-api.md#query-with-post-method)說明的模式。

![現有庫存查詢設定](media/inventory-visibility-query-settings.png "現有庫存查詢設定")

### <a name="reservation-posting"></a>過帳保留要求

使用 **過帳保留要求** 索引標籤過帳保留要求。 在過帳保留要求之前，您必須開啟 *OnHandReservation* 功能。 有關此功能的詳細資訊，請參閱[庫存能見度保留](inventory-visibility-reservations.md)。

若要過帳保留要求，您必須在要求本文中輸入一個值。 使用[建立一個保留事件](inventory-visibility-api.md#create-one-reservation-event)說明的模式。 然後選取 **過帳**。 若要查看要求回應詳細資料，請選取 **顯示詳細資料**。 您還可以從回應詳細資料中取得 `reservationId` 值。

## <a name="inventory-summary"></a><a name="inventory-summary"></a>庫存摘要

**庫存摘要** 是 *現有庫存總和* 實體的自訂視圖。 它提供產品的庫存摘要以及所有維度。 系統會從庫存能見度定期同步處理庫存摘要資料。 查看 **庫存摘要** 索引標籤資料前，您必須開啟 **功能管理** 索引標籤上的 *OnHandMostSpecificBackgroundService* 功能。

使用 Dataverse 的 **進階篩選** 可建立個人視圖，顯示您認為重要的資料列。 進階篩選選項可讓您建立從簡單到複雜的各種視圖。 您還可以新增群組和巢狀條件至篩選器。 若要瞭解更多 **進階篩選** 使用方式相關資訊，請參閱[使用進階格線篩選器編輯或建立個人視圖](/powerapps/user/grid-filters-advanced)。

自訂視圖的頂端提供三個欄位：**預設維度**、**自訂維度**，和 **量值**。 您可以使用這些欄位來控制要顯示哪些資料欄。

您可以選取欄標題來篩選或排序目前結果。

自訂視圖底部顯示「50 則記錄 (已選取 29 則)」或「50 則記錄」等資訊。 此資訊是從 **進階篩選** 結果載入的目前記錄。 「已選取 29 則」這段文字是指透過欄標題篩選器從載入記錄選取的記錄數。

視圖底部的 **載入更多** 按鈕可讓您從 Dataverse 載入更多記錄。 預設載入的記錄數為 50 則。 當您選取 **載入更多** 時，接下來 1,000 則可用記錄將載入視圖。 **載入更多** 按鈕顯示的數字表示目前載入的記錄和 **進階篩選** 結果的記錄總數。

![庫存摘要](media/inventory-visibility-onhand-list.png "庫存摘要")
