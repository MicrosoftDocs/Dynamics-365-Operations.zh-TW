---
title: 透過 Warehouse Management 行動應用程式的牌照接收
description: 本主題說明如何設定 Warehouse Management 行動應用程式以支援使用牌照接收流程來接收實際庫存。
author: perlynne
ms.date: 04/29/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSParameters, WHSRFMenuItem, WHSLicensePlate, WHSPackingStructure
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-03-31
ms.dyn365.ops.version: 10.0.11
ms.openlocfilehash: 6663188334c70035906f924c7850a0dc5002f306
ms.sourcegitcommit: fcb8a3419e3597fe855cae9eb21333698518c2c7
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/09/2022
ms.locfileid: "8449949"
---
# <a name="license-plate-receiving-via-the-warehouse-management-mobile-app"></a>透過 Warehouse Management 行動應用程式的牌照接收

[!include [banner](../includes/banner.md)]

本主題說明如何設定 Warehouse Management 行動應用程式，以便支援使用牌照接收流程來接收實際庫存。

您可以使用此功能快速記錄與提前出貨通知 (ASN) 相關的入庫庫存的收貨。 當使用倉庫管理流程為轉移單發貨時，系統會自動建立 ASN。 對於訂購單流程，可以手動記錄 ASN，也可以透過入庫 ASN 資料實體流程自動匯入。

ASN 資料透過 *裝箱結構* 連結到負載和裝運，其中托盤 (上層牌照) 可以包含貨箱 (嵌套牌照)。

> [!NOTE]
> 為了減少使用具有嵌套牌照的裝箱結構時的庫存交易數量，系統會在上層牌照上記錄實際現有庫存。 為了根據裝箱結構資料觸發實際現有庫存從上層牌照移動到嵌套牌照，行動裝置必須提供基於 *裝箱到嵌套的牌照* 工作建立流程的功能表項目。

## <a name="warehousing-mobile-device-app-processing"></a>Warehousing 行動裝置應用程式處理

當工作人員掃描傳入的牌照識別碼時，系統會初始化牌照接收流程。 根據此資訊，牌照的內容 (來自 ASN 的資料) 在入庫台位置進行實際登記。 接下來的流程將取決於您的業務流程需求。

## <a name="work-policies"></a>工作原則

例如，與 *報告為完成* 行動裝置功能表項目流程一樣，牌照接收流程支援根據定義設定的多個工作流程。

### <a name="work-policies-with-work-creation"></a>具有建立工作的工作原則

當您使用建立工作的工作原則登記傳入品項時，系統會為每個登記產生並儲存存放工作記錄。 如果您使用 *牌照接收和存放* 工作流程，登記和存放將使用單個行動裝置功能表項目作為單個工序。 如果您使用 *牌照接收* 流程，則接收和存放流程將作為兩個不同的倉庫工序，每個工序都有自己的行動裝置功能表項目。

### <a name="work-policies-without-work-creation"></a>不具有建立工作的工作原則

您無需建立工作就可以使用牌照接收流程。 如果您定義具有工單類型為 *轉移收貨* 和/或 *訂購單* 的工作原則，且將該流程用於 *牌照接收 (和存放)*，以下兩個 Warehousing 行動應用程式流程不會建立工作。 相反，他們只會在入庫接收台的牌照上登記入庫實際庫存。

- *牌照接收*
- *牌照接受及存放*

> [!NOTE]
> - 您必須在 **庫存貨位** 區段為工作原則定義至少一個位置。 您不能為多個工作原則指定相同的位置。
> - Warehousing 行動裝置功能表項目的 **列印標籤** 選項不會在不建立工作的情況下列印牌照標籤。

若要讓此功能可在您的系統上使用，您必須在 [功能管理](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)中打開 *牌照接收增強* 功能。

### <a name="receive-inventory-on-a-location-that-doesnt-track-license-plates"></a>在不追蹤牌照的位置接收庫存

即使未開啟 **使用牌照追蹤** 選項，也可以使用指派給位置設定檔的倉庫位置。 因此，當您接收庫存時，可以直接在某個位置登記現有庫存，而無需建立工作。

