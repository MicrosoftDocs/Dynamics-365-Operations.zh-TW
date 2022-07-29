---
title: 使用擴充在稅務整合中新增資料欄位
description: 本主題介紹如何使用 X++ 擴充在稅務整合中新增資料欄位。
author: qire
ms.date: 02/17/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: acbe8070424febf24883362448ea56857d9d72d9
ms.sourcegitcommit: 68114cc54af88be9a3a1a368d5964876e68e8c60
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/17/2022
ms.locfileid: "8451626"
---
# <a name="add-data-fields-in-the-tax-integration-by-using-extension"></a>使用擴充在稅務整合中新增資料欄位

[!include [banner](../includes/banner.md)]


本主題介紹如何使用 X++ 擴充在稅務整合中新增資料欄位。 這些欄位可以擴充到稅務服務的稅務資料模型，並用於確定稅碼。 如需更多資訊，請參閱[在稅務設定中新增資料欄位](tax-service-add-data-fields-tax-configurations.md)。

## <a name="data-model"></a>資料模型

資料模型中的資料由物件承載，由類別實現。

以下是主要物件的列表: 

* AxClass/TaxIntegration **文件** 物件
* AxClass/TaxIntegration **行** 物件
* AxClass/TaxIntegration **稅行** 物件

下圖顯示這些物件之間的關係。

[![資料模型物件關係。](./media/tax-service-customize-image1.png)](./media/tax-service-customize-image1.png)

**文件** 物件可以包含許多 **行** 物件。 每個物件都包含稅務服務的中繼資料。

- `TaxIntegrationDocumentObject` 擁有 `originAddress` 中繼資料，其包含有關來源地址的資訊，以及`includingTax` 中繼資料，其顯示行金額是否包括銷售稅。
- `TaxIntegrationLineObject` 擁有 `itemId`、 `quantity` 和 `categoryId` 中繼資料。

> [!NOTE]
> `TaxIntegrationLineObject`還實作 **收費** 物件。

## <a name="integration-flow"></a>整合流程

流程中的資料由活動操控。

### <a name="key-activities"></a>重要活動

* AxClass/TaxIntegration **Calculation** ActivityOnDocument
* AxClass/TaxIntegration **CurrencyExchange** ActivityOnDocument
* AxClass/TaxIntegration **DataPersistence** ActivityOnDocument
* AxClass/TaxIntegration **DataRetrieva** ActivityOnDocument
* AxClass/TaxIntegration **SettingRetrieval** ActivityOnDocument

活動按以下順序執行: 

1. 設定檢索
2. 資料檢索
3. 計算服務
4. 貨幣兌換
5. 資料永續性

例如，在 **計算服務** 前擴充 **資料檢索**。

#### <a name="data-retrieval-activities"></a>資料檢索活動

**資料檢索** 活動從資料庫中擷取資料。 不同交易的配接器可用於從不同交易資料表中擷取資料: 

- AxClass/TaxIntegration **PurchTable** DataRetrieval
- AxClass/TaxIntegration **PurchParmTable** DataRetrieval
- AxClass/TaxIntegration **PurchREQTable** DataRetrieval
- AxClass/TaxIntegration **PurchRFQTable** DataRetrieval
- AxClass/TaxIntegration **VendInvoiceInfoTable** DataRetrieval
- AxClass/TaxIntegration **SalesTable** DataRetrieval
- AxClass/TaxIntegration **SalesParm** DataRetrieval

在這些 **資料檢索** 活動中，資料從資料庫複製到 `TaxIntegrationDocumentObject` 和 `TaxIntegrationLineObject`。 因為所有這些活動都擴充相同的抽像範本類別，所以它們有共同的方法。

#### <a name="calculation-service-activities"></a>計算服務活動

**計算服務** 活動連結了稅務服務和稅務整合。 該活動負責以下功能: 

1. 建構要求。
2. 將要求發布到稅務服務。
3. 獲取稅務服務的回應。
4. 剖析回應。

您新增至該要求的資料欄位將與其他中繼資料一起發布。 

