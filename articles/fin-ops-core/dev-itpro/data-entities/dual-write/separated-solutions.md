---
title: 分離的雙重寫入應用程式協調流程封裝
description: 雙重寫入應用程式協調流程封裝不再是單個封裝，而是被分成更小的封裝。 本主題解釋了每個封裝所包含的解決方案和地圖服務，以及它對其他封裝的相依性。
author: RamaKrishnamoorthy
ms.date: 11/29/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.custom: separate-solution
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2021-11-29
ms.openlocfilehash: e2f870368dc662032a3e7ca7ddca902feb23a713
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8460590"
---
# <a name="separated-dual-write-application-orchestration-package"></a>分離的雙重寫入應用程式協調流程封裝

[!include [banner](../../includes/banner.md)]



以前，雙重寫入應用程式協調流程封裝是包含以下解決方案的單個封裝：

- Dynamics 365 Notes
- Dynamics 365 Finance 和營運常見錨點
- Dynamics 365 Finance 和營運雙重寫入實體地圖服務
- Dynamics 365 資產管理應用程式
- Dynamics 365 資產管理
- HCM 一般
- Dynamics 365 Supply Chain 擴展
- Dynamics 365 Finance Extended
- Dynamics 365 Finance 和營運常見
- Dynamics 365 公司
- 貨幣匯率
- Field Service Common

因為它是單一的封裝，所以這個封裝為客戶創造了「全有或全無」的情況。 但是，Microsoft 現在已經將它分成更小的封裝。 因此，客戶可以只選取他們需要的解決方案的封裝。 例如，如果您是 Microsoft Dynamics 365 Supply Chain Management 客戶，並且不需要與 Dynamics 365 Human Resources、Notes 和資產管理整合，則可以從已安裝的解決方案中排除這些解決方案。 由於基礎解決方案名稱、發行者和地圖版本保持不變，因此此更改不會中斷。 升級現有的安裝。

![分離的封裝。](media/separated-package-1.png)

本主題解釋了每個封裝所包含的解決方案和地圖服務，以及它對其他封裝的相依性。

## <a name="dual-write-application-core"></a>雙重寫入應用程式核心

雙重寫入應用程式核心封裝讓使用者無需任何客戶業務開發應用程式即可安裝和設定雙重寫入。 它包含以下五個解決方案。

| 唯一名稱                           | 顯示名稱                               |
|---------------------------------------|--------------------------------------------|
| Dynamics365Company                    | Dynamics 365 公司                       |
| Dynamics365FinanceAndOperationsCommon | Dynamics 365 Finance 和營運常見 |
| CurrencyExchangeRates                 | 貨幣匯率                    |
| msdyn_DualWriteAppCoreMaps            | 雙重寫入應用程式核心實體圖   |
| msdyn_DualWriteAppCoreAnchor          | 雙重寫入應用程式核心錨點        |

此封裝中提供以下地圖服務：

| 財務和營運應用程式     | 客戶業務開發應用程式                    |
|---------------------------------|---------------------------------------------|
| 營運單位                  | msdyn_internalorganizations                 |
| 組織階層          | msdyn_internalorganizationhierarchies       |
| 法律實體                  | msdyn_internalorganizations                 |
| 法律實體                  | cdm_companies                               |
| 組織階層目的 | msdyn_internalorganizationhierarchypurposes |
| 匯率貨幣對     | msdyn_currencyexchangeratepairs             |
| 名稱附加                    | msdyn_nameaffixes                           |
| 匯率類型              | msdyn_exchangeratetypes                     |
| CDS 匯率              | msdyn_currencyexchangerates                 |
| 組織階層類型     | msdyn_internalorganizationhierarchytypes    |
| 貨幣                      | transactioncurrencies                       |
| 混合實境指南實體     | msmrw_guides                                |

**相依性資訊**

雙重寫入應用程式核心封裝與其他封裝沒有相依性。

## <a name="dual-write-human-resources"></a>雙重寫入 Human Resources

雙重寫入 Human Resources 封裝包含同步 Human Resources 資料所需的解決方案和地圖。 它包含以下三個解決方案。

| 唯一名稱                | 顯示名稱                             |
|----------------------------|------------------------------------------|
| HCMCommon                  | HCM 一般                               |
| msdyn_Dynamics365HCMMaps   | Dynamics 365 Human Resources 實體圖 |
| msdyn_Dynamics365HCMAnchor | Dynamics 365 Human Resources 錨點      |

