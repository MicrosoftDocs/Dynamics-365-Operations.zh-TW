---
title: 直接在 Sales 和 Supply Chain Management 之間同步銷售訂單
description: 本主題討論用於在 Dynamics 365 Sales 和 Dynamics 365 Supply Chain Management 之間直接執行銷售訂單同步的範本和基礎工作。
author: Henrikan
ms.date: 05/09/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: henrikan
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: eb41a21395a5d115b779e6b1ef71e9eb1176e28e
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8449817"
---
# <a name="synchronization-of-sales-orders-directly-between-sales-and-supply-chain-management"></a>直接在 Sales 和 Supply Chain Management 之間同步銷售訂單

[!include [banner](../includes/banner.md)]



本主題討論用於在 Dynamics 365 Sales 和 Dynamics 365 Supply Chain Management 之間直接執行銷售訂單同步的範本和基礎工作。

## <a name="data-flow-in-prospect-to-cash"></a>從潛在客戶到現金的資料流程

「從潛在客戶到現金」解決方案使用資料整合功能，在 Supply Chain Management 和 Sales 執行個體之間同步資料。 提供資料整合功能的「從潛在客戶到現金」範本啟用 Supply Chain Management 與 Sales 之間的帳戶、連絡人、產品、銷售報價、銷售訂單和銷售發票的資料流程。 下圖顯示了資料如何在 Supply Chain Management 和 Sales 之間同步。