## <a name="extension-implementation"></a>擴充實作

本節提供詳細的步驟來解釋如何實作擴充。 它使用 **成本中心** 和 **項目** 財務維度為例。

### <a name="step-1-add-the-data-variable-in-the-object-class"></a>步驟 1. 在物件類別中添加資料變數

該資料類別包含資料變數和資料的 getter/setter 方法。 將資料欄位添加到 `TaxIntegrationDocumentObject` 或 `TaxIntegrationLineObject`，取決於欄位級別。 下面的例子使用行級別，檔案名稱是 `TaxIntegrationLineObject_Extension.xpp`。

> [!NOTE]
> 如果您要新增的資料欄位位於檔案級別，請將檔案名稱改為 `TaxIntegrationDocumentObject_Extension.xpp`。

```X++
[ExtensionOf(classStr(TaxIntegrationLineObject))]
final class TaxIntegrationLineObject_Extension
{
    private OMOperatingUnitNumber costCenter;
    private ProjId projectId;

    /// <summary>
    /// Gets a costCenter.
    /// </summary>
    /// <returns>The cost center.</returns>
    public final OMOperatingUnitNumber getCostCenter()
    {
        return this.costCenter;
    }

    /// <summary>
    /// Sets the cost center.
    /// </summary>
    /// <param name = "_value">The cost center.</param>
    public final void setCostCenter(OMOperatingUnitNumber _value)
    {
        this.costCenter = _value;
    }

    /// <summary>
    /// Gets a project ID.
    /// </summary>
    /// <returns>The project ID.</returns>
    public final ProjId getProjectId()
    {
        return this.projectId;
    }

    /// <summary>
    /// Sets the project ID.
    /// </summary>
    /// <param name = "_value">The project ID.</param>
    public final void setProjectId(ProjId _value)
    {
        this.projectId = _value;
    }
}
```

**成本中心** 和 **項目** 被添加為私用變數。 為這些資料欄位建立 getter 和 setter 方法來操控資料。

### <a name="step-2-retrieve-data-from-the-database"></a>步驟 2. 從資料庫擷取資料

指定交易，並擴充適當的配接器類別以擷取資料。 例如，如果您使用 **訂購單** 交易，您必須擴充 `TaxIntegrationPurchTableDataRetrieval` 和 `TaxIntegrationVendInvoiceInfoTableDataRetrieval`。 

> [!NOTE]
> `TaxIntegrationPurchParmTableDataRetrieval` 繼承自 `TaxIntegrationPurchTableDataRetrieval`。 它不應該改變，除非 `purchTable` 資料表的邏輯和 `purchParmTable` 資料表的邏輯不同。

如果應為所有交易添加資料欄位，則擴充所有 `DataRetrieval` 類別。

因為所有 **資料檢索** 活動擴充相同的範本類別，所以類結構、變數和方法相似。

```X++
protected TaxIntegrationDocumentObject document;

/// <summary>
/// Copies to the document.
/// </summary>
protected abstract void copyToDocument()
{
    // It is recommended to implement as:
    //
    // this.copyToDocumentByDefault();
    // this.copyToDocumentFromHeaderTable();
    // this.copyAddressToDocument();
}
 
/// <summary>
/// Copies to the current line of the document.
/// </summary>
/// <param name = "_line">The current line of the document.</param>
protected abstract void copyToLine(TaxIntegrationLineObject _line)
{
    // It is recommended to implement as:
    //
    // this.copyToLineByDefault(_line);
    // this.copyToLineFromLineTable(_line);
    // this.copyQuantityAndTransactionAmountToLine(_line);
    // this.copyAddressToLine(_line);
    // this.copyToLineFromHeaderTable(_line);
}
```

以下例子顯示使用 `PurchTable`資料表時的基本結構。