此封裝中提供以下地圖服務：

| 財務和營運應用程式 | 客戶業務開發應用程式         |
|-----------------------------|----------------------------------|
| 種族血統              | cdm_ethnicorigins                |
| 薪酬工作職能   | cdm_jobfunctions                 |
| 職位 V2                | cdm_jobpositions                 |
| 工作                        | cdm_jobs                         |
| 薪酬工作類型       | cdm_jobtypes                     |
| 語言代碼              | cdm_languages                    |
| 職位類型               | cdm_positiontypes                |
| 職位工作者指派 | cdm_positionworkerassignmentmaps |
| 專家狀態              | cdm_veteranstatuses              |
| 工作人員                      | cdm_workers                      |
| 每家公司的就業人數      | cdm_employments                  |

**相依性資訊**

雙重寫入 Human Resources 封裝依賴於雙重寫入應用程式核心封裝。 因此，您應該在安裝雙重寫入 Human Resources 封裝之前安裝雙重寫入應用程式核心封裝。

## <a name="dual-write-supply-chain"></a>雙重寫入 Supply Chain

雙重寫入 Supply Chain 封裝包含同步 Supply Chain Management 資料所需的解決方案和地圖。 它包含以下三個解決方案。

| 唯一名稱                                | 顯示名稱                                              |
|--------------------------------------------|-----------------------------------------------------------|
| Dynamics365SupplyChainExtended             | Dynamics 365 Supply Chain 擴展                        |
| msdyn_Dynamics365SupplyChainExtendedMaps   | Dynamics 365 Supply Chain Management 擴展實體圖 |
| msdyn_Dynamics365SupplyChainExtendedAnchor | Dynamics 365 Supply Chain Management 擴展錨點      |

此封裝中提供以下地圖服務：

| 財務和營運應用程式                 | 客戶業務開發應用程式                      |
|---------------------------------------------|-----------------------------------------------|
| 單位                                       | uoms                                          |
| CDS 銷售訂單標題                     | salesorders                                   |
| CDS 銷售訂單明細                       | salesorderdetails                             |
| CDS 銷售報價單標題                  | 報價                                        |
| CDS 銷售報價單明細                   | quotedetails                                  |
| CDS 發佈獨特產品              | 產品                                      |
| 倉庫區域                             | msdyn_warehousezones                          |
| 倉庫區域群組                       | msdyn_warehousezonegroups                     |
| 倉庫工作明細                        | msdyn_warehouseworklines                      |
| 倉庫工作標題                      | msdyn_warehouseworkheaders                    |
| 倉庫                                  | msdyn_warehouses                              |
| 庫存通道                             | msdyn_warehouseaisles                         |
| 單位轉換                            | msdyn_unitofmeasureconversions                |
| 交貨條件                           | msdyn_termsofdeliveries                       |
| 交貨模式                           | msdyn_shipvias                                |
| 基準產品樣式                       | msdyn_sharedproductstyles                     |
| 銷售發票明細 V2                      | invoicedetails                                |
| 銷售發票標題 V2                    | 發票                                      |
| 基準產品大小                        | msdyn_sharedproductsizes                      |
| 已發佈產品 V2                        | msdyn_sharedproductdetails                    |
| 基準產品設定               | msdyn_sharedproductconfigurations             |
| 基準產品顏色                       | msdyn_sharedproductcolors                     |
| 銷售訂單來源代碼                    | msdyn_salesorderorigins                       |
| 產品收據抬頭                      | msdyn_purchaseorderreceipts                   |
| 產品收據明細                        | msdyn_purchaseorderreceiptproducts            |
| 訂購單抬頭 V2                   | msdyn_purchaseorders                          |
| CDS 訂購單明細虛刪除實體 | msdyn_purchaseorderproducts                   |
| CDS 訂購單明細實體              | msdyn_purchaseorderproducts                   |
| 追蹤維度群組                   | msdyn_producttrackingdimensiongroups          |
| 樣式                                      | msdyn_productstyles                           |
| 儲存維度群組                    | msdyn_productstoragedimensiongroups           |
| 產品專用單位換算           | msdyn_productspecificunitofmeasureconversions |
| 產品預設訂單設定 V2           | msdyn_productspecificdefaultordersettings     |
| 尺寸                                       | msdyn_productsizes                            |
| 產品尺寸群組                    | msdyn_productdimensiongroups                  |
| 預設訂單設定值                      | msdyn_productdefaultordersettings             |
| 配置                              | msdyn_productconfigurations                   |
| 所有產品                                | msdyn_globalproducts                          |
| 色彩                                      | msdyn_productcolors                           |
| 產品類別階層角色            | msdyn_productcategoryhierarchyroles           |
| 產品類別階層                | msdyn_productcategoryhierarchies              |
| 產品類別指派                | msdyn_productcategoryassignments              |
| 產品類別                          | msdyn_productcategories                       |
| 倉庫位置                         | msdyn_inventorylocations                      |
| CDS 庫存在                            | msdyn_inventoryonhandentries                  |
| 產品類別                          | msdyn_productcategories                       |
| CDS 庫存在                            | msdyn_inventoryonhandrequests                 |
| 產品編號識別的條碼           | msdyn_productbarcodes                         |
| 會員卡                                | msdyn_loyaltycards                            |
| 忠誠獎勵點數                       | msdyn_loyaltyrewardpoints                     |
| 價格客戶群組                       | msdyn_pricecustomergroups                     |
| 網站                                       | msdyn_operationalsites                        |
| CDS 銷售報價單明細                   | quotedetails                                  |
| CDS 銷售訂單明細                       | salesorderdetails                             |

