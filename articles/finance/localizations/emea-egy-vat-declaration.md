---
title: 埃及加值稅申報
description: 本主題介紹如何為埃及設定和生成增值稅申報表。
author: sndray
ms.date: 06/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: ''
ms.search.region: Global
ms.author: sndray
ms.search.validFrom: 2017-06-20
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: a67c6e00b94d49b3eb279416407f603923e53b2e
ms.sourcegitcommit: 7aa7d756e1e98a53da62e03c608a9597ef9893ea
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/20/2021
ms.locfileid: "8450951"
---
#  <a name="vat-declaration-for-egypt-eg-00002"></a>埃及加值稅申報 (EG-00002)

[!include[banner](../includes/banner.md)]

[!include[banner](../includes/banner.md)]

本主題說明如何為埃及法人設置和生成增值稅申報表以及銷售和採購帳簿。

埃及增值稅申報表是匯總應繳銷項增值稅總額、可收回的進項增值稅總額以及相關增值稅應納稅額的官方文件。 該表格適用於所有類型的納稅人，應通過稅務機關門戶手動填寫。 增值稅申報表通常稱為增值稅申報表。

Dynamics 365 Finance 中的增值稅申報表包括以下報告：

- 增值稅申報表第 10 號，提供了增值稅申報表中每個行項目的金額、調整和增值稅金額的細目，如立法中所述。
- 銷售交易手冊
- 購買交易手冊

## <a name="prerequisites"></a>先決條件
法律實體的主要地址必須在埃及。
在 **功能管理** 工作區中啟用下列功能：

   - (埃及) 銷售和採購稅報告的類別層次結構。

有關如何啟用此功能的資訊，請參閱[功能管理概述](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)。

在裡面 **電子報告** 工作區，從存儲庫中匯入以下電子報告格式：

- 增值稅申報表 Excel (EG)

> [!NOTE]
> 以上格式基於 **納稅申報模式** 並使用 **納稅申報模型映射**。 其他設定將自動匯入。

有關如何匯入電子申報設定的更多信息，請參閱[從 Lifecycle Services 下載電子報告設定](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md)。

## <a name="download-electronic-reporting-configurations"></a>下載電子報告組態

埃及增值稅申報表的實施基於電子報告 (ER) 設定。 有關可設定報告的功能和概念的更多信息，請參閱[電子報告](../../fin-ops-core/dev-itpro/analytics/general-electronic-reporting.md)。

對於生產和使用者驗收測試 (UAT) 環境，請查看[從 Lifecycle Services 下載電子報表設定](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md)進行作業。

要在埃及法人實體中生成增值稅申報表和相關報告，請上傳以下設定：

- 報稅 model.version.70.xml 或更高版本
- 報稅模型 mapping.version.70.120.xml 或更高版本
- 增值稅申報 Excel (EG).version.70.32 或更高版本

從 Lifecycle Services (LCS) 或全域存放庫下載 ER 設定後，請完成以下步驟。

1. 前往 **電子報表** 工作區中，選擇 **報表設定** 磚格。
1. 在 **設定** 頁面上，在動作窗格上，選取 **Exchange**  > **從 XML 檔案載入**。
1. 按照上面列出的順序上傳檔案。 上傳所有設定後，設定樹應該出現在 Finance 中。

## <a name="set-up-application-specific-parameters"></a>設定應用程式特定參數

特定於應用程式的參數使您可以建立在生成報告時如何在每一行中分類和計算稅務交易的標準。 該確定基於項目銷售稅組、銷售稅組、銷售稅代碼和查找定義中建立的其他標準的設定。

埃及的銷售和採購帳簿報告包括一組列，這些列對應於特定交易分類，即埃及特定的操作、產品和文檔類型。 在過帳交易時，不會將這些新分類作為新條目數據包括在內，而是將根據引入的不同查找來確定分類。**設定** > **設置特定於應用程式的參數** > **設置** 以滿足埃及增值稅報告的要求。 

![應用程式特定參數頁面。](media/egypt-vat-declaration-setup1.png)

以下查找設定用於對採購和銷售增值稅帳簿報告中的交易進行分類：

- **採購項目類型查找**> O 欄：項目類型
- **增值稅率類型查找**> B 欄：稅種
- **增值稅率類型查找**> C 欄：資料表項目類型
- **購買操作類型查找**> A 欄：文件類型
- **客戶類型查找**> A 欄：文件類型
- **銷售操作類型查找**> N 欄：操作類型
- **SalesItemTypeLookup**> O 欄：項目類型

完成以下步驟以設置用於生成增值稅申報和相關書籍報告的不同查找。 