```X++
public class TaxIntegrationPurchTableDataRetrieval extends TaxIntegrationAbstractDataRetrievalTemplate
{
    protected PurchTable purchTable;
    protected PurchLine purchLine;

    // Query builder methods
    [Replaceable]
    protected SysDaQueryObject getDocumentQueryObject()
    [Replaceable]
    protected SysDaQueryObject getLineQueryObject()
    [Replaceable]
    protected SysDaQueryObject getDocumentChargeQueryObject()
    [Replaceable]
    protected SysDaQueryObject getLineChargeQueryObject()

    // Data retrieval methods
    protected void copyToDocument()
    protected void copyToDocumentFromHeaderTable()
    protected void copyToLine(TaxIntegrationLineObject _line)
    protected void copyToLineFromLineTable(TaxIntegrationLineObject _line)
    ...
}
```

調用 `CopyToDocument` 方法時，`this.purchTable` 緩衝區已經存在。 此方法的目的是使用建立在 `DocumentObject`類別的 setter 方法複製從 `this.purchTable` 到 `document`物件的所有必要資料。

同樣，一個 `this.purchLine`緩衝區已存在於 `CopyToLine` 方法內。 此方法的目的是使用建立在 `LineObject` 類別的 setter 方法複製從 `this.purchLine` 到 `_line`物件的所有必要資料。

最直接的方法是擴充 `CopyToDocument` 和 `CopyToLine` 方法。 但是，我們建議您先嘗試 `copyToDocumentFromHeaderTable` 和 `copyToLineFromLineTable` 方法。 如果它們不能按您的要求工作，請實作您自己的方法，並在 `CopyToDocument` 和 `CopyToLine` 調用它。 您可以在三種常見情況下使用此方法: 

- 必填欄位在 `PurchTable` 或 `PurchLine` 內。 在這種情況下，您可以擴充 `copyToDocumentFromHeaderTable`和 `copyToLineFromLineTable`。 這是範例程式碼。

    ```X++
    /// <summary>
    /// Copies to the current line of the document from.
    /// </summary>
    /// <param name = "_line">The current line of the document.</param>
    protected void copyToLineFromLineTable(TaxIntegrationLineObject _line)
    {
        next copyToLineFromLineTable(_line);
        // if we already added XXX in TaxIntegrationLineObject
        _line.setXXX(this.purchLine.XXX);
    }
    ```

- 必要資料不在交易的預設資料表中。 但是，與預設資料表存在一些聯結關聯性，且該欄位在大多數行上都是必需的。 在這種情況下，更換 `getDocumentQueryObject`或`getLineObject` 以透過聯結關聯性查詢資料表。 在以下示例中，**立即交付** 欄位與行級別的銷售訂單整合。

    ```X++
    public class TaxIntegrationSalesTableDataRetrieval
    {
        protected MCRSalesLineDropShipment mcrSalesLineDropShipment;

        /// <summary>
        /// Gets the query for the lines of the document.
        /// </summary>
        /// <returns>The query for the lines of the document</returns>
        [Replaceable]
        protected SysDaQueryObject getLineQueryObject()
        {
            return SysDaQueryObjectBuilder::from(this.salesLine)
                .where(this.salesLine, fieldStr(SalesLine, SalesId)).isEqualToLiteral(this.salesTable.SalesId)
                .outerJoin(this.mcrSalesLineDropShipment)
                .where(this.mcrSalesLineDropShipment, fieldStr(MCRSalesLineDropShipment, SalesLine)).isEqualTo(this.salesLine, fieldStr(SalesLine, RecId))
                .toSysDaQueryObject();
        }
    }
    ```

    在這個例子中，宣告一個 `mcrSalesLineDropShipment` 緩衝區，且在 `getLineQueryObject` 定義查詢。 該查詢使用關聯性 `MCRSalesLineDropShipment.SalesLine == SalesLine.RecId`。 在這種情況下進行擴充時，您可以使用自己建構的查詢物件替換 `getLineQueryObject`。 但是，請注意以下幾點: 

    * 因為 `getLineQueryObject`方法的傳回值是 `SysDaQueryObject`，因此您必須使用 SysDa 方法建構此物件。
    * 無法刪除現有資料表。