**相依性資訊**

雙重寫入 Supply Chain 封裝依賴於以下三個封裝。 因此，您應該在安裝雙重寫入 Supply Chain 封裝之前安裝這些封裝。

- 雙重寫入應用程式核心封裝
- 雙重寫入 Finance 封裝
- 雙重寫入 Human Resources 封裝

## <a name="dual-write-finance"></a>雙重寫入 Finance

雙重寫入 Finance 封裝包含同步 Dynamics 365 Finance 資料所需的解決方案和地圖。 它包含以下四個解決方案。

| 唯一名稱                            | 顯示名稱                               |
|----------------------------------------|-------------------------------------------|
| Dynamics365FinanceExtended             | Dynamics 365 Finance Extended             |
| msdyn_Dynamics365FinanceExtendedMaps   | Dynamics 365 Finance Extended 實體圖 |
| FieldServiceCommon                     | Field Service Common                      |
| msdyn_Dynamics365FinanceExtendedAnchor | Dynamics 365 Finance Extended 錨點      |

此封裝中提供以下地圖服務：

| 財務和營運應用程式             | 客戶業務開發應用程式        |
|-----------------------------------------|---------------------------------|
| 扣繳稅款群組                  | msdyn_withholdingtaxgroups      |
| CDS 聯絡人 V2 (客戶)              | 聯絡人                        |
| CDS 聯絡人 V2 (廠商)                | 聯絡人                        |
| 客戶 V3                            | 聯絡人                        |
| 扣繳稅款代碼                   | msdyn_withholdingtaxcodes       |
| 廠商 V2                              | msdyn_vendors                   |
| 廠商付款方式                   | msdyn_vendorpaymentmethods      |
| 廠商群組                           | msdyn_vendorgroups              |
| 會計科目表                       | msdyn_chartofaccountses         |
| 銷售稅分類帳過帳群組 V2      | msdyn_taxpostinggroups          |
| 品項銷售稅群組                    | msdyn_taxitemgroups             |
| 銷售稅金群組                        | msdyn_taxgroups                 |
| 銷售稅免稅代碼實體 CDS        | msdyn_taxexemptcodes            |
| 客戶群組                         | msdyn_customergroups            |
| 客戶付款方式                 | msdyn_customerpaymentmethods    |
| 財務維度                    | msdyn_dimensionattributes       |
| 銷售稅主管機構                   | msdyn_taxauthorities            |
| 財務維度格式              | msdyn_financialdimensionformats |
| 會計行事曆期間                  | msdyn_fiscalcalendarperiods     |
| 會計行事曆整合實體      | msdyn_fiscalcalendars           |
| 會計行事曆年度整合實體 | msdyn_fiscalcalendaryears       |
| 付款條款                        | msdyn_paymentterms              |
| 付款排程                        | msdyn_paymentschedules          |
| 付款排程明細                  | msdyn_paymentschedulelines      |
| 付款日 CDS                        | msdyn_paymentdays               |
| 付款日明細 CDS V2                | msdyn_paymentdaylines           |
| 主科目                            | msdyn_mainaccounts              |
| 主科目類別                 | msdyn_mainaccountcategories     |
| 分類帳                                  | msdyn_ledgers                   |
| 客戶 V3                            | 客戶                        |