[![從潛在客戶到現金中的資料流程](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)

## <a name="templates-and-tasks"></a>範本和工作

若要存取可用的範本，請打開 [Power Apps 系統管理中心](https://preview.admin.powerapps.com/dataintegration)。 選取 **專案**，然後選取右上角的 **新專案** 以選擇公用範本。

以下範本和基礎工作用於在 Sales 和 Supply Chain Management 之間直接執行銷售訂單的同步。

- **資料整合中的範本名稱：** 

    - 銷售訂單 (Sales 到 Supply Chain Management) - 直接
    - 銷售訂單 (Supply Chain Management 到 Sales) - 直接

- **資料整合專案中的工作名稱：**

    - OrderHeader
    - OrderLine

在同步銷售發票抬頭和明細之前，需要執明細以下同步工作：

- 產品 (Supply Chain Management 到 Sales) - 直接
- 科目 (Sales 到 Supply Chain Management) - 直接 (如果使用)
- 從連絡人到客戶 (Sales 到 Supply Chain Management) - 直接 (如果使用)

## <a name="entity-set"></a>實體集

| Supply Chain Management  | 銷售             |
|-------------------------|-------------------|
| Dataverse 銷售訂單標題 | SalesOrders       |
| Dataverse 銷售訂單行   | SalesOrderDetails |

## <a name="entity-flow"></a>實體流程

在為根據 **銷售訂單 (Sales 到 Supply Chain Management) - 直接** 範本的專案觸發 **執行專案** 後，銷售訂單會在 Sales 中建立，然後同步到 Supply Chain Management。 只有當所有 **訂單產品** 都由外部維護的產品組成時，才能啟用和同步來自 Sales 的訂單。 因此，可能沒有型錄外產品。 訂單啟用後，銷售訂單將在使用者介面 (UI) 中變為唯讀狀態。 此時，更新由 Supply Chain Management 進行。 在銷售訂單狀態為 **已確認** 後，根據 **銷售訂單 (Supply Chain Management 到 Sales) - 直接** 範本的專案可用於將 Supply Chain Management 的更新或履行狀態全部同步到 Sales。

您不必在 Sales 中建立訂單。 可以改在 Supply Chain Management 中建立新的銷售訂單。 在銷售訂單的狀態為 **已確認** 後，其將被同步到 Sales，如前面段落中所述。

在 Supply Chain Management 中，範本中的篩選有助於確保同步只包含相關的銷售訂單：

- 在銷售訂單上，訂購客戶和開立發票的客戶都必須來自 Sales 才能包含在同步中。 在 Supply Chain Management 中，**OrderingCustomerIsExternallyMaintained** 和 **InvoiceCustomerIsExternallyMaintained** 資料行用於篩選資料表中的銷售訂單。
- 必須確認 Supply Chain Management 中的銷售訂單。 僅已確認的銷售訂單或具有較高處理狀態 (例如 **已出貨** 或 **已開立發票**) 的銷售訂單同步到 Sales。
- 建立或修改銷售訂單後，必須執行 Supply Chain Management 中的 **計算銷售總額** 批次處理作業。 僅計算了銷售總額的銷售訂單才會同步到 Sales。

## <a name="freight-tax"></a>貨運稅

因為稅儲存在行等級，因此 Sales 不支援抬頭等級的稅。 若要支援 Supply Chain Management 訂單抬頭等級的稅 (例如貨運稅)，系統將稅做為名為 **貨運稅**，且具有來自 Supply Chain Management 稅額的型錄外產品同步到 Sales。 這樣，即使在 Supply Chain Management 的訂單抬頭等級存在稅時，Sales 中的標準價格計算可用於總金額。

## <a name="discount-calculation-and-rounding"></a>折扣計算和進位

Sales 中的折扣計算模型與 Supply Chain Management 中的折扣計算模型不同。 在 Supply Chain Management 中，銷售行的最終折扣金額可以是折扣金額和折扣百分比的組合結果。 如果此最終折扣金額除以行中的數量，則可能會發生進位。 但是，如果進位的單位折扣金額與銷售額同步，則不考慮此進位。 為幫助確保 Supply Chain Management 中銷售行的全部折扣金額正確同步到 Sales，必須在不除以行數量的情況下同步全部金額。 因此，您必須在 Sales 中將 **折扣計算方法** 定義為 **行項**。

當銷售訂單行從 Sales 同步到 Supply Chain Management 時，將使用完整行折扣金額。 因為 Supply Chain Management 沒有可以儲存完整折扣金額的欄位，所以金額除以數量並儲存在 **行折扣** 欄位中。 此除法計算中發生的任何進位都將儲存在銷售行的 **銷售費用** 欄位中。

### <a name="example"></a>範例

**從 Sales 同步到 Supply Chain Management**

- **Sales：** 數量 = 3，每行折扣 = $10.00
- **Supply Chain Management：** 數量 = 3，行折扣金額 = $3.33，銷售費用 = -$0.01 

**從 Supply Chain Management 同步到 Sales**

- **Supply Chain Management：** 數量 = 3，行折扣金額 = $3.33，銷售費用 = -$0.01
- **Sales：** 數量 = 3，每行折扣 = (3 × $3.33) + $0.01 = $10.00

## <a name="prospect-to-cash-solution-for-sales"></a>從潛在客戶到現金解決方案

新列已新增到 **訂單** 資料表並出現在頁面上：

- **外部維護** – 當訂單來自 Supply Chain Management 時，將此選項設為 **是**。
- **處理狀態** – 此列顯示 Supply Chain Management 中訂單的處理狀態。 以下是可供使用的值：

    - **草稿** – 在 Sales 中建立訂單時的初始狀態。 在 Sales 中，只能編輯具有此處理狀態的訂單。
    - **使用中** – 使用 **啟用** 按鈕在 Sales 中啟用訂單後的狀態。
    - **已確認**
    - **裝箱單**
    - **已請款**
    - **已領料**
    - **已部分領料**
    - **已部分包裝**
    - **已運送**
    - **已部分裝運**
    - **已部分開立發票**
    - **已取消**

**僅具有外部維護的產品** 在訂單啟用期間使用設定來持續追蹤銷售訂單是否完全由外部維護的產品組成。 如果銷售訂單完全由外部維護的產品組成，則產品將在 Supply Chain Management 中進行維護。 此設定有助於確保您不會啟用並嘗試將具有未知產品的銷售訂單行同步到 Supply Chain Management 。

對於外部維護的訂單，**銷售訂單** 頁面上的 **建立發票**、**取消訂單**、**重新計算**、**取得產品** 和 **查詢地址** 按鈕是隱藏的，因為發票將在 Supply Chain Management 中建立並同步到 Sales。 這些訂單無法編輯，因為將在啟用後同步來自 Supply Chain Management 的銷售訂單資訊。

銷售訂單狀態將維持 **使用中**，以協助確保來自 Supply Chain Management 的變更可以流向 Sales 中的銷售訂單。 若要控制此行為，請在資料整合項目中將預設的 **狀態代碼 \[Status\]** 值設為 **使用中**。

## <a name="preconditions-and-mapping-setup"></a>先決條件和對應設定

在同步銷售訂單之前，請務必更新系統中的以下設定。

### <a name="setup-in-sales"></a>Sales 中的設定

- 確保為 Sales 連接集中的使用者指派到的團隊設定了權限。 如果使用的示範資料，使用者通常具有管理員存取權，但團隊沒有管理員存取權。 如果團隊沒有管理員存取權，當您從資料整合執行專案時，將收到錯誤訊息，指出缺少主體團隊。

    移至 **設定** &gt; **安全** &gt; **團隊**，選擇相關團隊，選擇 **管理角色**，然後選擇具有所需權限的角色，例如 **系統管理員**。

- 若要確保在Sales 和 Supply Chain Management 中正確計算折扣，**折扣計算方法** 必須設為 **行項**。
- 移至 **設定** &gt; **管理** &gt; **系統設定** &gt; **Sales**，並確保使用以下設定：

    - **使用系統定價計算系統** 選項設為 **是**。
    - **折扣計算方法** 資料行設為 **行項**。

### <a name="setup-in-supply-chain-management"></a>Supply Chain Management 設定

- 移至 **銷售和行銷** &gt; **定期工作** &gt; **計算銷售總額**，並將作業設為作為批次處理作業執行。 將 **計算銷售訂單的總計** 選項設為 **是**。 此步驟很重要，因為只有計算了銷售總額的銷售訂單才會同步到 Sales。 批次處理作業的頻率應與銷售訂單同步的頻率保持一致。

如果您還使用工單整合，則需要設定銷售來源。 銷售來源用於區分從 Field Service 工單建立的 Supply Chain Management 銷售訂單。 當銷售訂單的訂單來源類型為 **工單整合** 時，銷售訂單抬頭會顯示 **外部工單狀態** 欄位。 此外，銷售來源可確保在從 Supply Chain Management 到 Field Service 的銷售訂單同步期間篩選掉從 Field Service 中的工作訂單建立的銷售訂單。

1. 依序前往 **銷售和行銷** \> **設定** \> **銷售訂單** \> **銷售來源**。
2. 選擇 **新增** 以建立新的銷售來源。
3. 在 **銷售來源** 資料行，輸入銷售來源的名稱，例如 **SalesOrder**。
4. 在 **描述** 資料行，輸入描述，例如 **來自 Sales 的銷售訂單**。
5. 選擇 **來源類型指派** 核取方塊。
6. 將 **銷售來源類型** 資料行設為 **銷售訂單整合**。
7. 選取 **儲存**。

### <a name="setup-in-the-sales-orders-sales-to-supply-chain-management---direct-data-integration-project"></a>銷售訂單中的設定 (Sales 到 Supply Chain Management) - 直接資料整合專案

- 確保存在 **Shipto\_country** 到 **DeliveryAddressCountryRegionISOCode** 所需的對應。 您可以在值對應中的預設值保留空白，以避免必須為國家訂單輸入國家/地區。 將左側設為「空白」，將右側設為所需的國家或地區。

    範本值是對應了多個國家或地區的值對應，其中「空白」= US。

### <a name="setup-in-the-sales-orders-supply-chain-management-to-sales---direct-data-integration-project"></a>銷售訂單中的設定 (Supply Chain Management 到 Sales) - 直接資料整合專案

#### <a name="salesheader-task"></a>SalesHeader 工作

- 需要價目表才能在 Sales 中建立訂單。 將 **pricelevelid.name\[價目表名稱\]** 的值對應依貨幣更新至 Sales 中使用的價目表。 您可以為單一貨幣使用預設價目表。 或者，如果您的價目表有多種貨幣，則可以使用值對應。

    **pricelevelid.name\[價目表名稱\]的預設範本值** 是 **美國 CRM 服務 (範例)**。

#### <a name="salesline-task"></a>SalesLine 工作

- 確保在 Supply Chain Management 中存在所需的 **SalesUnitSymbol** 值對應。
- 確保在 Sales 中定義了所需的單位。

    為 **SalesUnitSymbol** 到 **oumid.name** 定義具有值對應的範本值。

## <a name="template-mapping-in-data-integration"></a>資料整合中的範本對應

> [!NOTE]
> **付款條款**、**貨運條款**、**交貨條款**、**運送方式** 和 **交貨方式** 資料行不包含在預設對應中。 若要對應這些資料行，必須設定特定於在其中同步資料表之組織中的資料值對應。

下圖顯示資料整合中的範本對應範例。

> [!NOTE]
> 該對應顯示哪些列資訊將從 Sales 同步到 Supply Chain Management，或從 Supply Chain Management 同步到 Sales 的資料行資訊。

### <a name="sales-orders-supply-chain-management-to-sales---direct-orderheader"></a>銷售訂單 (Supply Chain Management 到 Sales) - 直接：OrderHeader

[![資料整合中的範本對應，銷售訂單 (Supply Chain Management 到 Sales) - 直接：OrderHeader。](./media/sales-order-direct-template-mapping-data-integrator-1.png)](./media/sales-order-direct-template-mapping-data-integrator-1.png)

### <a name="sales-orders-supply-chain-management-to-sales---direct-orderline"></a>銷售訂單 (Supply Chain Management 到 Sales) - 直接：OrderLine

[![資料整合中的範本對應，銷售訂單 (Supply Chain Management 到 Sales) - 直接：OrderLine。](./media/sales-order-direct-template-mapping-data-integrator-2.png)](./media/sales-order-direct-template-mapping-data-integrator-2.png)

### <a name="sales-orders-sales-to-supply-chain-management---direct-orderheader"></a>銷售訂單 (Sales 到 Supply Chain Management) - 直接：OrderHeader

[![資料整合中的範本對應，銷售訂單 (Sales 到 Supply Chain Management) - 直接：OrderHeader。](./media/sales-order-direct-template-mapping-data-integrator-3.png)](./media/sales-order-direct-template-mapping-data-integrator-3.png)

### <a name="sales-orders-sales-to-supply-chain-management---direct-orderline"></a>銷售訂單 (Sales 到 Supply Chain Management) - 直接：OrderLine

[![資料整合中的範本對應，銷售訂單 (Sales 到 Supply Chain Management) - 直接：OrderLine。](./media/sales-order-direct-template-mapping-data-integrator-4.png)](./media/sales-order-direct-template-mapping-data-integrator-4.png)

## <a name="related-topics"></a>相關主題

[潛在客戶到現金](prospect-to-cash.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]