- 所需資料透過複雜的聯結關聯性與交易資料表相關，或者關聯不是一對一 (1:1) 而是一對多 (1:N)。 在這種情況下，事情變得有點複雜。 這種情況適用於財務維度的示例。 

    在這種情況下，您可以實作自己的方法來擷取資料。 這是 `TaxIntegrationPurchTableDataRetrieval_Extension.xpp` 檔案內的範例程式碼。

    ```X++
    [ExtensionOf(classStr(TaxIntegrationPurchTableDataRetrieval))]
    final class TaxIntegrationPurchTableDataRetrieval_Extension
    {
        private const str CostCenterKey = 'CostCenter';
        private const str ProjectKey = 'Project';

        /// <summary>
        /// Copies to the current line of the document from.
        /// </summary>
        /// <param name = "_line">The current line of the document.</param>
        protected void copyToLineFromLineTable(TaxIntegrationLineObject _line)
        {
            Map dimensionAttributeMap = this.getDimensionAttributeMapByDefaultDimension(this.purchline.DefaultDimension);
            if (dimensionAttributeMap.exists(CostCenterKey))
            {
                _line.setCostCenter(dimensionAttributeMap.lookup(CostCenterKey));
            }
            if (dimensionAttributeMap.exists(ProjectKey))
            {
                _line.setProjectId(dimensionAttributeMap.lookup(ProjectKey));
            }
            next copyToLineFromLineTable(_line);
        }
        private Map getDimensionAttributeMapByDefaultDimension(RefRecId _defaultDimension)
        {
            DimensionAttribute dimensionAttribute;
            DimensionAttributeValue dimensionAttributeValue;
            DimensionAttributeValueSetItem dimensionAttributeValueSetItem;
            Map ret = new Map(Types::String, Types::String);

            select Name, RecId from dimensionAttribute
                join dimensionAttributeValue
                    where dimensionAttributeValue.dimensionAttribute == dimensionAttribute.RecId
                join DimensionAttributeValueSetItem
                    where DimensionAttributeValueSetItem.DimensionAttributeValue == DimensionAttributeValue.RecId
                        && DimensionAttributeValueSetItem.DimensionAttributeValueSet == _defaultDimension;

            while(dimensionAttribute.RecId)
            {
                ret.insert(dimensionAttribute.Name, dimensionAttributeValue.DisplayValue);
                next dimensionAttribute;
            }
            return ret;
        }
    }
    ```

### <a name="step-3-add-data-to-the-request"></a>步驟 3. 將資料新增至要求

擴充 `copyToTaxableDocumentHeaderWrapperFromTaxIntegrationDocumentObject` 或`copyToTaxableDocumentLineWrapperFromTaxIntegrationLineObjectByLine` 以便將資料新增至要求。 這是 `TaxIntegrationCalculationActivityOnDocument_CalculationService_Extension.xpp` 檔案內的範例程式碼。

```X++
[ExtensionOf(classStr(TaxIntegrationCalculationActivityOnDocument_CalculationService))]
final static class TaxIntegrationCalculationActivityOnDocument_CalculationService_Extension
{
    // Define key for the form in post request
    private const str IOCostCenter = 'Cost Center';
    private const str IOProject = 'Project';

    /// <summary>
    /// Copies to <c>TaxableDocumentLineWrapper</c> from <c>TaxIntegrationLineObject</c> by line.
    /// </summary>
    /// <param name = "_destination"><c>TaxableDocumentLineWrapper</c>.</param>
    /// <param name = "_source"><c>TaxIntegrationLineObject</c>.</param>
    protected static void copyToTaxableDocumentLineWrapperFromTaxIntegrationLineObjectByLine(Microsoft.Dynamics.TaxCalculation.ApiContracts.TaxableDocumentLineWrapper _destination, TaxIntegrationLineObject _source)
    {
        next copyToTaxableDocumentLineWrapperFromTaxIntegrationLineObjectByLine(_destination, _source);
        // Set the field we need to integrated for tax service
        _destination.SetField(IOCostCenter, _source.getCostCenter());
        _destination.SetField(IOProject, _source.getProjectId());
    }
}
```

