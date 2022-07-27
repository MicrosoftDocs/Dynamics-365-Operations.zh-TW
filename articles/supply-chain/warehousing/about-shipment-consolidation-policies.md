---
title: 貨件整合原則
description: 本主題摘要的功能可讓您靈活設定貨件整合原則。
author: GarmMSFT
ms.date: 05/12/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSShipConsolidationPolicy, WHSShipConsolidationWorkbench, WHSShipConsolidationError, WHSShipConsolidationSetShipment, WHSShipConsolidationPolicySelect, WHSShipPlanningListPage, TMSCarrierGroup, WHSShipConsolidationTemplate, WHSShipConsolidationTemplateApply, WHSShipConsolidationTemplateCreate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: 10.0.3
ms.openlocfilehash: 11ee4beefed02425d4650de3e896e608d3d00ef5
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449058"
---
# <a name="shipment-consolidation-policies"></a>貨件整合原則

[!include [banner](../includes/banner.md)]

使用貨件整合原則的貨件整合程序，可以在自動和手動發佈到倉庫時執行自動進行貨件整合。 在此功能引入之前，可用的自動整合只有寫死欄位，並且是建立在設定給倉庫的 **在發布貨到倉庫時整合貨件** 欄位。

貨件整合原則可提供以下功能：

- 自動發佈到倉庫的批次作業
- 銷售訂單或調撥單中的 **發佈到倉庫** 的命令
- **發佈到倉庫** 專屬頁面
- **負載規劃工作台** 頁面上的 **發佈到倉庫** 命令
- **整合貨件** 和 **貨件整合工作台** 頁面上的手動整合貨件

在引入貨件整合策略之前，整合功能就存在在倉庫層級的設定。 單一倉庫的所有客戶的所有訂單都被視為具有相同的整合要求。 在貨件整合原則新增了功能，支援不同組織對貨件整合的不同要求。

查詢用於找出適用的貨件整合原則，然後一組可編輯的欄位決定負載明細在貨件層面的分組方式。 (此模式類似於波次範例範本依循的模式。)此外，**與現有貨件整合** 選項已新增到每個原則。 開啟此選項後，*發佈到倉庫* 過程可搜尋由相同整合原則建立的現有貨件，查找要整合的貨件。 在這種情況下，系統將選擇現有的貨件或負載，而不用建立新的。 但是，系統只會與狀態為 *未結* 的貨件整合；波次發佈的狀態為 *發佈* 或更高的貨件將不會被視為整合的目標。

當貨件整合原則可用時，以前在 **倉庫** 設定頁面的 **發布到倉庫時整合** 會被隱藏。 為幫助您轉換到新的貨件整合功能，**貨件整合原則** 頁面會建立一個預設原則，該原則自動包含現有倉庫的舊設定。 建立該預設原則後，在 **倉庫** 設定頁面的 **發佈到倉庫時整合貨件** 設定將不再使用。

您可以使用 **發佈到倉庫** 頁面來手動覆寫適用的整合原則，方式與覆寫履行原則一樣。

**負載規劃工作台** 頁面上，您可以使用 **發佈\>發佈到倉庫** 命令以在您發佈到倉庫之前，由銷售訂單和調撥單明細組建出庫負載。 這些負載使用與貨件原則整合一起引入的相同整合邏輯。

您可以使用 **貨件整合工作台** 頁面以合併尚未確認但已發佈到倉庫的現有貨件。 此功能支援自動發佈程序，也就是擁有自己的貨件整合，每天運行多次的情況，但完成運送到承運業者之前，在確認流程中，要手動識別潛在的額外整合。 此功能使您可以在貨件發佈到倉庫後並在確認前之間的任何時間，整合從銷售訂單或調撥單明細建立的出庫貨件。

這 **貨件整合工作台** 頁面的工作方式類似於負載組建工作台，您可以在其中同時評估多個貨件並將非整合訂單指派給指定貨件。 您可以套用貨件整合範本來多次評估建議的整合並確認。 存在一些規則來防止沒有授權的整合，並警告您可能出現的錯誤。

## <a name="overview-of-new-functionality"></a>新功能概述

本節介紹當您啟動和使用 *貨件整合原則* 功能時，出現變更或新增的頁面、命令、功能。

### <a name="shipment-consolidation-policies-page"></a>貨件整合原則頁面

原則因工單類型而異。 這 **銷售訂單** 類型代表 _銷售訂單_ 貨件，以及 **轉單** 類型代表 _調撥出貨_ 貨件。

每個貨件整合原則都有一個能定義何時套用的查詢，和一個確定執行順序的序列編號。 整合套用在選取欄位的每個唯一組合。 提供的其他參數可用在與現有(未結) 貨件整合。 每次建立新貨件時 (在波次處理之前)，都會評估和套用這些原則。

如果原則缺少任何必填欄位，或者包含任何禁止欄位，則該原則會在 **選定** 區段標註為無效。 強制欄位和禁止欄位的列表是寫死的，可以擴展。