**相依性資訊**

雙重寫入 Finance 封裝依賴於雙重寫入應用程式核心封裝。 因此，您應該在安裝雙重寫入 Finance 封裝之前安裝雙重寫入應用程式核心封裝。

## <a name="dual-write-notes"></a>雙重寫入 Notes

雙重寫入 Notes 封裝包含同步附註和註釋資料所需的解決方案和地圖。 它包含以下四個解決方案。

| 唯一名稱                  | 顯示名稱                   |
|------------------------------|--------------------------------|
| Dynamics365Notes             | Dynamics 365 Notes             |
| Dynamics365NotesExtended     | Dynamics 365 notes extended    |
| msdyn_Dynamics365NotesMaps   | Dynamics 365 Notes 實體圖 |
| msdyn_Dynamics365NotesAnchor | Dynamics 365 Notes 錨點      |

此封裝中提供以下地圖服務：

| 財務和營運應用程式                     | Customer Engagement |
|--------------------------------------------|---------------------|
| 銷售訂單抬頭檔案附件    | 註釋         |
| 客戶附件                       | 註釋         |
| 廠商檔案附件                | 註釋         |
| 訂購單抬頭檔案附件 | 註釋         |

**相依性資訊**

雙重寫入 Notes 封裝依賴於以下兩個封裝。 因此，您應該在安裝雙重寫入 Notes 封裝之前安裝這些封裝。

- 雙重寫入應用程式核心封裝
- 雙重寫入 Finance 封裝

## <a name="dual-write-asset-management"></a>雙重寫入資產管理

雙重寫入資產管理封裝包含從 Supply Chain Management 或 Dynamics 365 Field Service 同步資產資料所需的解決方案和地圖。 它包含以下四個解決方案。

| 唯一名稱                          | 顯示名稱                              |
|--------------------------------------|-------------------------------------------|
| Dynamics365AssetManagement           | Dynamics 365 資產管理             |
| Dynamics365AssetManagementApp        | Dynamics365 資產管理應用程式          |
| msdyn_DualWriteAssetManagementMaps   | Dynamics 365 資產管理實體圖 |
| msdyn_DualWriteAssetManagementAnchor | Dynamics 365 資產管理錨點      |

此封裝中提供以下地圖服務：

| 財務和營運應用程式                           | 客戶業務開發應用程式                |
|-------------------------------------------------------|-----------------------------------------|
| 資產管理保固                             | msdyn_warranties                        |
| 資產管理模型                               | msdyn_models                            |
| 資產管理製造商                        | msdyn_manufacturers                     |
| 資產管理機能位置類型            | msdyn_functionallocationtypes           |
| 資產管理機能位置                 | msdyn_functionallocations               |
| 資產管理機能位置生命週期狀態 | msdyn_functionallocationlifecyclestates |
| 資產管理機能位置生命週期模型 | msdyn_functionallocationlifecyclemodels |
| 資產管理資產                               | msdyn_customerassets                    |
| 資產管理資產類型                          | msdyn_customerassetcategories           |
| 資產管理資產生命週期狀態               | msdyn_assetlifecyclestates              |
| 資產管理資產生命週期模型               | msdyn_assetlifecyclemodels              |

**相依性資訊**

雙重寫入資產管理封裝依賴於雙重寫入應用程式核心封裝。 因此，您應該在安裝雙重寫入資產管理封裝之前安裝雙重寫入應用程式核心封裝。

## <a name="packages-required-for-project-operations"></a>Project Operations 所需的封裝
Project Operations 依賴於以下封裝。 因此，您應該在安裝 Project Operations 之前安裝這些封裝。

- 雙重寫入應用程式核心封裝
- 雙重寫入 Finance 封裝
- 雙重寫入 Supply Chain 封裝
- 雙重寫入資產管理封裝
- 雙重寫入 Human Resources 封裝