在該程式碼中，`_destination`是用於生成發布要求的包裝函式物件，而 `_source` 是 `TaxIntegrationLineObject` 物件。

> [!NOTE]
> 將要求表單中使用的金鑰定義為 **private const str**。 該字串應與主題中新增的量值名稱完全相同，[在稅務設定中新增資料欄位](tax-service-add-data-fields-tax-configurations.md)。
> 使用 **SetField** 方法，在 **copyToTaxableDocumentLineWrapperFromTaxIntegrationLineObjectByLine** 方法中設定欄位。 第二參數的資料類型必須是 **字串**。 如果資料類型不是 **字串**，請轉換它。
> 如果一個 X++**列舉類型** 是擴充的，注意它的值、標籤和名稱之間的區別。
> 
>   - 該列舉值為整數。
>   - 列舉的標籤可能因偏好的語言而異。 請勿使用 **enum2Str** 將列舉類型轉換為字串。
>   - 建議使用列舉名稱，因為它是固定的。 **enum2Symbol** 可用於將列舉轉換為其名稱。 稅務設定中新增的列舉值應與列舉名稱完全相同。

## <a name="model-dependency"></a>模型相依性

要成功構建項目，請將以下參考模型添加到模型相依性中: 

- ApplicationPlatform
- ApplicationSuite
- 稅務引擎
- 維度，如果使用財務維度
- 程式碼中引用的其他必要模型

## <a name="validation"></a>驗證

完成前面的步驟後，您可以驗證您的更改。

1. 在財務中，前往 **應付帳款** 並將 **&debug=vs%2CconfirmExit&** 添加到 URL。 例如，https://usnconeboxax1aos.cloud.onebox.dynamics.com/?cmp=DEMF&mi=PurchTableListPage&debug=vs%2CconfirmExit&。 最後的 **&** 必不可少。
2. 開啟 **訂購單** 頁面，選擇 **新增** 建立一個訂購單。
3. 設定自訂欄位的值，然後選擇 **銷售稅**。 帶有首碼的故障排除檔案，**TaxServiceTroubleshootingLog** 是自動下載的。 此文件包含發布到稅務計算服務的交易資訊。 
4. 檢查添加的自訂欄位是否存在於 **稅務服務計算輸入 JSON** 部分，以及它的值是否正確。 如果值不正確，請複查本文檔中的步驟。

檔案示例: 

```
===Tax service calculation input JSON:===
{
  "TaxableDocument": {
    "Header": [
      {
        "Lines": [
          {
            "Line Type": "Normal",
            "Item Code": "",
            "Item Type": "Item",
            "Quantity": 0.0,
            "Amount": 1000.0,
            "Currency": "EUR",
            "Transaction Date": "2022-1-26T00:00:00",
            ...
            /// The new fields added at line level
            "Cost Center": "003",
            "Project": "Proj-123"
          }
        ],
        "Amount include tax": true,
        "Business Process": "Journal",
        "Currency": "",
        "Vendor Account": "DE-001",
        "Vendor Invoice Account": "DE-001",
        ...
        // The new fields added at header level, no new fields in this example
        ...
      }
    ]
  },
}
...
```

## <a name="appendix"></a>附錄

本附錄顯示了財務維度、**成本中心** 和 **項目** 整合在行級別的完整範例程式碼。

### <a name="taxintegrationlineobject_extensionxpp"></a>TaxIntegrationLineObject_Extension.xpp

```X++
[ExtensionOf(classStr(TaxIntegrationLineObject))]
final class TaxIntegrationLineObject_Extension
{
    private OMOperatingUnitNumber costCenter;
    private ProjId projectId;

    /// <summary>
    /// Gets a costCenter.
    /// </summary>
    /// <returns>The cost center.</returns>
    public final OMOperatingUnitNumber getCostCenter()
    {
        return this.costCenter;
    }

    /// <summary>
    /// Sets the cost center.
    /// </summary>
    /// <param name = "_value">The cost center.</param>
    public final void setCostCenter(OMOperatingUnitNumber _value)
    {
        this.costCenter = _value;
    }

    /// <summary>
    /// Gets a project ID.
    /// </summary>
    /// <returns>The project ID.</returns>
    public final ProjId getProjectId()
    {
        return this.projectId;
    }

    /// <summary>
    /// Sets the project ID.
    /// </summary>
    /// <param name = "_value">The project ID.</param>
    public final void setProjectId(ProjId _value)
    {
        this.projectId = _value;
    }
}
```

