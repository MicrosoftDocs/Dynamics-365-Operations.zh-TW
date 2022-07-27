---
title: 為 Warehouse Management 行動裝置應用程式中的步驟設定升階的欄位
description: 本主題描述如何為 Warehouse Management 行動應用程式工作流程中的任何步驟升階和醒目顯示特定資訊。
author: Mirzaab
ms.date: 10/15/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-10-15
ms.dyn365.ops.version: 10.0.23
ms.openlocfilehash: 0ce3fb829d349a35c6c2f29838a2c725f7b61c55
ms.sourcegitcommit: 008779c530798f563fe216810d34b2d56f2c8d3c
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/14/2021
ms.locfileid: "8449574"
---
# <a name="configure-promoted-fields-for-steps-in-the-warehouse-management-mobile-app"></a>為 Warehouse Management 行動裝置應用程式中的步驟設定升階的欄位

[!include [banner](../includes/banner.md)]

> [!IMPORTANT]
> 本主題中描述的功能僅適用於新的 Warehouse Management 行動應用程式。 這不會影響現在已取代的舊倉庫應用程式。

本主題描述如何為 Warehouse Management 行動應用程式工作流程中的任何步驟升階和醒目顯示特定資訊。 此功能可以幫助工作人員在流程中工作時將注意力集中在最重要的欄位上。 對於每個流程中的每個步驟，管理員都可以選擇要升階的欄位以及要醒目顯示的欄位。

## <a name="enable-promoted-fields-in-your-system"></a>在系統中啟用升階欄位

在設定升階欄位之前，必須完成以下程序以在 Warehouse Management 行動應用程式中啟用所需的功能並產生所需的欄位名稱。

1. 前往 **系統管理 \> 工作區 \> 功能管理**。
1. 在 [**功能管理** 工作區](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)，啟用以下列方式列出的功能：

    - **模組：***倉庫管理*
    - **功能名稱：** *Warehouse 應用程式步驟指示*

    有關 *倉庫應用程式步驟說明* 功能的更多資訊，請參閱[自訂 Warehouse Management 行動應用程式的步驟標題和說明](mobile-app-titles-instructions.md)。 此功能是 *倉庫應用程式升階欄位* 功能的先決條件。

1. 啟用以下列方式列出的功能：

    - **模組：***倉庫管理*
    - **功能名稱：***倉庫應用程式升階欄位*

    此功能是本主題中描述的功能。

1. 透過前往 **Warehouse Management \> 設定 \> 行動裝置 \> 倉庫應用程式欄位名稱**，並選擇 **建立預設設定**，更新 Warehouse Management 行動應用程式中的欄位名稱。 如需更多資訊，請參閱[設定 Warehouse Management 行動裝置應用程式的欄位](configure-app-field-names-priorities-warehouse.md)。
1. 對您使用 Warehouse Management 行動應用程式的每個法律實體 (公司) 重複上一步。

## <a name="configure-promoted-fields-from-a-menu-specific-override"></a>從特定功能表的覆寫設定升階欄位

使用以下程序來設定升階欄位。

1. 為相關功能表和步驟建立特定功能表的覆寫，如[自訂 Warehouse Management 行動應用程式的步驟標題和說明](mobile-app-titles-instructions.md)中所述。
1. 尋找要編輯的 **步驟識別碼** 和 **功能表項目名稱** 值組合，然後選取 **步驟識別碼** 資料行中的值。
1. 在顯示的頁面的 **選取升階欄位** FastTab 上，在工具列上選擇 **選擇欄位**。
1. 在 **升階欄位** 對話方塊中，選擇要升階的欄位。 您還可以醒目顯示最多兩個選定欄位。 醒目顯示的欄位將在 Warehouse Management 行動應用程式中將以粗體顯示。 選擇欄位時，請考慮到某些畫面可能大到僅顯示前一或兩個升階欄位。 有關顯示如何使用這些設定的範例，請參閱本主題後面的案例。

    > [!NOTE]
    > **可用欄位** 清單僅限於可以為功能表項目顯示的欄位。 但是，其他因素 (例如項目構成) 將決定欄位是否實際顯示在 Warehouse Management 行動應用程式中。 如果您已設定升階欄位，則只有選定的欄位將顯示在 Warehouse Management 行動應用程式的主頁上。 但是，工作人員仍然可以透過點選詳細資料頁面來查看剩餘的欄位。

1. 選取 **確定** 套用您的設定。 您選擇的欄位現在列在 **選擇升階欄位** FastTab 上。

## <a name="example-scenario"></a>範例案例

### <a name="enable-sample-data"></a>啟用範例資料

若要使用指定的範例記錄和值完成此案例，您必須使用已安裝標準示範資料的系統。 在開始之前，您還必須先選擇 **USMF** 法律實體。

### <a name="configure-sales-picking-with-promoted-steps-on-the-license-plate-step"></a>使用牌照步驟上的升階步驟設定銷售揀料

在此程序中，將為牌照步驟中的 **銷售揀料** 功能表項目設定升階和醒目顯示欄位。

1. 前往 **倉庫管理 \> 設定 \> 行動裝置 \> 行動裝置步驟**。
1. 尋找名為 *LicensePlateId* 的步驟識別碼，並選擇它。
1. 在動作窗格上，選擇 **新增步驟設定**。
1. 在下拉式對話方塊中，使用 **功能表項目** 欄位尋找，並選擇 *銷售揀料*。
1. 選取 **確定**。
1. 將顯示您剛剛建立的覆寫的詳細資料頁面。 在 **選取升階欄位** FastTab 上，在工具列上選擇 **選擇欄位**。
1. 在 **升階欄位** 對話方塊中，選擇要升階和醒目顯示的欄位。 在 **可用欄位** 清單中，尋找並選擇以下欄位，然後使用按鈕將它們移動到 **選定欄位** 清單：

    - 位置
    - 項目
    - 產品名稱
    - 庫存狀態

1. 使用向上箭頭和向下箭頭按鈕自訂欄位在 **選定欄位** 清單中的順序。 在 Warehouse Management 行動應用程式中，這些欄位將按照您在此處設定的順序顯示。
1. 選擇 **位置** 欄位，然後選擇 **醒目顯示**。
1. 選擇 **確定** 以儲存設定。

### <a name="view-the-promoted-fields-in-the-warehouse-management-mobile-app"></a>在 Warehouse Management 行動裝置應用程式中查看升階的欄位

在此程序中，您將打開 Warehouse Management 行動應用程式並執行步驟以查看您在上一個程序中升階和醒目顯示的欄位。

1. 在 Microsoft Dynamics 365 Supply Chain Management 中建立銷售訂單，該訂單需要從已追蹤牌照的位置揀料的揀料步驟。 然後將銷售訂單發貨到倉庫。 記下產生的工作識別碼。
1. 打開 Warehouse Management 行動應用程式，登入倉庫 24。 (在標準示範資料中，使用 *24* 作為用戶識別碼和 *1* 作為密碼進行登入。)
1. 選取 **出庫** 功能表，然後選取 **銷售揀料** 功能表項目。
1. 按照畫面上的資料輸入說明輸入在步驟 1 中產生的工作識別碼。
1. 在包含文本 **掃描牌照** 的步驟上，您應該會在詳細資料頁面上看到您所做的變更。 欄位將按照您為升階欄位設定的順序顯示，且 **位置** 欄位以粗體顯示。