以下列表為必填欄位。 由於貨件必須根據這些欄位進行拆分，因此若要分組幾個在這些欄位具有不同值的貨件，您將無法進行。

- 在銷售訂單：

    - **帳戶號碼：**_WHSShipmentTable.AccountNum_
    - **交貨收件者：** _WHSShipmentTable.DeliveryName_
    - **郵寄地址 (RecId)：**_WHSShipmentTable.DeliveryPostalAddress_
    - **倉庫：** _WHSShipmentTable.InventLocationId_

- 在調撥單：

    - **起點倉庫：**_InventTransferTable.InventLocationIdFrom_
    - **抵達倉庫：** _InventTransferTable.InventLocationIdTo_

以下欄位不適用於所有文件類型。 這些欄位在用戶介面 (UI) 中無法看到，並且不能用於整合。

- **貨件識別碼：** _WHSShipmentTable.ShipmentId_
- **狀態：** _WHSShipmentTable.ShipmentStatus_
- **貨件整合原則：** _WHSShipmentTable.ShipConsolidationPolicyName_
- **工作交易類型：** _WHSShipmentTable.WorkTransType_
- **波次識別碼：** _WHSShipmentTable.WaveId_
- **負載識別碼：** _WHSShipmentTable.LoadId_
- **貨件識別碼：** _WHSLoadLine.ShipmentId_
- **負載識別碼：** _WHSLoadLine.LoadId_

預設情況下，當您建立原則時，必填欄位集被用作整合欄位。 但是，您可以使用左箭頭和右箭頭按鈕修改列表。 (該過程類似於在波次範本中選擇方法的程序。)

使用者為這些欄位選擇的值將用於所有新建立的貨件，或者在與這些貨件整合期間將它們新增到現有貨件中。 當兩個貨件的某個欄位的值相同，而該欄位被選來整合這些貨件，這兩個貨件將被整合。 相同的原則套用在後續所有選取的整合欄位。 如果值不同，則第二批貨件會被放棄並被選定為新的貨件。 自動整合程序由下列步驟組成：為運貨件整合欄位的值全部建立唯一組合，然後將貨件指派給相關組合。

在整合程序中，未選取的欄位將被忽略。 如果兩個貨件在未選取欄位的值不同，則該欄位將被清除 (即設定為空白)。 如果兩個貨件的未選取欄位的值相同，則填上該欄位。

合併欄位列表 (即，如果它們具有不同的值將被清除的欄位) 是寫死的。 在建立新貨件時，由銷售訂單或調撥單明細初始化的所有欄位都包含該列表中。 換言之，如果某個欄位未由銷售訂單或調撥單明細初始化，則在將新資料新增到現有貨件時將忽略該欄位。

### <a name="release-to-warehouse-page"></a>發佈到倉庫頁面

- 下方網格中的新欄位顯示已套用的整合原則。
- 一個新按鈕可讓您手動選取和/或覆寫整合原則。

### <a name="release-to-warehouse-command-on-the-load-planning-workbench-page"></a>在負載規劃工作台頁面上的發佈到倉庫命令

- 邏輯已被調整，使其使用已套用的整合原則。
- 貨件現在整合到僅在單一負載。

### <a name="consolidate-shipments-page"></a>整合貨件頁面

- 對類似貨件 (即候選整合) 的搜尋會更改，這樣它使用在貨件整合原則中選定的欄位。
- 在不同貨件中有著不同值的欄位現在設定為空白。 (以前，會使用已選取「基本」貨件的值。)

### <a name="shipment-consolidation-workbench-page"></a>貨件整合工作台頁面

- 新功能更大規模地複製了手動整合的過程。
- 您現在可以從 **Warehouse Management** 模組的 **發佈到倉庫** 功能表中打開此頁面。
- 該演算法分析尚未運送的現有貨件。 然後，它會根據在整合原則中選定的欄位建議整合。

## <a name="comparison-of-functionality"></a>功能比較

下表總結了當您不使用貨件整合原則時和使用時的貨件整合方式。