### <a name="taxintegrationpurchtabledataretrieval_extensionxpp"></a>TaxIntegrationPurchTableDataRetrieval_Extension.xpp

```X++
[ExtensionOf(classStr(TaxIntegrationPurchTableDataRetrieval))]
final class TaxIntegrationPurchTableDataRetrieval_Extension
{
    private const str CostCenterKey = 'CostCenter';
    private const str ProjectKey = 'Project';

    /// <summary>
    /// Copies to the current line of the document from.
    /// </summary>
    /// <param name = "_line">The current line of the document.</param>
    protected void copyToLineFromLineTable(TaxIntegrationLineObject _line)
    {
        Map dimensionAttributeMap = this.getDimensionAttributeMapByDefaultDimension(this.purchline.DefaultDimension);
        if (dimensionAttributeMap.exists(CostCenterKey))
        {
            _line.setCostCenter(dimensionAttributeMap.lookup(CostCenterKey));
        }
        if (dimensionAttributeMap.exists(ProjectKey))
        {
            _line.setProjectId(dimensionAttributeMap.lookup(ProjectKey));
        }
        next copyToLineFromLineTable(_line);
    }
    private Map getDimensionAttributeMapByDefaultDimension(RefRecId _defaultDimension)
    {
        DimensionAttribute dimensionAttribute;
        DimensionAttributeValue dimensionAttributeValue;
        DimensionAttributeValueSetItem dimensionAttributeValueSetItem;
        Map ret = new Map(Types::String, Types::String);
        select Name, RecId from dimensionAttribute
            join dimensionAttributeValue
                where dimensionAttributeValue.dimensionAttribute == dimensionAttribute.RecId
            join DimensionAttributeValueSetItem
                where DimensionAttributeValueSetItem.DimensionAttributeValue == DimensionAttributeValue.RecId
                    && DimensionAttributeValueSetItem.DimensionAttributeValueSet == _defaultDimension;
        while(dimensionAttribute.RecId)
        {
            ret.insert(dimensionAttribute.Name, dimensionAttributeValue.DisplayValue);
            next dimensionAttribute;
        }
        return ret;
    }
}
```

### <a name="taxintegrationcalculationactivityondocument_calculationservice_extensionxpp"></a>TaxIntegrationCalculationActivityOnDocument_CalculationService_Extension.xpp

```X++
[ExtensionOf(classStr(TaxIntegrationCalculationActivityOnDocument_CalculationService))]
final static class TaxIntegrationCalculationActivityOnDocument_CalculationService_Extension
{
    // Define key for the form in post request
    private const str IOCostCenter = 'Cost Center';
    private const str IOProject = 'Project';

    /// <summary>
    /// Copies to <c>TaxableDocumentLineWrapper</c> from <c>TaxIntegrationLineObject</c> by line.
    /// </summary>
    /// <param name = "_destination"><c>TaxableDocumentLineWrapper</c>.</param>
    /// <param name = "_source"><c>TaxIntegrationLineObject</c>.</param>
    protected static void copyToTaxableDocumentLineWrapperFromTaxIntegrationLineObjectByLine(Microsoft.Dynamics.TaxCalculation.ApiContracts.TaxableDocumentLineWrapper _destination, TaxIntegrationLineObject _source)
    {
        next copyToTaxableDocumentLineWrapperFromTaxIntegrationLineObjectByLine(_destination, _source);
        // Set the field we need to integrated for tax service
        _destination.SetField(IOCostCenter, _source.getCostCenter());
        _destination.SetField(IOProject, _source.getProjectId());
    }
}
```