1. 在裡面 **電子報告** 工作區，選擇 **設定** > **設置** 在增值稅申報表的相關框中設置識別稅收交易的規則。
2. 選擇當前版本，然後在 **查找** FastTab，選擇查找名稱。 例如，**銷售項目類型查找**。 此查找標識稅務機關要求的銷售增值稅帳簿中的分類列表。
3. 在 **狀況** 快速選項卡，選擇 **添加** 並在新行中 **查找結果** 列，選擇代表分類的相關行 **O 欄**。
4. 在裡面 **營業稅組** 列，選擇用於標識分類的增值稅組。 例如，**國內銷售發票**。 如果設定以其他方式定義，您還可以使用物料銷售稅組、稅碼或樹屬性的組合。 
5. 在裡面 **姓名** 列，選擇稅務交易分類。
6. 對所有可用的查找重複步驟 3-5。
7. 選擇 **添加** 包括最後的記錄行，並在 **查找結果** 列，選擇 **不適用**。 
8. 在其餘列中，選擇 **非空白**。 
9. 在 **狀態** 欄位中，選取 **已完成**。
10. 選擇 **儲存**，然後關閉 **特定應用參數** 頁面。

> [!NOTE]
> 添加最後一條記錄時，**不適用**，您定義以下規則：當作為參數傳遞的銷售稅組、項目銷售稅組、稅碼和名稱不滿足任何前面的規則時，交易記錄不包含在銷售增值稅帳簿中。 雖然在生成報告時不使用此規則，但當缺少規則設定時，該規則確實有助於避免報告生成錯誤。

下表代表所描述的查找設定的建議設定範例。 

**SalesItemTypeLookup**

| 查閱結果         | 行 | 銷售稅群組    | 品項銷售稅群組    | 稅代碼 (Code) | 姓名                  |
|-----------------------|------|--------------------|-------------------------|-----------------|-----------------------|
| 國內              | 1    | VAT_LOCAL          | *非空白*             | *非空白*     | 銷售                 |
| 國內              | 2    | VAT_LOCAL          | *非空白*             | *非空白*     | SalesCreditNote       |
| 國內              | 3    | VAT_FINALC         | *非空白*             | *非空白*     | 銷售                 |
| 國內              | 4    | VAT_FINALC         | *非空白*             | *非空白*     | SalesCreditNote       |
| 國內              | 5    | VAT_PUBLIO         | *非空白*             | *非空白*     | 銷售                 |
| 國內              | 6    | VAT_PUBLIO         | *非空白*             | *非空白*     | SalesCreditNote       |
| 匯出                | 7    | VAT_EXPORT         | *非空白*             | *非空白*     | 銷售                 |
| 匯出                | 8    | VAT_EXPORT         | *非空白*             | *非空白*     | SalesCreditNote       |
| 機器和設備 | 9    | *非空白*        | VAT_M&E                 | *非空白*     | 銷售                 |
| 機器和設備 | 10   | *非空白*        | VAT_M&E                 | *非空白*     | SalesCreditNote       |
| 零件機器        | 11   | *非空白*        | VAT_PARTS               | *非空白*     | 銷售                 |
| 零件機器        | 12   | *非空白*        | VAT_PARTS               | *非空白*     | SalesCreditNote       |
| 豁免            | 13   | VAT_EXE            | *非空白*           | *非空白*     | SaleExempt            |
| 豁免            | 14   | VAT_EXE            | *非空白*           | *非空白*     | SalesExemptCreditNote |
| 不適用        | 15   | *空白*            | *空白*                 | VAT_ADJ         | *非空白*           |
| 不適用        | 16   | *非空白*        | *非空白*             | *非空白*     | *非空白*           |

 **SalesOperationTypeLookup**

| 查閱結果  | 行 | 品項銷售稅群組    | 稅務代碼    | 姓名                  |
|----------------|------|-------------------------|-------------|-----------------------|
| 商品          | 1    | VAT_GOODS               | *非空白* | 銷售                 |
| 商品          | 2    | VAT_GOODS               | *非空白* | SalesCreditNote       |
| 商品          | 3    | VAT_GOODS               | *非空白* | SaleExempt            |
| 商品          | 4    | VAT_GOODS               | *非空白* | SalesExemptCreditNote |
| 服務       | 5    | VAT_SERV                | *非空白* | 銷售                 |
| 服務       | 6    | VAT_SERV                | *非空白* | SalesCreditNote       |
| 服務       | 7    | VAT_SERV                | *非空白* | SaleExempt            |
| 服務       | 8    | VAT_SERV                | *非空白* | SalesExemptCreditNote |
| 調整    | 9    | *空白*                 | VAT_ADJ     | 銷售                 |
| 調整    | 10   | *空白*                 | VAT_ADJ     | SalesCreditNote       |
| 不適用 | 11   | *非空白*             | *非空白* | *非空白*           |

**PurchaseItemTypeLookup**

