---
title: 倉庫流程的品質管理
description: 本主題提供倉庫流程的品質管理功能的相關資訊。 此功能可擴充品質管理能力，讓使用者透過進階倉庫管理將品項取樣控制整合到倉庫收貨流程中。
author: Henrikan
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2020-04-02
ms.dyn365.ops.version: 10.0.10
ms.openlocfilehash: d81441fcc8cb86927923e76bd1a4d16a141ddc75
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448467"
---
# <a name="quality-management-for-warehouse-processes"></a>倉庫流程的品質管理

[!include [banner](../includes/banner.md)]

_倉庫流程的品質管理_ 功能可讓您透過進階倉庫管理，將品項取樣控制整合到倉庫收貨流程中。 系統可以自動產生倉庫工作，以根據百分比或固定數量或每 *n* 個牌照，將庫存移動到品質控制位置。 品質檢驗訂單完成後，系統會根據品質結果自動產生工作，以將庫存移動到流程中的下一個位置。

_倉庫流程的品質管理_ 功能擴展了基本品質管理功能的能力。 此功能也提供選項，可視需要為傳送到品質控制位置的庫存建立品質檢驗訂單 (儘管品質檢驗訂單未必是必要品項)。 這樣，此功能就可提供以倉庫工作為依據的輕量化品質控制流程。

## <a name="turn-on-the-quality-management-for-warehouse-processes-feature"></a>開啟倉庫流程的品質管理功能

使用此功能之前，您必須先在系統中開啟。 管理員可利用[功能管理](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)設定檢查功能狀態，並開啟該功能。 在 **功能管理** 工作區，該功能會依以下方式列出：

- **模組：** *倉庫管理*
- **功能名稱：** *倉庫流程的品質管理*

## <a name="key-benefits"></a>重點優勢

_倉庫流程的品質管理_ 功能可以為接收程序自動產生工作，以將品質控制所需的庫存數量移動到品質控制位置。 如果收到的數量超過品質控制所需的數量 (根據品項取樣設定)，超過的數量會移動到位置指令設定中定義的入庫位置。 驗證品質檢驗訂單後，系統會根據驗證結果和位置指令設定，自動產生工作以將品質檢驗訂單的數量移動到新的入庫或退貨位置。 自動產生的工作只包含必須在品質控制中進出的數量，進而提供整合流程體驗。

> [!NOTE]
> 當 _倉庫流程的品質管理_ 功能開啟時，您仍可以使用手動流程。 手動流程中會使用庫存移動和按範本移動，以讓倉庫工作人員觸發建立倉庫工作，將庫存從品質控制位置移動到新位置。 您還可以設定入庫位置指令，將整個庫存從接收位置移動到品質控制位置，而無需考慮品項取樣設定。

## <a name="quality-management-and-the-quality-management-for-warehouse-processes-feature"></a>品質管理以及倉庫流程的品質管理功能

當 _倉庫流程的品質管理_ 功能開啟時，會變更金鑰倉庫管理和品質管理實體的設定。 下圖概述為倉庫流程啟用品質檢驗訂單的實體。 括號中的文字表示在 _倉庫管理流程的品質管理_ 功能開啟前實施品質管理所建議採取的行動。

![品質管理實體。](media/quality-management-entity-diagram.png "品質管理實體")

## <a name="enablers-the-quality-item-sampling-and-quality-order-work-order-types"></a>促成因素：品質品項取樣和品質檢驗訂單工單類型

_倉庫流程的品質管理_ 功能引進兩種啟用工作建立程序的工單類型：

- **品質品項取樣** – 此工單類型用於建立將已登記庫存移動到品質控制的工作。
- **品質檢驗訂單** – 此工單類型用於根據位置指令設定，建立將庫存從品質控制移動到新位置的工作。

### <a name="work-classes-location-directives-and-work-templates"></a>工作類別、位置指令和工作範本

系統會按位置指令、工作類別和工作範本使用 _品質品項取樣_ 和 _品質檢驗訂單_ 工單類型。

在系統自動產生倉庫工作以將庫存移動到品質控制之前，您必須按照以下步驟設定系統。

1. 為 _品質品項取樣_ 和 _品質檢驗訂單_ 工單類型建立不同的工作類別。 這樣一來，您就能確保可以根據兩種工單類型自動產生適當的工作，然後可以使用 Warehouse Management 行動應用程式執行該工作。
1. 為每個工單類型設定工作範本：

    - 設定使用 _品質品項取樣_ 工單類型的工作範本，以自動將已登記的庫存移動到品質控制位置。
    - 設定使用 _品質檢驗訂單_ 工單類型的工作範本，以在品質控制完成後將庫存移出品質控制位置。

1. 針對每種工單類型，設定可將庫存移動到正確品質控制位置的位置指令。 品質控制完成後，_品質檢驗訂單_ 工單類型的位置指令可確保選擇新的目的地位置，以便將庫存移出品質控制位置。
1. 設定相關的行動裝置選單品項以支援將收到的庫存移動到品質控制位置，以及將通過或未通過品質控制的庫存從品質控制位置移動到新位置。