## <a name="add-mobile-device-menu-items-for-each-receiving-location-in-a-warehouse"></a>為倉庫中的每個接收位置新增行動裝置功能表項目

*牌照接收增強* 功能可讓您透過將特定位置的牌照接收 (和存放) 功能表項目新增到 Warehousing 行動應用程式，在倉庫的任何位置接收。 先前系統僅支援在為每個倉庫定義的預設位置收貨。 但是，打開此功能後，用於牌照接收 (和存放) 的行動裝置功能表項目現在提供 **使用預設資料** 選項，可讓您為每個功能表項目選擇自訂的「目標」位置。 (此選項已可用於某些其他類型的功能表項目。)

若要讓此功能可在您的系統上使用，您必須在 [功能管理](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)中打開 *牌照接收增強* 功能。

## <a name="show-or-skip-the-receiving-summary-page"></a>顯示或跳過接收摘要頁面

您可以使用 *控制是否在行動裝置上顯示接收摘要頁面* 功能在牌照接收流程中利用其他詳細 Warehouse Management 行動應用程式流程。

開啟此功能後，牌照接收或牌照接收和存放的行動裝置功能表項目將提供 **顯示接收摘要頁面** 設定。 此設定具有以下選項：

- **顯示詳細摘要** – 在接收牌照期間，工作人員將看到顯示完整 ASN 資訊的額外頁面。
- **跳過摘要** – 工人不會看到完整的 ASN 資訊。 倉庫工作人員也無法在收貨流程中設定處置代碼或新增例外狀況。

若要使用此功能，您必須為系統打開 *控制是否在行動裝置上顯示接收摘要頁面* 功能。 從 Supply Chain Management 版本 10.0.21 開始，此功能預設開啟。 從 Supply Chain Management 10.0.25 開始，此功能為強制性開啟，且不能關閉。 如果您執行的版本為 10.0.25 之前的版本，管理員可以前往 [功能管理](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) 工作區並搜尋 *控制是否在行動裝置上顯示接收摘要頁面* 功能，然後開啟或關閉此功能。

## <a name="prevent-transfer-ordershipped-license-plates-from-being-used-at-warehouses-other-than-the-destination-warehouse"></a>防止在目的地倉庫以外的倉庫使用轉移單已裝運牌照

如果 ASN 包含已存在的牌照識別碼，並且具有的實際現有資料所在倉庫位置不是牌照的登記倉庫位置，則不能使用牌照接收流程。

對於中轉倉庫不追蹤牌照 (因此也不追蹤每個牌照的實際現有庫存) 的轉移單案例，您可以使用 *防止在目的地倉庫以外的其他倉庫使用轉移單已裝運牌照* 功能防止對運輸中的牌照的實際現有更新。 若要讓此功能可用，您必須為系統打開 *防止在目的地倉庫以外的其他倉庫使用轉移單已裝運牌照* 功能。 從 Supply Chain Management 10.0.25 開始，此功能為強制性開啟，且不能關閉。 如果您執行的版本為 10.0.25 之前的版本，管理員可以前往[功能管理](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)工作區搜尋該功能，然後開啟或關閉此功能。

若要在此功能可用時管理功能，請按照以下步驟操作。

1. 前往 **倉庫管理 \> 設定 \> 倉庫管理參數**。
1. 在 **一般** 索引標籤的 **牌照** FastTab，將 **中轉倉庫牌照原則** 欄位設定為以下值之一：

    - **允許重複使用未追蹤牌照** – 系統的運作方式與 *防止在目的地倉庫以外的其他倉庫使用轉移單已裝運牌照* 功能不可用時的運作方式相同。 此值是您首次啟動該功能時的預設設定。
    - **防止重複使用非追蹤牌照** – 在收到轉移單之前，目的地倉庫只允許與已裝運牌照相關的現有更新。

## <a name="more-information"></a>更多資訊

有關行動裝置功能表項目的更多資訊，請參閱[為倉庫工作設定行動裝置](configure-mobile-devices-warehouse.md)。

有關 *報告為完成* 生產案例的更多資訊，請參閱[倉庫工作原則概觀](warehouse-work-policies.md)。

有關入庫負載管理的更多資訊，請參閱[倉庫對訂購單入庫負載的處理](inbound-load-handling.md)。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]