| 不使用貨件整合原則 | 使用貨件整合原則 |
|---|----|
| 不適用 | 選定進行整合的銷售或調撥貨件必須與正在建立的貨件具有相同的整合原則，或者必須被指派到未結貨件 (當 **與現有貨件合併** 選項已打開)。 |
| 這 *發佈到倉庫* 程序不會在現有貨件中搜索以找到要整合的貨件。 僅由當前 *發佈到倉庫* 程序執行個體建立的貨件會用於查找要整合的貨件。 | 如果當前正在使用的整合原則的 **與現有貨件整合** 選項開啟，則 *發佈到倉庫* 程序將搜尋那些由相同整合原則建立的現有貨件，以查找要整合的貨件。 因此，如果您有兩個原則，則根據原則 2 建立的貨件將永遠不會與基於原則 1 建立的貨件整合。 |
| 不適用 | 如果整合原則欄位列表為空白，或者如果找不到原則，則會為每個銷售訂單或調撥單明細建立一個新貨件。 |
| 以下整合欄位定義了用於 *調撥明細* 整合貨件值的唯一組合。 (所有其他欄位都被忽略。)<ul><li>訂單編號 (OrderNum)</li></ul> | 以下整合欄位定義了用於 *調撥明細* 整合貨件值的唯一組合。 (所有其他欄位都被忽略。)<ul><li>訂單編號 (OrderNum)</li><li>交貨收件者 (DeliveryName)</li><li>郵政地址 (DeliveryPostalAddress)</li><li>ISO 國碼 (地區碼) (CountryRegionISOCode)</li><li>地址 (Address)</li><li>站點 (InventSiteId)</li><li>倉庫 (InventLocationId)</li><li>承運業者 (CarrierCode)</li><li>貨運服務 (CarrierServiceCode)</li><li>交貨模式 (ModeCode)</li><li>貨運群組 (CarrierGroupCode)</li><li>交貨條款 (DlvTermId)</li></ul>這些欄位是唯一可用的，且在建立新貨件時就初始化的欄位。 |
| 以下整合欄位定義了用於 *銷售明細* 整合貨件值的唯一組合。 (所有其他欄位都被忽略。)<ul><li>訂單編號 (OrderNum)</li><li>客戶參考 (CustomerRef)</li><li>客戶申請 (CustomerReq)</li><li>交貨條款 (DlvTermId)</li></ul> | 以下整合欄位定義了用於 *銷售明細* 整合貨件值的唯一組合。 (所有其他欄位都被忽略。)<ul><li>訂單編號 (OrderNum)</li><li>帳戶號碼 (AccountNum)</li><li>交貨收件者 (DeliveryName)</li><li>郵政地址 (DeliveryPostalAddress)</li><li>ISO 國碼 (地區碼) (CountryRegionISOCode)</li><li>地址 (Address)</li><li>站點 (InventSiteId)</li><li>倉庫 (InventLocationId)</li><li>承運業者 (CarrierCode)</li><li>貨運服務 (CarrierServiceCode)</li><li>交貨模式 (ModeCode)</li><li>貨運群組 (CarrierGroupCode)</li><li>經紀商識別碼 (BrokerCode)</li><li>方向 (LoadDirection)</li><li>交貨條款 (DlvTermId)</li><li>客戶參考 (CustomerRef)</li><li>客戶申請 (CustomerReq)</li></ul>這些欄位是唯一可用的，且在建立新貨件時就初始化的欄位。 |
| 不適用 | 以下整合欄位對 *銷售明細* 為必要並且無法刪除：<ul><li>帳戶號碼 (AccountNum)</li><li>交貨收件者 (DeliveryName)</li><li>郵政地址 (DeliveryPostalAddress)</li><li>倉庫 (InventLocationId)</li></ul>預設情況下，這些欄位將在建立新原則時指定。 不能被移除。 |
| **負載規劃工作台** 頁面上的 *負載發佈到倉庫* 流程使用其獨立代碼來建立貨件和波次。 | 套用貨件整合原則來確定應評估哪些欄位以進行整合。 貨件被整合到僅在單一負載。 |
| 在 **所有貨件** 頁面，您手動選取 **整合貨件**，然後選取目標「基礎」貨件。 篩選將建議那些在幾個關鍵欄位中有相符值的現有貨件。 | 在 **所有貨件** 頁面，您手動選取 **整合貨件**，然後選取目標「基礎」貨件。 比對完相關貨件整合原則中設定的幾個關鍵欄位的值，系統將建議其他現有貨件。 |
| 在單個貨件的 **所有貨件** 頁面上，您可以使用 **整合貨件** 命令。 | **貨件整合工作台** 頁面可幫助您查找尚未處於已運送狀態的貨件組。 這些貨件是根據貨件整合原則中設定的幾個關鍵欄位進行分析的。 這些欄位的值相符的任何貨件，都會被建議整合。<p>您可以手動調整整合，只要從建議的整合中刪除貨件和/或新增貨件。 可能會出現幾種類型的錯誤，其中一些可以被覆寫。</p> |
| **設計說明：** *銷售訂單自動發佈到倉庫* 程序將銷售明細分成群組。 每個組都有自己獨特的 **ReleaseToWarehouseId** 值，並由 *發佈到倉庫* 程序單獨處理。 無論工作中斷設定如何，此過程都會建立新工作。 | **設計說明：** *銷售訂單自動發佈到倉庫* 程序指派相同的 **ReleaseToWarehouseId** 值到所有正在處理的銷售明細。 所有銷售明細同時由 *發佈到倉庫* 流程處理。 為確保及早行動，您必須設定每個貨件識別碼的工作中斷。 |

## <a name="additional-resources"></a>其他資源

- [配置貨件整合原則](configure-shipment-consolidation-policies.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]