有關說明如何完成此設定的逐步範例，請參閱本主題結尾的[範例案例](#example-scenario)。

## <a name="enable-a-warehouse-for-quality-management"></a>啟用倉庫的品質管理

為特定倉庫套用 _倉庫流程的品質管理_ 功能之前，您必須按照以下步驟使該功能可用於該倉庫。

1. 前往 **倉庫管理 \> 設定 \> 倉庫 \> 倉庫**。
1. 選擇要啟用品質管理的倉庫。
1. 在 **倉庫** FastTab，將 **為倉庫流程啟用品質檢驗訂單** 選項設定為 _是_。 (請注意，此選項只可針對使用倉庫管理流程的倉庫設定為 _是_。)

當 **為倉庫流程啟用品質檢驗訂單** 選項設定為 _是_ 時，品質關聯設定會控制 _倉庫流程的品質管理_ 功能是否實際套用至所選倉庫。 您隨時可以將選項設定變更為 _否_。 在這種情況下，無論品輛關聯設定為何，該功能都不會套用至倉庫。

## <a name="quality-control"></a>品質控制

_倉庫流程的品質管理_ 功能可控制品質關聯和品項取樣的幾個重要設定。

### <a name="quality-associations"></a>品質關聯

每個[品質關聯記錄](enable-quality-management.md)定義適用於所產生的品質檢驗訂單的測試集、可接受的品質等級 (AQL) 和取樣計劃。 請按照以下步驟設定品質關聯記錄。

1. 前往 **庫存管理 \> 設定 \> 品質控制 \> 品質關聯**。
1. 為您正在使用的品項或所有品項建立或選擇品質關聯項目。
1. 在 **條件** FastTab，將 **適用的倉庫類型** 欄位設定為以下值之一：

    - **僅針對倉庫流程的品質管理** – 啟動 _倉庫流程的品質管理_ 功能。 只有當參考類型為 *購買* 或 *生產* 時，您才可以選取這個值。
    - **所有** – 停用 _倉庫流程的品質管理_ 功能。 為所有參考類型選擇此值，除了 *購買* 和 *生產*。

> [!NOTE]
> 只有當來源文件明細使用進階倉庫管理流程，而且來源文件明細上的倉庫的 **為倉庫流程啟用品質檢驗訂單** 選項設定為 _是_ 時，_倉庫流程的品質管理_ 功能才會生效。

當每個品項完成登記 (或報告為完成) 時，系統會決定哪些品質關聯適用於該品項。

當 _倉庫流程的品質管理_ 開啟時，系統會以符合邏輯的方式將適用的倉庫類型插入到品質關聯搜尋階層的第四個搜尋群組中。 下表為搜尋階層的邏輯表示法。

| 搜尋群組 | 描述 |
|---|---|
| 群組 1 | 針對每個品質關聯，檢查品項的 **參考類型**、**事件類型**，以及 **執行比對** 值。 如果有與來源文件明細相符的項目，則移動到群組 2。 |
| 群組 2 | 針對每個品質關聯，檢查品項的 **品項代碼** 值 (_資料表_、_群組_ 或 _全部_)。 _資料表_ 比 _群組_ 更具體，而 _群組_ 則比 _全部_ 更具體。 如果有與 _資料表_ (特定品項) 符合的項目，則移動到群組 3。 如果沒有與 _資料表_ 相符的項目，則搜尋與 _群組_ 相符的項目。 若沒有與 _群組_ 相符的項目，則會套用 _全部_。 如果有相符項目，則移動至群組 3。 |
| 群組 3 | 針對每個品質關聯，檢查品項的 **帳戶代碼** 和 **資源代碼** 值。 所套用的邏輯會類似套用至 **品項代碼** 值的邏輯。 |
| 群組 4 | 針對每個品質關聯，檢查品項的 **適用倉庫類型** 值 (_僅針對倉庫流程的品質管理_ 或 _全部_)。 如果來源文件上的倉庫的 **為倉庫流程啟用品質檢驗訂單** 選項設定為 _是_，而且來源文件明細上的品項設定為 _使用倉庫管理流程_，則包含與 _僅針對倉庫流程的品質管理_ 相符項目的關聯以及包含與 _全部_ 相符項目的關聯將會並行適用 (如果兩者皆存在)。 如果來源文件上的倉庫的 **為倉庫流程啟用品質檢驗訂單** 選項設定為 _否_，而且來源文件明細上的品項設定為 _使用倉庫管理流程_，則僅適用品質管理。 |

例如，您定義了一個倉庫，其中 **為倉庫流程啟用品質檢驗訂單** 選項設定為 _是_，並且您有兩個為 *購買* 參考類型定義的品質關聯：一個適用於所有品項，另一個適用於 *登記* 事件類型。 兩個品質關聯之間的唯一區別是 **適用的倉庫類型** 值：其中一個品質關聯設定為 _全部_，另一個則設定為 _僅針對倉庫流程的品質管理_。 在這種情況下，兩個品質關聯都是同樣具體的，而且皆適用。

品質關聯的 **測試群組** 欄位值也是一個因素。 此欄位定義必須採用的測試程序。 如果兩個關聯的 **測試群組** 值相同，則系統只會建立一個品質檢驗訂單，建立對象為 **適用的倉庫類型** 值為 _僅針對倉庫流程的品質管理_ 的品質關聯。 如果兩個關聯的 **測試群組** 值不同，則系統會建立兩個品質檢驗訂單。 系統會針對 **適用的倉庫類型** 值為 _僅針對倉庫流程的品質管理_ 的品質關聯建立第一個品質檢驗訂單。 系統會針對 **適用的倉庫類型** 值為 _全部_ 的品質關聯建立第二個品質檢驗訂單。

> [!NOTE]
> 當群組 1 和 2 的品質關聯條件相同，而且測試群組相同時，_僅針對倉庫流程的品質管理_ 值會認為比 _全部_ 更具體。 只有當測試群組不同時，系統才會建立兩個品質檢驗訂單。

#### <a name="reference-types"></a>參考類型

當 **參考類型** 值為 _購買_，而且 **適用的倉庫類型** 值為 _僅針對倉庫流程的品質管理_ 時，則 **程序** FastTab 上的 **事件類型** 欄位必須設定為 _登記_。 如果您使用 _倉庫流程的品質管理_ 功能，則 _登記_ 是 _購買_ 參考類型唯一支援的事件類型。

#### <a name="quality-processing-policy"></a>品質處理原則

_倉庫流程的品質管理_ 功能只能根據品項取樣來建立工作。 因此，該功能可以進行輕量化流程。 建立工作的庫存取決於與品質關聯有關的品項抽樣。 採用輕量化流程時，工作人員將數量放入品質控制位置後，如果需要品質檢驗訂單，品質部門可以手動建立品質檢驗訂單。

**品質檢驗訂單流程** FastTab 的 **品質處理原則** 欄位可以控制當建立工作以將品項移動到品質控制位置時，是否也會建立品質檢驗訂單。 此欄位可以設定為 _建立品質檢驗訂單_ 或 _只建立工作_。 預設值為 _建立品質檢驗訂單_。

> [!NOTE]
> 無論您是透過手動或自動方式建立品質檢驗訂單，只要品質檢驗訂單標記為已驗證時，系統都會自動產生工作以將品項移出品質控制位置。

品質檢驗訂單工作的建立與品質關聯設定無關。 如果有 **工單類型** 的值為 *品質檢驗訂單* 的工作範本，而且該工作範本符合查詢準則，品質檢驗訂單的驗證就會觸發品質檢驗訂單工作的建立。

#### <a name="referenced-item-sampling"></a>參考品項取樣

每個品質關聯都必須參考一個品項取樣。 品項取樣可以定義系統要傳送以進行品質控制的數量。 您可以設定品項取樣，讓其只套用到 **適用的倉庫類型** 值為 _僅針對倉庫流程的品質管理_ 的品質關聯。 如果品項取樣的 **取樣範圍** 值為 _負載_ 或 _運送_，或者 **數量規格** 值為 _完整牌照_，則只有 **適用的倉庫類型** 值為 _僅針對倉庫流程的品質管理_ 的品質關聯能夠參考該品項取樣。

如果您將使用 _僅針對倉庫流程的品質管理_ 適用倉庫類型的品項取樣，並且嘗試透過不使用 _倉庫流程的品質管理_ 功能的品質關聯參考該品項取樣，您就會收到錯誤訊息。

> [!NOTE]
> **適用的倉庫類型** 欄位設定為 _僅針對倉庫流程的品質管理_ 的品質關聯不支援使用完整封鎖的品項取樣。

### <a name="item-sampling"></a>品項取樣

品項取樣可以控制系統傳送品項以進行品質控制的頻率。 _倉庫流程的品質管理_ 功能引進 _品項取樣範圍_ 的概念。 系統在評估是否以及如何建立品質檢驗訂單和/或品質品項取樣工作及品質檢驗訂單工作時，會使用品項取樣範圍。

若要設定品項取樣，請前往 **庫存管理 \> 設定 \> 品質控制 \> 品項取樣**，並將 **取樣範圍** 欄位設定為以下值之一：

- **訂單** – 使用來源文件明細作為根據，以評估是否以及如何建立品質檢驗訂單和/或品質品項取樣工作及品質檢驗訂單工作。 此值為預設值，若選取這個值，系統的運作方式會與 _倉庫流程的品質管理_ 功能未開啟時相同。
- **負載** – 使用負載作為根據，以評估是否以及如何建立品質檢驗訂單和/或工作。 這個值只有在 _倉庫流程的品質管理_ 功能開啟時才提供使用。
- **裝運** – 使用裝運作為根據，以評估是否以及如何建立品質檢驗訂單和/或工作。 這個值只有在 _倉庫流程的品質管理_ 功能開啟時才提供使用。

> [!NOTE]
> 當 **取樣範圍** 欄位設定為 *負載* 或 *裝運* 時，系統會使用負載實體和裝運實體 (如果可用)。 如果上述實體不可用，系統就會使用訂單實體。

_倉庫流程的品質管理_ 功能也為 **數量規格** 欄位提供 *完整牌照* 值。 此值支援以牌照作為根據來建立品質檢驗訂單工作和品質品項取樣工作。 選擇此值時，會發生以下變更：

- **程序** FastTab 上的 **按品項分解計數** 選項和 **每 n 個牌照** 欄位變為可用。
- **取樣數量** FastTab 上的 **值** 欄位變得不可用。
- **每更新數量**、**位置** 和 **牌照** 選項會全部設定為 *是*，且無法更改設定。

**按品項分解計數** 選項控制系統是按品項評估牌照，還是按取樣範圍中的所有品項評估牌照。 系統會將產品變體視為同一個品項。 此選項也控制是否為每個品項重設牌照計數。

**每 n 個牌照** 欄位的值可以控制根據已登記品項數量來建立品質檢驗訂單的頻率。 例如，如果值設定為 *3*，系統就會從第一個品項算起，將每第三個品項傳送到品質控制。 值必須大於 0 (零)。

當工作人員使用 Warehouse Management 行動裝置應用程式接收品項時，系統會驗證每個收到的品項是否已設定品質關聯。 如果已設定品質關聯，則系統會使用為該品質關聯設定的品項取樣記錄，以決定如何建立品質檢驗訂單、品質品項取樣工作和訂購單工作。

> [!NOTE]
> 在 Web 用戶端中完成收貨登記時 (透過使用小型登記頁面或訂購單明細的品項到貨日記帳)，無論設定為何，系統都不會建立品質品項取樣工作或訂購單工作。 相反地，對於符合品質關聯的品項，參考的品項取樣只會用來控制品質檢驗訂單的建立。

## <a name="examples-of-automatic-generation-of-quality-orders"></a>自動產生品質檢驗訂單的範例

以下範例說明當 **適用的倉庫類型** 欄位設定為 _僅針對倉庫流程的品質管理_ 時，品質關聯和相關品項取樣的設定如何影響品質檢驗訂單的產生。

當 **數量規格** 值為 _完整牌照_ 時，**每 n 個牌照** 欄位會控制要為哪些牌照建立品質品項取樣工作。 第一個牌照一律會移動到品質控制，接著此欄位的值會指定該牌照之後的每 *n* 個牌照也應移至品質控制。

以下範例的 **參考類型** 值為 _購買_，**事件類型** 值為 *登記*。

| 取樣範圍 | 數量規格 | 每更新數量 | 每個儲存尺寸 | 按品項分解計數 | 每 n 個牌照 | 結果 |
|---|---|---|---|---|---|---|
| 訂單 | 完整牌照 | 是 _(鎖定/不可編輯)_ | <p>位置：是</p><p>牌照：是 _(鎖定/不可編輯)_</p> | 否 | 3 | <p>**訂單明細數量：100 EA**</p><ol><li>在 Warehouse Management 行動裝置應用程式中登記 20 EA，LP1 的收貨<p>20 EA 的品質品項取樣工作</p><p>20 EA 的品質檢驗訂單 1</p></li><li>在 Warehouse Management 行動裝置應用程式中登記 20 EA，LP2 的收貨<p>20 EA 的訂購單工作 (入庫)</p></li><li>在 Warehouse Management 行動裝置應用程式中登記 20 EA，LP3 的收貨<p>20 EA 的訂購單工作 (入庫)</p></li><li>在 Warehouse Management 行動裝置應用程式中登記 20 EA，LP4 的收貨<p>20 EA 的品質品項取樣工作</p></li><li>在 Warehouse Management 行動裝置應用程式中登記 20 EA，LP5 的收貨<p>20 EA 的訂購單工作 (入庫)</p></li></ol> |
| 訂單 | 固定數量 = 1 | 是 | <p>位置：是</p><p>牌照：是</p> | 否 | 不適用 | <p>**訂單明細數量：100**</p><ol><li>在 Warehouse Management 行動裝置應用程式中登記 20 EA，LP1 的收貨<p>1 EA 的品質品項取樣工作</p><p>1 EA 的品質檢驗訂單 1</p><p>19 EA 的訂購單工作 (入庫)</p></li><li>在 Warehouse Management 行動裝置應用程式中登記 20 EA，LP2 的收貨<p>1 EA 的品質品項取樣工作</p><p>1 EA 的品質檢驗訂單 1</p><p>19 的訂購單工作 (入庫)</p></li><li>在 Warehouse Management 行動裝置應用程式中登記 20 EA，LP3 的收貨<p>1 EA 的品質品項取樣工作</p><p>1 EA 的品質檢驗訂單 1</p><p>19 EA 的訂購單工作 (入庫)</p></li><li>在 Warehouse Management 行動裝置應用程式中登記 20 EA，LP4 的收貨<p>1 EA 的品質品項取樣工作</p><p>1 EA 的品質檢驗訂單 1</p><p>19 EA 的訂購單工作 (入庫)</p></li><li>在 Warehouse Management 行動裝置應用程式中登記 20 EA，LP5 的收貨<p>1 EA 的品質品項取樣工作</p><p>1 EA 的品質檢驗訂單 1</p><p>19 EA 的訂購單工作 (入庫)</p></li></ol> |
| 訂單 | 百分比 = 10 | 否 | <p>位置：否</p><p>牌照：否</p> | 否 | 不適用 | <p>**訂單明細數量：100 EA**</p><ol><li>在 Warehouse Management 行動裝置應用程式中登記 50 EA，LP1 的收貨<p>10 EA 的品質品項取樣工作</p><p>1 EA 的品質檢驗訂單 10</p><p>40 EA 的訂購單工作 (入庫)</p></li><li>在 Warehouse Management 行動裝置應用程式中登記 50 EA，LP2 的收貨<p>50 EA 的訂購單工作 (入庫)</p></li></ol> |
| 載入 | 百分比 = 5 | 是 _(鎖定/不可編輯)_ | <p>位置：否</p><p>牌照：否</p> | 否 | 不適用 | <p>**訂單明細數量：500 EA**</p><p>**兩個負載：第一個負載 200 EA，第二個負載 300 EA**</p><ol><li>在 Warehouse Management 行動裝置應用程式中登記 100 EA 的第一個負載<p>5 EA 的品質品項取樣工作</p><p>5 EA 的品質檢驗訂單 1</p><p>95 EA 的訂購單工作 (入庫)</p></li><li>在 Warehouse Management 行動裝置應用程式中登記 100 EA 的第一個負載<p>5 EA 的品質品項取樣工作</p><p>5 EA 的品質檢驗訂單 1</p><p>95 EA 的訂購單工作 (入庫)</p></li><li>在 Warehouse Management 行動裝置應用程式中登記 300 EA 的第二個負載<p>15 EA 的品質品項取樣工作</p><p>15 EA 的品質檢驗訂單 1</p><p>285 EA 的訂購單工作 (入庫)</p></li></ol> |
| 訂單 | 百分比 = 10 | 是 | <p>位置：是</p><p>牌照：是</p> | 否 | 不適用 | <p>**訂單明細數量：100**</p><ol><li>在 Warehouse Management 行動裝置應用程式中登記 50 EA，LP1 的收貨<p>5 EA 的品質品項取樣工作</p><p>5 EA 的品質檢驗訂單 1</p><p>45 EA 的訂購單工作 (入庫)</p></li><li>在 Warehouse Management 行動裝置應用程式中登記 50 EA，LP2 的收貨<p>5 EA 的品質品項取樣工作</p><p>5 EA 的品質檢驗訂單 1</p><p>45 的訂購單工作 (入庫)</p></li></ol> |
| 負載 | 完整牌照 | 是 _(鎖定/不可編輯)_ | <p>位置：是</p><p>牌照：是 _(鎖定/不可編輯)_</p> | 否 | 3 | <p>**兩個品項：**</p><ul><li>**品項 A 的訂單明細數量：120 EA (4 個棧板)**</li><li>**品項 B 的訂單明細數量：90 EA (3 個棧板)**</li></ul><p>**一個負載，每個訂單明細有兩個負載明細**</p><ol><li>在 Warehouse Management 行動裝置應用程式中登記品項 A，30 EA，LP1 的收貨<p>30 EA 的品質品項取樣工作</p><p>1 EA 的品質檢驗訂單 30</p></li><li>在 Warehouse Management 行動裝置應用程式中登記品項 A，30 EA，LP2 的收貨<p>30 EA 的訂購單工作 (入庫)</p></li><li>在 Warehouse Management 行動裝置應用程式中登記品項 A，30 EA，LP3 的收貨<p>30 EA 的訂購單工作 (入庫)</p></li><li>在 Warehouse Management 行動裝置應用程式中登記品項 A，30 EA，LP4 的收貨<p>30 EA 的品質品項取樣工作</p><p>1 EA 的品質檢驗訂單 30</p></li><li>在 Warehouse Management 行動裝置應用程式中登記品項 B，30 EA，LP5 的收貨<p>30 EA 的訂購單工作 (入庫)</p></li><li>在 Warehouse Management 行動裝置應用程式中登記品項 B，30 EA，LP6 的收貨<p>30 EA 的訂購單工作 (入庫)</p></li><li>在 Warehouse Management 行動裝置應用程式中登記品項 A，30 EA，LP7 的收貨<p>30 EA 的品質品項取樣工作</p><p>1 EA 的品質檢驗訂單 30</p></li></ol> |
| 負載 | 完整牌照 | 是 _(鎖定/不可編輯)_ | <p>位置：是</p><p>牌照：是 _(鎖定/不可編輯)_</p> | 是 | 3 | <p>**兩個品項：**</p><ul><li>**品項 A 的訂單明細數量：120 EA (4 個棧板)**</li><li>**品項 B 的訂單明細數量：90 EA (3 個棧板)**</li></ul><p>**一個負載，每個訂單明細有兩個負載明細**</p><ol><li>在 Warehouse Management 行動裝置應用程式中登記品項 A，30 EA，LP1 的收貨<p>30 EA 的品質品項取樣工作</p><p>1 EA 的品質檢驗訂單 30</p></li><li>在 Warehouse Management 行動裝置應用程式中登記品項 A，30 EA，LP2 的收貨<p>30 EA 的訂購單工作 (入庫)</p></li><li>在 Warehouse Management 行動裝置應用程式中登記品項 A，30 EA，LP3 的收貨<p>30 EA 的訂購單工作 (入庫)</p></li><li>在 Warehouse Management 行動裝置應用程式中登記品項 A，30 EA，LP4 的收貨<p>30 EA 的品質品項取樣工作</p><p>1 EA 的品質檢驗訂單 30</p></li><li>在 Warehouse Management 行動裝置應用程式中登記品項 B，30 EA，LP5 的收貨<p>30 EA 的品質品項取樣工作</p><p>1 EA 的品質檢驗訂單 30</p></li><li>在 Warehouse Management 行動裝置應用程式中登記品項 B，30 EA，LP6 的收貨<p>30 EA 的訂購單工作 (入庫)</p></li><li>在 Warehouse Management 行動裝置應用程式中登記品項 A，30 EA，LP7 的收貨<p>30 EA 的訂購單工作 (入庫)</p></li></ol> |
| 載入 | 百分比 = 10 | 是 _(鎖定/不可編輯)_ | <p>位置：否</p><p>牌照：否</p> | 否 | 不適用 | <p>**訂單明細數量：100 EA**</p><p>**未建立負載。已套用訂單範圍。**</p><ol><li>在 Warehouse Management 行動裝置應用程式中登記 50 EA，LP1 的收貨<p>5 EA 的品質品項取樣工作</p><p>5 EA 的品質檢驗訂單 1</p><p>45 EA 的訂購單工作 (入庫)</p></li><li>在 Warehouse Management 行動裝置應用程式中登記 50 EA，LP2 的收貨<p>5 EA 的品質品項取樣工作</p><p>5 EA 的品質檢驗訂單 1</p><p>45 EA 的訂購單工作 (入庫)</p></li></ol> |

當工作人員驗證上表中顯示的其中一項品質檢驗訂單時，系統會自動產生品質檢驗訂單工作，以將庫存從品質控制位置移動到在位置指令中為 _品質檢驗訂單_ 工單類型定義的位置。 您可以為此目的設定任何位置，例如退貨或儲存位置，實際取決於品質檢驗訂單的測試結果。 有關此設定的範例，請參閱本主題結尾的[範例案例](#example-scenario)。

您可以重新開啟已驗證的品質檢驗訂單，前提是與從品質控制位置移動庫存相關的品質檢驗訂單工作的 **工作狀態** 值不是 *已關閉* 或 *進行中*。

## <a name="process-insights-when-multiple-quality-associations-coexist"></a>當多種品質關聯共存時處理深入解析

可以為同一個來源文件明細定義和套用多個品質關聯，並且可針對其中的部分關聯，將 **適用的倉庫類型** 欄位設定為 _僅針對倉庫流程的品質管理_，並將其他關連的該欄位設定為 _全部_。

在下列範例中，**參考類型** 值為 _購買_。

1. 第一個品質關聯的建立方式如下：

    - **適用的倉庫類型：** *僅針對倉庫流程的品質管理*
    - **品項代碼：** *A0001*
    - **帳戶代碼：** *所有*
    - **測試群組：** *機櫃*
    - **品項取樣：** *5 個*

1. 第二個品質關聯的建立方式如下：

    - **適用的倉庫類型：** *全部*
    - **品項代碼：** *全部*
    - **帳戶代碼：** *所有*
    - **測試群組：** *機櫃*
    - **品項取樣：** *1 個*

1. 第三個品質關聯的建立方式如下：

    - **適用的倉庫類型：** *僅針對倉庫流程的品質管理*
    - **品項代碼：** *全部*
    - **帳戶代碼：** *104*
    - **測試群組：** *阻抗*
    - **項目取樣：** *每隔一個牌照* (此設定表示收到的第一、第三、第五個等牌照將建立品質訂單。)

1. 第四個品質關聯的建立方式如下：

    - **適用的倉庫類型：** *全部*
    - **品項代碼：** *全部*
    - **帳戶代碼：** *所有*
    - **測試群組：** *阻抗*
    - **品項取樣：** *5 個*

1. 第五個品質關聯的建立方式如下：

    - **適用的倉庫類型：** *全部*
    - **品項代碼：** *全部*
    - **帳戶代碼：** *所有*
    - **測試群組：** *圓錐體*
    - **品項取樣：** *10%*

現在已為供應商 104 建立數量為 10 的品項 A0001 的訂購單。 然後，已使用 Warehouse Management 行動應用程式在一個牌照上登記已收到數量為 10 的訂購單。 結果如下：

- 第一個品質關聯中有一個品質檢驗訂單用於 *機櫃* 測試群組。 數量為 5。 第二個品質關聯沒有品質檢驗訂單，因為第一個品質關聯的條件相對於 *機櫃* 測試群組更為具體。
- 第三個品質關聯中有一個品質檢驗訂單用於 *阻抗* 測試群組。 數量為 10。 第四個品質關聯沒有品質檢驗訂單，因為第一個品質關聯的條件相對於 *阻抗* 測試群組更為具體。
- 第五個品質關聯中有一個品質檢驗訂單用於 *圓錐體* 測試群組。 數量為 1。

系統為三個品質關聯各別創建一個品質檢驗訂單時，也建立了品質品取樣工作。 登記數量只有 10 個。 但是，由於品項取樣設定，為 *僅針對倉庫流程的品質管理* 適用倉庫類型建立的品質檢驗訂單總數是 16 個，數量超過實際登記的 10 個。 因此，不會為所有品質檢驗訂單 (16 個) 建立工作，因為只有 10 個品質檢驗訂單實際可以移動到品質控制位置。 品質品項取樣工作建立的優先順序會遵循品質檢驗訂單的建立順序：

- **第一個品質檢驗訂單 (數量 = 5)：** 為 5 個建立品質品項取樣工作。 數量 5 個 (10 – 5) 現在留作後續建立品質品項取樣工作。
- **第二個品質檢驗訂單 (數量 = 10)：** 為 5 個建立品質品項取樣工作。 數量 0 個 (零) 現在留作後續建立品質品項取樣工作。
- **第三個品質檢驗訂單 (數量 = 1)：** 沒有建立任何品質品項取樣工作。

作為建立品質檢驗訂單流程的一部分，系統會建立數量為 10 的庫存封鎖。 三個品質檢驗訂單會各自參考此庫存封鎖。 品質檢驗訂單數量的總和為 16。

驗證品質檢驗訂單後，系統會嘗試為每個通過驗證的品質檢驗訂單建立品質檢驗訂單工作。 由於品質檢驗訂單數量的總和超過實際封鎖因而可用於建立工作的數量，所以系統無法為全部數量的品質檢驗訂單建立品質檢驗訂單工作，如此處所示。 (此範例延續上一個範例。)

1. **驗證已建立的第二個品質檢驗訂單 (數量 = 10)。系統會建立數量為 4 的品質檢驗訂單。**

    品質檢驗訂單工作的建立是由庫存封鎖數量的變更所觸發。 因品質檢驗訂單的總和是 16，所以數量為 10 的驗證會導致要驗證的剩餘品質檢驗訂單數量等於 6。 庫存封鎖數量從 10 減少到 6。 減少的數量 4 分配給品質檢驗訂單工作建立。

2. **驗證已建立的第一個品質檢驗訂單 (數量 = 5)。系統會建立數量為 5 的品質檢驗訂單。**

    品質檢驗訂單工作的建立是由庫存封鎖數量的變更所觸發。 因品質檢驗訂單的總和是 6，所以數量為 5 的驗證會導致要驗證的剩餘品質檢驗訂單數量等於 1。 庫存封鎖數量從 6 減少到 1。 減少的數量 5 分配給品質檢驗訂單工作建立。

3. **驗證已建立的第三個品質檢驗訂單 (數量 = 1)。系統會建立數量為 1 的品質檢驗訂單。**

    品質檢驗訂單工作的建立是由庫存封鎖數量的變更所觸發。 因品質檢驗訂單的總和是 1，所以數量為 1 的驗證會導致要驗證的剩餘品質檢驗訂單數量等於 0 (零)。 系統會移除庫存封鎖 (即庫存封鎖數量從 1 減少到 0)。 減少的數量 1 分配給品質檢驗訂單工作建立。

> [!NOTE]
> 品質檢驗訂單工作的建立取決於一或多個品質檢驗訂單參考的庫存封鎖數量。 如果品質檢驗訂單數量的總和超過參考的庫存封鎖數量，則品質檢驗訂單在其中驗證的訂單會決定品質檢驗訂單工作的建立。

## <a name="canceling-quality-item-sampling-work"></a>取消品質品項取樣工作

您可以取消為品質品項取樣建立的工作。 若要控管取消此工作時發生的情況，請按照下列步驟操作。

1. 前往 **倉庫管理 \> 設定 \> 倉庫管理參數**。
1. 在 **一般** 索引標籤，在 **工作** FastTab 上，將 **取消工作時註銷收據** 選項設定為以下任意值：

    - **是** – 取消品質品項取樣工作時，系統會刪除關聯品質檢驗訂單，並註銷庫存。
    - **否** – 取消品質品項取樣工作時，系統不會刪除關聯品質檢驗訂單，且不會註銷庫存。

## <a name="cross-docking"></a>直接轉運

您可以有一個能建立品項取樣工作的品質關聯設定。 但是，如果直接轉運與建立品質品項取樣工作的品質關聯並行存在，且若有足夠的數量來滿足直接轉運，則系統只會建立品項取樣工作。 如果收貨倉庫的 **為倉庫流程啟用品質檢驗訂單** 選項設定為 _是_，且 **適用的倉庫類型** 欄位設定為 _僅針對倉庫流程的品質管理_，品質品項取樣工作的建立會優先於直接轉運工作的建立。 如果數量超過直接轉運的要求，系統仍然只建立品項取樣工作。

## <a name="destructive-testing"></a>破壞性測試

您可以定義執行破壞性測試的測試群組。 在破壞性測試的情況下，假設無論測試結果為何，受測數量的品項都將遭到破壞 (這是測試的一部分)。 _倉庫流程的品質管理_ 功能支援破壞性測試的方式，類似於未開啟該功能時品質管理支援破壞性測試的方式。 在驗證品質檢驗訂單之前，品質控制者必須為遭到銷毀的數量指定揀貨位置。 您可以在品質檢驗訂單頁面上登記揀貨，方法是在在動作窗格上選取 **庫存 \> 揀貨**。 為品質檢驗訂單數量登記揀貨後，即可完成驗證。

## <a name="example-scenario"></a>範例案例

### <a name="prepare-the-scenario"></a>準備案例

若要演練這個案例，您必須按照下列方法準備系統：

- 確保系統已安裝示範資料，然後選擇 **USMF** 法律實體。
- 在 [功能管理](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)中開啟 _倉庫流程的品質管理_ 功能。
- 按照以下步驟，將倉庫 51 設定為使用 _倉庫流程的品質管理_ 功能：

    1. 前往 **倉庫管理 \> 設定 \> 倉庫 \> 倉庫**。
    1. 選擇倉庫 51。
    1. 在 **倉庫** FastTab，將 **為倉庫流程啟用品質檢驗訂單** 選項設定為 *是*。

### <a name="quality-in-setup--move-to-the-quality-control-location"></a>品質輸入設定 – 移動到品質控制位置

您現在必須準備基本設定，以讓您的系統能針對倉庫 51 支援 _倉庫流程的品質管理_ 功能。 (示範資料定義名稱為 *QMS* 的品質管理位置。 該位置在此案例中多次被參考。) 您將會準備以下元素，如本節各小節中所述：

- 工作類別
- 工作範本
- 位置指令
- 品項取樣
- 品質關聯
- 行動裝置功能表項目

#### <a name="work-class-for-quality-in"></a>品質輸入工作類別

1. 前往 **倉庫管理 \> 設定 \> 工作 \> 工作類別**。
1. 建立一個工作類別，並設定以下值：

    - **工作類別識別碼：** _QualityIn_
    - **說明：** _品質品項取樣_
    - **工單類型：** _品質品項取樣_

#### <a name="work-template"></a>工作範本

1. 前往 **倉庫管理 \> 設定 \> 工作 \> 工作範本**。
1. 將 **工單類型** 欄位設定為 _品質品項取樣_。
1. 建立一個工作範本，並設定以下值：

    - **工作範本：** _51 品質_
    - **工作範本說明：** _51 品質_

1. 在工作範本中新增明細，並設定以下值：

    - **工作類型：** _揀貨_
    - **工作類別識別碼：** _QualityIn_

1. 在工作範本中新增第二個明細，並設定以下值：

    - **工作類型：** _放置_
    - **工作類別識別碼：** _QualityIn_

#### <a name="location-directive"></a>位置指令

1. 前往 **倉庫管理 \> 設定 \> 位置指令**。
1. 將 **工單類型** 欄位設定為 _品質品項取樣_。
1. 建立位置指令，並為其設定以下值：

    - **名稱：** _51 終止品質_
    - **工作類型：** _放置_
    - **地點：** 5
    - **倉庫：** _51_

1. 在位置指令中新增明細，並設定以下值：

    - **起始數量：** _1_
    - **終止數量：** _1000000_

1. 建立位置指令動作，並為其設定以下值：

    - **名稱：** _品質_

1. 針對新的位置指令動作，選擇 **編輯查詢**，並指定具有以下值的 **範圍** 記錄：

    - **資料表：** *位置*
    - **欄位：** _位置設定檔識別碼_
    - **標準：** *QMS*

1. 選擇 **確定** 以儲存查詢，並儲存新的位置指令。

接下來，您必須針對倉庫 51 變更現有訂購單位置指令的順序。 示範資料包括兩個位置指令，兩者的 **工單類型** 值為 _購買_：一個名稱是 _51 QMS_，另一個命名為 _51 直接訂購單_。 為確保 *倉庫流程的品質管理* 功能套用至倉庫 51，請務必確認系統並未套用 _51 QMS_ 位置指令。 但是，您可以更改位置指令順序，而不需刪除該位置指令 (因為您將來可能會想使用該位置指令)。

1. 前往 **倉庫管理 \> 設定 \> 位置指令**。
1. 將 **工單類型** 欄位設定為 _訂購單_。
1. 在順序清單中，為 _51 直接訂購單_ 位置指令選擇序號 5。
1. 將所選的順序向上移動到序號 4。
1. 驗證 _51 QMS_ 位置指令的序號現在至少為 5。

#### <a name="item-sampling"></a>品項取樣

_倉庫流程的品質管理_ 功能新增一些新的品項取樣功能。 **取樣範圍** 值現在可以是 _命令_、_運送_ 或 _負載_，而且 **採樣數量** 值現在可以是 _完整牌照_。

1. 前往 **庫存管理 \> 設定 \> 品質控制 \> 品項取樣**。
1. 建立品項取樣記錄，並設定以下值：

    - **品項取樣：** _第三個 LP_
    - **說明：** _每三個牌照_
    - **取樣範圍：** _順序_

1. 在 **採樣數量** FastTab，將 **數量規格** 欄位設定為 _完整牌照_。
1. 在 **程序** FastTab，將 **每 n 個牌照** 欄位設定為 _3_。
1. 在 **每個儲存維度** 區段，同時啟用 **倉庫** 和 **庫存狀態**。

#### <a name="quality-associations"></a>品質關聯

建立將使用新品項取樣的品質關聯。

1. 前往 **庫存管理 \> 設定 \> 品質控制 \> 品質關聯**。
1. 建立品質關聯記錄，並設定以下值：

    - **參考類型：** _購買_
    - **品項代碼：** _資料表_
    - **品項：** _M9201_
    - **站點：** _5_

1. 在 **程序** FastTab，將 **事件類型** 欄位設定為 *登記*。
1. 在 **條件** FastTab，將 **適用的倉庫類型** 欄位設定為 *僅針對倉庫流程的品質管理*。
1. 在 **品質檢驗訂單流程** 快速選項卡，將 **品質處理原則** 欄位設定為 _建立品質檢驗訂單_。
1. 在 **規格** FastTab，以右鍵按一下 **測試群組** 欄位，然後選擇 **檢視詳細資料** 以開啟 **測試群組** 頁面。
1. 在 **測試群組** 頁面，上方網格的 **概述** 索引標籤上，建立測試群組，並設定以下值：

    - **測試群組：** _QMS_
    - **說明：** _QMS 測試_
    - **可接受數量：** _100_
    - **品項取樣：** _第三個 LP_ (選擇)

1. 在下方網格的 **概述** 索引標籤上，為一個測試新增記錄，並設定以下值：

    - **順序：** *1*
    - **測試：** *機櫃測量*

1. 在下方網格的 **測試** 索引標籤上，設定以下值：

    - **測試變數：** *通過/失敗*
    - **預設結果：** *通過*

1. 儲存新的測試群組，然後關閉 **測試群組** 頁面。
1. 返回 **品質關聯** 頁面，在 **測試群組** 欄位，選取 **QMS**。
1. 儲存記錄。

#### <a name="mobile-device-menu-items-for-quality-in"></a>用於品質輸入的行動裝置選單項目

若要完成將貨物移動到品質控制位置的設定，您必須從行動裝置選單項目中提供品質項目取樣工作。

1. 移至 **Warehouse Management\>設定\>行動裝置\>行動裝置功能表項目**。
1. 選擇 **採購入庫** 行動裝置選單項目。
1. 在 **工作類別** FastTab，新增 *品質輸入* 工作類別識別碼。

#### <a name="summary-your-setup-to-move-goods-to-quality-control"></a>摘要：將貨物轉移到品質控制的設定

您現在已定義一個品質關聯，其使用 *倉庫流程的品質管理* 功能來觸發品質檢驗訂單建立。 您已為倉庫 51 設定工作和位置資料，以確保品項 M9201 完成購買登記時，系統會建立特定工作。 此設定可確保每三個登記的牌照會移動到品質位置 (_QMS_)，並且為牌照數量建立品質檢驗訂單。 所有其他項目都會移至入庫位置，而不是品質控制位置。

### <a name="process-quality-management-work"></a>處理品質管理工作

1. 前往 **採購和資源開發 \> 訂購單 \> 所有訂購單**。
1. 建立一個訂購單，並設定以下值：

    - **特定廠商帳戶：** *104*
    - **倉庫：** *51*

1. 新增一個訂購單明細，並設定以下值：

    - **項目：** *M9201*
    - **數量：** *20*
    - **UoM：** *ea*
    - **倉庫：** *51*

1. 記下訂購單編號，以備日後使用。
1. 前往執行 Warehouse Management 行動裝置應用程式的行動裝置或模擬器，並使用使用者識別碼 *51* 和密碼 *1* 登入倉庫 51。
1. 前往 **輸入 \> 購買接收**，並輸入以下值：

    - **PONum：** 您剛才建立的訂購單編號
    - **數量：** *5*
    - **單位：** *ea*

1. 繼續按明細接收，一次 *5 ea*，直到完全接收明細。 (總共會建立四個牌照。)
1. 登出 Warehouse Management 行動應用程式。
1. 返回 Web 用戶端，前往 **採購和開源 \> 訂購單 \> 所有訂購單**。
1. 查找並開啟您的訂購單。
1. 在 **訂購單明細** 部分，選擇品項編號明細 *M9201*，然後選擇 **訂購單明細 \> 工作詳細資料**。
1. 請注意，所建立的第二個和第三個工作標題是一般入庫工作，而第一個和第四個工作標題是品質品項取樣工作。 這個結果與品項取樣設定一致，設定為每三個牌照取樣一次。

#### <a name="move-to-the-quality-control-location"></a>移動到品質控制位置

您現在會將牌照移動到指定位置。 第一個和第四個牌照將移至品質控制位置，而第二個和第三個牌照會直接進入存放處。

1. 前往執行 Warehouse Management 行動裝置應用程式的行動裝置或模擬器，並使用使用者識別碼 *51* 和密碼 *1* 登入倉庫 51。
1. 前往 **輸入 \> 採購入庫**，並入庫上一個過程中的每個牌照，直到您完成所有工作。

#### <a name="summary-process-quality-management-work"></a>摘要：處理品質管理工作

現在，只要將第一個和第四個牌照移動到品質控制位置，您就能執行品質品項取樣工作。 您還存放了第二個和第三個牌照。 下一步是進行品質檢驗訂單測試和控制。

### <a name="quality-out-setup-move-from-the-quality-control-location-to-storage-or-return"></a>品質輸出設定：從品質控制位置移動到存放處或退貨

當工作人員報告品質檢驗訂單結果時，系統會自動產生工作。

您現在會繼續進行工作類別、工作範本和位置指令所需的基本設定，以為倉庫流程啟用品質管理，讓系統可以建立所需的工作將品質檢驗訂單數量從品質控制位置移動到指定的位置倉庫位置。

#### <a name="work-class-for-quality-out"></a>品質輸出工作類別

1. 前往 **倉庫管理 \> 設定 \> 工作 \> 工作類別**。
1. 建立一個工作類別，並設定以下值：

    - **工作類別識別碼：** *QualityOut*
    - **說明：** *品質輸出*
    - **工單類型：** *品質檢驗訂單*

#### <a name="work-templates"></a>工作範本

1. 前往 **倉庫管理 \> 設定 \> 工作 \> 工作範本**。
1. 將 **工單類型** 值變更為 *品質檢驗訂單*。
1. 建立一個工作範本，並設定以下值：

    - **工作範本：** *51 品質輸出*
    - **工作範本說明：** *51 品質輸出*

1. 新增一個明細，並設定以下值：

    - **工作類型：** *揀貨*
    - **工作類別識別碼：** **QualityOut**

1. 新增第二個明細，並設定以下值：

    - **工作類型：** *放置*
    - **工作類別識別碼：** *QualityOut*

#### <a name="location-directives"></a>位置指令

1. 前往 **倉庫管理 \> 設定 \> 位置指令**。
1. 將 **工單類型** 值變更為 *品質檢驗訂單*。
1. 建立位置指令，並為其設定以下值：

    - **姓名：** *51 通過*
    - **工作類型：** *放置*
    - **站點：** *5*
    - **倉庫：** *51*

1. 在動作窗格上，選取 **編輯查詢**，開啟查詢編輯器對話方塊。
1. 在 **範圍** 索引標籤上，設定以下值：

    - **資料表：** *品質檢驗訂單*
    - **欄位：** *狀態*
    - **條件：** *通過*

1. 選取 **確定** 儲存查詢並關閉對話方塊。
1. 在 **明細** FastTab 上新增明細，並設定以下值：

    - **起始數量：** *1*
    - **終止數量：** *1000000*

1. 在 **位置指令動作** FastTab 上新增一列，並設定以下值：

    - **姓名：** *通過*

1. 在 **位置指令動作** FastTab 上，選取 **編輯查詢** 以開啟查詢編輯器對話方塊。
1. 在 **範圍** 索引標籤上，設定以下值：

    - **資料表：** *位置*
    - **欄位：** *區域識別碼*
    - **準則：** *大量*

1. 選取 **確定** 儲存查詢並關閉對話方塊。
1. 在動作窗格上，選擇 **儲存** 以儲存新的位置指令。
1. 建立第二個位置指令，並為其設定以下值：

    - **名稱：** *51 失敗*
    - **工作類型：** *放置*
    - **站點：** *5*
    - **倉庫：** *51*

1. 在動作窗格上，選取 **編輯查詢**，開啟查詢編輯器對話方塊。
1. 在 **範圍** 索引標籤上，設定以下值：

    - **資料表：** *品質檢驗訂單*
    - **欄位：** *狀態*
    - **準則：** *失敗*

1. 選取 **確定** 儲存查詢並關閉對話方塊。
1. 在 **明細** FastTab 上新增明細，並設定以下值：

    - **起始數量：** *1*
    - **終止數量：** *1000000*

1. 在 **位置指令動作** FastTab 上新增一列，並設定以下值：

    - **名稱：** *失敗*

1. 在 **位置指令動作** FastTab 上，選取 **編輯查詢** 以開啟查詢編輯器對話方塊。
1. 在 **範圍** 索引標籤上，設定以下值：

    - **資料表：** *位置*
    - **欄位：** *區域識別碼*
    - **準則：** *退貨*

1. 選取 **確定** 儲存查詢並關閉對話方塊。
1. 在動作窗格上，選擇 **儲存** 以儲存新的位置指令。

#### <a name="mobile-device-menu-items-for-quality-out"></a>用於品質輸出的行動裝置選單項目

1. 移至 **Warehouse Management\>設定\>行動裝置\>行動裝置功能表項目**。
1. 選擇 **QMS 入庫** 行動裝置選單項目。
1. 在 **工作類別** FastTab，新增 *QualityPut* 工作類別識別碼。

倉庫工作人員現在可以使用 **QMS 入庫** 選單項目挑選品質檢驗訂單工作。 未通過品質控制的商品可以放在退貨位置，通過的商品則可放入 bulk-001 位置。

#### <a name="summary-your-setup-to-move-goods-from-quality-control"></a>摘要：將貨物轉出品質控制的設定

您已為倉庫 51 設定工作和位置資料，以確保品質檢驗訂單完成時，系統會自動建立工作。 此設定可確保將每個經過品質控制的牌照移動到散裝地點或退貨位置。

### <a name="process-quality-management-work"></a>處理品質管理工作

1. 前往 **庫存管理 \> 定期工作 \> 品質管理 \> 品質檢驗訂單**。
1. 為已登記的數量選擇第一個品質檢驗訂單。
1. 選取 **驗證**。 測試狀態會更新為 *失敗*。
1. 前往 **倉庫管理 \> 所有工作**。
1. 開啟您剛才建立的工作，並留意 **工單類型** 值為 *品質檢驗訂單*。 工作包含一個明細，其中放置位置為 *退貨*，狀態則是 *失敗*。 (如果品質檢驗訂單的狀態是 *通過*，放置位置則是 *散裝*。)
1. 返回 **庫存管理 \> 定期工作 \> 品質管理 \> 品質檢驗訂單**。
1. 為已登記的品項選擇第二個品質檢驗訂單。
1. 選擇下方網格上方的 **結果**。 將 **結果數量** 值更新為 *5*，並驗證 **測試結果** 值已更改為勾選符號。
1. 選取 **驗證**，然後關閉頁面。
1. 返回 **品質檢驗訂單** 頁面，選擇 **驗證**，並進行驗證。 狀態更新為 *通過*。

    > [!NOTE]
    > 驗證事件會觸發品質檢驗訂單工作的建立，以將數量從品質控制位置移動到新位置。

1. 前往 **倉庫管理 \> 所有工作**。
1. 選擇剛才建立的工作，注意系統已建立第二個品質檢驗訂單工作標題，其中放置位置為 *BULK-001*。
1. 前往執行 Warehouse Management 行動裝置應用程式的行動裝置或模擬器，並使用使用者識別碼 *51* 和密碼 *1* 登入倉庫 51。
1. 前往 **品質 \> 從 QMS 入庫**，並分別處理與這兩個工作相關的兩個牌照，因此所有工作都會關閉。

> [!NOTE]
> 請考慮將品質輸出項目新增到其中活動代碼為 *顯示打開的工作清單* 的行動裝置選單項目。 例如，請參閱示範資料中名稱為 **工作清單** 的行動裝置選單項目。 首先將 *品質檢驗訂單* 工作類別新增到使用者導向選單項目，因為必須要有此工作類別，工作才會顯示在工作清單中。 然後將 *品質檢驗訂單* 工作級別新增到 **工作清單** 選單項目。 有權存取工作清單的使用者，將能夠挑選及處理由品質檢驗訂單驗證自動產生的工作。

## <a name="additional-resources"></a>其他資源

- [品質和不符合管理概觀](quality-management-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]