| 查閱結果          | 行 | 品項銷售稅群組    | 稅務代碼    | 姓名                     |
|------------------------|------|-------------------------|-------------|--------------------------|
| 商品                  | 1    | VAT_GOODS               | *非空白* | 採購                 |
| 商品                  | 2    | VAT_GOODS               | *非空白* | PurchaseCreditNote       |
| 服務               | 3    | VAT_SERV                | *非空白* | 採購                 |
| 服務               | 4    | VAT_SERV                | *非空白* | PurchaseCreditNote       |
| 機器和設備  | 5    | VAT_M&E                 | *非空白* | 採購                 |
| 機器和設備  | 6    | VAT_M&E                 | *非空白* | PurchaseCreditNote       |
| 零件機器         | 7    | VAT_PARTS               | *非空白* | 採購                 |
| 零件機器         | 8    | VAT_PARTS               | *非空白* | PurchaseCreditNote       |
| 豁免             | 9    | VAT_EXE                 | *非銀行*  | PurchaseExempt           |
| 豁免             | 10   | VAT_EXE                 | *非空白* | PurchaseExemptCreditNote |
| 不適用         | 11   | *非空白*             | *非空白* | *非空白*              |

**PurchaseOperationTypeLookup**

| 查閱結果  | 行 | 銷售稅群組  | 稅務代碼    | 姓名                     |
|----------------|------|------------------|-------------|--------------------------|
| 國內       | 1    | VAT_LOCAL        | *非空白* | 採購                 |
| 國內       | 2    | VAT_LOCAL        | *非空白* | PurchaseCreditNote       |
| 國內       | 3    | VAT_LOCAL        | *非空白* | PurchaseExempt           |
| 國內       | 4    | VAT_LOCAL        | *非空白* | PurchaseExemptCreditNote |
| 已匯入       | 5    | VAT_IMPORT       | *非空白* | 採購                 |
| 已匯入       | 6    | VAT_IMPORT       | *非空白* | PurchaseCreditNote       |
| 已匯入       | 7    | VAT_IMPORT       | *非空白* | PurchaseExempt           |
| 已匯入       | 8    | VAT_IMPORT       | *非空白* | PurchaseExemptCreditNote |
| 調整    | 9    | *空白*          | VAT_ADJ     | PurchaseCreditNote       |
| 調整    | 10   | *空白*          | VAT_ADJ     | 採購                 |
| 不適用 | 11   | *非空白*      | *非空白* | *非空白*              |

**CustomerTypeLookup**

|    查閱結果    | 行 | 銷售稅群組 |
|---------------------|------|-----------------|
| 組織        |  1   | VAT_LOCAL       |
| 組織        |  2   | VAT_EXPORT      |
| 組織        |  3   | VAT_EXE         |
| 最終消費者      |  4   | VAT_FINALC      |
| 公共組織 |  5   | VAT_PUBLIO      |
| 不適用      |  6   | *非空白*     |

**VATRateTypeLookup**

| 查閱結果  | 行 | 稅代碼 (Code) |
|----------------|------|-----------------|
| 雜貨   | 1    | VAT_ST          |
| 雜貨   | 2    | VAT_RD          |
| FirstTable     | 3    | *非空白*     |
| SecondTable    | 4    | *非空白*     |
| 不適用 | 5    | *非空白*     |


## <a name="set-up-general-ledger-parameters"></a>設置總帳參數

生成增值稅申報表報告Microsoft Excel格式，定義一個 ER 格式 **總帳參數** 頁。

1. 前往 **稅務** >  **設定**  >  **總帳參數**。
2. 在 **銷售稅** 選項卡，在 **稅收選擇** 部分，在 **增值稅報表格式映射** 欄位，選擇 **增值稅申報表 Excel (EG)**。 如果您將該欄位留空，將以 SSRS 格式生成標准銷售稅報告。
3. 選擇 **類別階層**。 該分類使外貿選項卡交易中的商品代碼允許用戶對商品和服務進行選擇和分類。 此分類的描述在銷售和採購交易報告中有詳細說明。 此組太為選擇性選項。

![申報表單。](media/egypt-vat-declaration-setup2.png)


## <a name="generate-a-vat-return-report"></a>產生增值稅傳回報表
準備和提交某個期間的增值稅申報表的過程基於在結算和過帳銷售稅作業期間過帳的銷售稅支付交易記錄。 有關銷售稅結算和報告的更多信息，請參閱[營業稅概覽](../general-ledger/indirect-taxes-overview.md)。

完成以下步驟以生成納稅申報報告。

1. 去 **稅** > **聲明** > **銷售稅** > **報告結算期間的銷售稅** 要么 **結算和過帳銷售稅**。
2. 選擇 **結算期**。
3. 選擇起始日期，然後選擇銷售稅支付版本。
5. 選擇 **確定**。 
6. 輸入上一期間的貸記金額 (如果適用)，或將金額保留為零。
7. 在裡面 **報告詳情** 欄位，選擇以下可用選項之一。 
   - **購買增值稅帳簿**：生成購置稅交易明細報表。
   - **銷售增值稅帳簿**：生成銷售稅交易明細報表。
   - **增值稅申報**：只生成增值稅申報表。
8. 輸入註冊分配表格的人的姓名。
9. 選取語言。 所有報告都翻譯成 **en-us** 和 **ar-eg**。
  
[!INCLUDE[footer-include](../../includes/footer-banner.md)]


