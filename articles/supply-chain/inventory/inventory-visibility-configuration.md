---
title: 設定庫存能見度
description: 本主題將說明如何設定庫存能見度。
author: yufeihuang
ms.date: 12/09/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 8ba478fef424a6c4688191ed4e5375bbce52de0c
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8449811"
---
# <a name="configure-inventory-visibility"></a>設定庫存能見度

[!include [banner](../includes/banner.md)]


本主題將說明如何使用 Power Apps 中的庫存能見度應用程式設定庫存能見度。

## <a name="introduction"></a><a name="introduction"></a>簡介

在開始使用庫存能見度前，您必須按照本主題中的說明完成以下設定：

- [資料來源設定](#data-source-configuration)
- [分割區設定](#partition-configuration)
- [產品索引階層設定](#index-configuration)
- [保留設定 (選用)](#reservation-configuration)
- [預設設定樣本](#default-configuration-sample)

## <a name="prerequisites"></a>先決條件

在開始之前，請按照[安裝及設定庫存能見度](inventory-visibility-setup.md)的說明，安裝並設定庫存能見度增益集。

## <a name="enable-inventory-visibility-features-in-power-apps-feature-management"></a><a name="feature-switch"></a>在 Power Apps 功能管理中啟用庫存能見度功能

庫存能見度增益集會新增數個功能至 Power Apps 安裝。 這些功能預設為關閉。 若要使用功能，請開啟 Power Apps 中的 **設定** 頁面，然後在 **功能管理** 索引標籤中開啟以下功能。

- *OnHandReservation*
- *OnHandMostSpecificBackgroundService*

## <a name="find-the-service-endpoint"></a><a name="get-service-endpoint"></a>尋找服務端點

如果您不知道正確的庫存能見度服務端點，請開啟 Power Apps 的 **設定** 頁面，然後選取右上角的 **服務端點**。 該頁面將顯示正確的服務端點。

## <a name="the-configuration-page-of-the-inventory-visibility-app"></a><a name="configuration"></a>庫存能見度應用程式的「設定」頁面

在 Power Apps 中，[庫存能見度應用程式](inventory-visibility-power-platform.md)的 **設定** 頁面可協助您設置現有庫存設定和未確認保留庫存設定。 安裝增益集後，預設設定包括來自 Microsoft Dynamics 365 Supply Chain Management 預設設定 (`fno` 資料來源) 的值。 您可以檢閱預設設定。 此外，您可以根據業務需求和外部系統的庫存過帳需求修改設定，將庫存變更的跨系統過帳、整理和查詢方式標準化。 本主題的其餘章節將說明如何使用 **設定** 頁面的各個部分。

設定完成後，請務必選取應用程式中的 **更新設定**。

## <a name="data-source-configuration"></a>資料來源設定

每個資料來源都代表資料來自的系統。 範例資料來源名稱包括 `fno` (代表「Dynamics 365 Finance 和營運應用程式」) 和 `pos` (代表「銷售點」)。 在預設情況下，Supply Chain Management 設為庫存能見度的預設資料來源 (`fno`)。

> [!NOTE]
> `fno` 資料來源保留用於 Supply Chain Management。 如果您的庫存能見度增益集與 Supply Chain Management 環境整合，我們建議您不要刪除與資料來源中 `fno` 有關的設定。

若要建立資料來源，請按照以下步驟操作。

1. 登入 Power Apps 環境，並開啟 **庫存能見度**。
1. 開啟 **設定** 頁面。
1. 在 **資料來源** 索引標籤上，選取 **新增資料來源** 以新增資料來源。

> [!NOTE]
> 新增資料來源時，請務必先驗證資料來源名稱、實體測量和維度對應，再更新庫存能見度服務設定。 選取 **更新設定** 後即無法修改這些設定。

資料來源設定包括以下部分：

- 維度 (維度對應)
- 實體測量
- 計算測量

### <a name="dimensions-dimension-mapping"></a><a name="data-source-configuration-dimension"></a>維度 (維度對應)

維度設定的目的是根據維度組合將過帳事件和查詢的多系統整合標準化。 庫存能見度提供了可從資料來源維度對應的基本維度清單。 有 33 個維度可供對應。

- 在預設情況下，如果使用 Supply Chain Management 做為資料來源之一，則 13 個維度會對應到 Supply Chain Management 標準維度。 其他 12 個維度 (`inventDimension1` 到 `inventDimension12`) 對應到 Supply Chain Management 中的自訂維度。 其餘 8 個維度則是可對應到外部資料來源的擴充維度。
- 如不使用 Supply Chain Management 做為資料來源之一，您可以任意對應維度。 下表顯示了完整可用維度清單。

> [!NOTE]
> 如果您的維度不在預設維度清單中，且您使用的是外部資料來源，建議您使用 `ExtendedDimension1` 到 `ExtendedDimension8` 來進行對應。

| 維度類型 | 基本維度 |
|---|---|
| 產品 | `ColorId` |
| 產品 | `SizeId` |
| 產品 | `StyleId` |
| 產品 | `ConfigId` |
| 追蹤 | `BatchId` |
| 追蹤 | `SerialId` |
| 位置 | `LocationId` |
| 位置 | `SiteId` |
| 庫存狀態 | `StatusId` |
| 倉庫專用 | `WMSLocationId` |
| 倉庫專用 | `WMSPalletId` |
| 倉庫專用 | `LicensePlateId` |
| 其他 | `VersionId` |
| 庫存 (自訂) | `InventDimension1` 到 `InventDimension12` |
| 分機 | `ExtendedDimension1` 到 `ExtendedDimension8` |
| 系統 | `Empty` |

> [!NOTE]
> 上列維度類型僅供參考。 您不必在庫存能見度中定義這些維度。
>
> 系統可能會保留庫存 (自訂) 維度以供 Supply Chain Management 使用。 在這種情況下，您可以改用擴充維度。

外部系統可透過其 RESTful API 存取庫存能見度。 至於整合作業，您可透過庫存能見度設定 _外部資料來源_ 以及從 _外部維度_ 對應到 _基本維度_。 以下是維度對應表範例。

| 外部維度 | 基本維度 |
|---|---|
| `MyColorId` | `ColorId` |
| `MySizeId` | `SizeId` |
| `MyStyleId` | `StyleId` |
| `MyDimension1` | `ExtendedDimension1` |
| `MyDimension2` | `ExtendedDimension2` |

您可透過設定維度對應，將外部維度直接傳送到庫存能見度。 庫存能見度接著會自動將外部維度轉換為基本維度。

若要新增維度對應，請執行以下步驟。

1. 登入 Power Apps 環境，並開啟 **庫存能見度**。
1. 開啟 **設定** 頁面。
1. 在 **資料來源** 索引標籤的 **維度對應** 部分中，選取 **新增** 以新增維度對應。
    ![新增維度對應](media/inventory-visibility-dimension-mapping.png "新增維度對應")

1. 在裡面 **維度名稱** 欄為中，指定來源維度。
1. 在 **到基本維度** 欄位中，選取您要對應的庫存能見度維度。
1. 選擇 **儲存**。

舉例來說，如果資料來源包括產品顏色維度，您可以將其對應到 `ColorId` 基本維度，藉此在 `exterchannel` 資料來源中新增 `ProductColor` 自訂維度。 該維度會接著對應到 `ColorId` 基本維度。

### <a name="physical-measures"></a>實體測量

資料來源會使用 *實體測量*，將庫存變更過帳到庫存能見度。 實體測量會修改數量並反映庫存狀態。 您可以視需求自行定義實體測量。 可以根據實體測量進行查詢。

庫存能見度提供連結至 Supply Chain Management (`fno` 資料來源) 的預設實體測量清單。 這些預設實體測量取自 Supply Chain Management **現有清單** 頁面的庫存交易狀態 (**庫存管理 \> 查詢和報告 \> 現有清單**)。 下表提供實體測量的範例。

| 實體測量名稱 | 描述 |
|---|---|
| `NotSpecified` | 未指定 |
| `Arrived` | 已送達 |
| `AvailOrdered` | 可用的訂購品項 |
| `AvailPhysical` | 可用實物 |
| `Deducted` | 扣除 |
| `OnOrder` | 訂購 |
| `Ordered` | 已訂購 |
| `PhysicalInvent` | 實物庫存 |
| `Picked` | 已領料 |
| `PostedQty` | 過帳數量 |
| `QuotationIssue` | 報價問題 |
| `QuotationReceipt` | 報價收據 |
| `Received` | 已收到 |
| `Registered` | 已註冊 |
| `ReservOrdered` | 訂購保留 |
| `ReservPhysical` | 實物保留 |

如果資料來源為 Supply Chain Management，則不必重新建立預設實體測量。 不過如果是外部資料來源，您可以按照以下步驟建立新的實體測量。

1. 登入 Power Apps 環境，並開啟 **庫存能見度**。
1. 開啟 **設定** 頁面。
1. 在 **資料來源** 索引標籤的 **實體測量** 部分中，選取 **新增**，然後指定來源測量名稱並儲存變更。

### <a name="calculated-measures"></a>計算測量

您可以使用庫存能見度查詢庫存實體測量和 *自訂計算測量*。 計算測量提供包含一組實體測量的自訂計算公式。 您可透過此功能定義一組要加入和/或要減去的實體測量從自定義測量，以建立自訂測量。

這項設定可讓您定義一組要加入或減去的修飾詞，以獲得彙總的總輸出量。

若要設定自訂計算測量，請按照以下步驟操作。

1. 登入 Power Apps 環境，並開啟 **庫存能見度**。
1. 開啟 **設定** 頁面。
1. 在 **計算測量** 索引標籤中，選取 **新增計算測量** 以新增計算測量。 然後設定以下表格中說明的欄位。

    | 欄位 | 值 |
    |---|---|
    | 新增計算測量名稱 | 輸入計算測量的名稱。 |
    | 資料來源 | 查詢系統為資料來源。 |
    | 修飾詞資料來源 | 輸入修飾詞的資料來源。 |
    | 修飾詞 | 輸入修飾詞名稱。 |
    | 修飾詞類型 | 選擇修飾詞類型 (*加入* 或 *減去*)。 |

例如，查詢結果可能如下所示。

```json
[
    {
        "productId": "T-shirt",
        "dimensions": {
            "SiteId": "1",
            "LocationId": "11",
            "ColorId": "Red"
        },
        "quantities": {
            "pos": {
                "inbound": 80.0,
                "outbound": 20.0
            },
            "fno": {
                "availphysical": 100.0,
                "orderedintotal": 50.0,
                "orderedreserved": 10.0
            },
            "externalchannel": {
                "received": 90.0,
                "scheduled": 30.0,
                "issued": 60.0,
                "reserved": 40.0
            }
        }
    }
]
```

然後請設定名稱為 `MyCustomAvailableforReservation` 的計算測量，如下表所示。 此計算測量將由消耗系統使用。

| 消耗系統 | 計算測量 | 資料來源 | 實體測量 | 計算類型 |
|---|---|---|---|---|
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `availphysical` | `Addition` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedintotal` | `Addition` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedreserved` | `Subtraction` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `pos` | `inbound` | `Addition` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `pos` | `outbound` | `Subtraction` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `externalchannel` | `received` | `Addition` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `externalchannel` | `scheduled` | `Addition` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `externalchannel` | `issued` | `Subtraction` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `externalchannel` | `reserved` | `Subtraction` |

使用此計算公式時，新的查詢結果將包含自訂測量。

```json
[
    {
        "productId": "T-shirt",
        "dimensions": {
            "SiteId": "1",
            "LocationId": "11",
            "ColorId": "Red"
        },
        "quantities": {
            "pos": {
                "inbound": 80.0,
                "outbound": 20.0
            },
            "fno": {
                "availphysical": 100.0,
                "orderedintotal": 50.0,
                "orderedreserved": 10.0
            },
            "externalchannel": {
                "received": 90.0,
                "scheduled": 30.0,
                "issued": 60.0,
                "reserved": 40.0
            },
            "CustomChannel": {
                "MyCustomAvailableforReservation": 220.0
            }
        }
    }
]
```

根據自訂測量中的計算設定，`MyCustomAvailableforReservation` 輸出結果為 100 + 50 – 10 + 80 – 20 + 90 + 30 – 60 – 40 = 220。

## <a name="partition-configuration"></a><a name="partition-configuration"></a>分割區設定

分割區設定目前由兩個基本維度組成 (`SiteId` 和 `LocationId`)，表示資料的分佈方式。 同一分割區下的作業能以更低成本提供更高效能。 下表顯示庫存能見度增益集提供的預設分割區設定。

| 基本維度 | 階層 |
|---|---|
| `SiteId` | 1 |
| `LocationId` | 2 |

解決方案預設包含此分割區設定。 因此 *您不必自己定義*。

> [!IMPORTANT]
> 不要自訂預設分割區設定。 如果您刪除或變更它，可能會導致意外錯誤。

## <a name="product-index-hierarchy-configuration"></a><a name="index-configuration"></a>產品索引階層設定

在大多數情況下，庫存現有查詢不會只顯示等級最高的「總計」結果。 相反，您可能還想查看根據庫存維度彙總的結果。

庫存能見度可透過設定 _索引_ 彈性顯示查詢結果。 您可使用單一維度或數個維度的組合設定索引。 索引由一個 *集合編號*、一個 *維度*，和一個 *階層* 組成，如下表所定義。

| 姓名 | 描述 |
|---|---|
| 集合編號 | 屬於同一集合 (索引) 的維度將分為一組，並分配至相同的集合編號。 |
| 維度 | 彙總查詢結果的基本維度。 |
| 階層 | 階層用於定義支援的可查詢維度組合。 舉例來說，您設定了一個維度集，其階層序列為 `(ColorId, SizeId, StyleId)`。 在這種情況下，系統支援四種維度組合的查詢。 第一個組合為空，第二為 `(ColorId)`，第三個為 `(ColorId, SizeId)`，第四個為 `(ColorId, SizeId, StyleId)`。 其他組合則不支援。 相關詳細資訊請參閱以下範例。 |

若要設定您的產品階層索引，請按照以下步驟操作。

1. 登入 Power Apps 環境，並開啟 **庫存能見度**。
1. 開啟 **設定** 頁面。
1. 在 **產品階層索引** 索引標籤的 **維度對應** 部分中，選取 **新增** 以新增維度對應。
1. 系統會提供預設索引清單。 若要修改現有索引，請在相關索引專區選取 **編輯** 或 **新增**。 若要建立新的索引集，請選取 **新增索引集**。 在 **維度** 欄位中，從基本維度清單選取，即可為每個索引集新增一列維度。 以下欄位的值會自動產生：

    - **集合編號**：屬於同一群組 (索引) 的維度將分為一組，並分配至相同的集合編號。
    - **階層**：階層用於定義可在維度群組 (索引) 中查詢的支援維度組合。 舉例來說，如果您設定的維度群組階層順序為 *樣式*、*顏色* 和 *尺寸*，系統將支援這三個查詢群組的結果。 第一組只有樣式。 第二組是樣式和顏色的組合。 第三組是樣式、顏色和尺寸的組合。 其他組合則不支援。

### <a name="example"></a>範例

本節透過範例來說明階層的運作方式。

下表提供此範例的可用庫存清單。

| 項目 | ColorId | SizeId | StyleId | 數量 |
|---|---|---|---|---|
| T 恤 | 黑色 | 小 | 寬 | 1 |
| T 恤 | 黑色 | 小 | 正常 | 2 |
| T 恤 | 黑色 | 大 | 寬 | 3 |
| T 恤 | 黑色 | 大 | 正常 | 4 |
| T 恤 | 紅色 | 小 | 寬 | 5 |
| T 恤 | 紅色 | 小 | 正常 | 6 |
| T 恤 | 紅色 | 大 | 正常 | 7 |

下表顯示如何設定索引階層。

| 設定數目 | 維度 | 階層 |
|---|---|---|
| 1 | `ColorId` | 1 |
| 1 | `SizeId` | 2 |
| 1 | `StyleId` | 3 |

索引可讓您透過以下方式查詢現有庫存：

- `()`：按所有維度分組

    - T 恤、28

- `(ColorId)`：按 `ColorId` 分組

    - T 恤、黑色、10
    - T 恤、紅色、18

- `(ColorId, SizeId)`：按 `ColorId` 和 `SizeId` 的組合分組

    - T 恤、黑色、小、3
    - T 恤、黑色、大、7
    - T 恤、紅色、小、11
    - T 恤、紅色、大、7

- `(ColorId, SizeId, StyleId)`：按 `ColorId`、`SizeId` 和 `StyleId` 的組合分組

    - T 恤、黑色、小、寬、1
    - T 恤、黑色、小、正常、2
    - T 恤、黑色、大、寬、3
    - T 恤、黑色、大、正常、4
    - T 恤、紅色、小、寬、5
    - T 恤、紅色、小、正常、6
    - T 恤、紅色、正常、7

> [!NOTE]
> 分割區設定中定義的基本維度，不應在產品索引階層設定中定義。
> 
> 如果您必須只查詢所有維度組合彙總的庫存，可以設定包含基本維度 `Empty` 的單一索引。

## <a name="reservation-configuration-optional"></a><a name="reservation-configuration"></a>保留設定 (選用)

如要使用未確認保留功能，需設定保留。 設定包括由兩個基本部分：

- 未確認保留對應
- 未確認保留階層

### <a name="soft-reservation-mapping"></a>未確認保留對應

設定保留時，建議您瞭解現有庫存目前是否可供保留。 驗證會連結至代表實體測量組合之計算公式的計算測量。

設定從實體測量對應到計算測量，庫存能見度服務即可根據實體測量自動驗證保留可用性。

設定這類對應之前，必須在 Power Apps 的 **設定** 頁面中的 **資料來源**、**計算測量** 索引標籤定義實體測量、計算測量及其資料來源 (如本主題先前所述)。

若要定義未確認保留對應，請按照以下步驟操作。

1. 定義做為未確認保留測量的實體度量 (例如 `SoftReservOrdered`)。
1. 在 **設定** 頁面的 **計算測量** 索引標籤中，定義 *可供保留* (AFR) 計算測量，其中包含要對應到實體測量的 AFR 計算公式。 舉例來說，您可以設定 `AvailableToReserve` (可供保留) 以便對應到先前定義的 `SoftReservOrdered` 實體測量。 這樣一來，您即可找出庫存狀態為 `SoftReservOrdered` 的可供保留數量。 下表顯示 AFR 計算公式。

    | 計算類型 | 資料來源 | 實體測量 |
    |---|---|---|
    | 加法 | `fno` | `AvailPhysical` |
    | 加法 | `pos` | `Inbound` |
    | 減法 | `pos` | `Outbound` |
    | 減法 | `iv` | `SoftReservOrdered` |

    建議您設定計算測量，使其包含基於保留測量的實體測量。 這樣一來，保留測量數量就會影響計算測量數量。 因此，在本例中，資料來源 `iv` 的 `AvailableToReserve` 計算測量應將來自 `iv` 的 `SoftReservOrdered` 實體測量納為一個元件。

1. 開啟 **設定** 頁面。
1. 在 **未確認保留對應** 索引標籤中，設定從實體測量到計算測量的對應。 對於前述的範例，可使用以下設定將 `AvailableToReserve` 對應到先前定義的 `SoftReservOrdered` 物理測量。

    | 實體測量資料來源 | 實體測量 | 可用於保留資料來源 | 可用於保留計算測量 |
    |---|---|---|---|
    | `iv` | `SoftReservOrdered` | `iv` | `AvailableToReserve` |

    > [!NOTE]
    > 如果您無法編輯 **未確認保留對應** 索引標籤，您可能需開啟 **功能管理** 索引標籤中的 *OnHandReservation* 功能。

現在，當您在 `SoftReservOrdered` 中設定保留時，庫存能見度會自動找出 `AvailableToReserve` 以及其相關計算公式以進行保留驗證。

舉例來說，您在庫存能見度中有以下現有庫存。

```json
{
    "productId": "T-shirt",
    "dimensions": {
        "SiteId": "1",
        "LocationId": "11",
        "ColorId": "Red"
    },
    "quantities": {
        "iv": {
            "SoftReservOrdered": 90
        },
        "fno": {
            "availphysical": 70.0,
        },
        "pos": {
            "inbound": 50.0,
            "outbound": 20.0
        }
    }
}
```

在這種情況下，系統會套用以下計算：

`AvailableToReserve` = `fno.availphysical` + `pos.inbound` – `pos.outbound` – `iv.SoftReservOrdered`  
= 70 + 50 – 20 – 90  
= 10

因此，如果您嘗試在 `iv.SoftReservOrdered` 中設定保留，且數量小於或等於 `AvailableToReserve` (10)，即可保留庫存。

> [!NOTE]
> 在您呼叫保留 API 時，您可以透過指定要求本文中的 `ifCheckAvailForReserv` 布林值來控制保留驗證。 `True` 的值表示需要驗證，而 `False` 的值表示不需要驗證。 預設值為 `True`。

### <a name="soft-reservation-hierarchy"></a>未確認保留階層

保留階層會說明保留庫存時必須指定的維度序列。 保留階層的運作方式與現有查詢所用的產品索引階層相同。

保留階層與產品索引階層各自獨立運作。 您可以藉由這種獨立性實施類別管理，讓使用者將維度細分成詳細資料，以指定更精確的保留要求。 未確認保留階層應包含 `SiteId` 和 `LocationId`，這些元件會建構分割區設定。 當您進行保留時，必須為產品指定一個分割區。

未確認保留階層的範例如下。

| 基本維度 | 階層 |
|---|---|
| `SiteId` | 1 |
| `LocationId` | 2 |
| `ColorId` | 3 |
| `SizeId` | 4 |
| `StyleId` | 5 |

在此範例中，您可在以下維度序列中進行保留。 當您進行保留時，必須為產品指定一個分割區。 因此，您可以使用 `(SiteId, LocationId)` 這個基本階層。

- `(SiteId, LocationId)`
- `(SiteId, LocationId, ColorId)`
- `(SiteId, LocationId, ColorId, SizeId)`
- `(SiteId, LocationId, ColorId, SizeId, StyleId)`

有效維度序列中的每個維度都應該嚴格遵循保留階層。 舉例來說，階層序列 `(SiteId, LocationId, SizeId)` 無效，因為缺少 `ColorId`。

## <a name="complete-and-update-the-configuration"></a>完成並更新設定

完成設定後，您必須將所有變更提交至庫存能見度。 若要提交變更，請在 Power Apps 的 **設定** 頁面右上角選取 **更新設定**。

首次選取 **更新設定** 時，系統會要求您的認證。

- **用戶端識別碼**：您為庫存能見度建立的 Azure 應用程式識別碼。
- **租用戶識別碼**：您的 Azure 租用戶識別碼。
- **用戶端密碼**：您為庫存能見度建立的 Azure 應用程式密碼。

登入後，庫存能見度服務設定會更新。

> [!NOTE]
> 請務必先驗證資料來源名稱、實體測量和維度對應，再更新庫存能見度服務設定。 選取 **更新設定** 後即無法修改這些設定。

## <a name="default-configuration-sample"></a><a name="default-configuration-sample"></a>預設設定樣本

庫存能見度會在初始化階段設置預設設定，詳情請見此處。 您可以根據要求修改此設定。

### <a name="data-source-configuration"></a>資料來源設定

#### <a name="configuration-of-the-iv-data-source"></a>iv 資料來源設定

本節說明如何設定 `iv` 資料來源。

##### <a name="physical-measures-configured-for-the-iv-data-source"></a>為 iv 資料來源設定的實體測量

為 `iv` 資料來源設定的實體測量如下：

- `Ordered`
- `SoftReservPhysical`
- `SoftReservOrdered`
- `ReservOrdered`
- `ReservPhysical`

##### <a name="orderedtotal-calculated-measure"></a>OrderedTotal 計算測量

為 `iv` 資料來源設定 `OrderedTotal` 計算測量的做法如下表所示。

| 計算類型 | 資料來源 | 實體測量 |
|---|---|---|
| 加法 | `fno` | `Ordered` |
| 加法 | `fno` | `Arrived` |
| 加法 | `iv` | `Ordered` |

##### <a name="onhand-calculated-measure"></a>OnHand 計算測量

為 `iv` 資料來源設定 `OnHand` 計算測量的做法如下表所示。

| 計算類型 | 資料來源 | 實體測量 |
|---|---|---|
| 加法 | `fno` | `PhysicalInvent` |
| 加法 | `iom` | `OnHand` |
| 加法 | `erp` | `Unrestricted` |
| 加法 | `erp` | `QualityInspection` |
| 加法 | `pos` | `PosInbound` |
| 減法 | `pos` | `PosOutbound` |

##### <a name="reservedtotal-calculated-measure"></a>ReservedTotal 計算測量

為 `iv` 資料來源設定 `ReservedTotal` 計算測量的做法如下表所示。

| 計算類型 | 資料來源 | 實體測量 |
|---|---|---|
| 加法 | `fno` | `ReservPhysical` |
| 加法 | `fno` | `ReservOrdered` |
| 加法 | `iv` | `SoftReservPhysical` |
| 加法 | `iv` | `SoftReservOrdered` |
| 加法 | `iv` | `ReservPhysical` |
| 加法 | `iv` | `ReservOrdered` |

##### <a name="softreserved-calculated-measure"></a>SoftReserved 計算測量

為 `iv` 資料來源設定 `SoftReserved` 計算測量的做法如下表所示。

| 計算類型 | 資料來源 | 實體測量 |
|---|---|---|
| 加法 | `iv` | `SoftReservPhysical` |
| 加法 | `iv` | `SoftReservOrdered` |

##### <a name="hardreserved-calculated-measure"></a>HardReserved 計算測量

為 `iv` 資料來源設定 `HardReserved` 計算測量的做法如下表所示。

| 計算類型 | 資料來源 | 實體測量 |
|---|---|---|
| 加法 | `fno` | `ReservPhysical` |
| 加法 | `fno` | `ReservOrdered` |
| 加法 | `iv` | `ReservPhysical` |
| 加法 | `iv` | `ReservOrdered` |

##### <a name="openorder-calculated-measure"></a>OpenOrder 計算測量

為 `iv` 資料來源設定 `OpenOrder` 計算測量的做法如下表所示。

| 計算類型 | 資料來源 | 實體測量 |
|---|---|---|
| 加法 | `fno` | `OnOrder` |
| 加法 | `iom` | `OnOrder` |

##### <a name="onhandavailable-calculated-measure"></a>OnHandAvailable 計算測量

為 `iv` 資料來源設定 `OnHandAvailable` 計算測量的做法如下表所示。

| 計算類型 | 資料來源 | 實體測量 |
|---|---|---|
| 加法 | `fno` | `PhysicalInvent` |
| 加法 | `iom` | `OnHand` |
| 加法 | `erp` | `Unrestricted` |
| 加法 | `erp` | `QualityInspection` |
| 加法 | `pos` | `PosInbound` |
| 減法 | `fno` | `ReservPhysical` |
| 減法 | `iv` | `SoftReservPhysical` |
| 減法 | `pos` | `PosOutbound` |

##### <a name="availabletoreserve-calculated-measure"></a>AvailableToReserve 計算測量

為 `iv` 資料來源設定 `AvailableToReserve` 計算測量的做法如下表所示。

| 計算類型 | 資料來源 | 實體測量 |
|---|---|---|
| 加法 | `fno` | `PhysicalInvent` |
| 加法 | `iom` | `OnHand` |
| 加法 | `erp` | `Unrestricted` |
| 加法 | `erp` | `QualityInspection` |
| 加法 | `pos` | `PosInbound` |
| 加法 | `fno` | `Ordered` |
| 加法 | `fno` | `Arrived` |
| 加法 | `iv` | `Ordered` |
| 減法 | `fno` | `ReservPhysical` |
| 減法 | `fno` | `ReservOrdered` |
| 減法 | `iv` | `SoftReservPhysical` |
| 減法 | `iv` | `SoftReservOrdered` |
| 減法 | `iv` | `ReservPhysical` |
| 減法 | `iv` | `ReservOrdered` |
| 減法 | `pos` | `PosOutbound` |

##### <a name="inventorysupply-calculated-measure"></a>InventorySupply 計算測量

為 `iv` 資料來源設定 `InventorySupply` 計算測量的做法如下表所示。

| 計算類型 | 資料來源 | 實體測量 |
|---|---|---|
| 加法 | `fno` | `Ordered` |
| 加法 | `fno` | `Arrived` |
| 加法 | `iv` | `Ordered` |
| 加法 | `fno` | `PhysicalInvent` |
| 加法 | `iom` | `OnHand` |
| 加法 | `erp` | `Unrestricted` |
| 加法 | `erp` | `QualityInspection` |
| 加法 | `pos` | `PosInbound` |
| 減法 | `pos` | `PosOutbound` |

##### <a name="inventorydemand-calculated-measure"></a>InventoryDemand 計算測量

為 `iv` 資料來源設定 `InventoryDemand` 計算測量的做法如下表所示。

| 計算類型 | 資料來源 | 實體測量 |
|---|---|---|
| 加法 | `fno` | `OnOrder` |
| 加法 | `iom` | `OnOrder` |
| 加法 | `iv` | `SoftReservPhysical` |
| 加法 | `iv` | `SoftReservOrdered` |
| 加法 | `fno` | `ReservPhysical` |
| 加法 | `fno` | `ReservOrdered` |
| 加法 | `iv` | `ReservPhysical` |
| 加法 | `iv` | `ReservOrdered` |

#### <a name="configuration-of-the-fno-data-source"></a>fno 資料來源設定

本節說明如何設定 `fno` 資料來源。

##### <a name="dimension-mappings-for-the-fno-data-source"></a>fno 資料來源維度對應

下表列出 `fno` 資料來源設定的維度對應。

| 外部維度 | 基本維度 |
|---|---|
| `InventBatchId` | `BatchId` |
| `InventColorId` | `ColorId` |
| `InventLocationId` | `LocationId` |
| `InventSerialId` | `SerialId` |
| `InventSiteId` | `SiteId` |
| `InventSizeId` | `SizeId` |
| `InventStatusId` | `StatusId` |
| `InventStyleId` | `StyleId` |
| `LicensePlateId` | `LicensePlateId` |
| `WMSLocationId` | `WMSLocationId` |
| `WMSPalletId` | `WMSPalletId` |
| `ConfigId` | `ConfigId` |
| `InventVersionId` | `VersionId` |
| `InventDimension1` | `CustomDimension1` |
| `InventDimension2` | `CustomDimension2` |
| `InventDimension3` | `CustomDimension3` |
| `InventDimension4` | `CustomDimension4` |
| `InventDimension5` | `CustomDimension5` |
| `InventDimension6` | `CustomDimension6` |
| `InventDimension7` | `CustomDimension7` |
| `InventDimension8` | `CustomDimension8` |
| `InventDimension9` | `CustomDimension9` |
| `InventDimension10` | `CustomDimension10` |
| `InventDimension11` | `CustomDimension11` |
| `InventDimension12` | `CustomDimension12` |

##### <a name="physical-measures-configured-for-the-fno-data-source"></a>為 fno 資料來源設定的實體測量

為 `fno` 資料來源設定的實體測量如下：

- `Ordered`
- `Arrived`
- `AvailPhysical`
- `PhysicalInvent`
- `ReservPhysical`
- `ReservOrdered`
- `OnOrder`

#### <a name="configuration-of-the-pos-data-source"></a>pos 資料來源設定

本節說明如何設定 `pos` 資料來源。

##### <a name="physical-measures-for-the-pos-data-source"></a>為 pos 資料來源設定的實體測量

為 `pos` 資料來源設定的實體測量如下：

- `PosInbound`
- `PosOutbound`

##### <a name="availquantity-calculated-measure"></a>AvailQuantity 計算測量

為 `pos` 資料來源設定 `AvailQuantity` 計算測量的做法如下表所示。

| 計算類型 | 資料來源 | 實體測量 |
|---|---|---|
| 加法 | `fno` | `AvailPhysical` |
| 加法 | `pos` | `PosInbound` |
| 減法 | `pos` | `PosOutbound` |

#### <a name="configuration-of-the-iom-data-source"></a>iom 資料來源設定

為 `iom` (智慧型訂單管理) 資料來源設定的實體測量如下：

- `OnOrder`
- `OnHand`

#### <a name="configuration-of-the-erp-data-source"></a>erp 資料來源設定

為 `erp` (企業資源規劃) 資料來源設定的實體測量如下：

- `Unrestricted`
- `QualityInspection`

### <a name="partition-configuration"></a>分割區設定

預設分割區設定如下表所示。

| 基本維度 | 階層 |
|---|---|
| `SiteId` | 1 |
| `LocationId` | 2 |

### <a name="index-configuration"></a>索引設定

預設索引設定如下表所示。

| 設定數目 | 維度 | 階層 |
|---|---|---|
| 1 | `ColorId` | 1 |
| 1 | `SizeId` | 2 |
| 1 | `StyleId` | 3 |

### <a name="reservation-configuration"></a>保留設定

本節將說明預設保留設定。

#### <a name="reservation-mapping"></a>保留對應

預設保留對應如下表所示。

| 實體測量資料來源 | 實體測量 | 可用於保留資料來源 | 可用於保留計算測量 |
|---|---|---|---|
| `iv` | `SoftReservOrdered` | `iv` | `AvailableToReserve` |

#### <a name="reservation-hierarchy"></a>保留階層

預設保留階層如下表所示。

| 基本維度 | 階層 |
|---|---|
| `SiteId` | 1 |
| `LocationId` | 2 |
| `ColorId` | 3 |
| `SizeId` | 4 |
| `StyleId` | 5 |
| `BatchId` | 6 |
| `SerialId` | 7 |
| `StatusId` | 8 |
| `LicensePlateId` | 9 |
| `WMSLocationId` | 10 |
| `WMSPalletId` | 11 |
| `ConfigId` | 12 |
| `VersionId` | 13 |
| `CustomDimension1` | 14 |
| `CustomDimension2` | 15 |
| `CustomDimension3` | 16 |
| `CustomDimension4` | 17 |
| `CustomDimension5` | 18 |
| `CustomDimension6` | 19 |
| `CustomDimension7` | 20 |
| `CustomDimension8` | 21 |
| `CustomDimension9` | 22 |
| `CustomDimension10` | 23 |
| `CustomDimension11` | 24 |
| `CustomDimension12` | 25 |
| `ExtendedDimension1` | 26 |
| `ExtendedDimension2` | 27 |
| `ExtendedDimension3` | 28 |
| `ExtendedDimension4` | 29 |
| `ExtendedDimension5` | 30 |
| `ExtendedDimension6` | 31 |
| `ExtendedDimension7` | 32 |
| `ExtendedDimension8` | 33 |

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
