---
title: 埃及扣繳稅款申報
description: 本主題說明如何設定和生成埃及的預扣稅申報表。
author: sndray
ms.date: 03/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: ''
ms.search.region: Global
ms.author: sndray
ms.search.validFrom: 2017-06-20
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 8d78af13e0b3879afd0b6dae7b1a9ece651c3fd2
ms.sourcegitcommit: 7aa7d756e1e98a53da62e03c608a9597ef9893ea
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/20/2021
ms.locfileid: "8450945"
---
#  <a name="withholding-tax-declaration-for-egypt-eg-00005"></a>埃及扣繳稅款申報 (EG-00005)

[!include[banner](../includes/banner.md)]
[!include[banner](../includes/preview-banner.md)]

## <a name="overview"></a>概觀
本主題說明如何為埃及法人設定和生成預扣稅申報表和預扣稅申報表 41 和 11 

所有埃及實體都必須準備表格 41，該表格總結了從當地供應商和服務提供商處保留的所有稅款。 除了表格 41 之外，還必須生成表格 11，以詳細說明從外國供應商處徵稅的所有留存稅款。 

在 Dynamics 365 Finance 中 **預扣稅申報** 報到包括以下報告：

- 申報表編號 41
- 申報表編號 11
    
    
## <a name="prerequisites"></a>先決條件
法律實體的主要地址必須在埃及。
在 **功能管理** 工作區中必須啟用下列功能：

   - **全域扣繳稅款**

有關如何啟用此功能的資訊，請參閱[功能管理概述。](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)

1. 前往 **稅金** > **設定** > **參數** > **總帳參數**，然後在 **扣繳稅款** 索引標籤設定 **啟用全球扣繳稅款選項** 為 **是**。
2. 在裡面 **電子報告** 工作區，從存儲庫中導入以下電子報告格式：

    - 增值稅申報表 Excel (EG)

    > [!NOTE]
    > 以上格式基於 **納稅申報模式** 並使用 **納稅申報模型映射**。 其他配置將自動導入。

有關如何匯入電子申報設定的更多信息，請參閱[從 Lifecycle Services 下載電子報告設定](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md)。

## <a name="download-electronic-reporting-configurations"></a>下載電子報告組態

埃及預扣稅申報表的實施基於電子申報 (ER) 配置。 有關可設定報告的功能和概念的更多信息，請參閱[電子報告](../../fin-ops-core/dev-itpro/analytics/general-electronic-reporting.md)。

對於生產和使用者驗收測試 (UAT) 環境，請遵循標題[從 Lifecycle Services 下載電子報表設定](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md)中的說明進行作業。

要在埃及法人實體中生成預扣稅聲明，您需要上傳以下配置：

- 報稅 model.version.82.xml 或更新版本
- 報稅模型 mapping.version.82.133.xml 或更新版本
- 增值稅申報 Excel (EG).version.82.21 或更高版本

從 Lifecycle Services (LCS) 或全域存放庫完成下載 ER 設定後，請完成以下步驟。

1. 前往 **電子報表** 工作區中，選擇 **報表設定** 磚格。
1. 在 **設定** 頁面上，在動作窗格上，選取 **Exchange > 從 XML 檔案載入**。
1. 按照之前項目符號中列出的順序上傳所有檔案。 上傳所有設定後，設定樹應該出現在 Finance 中。

## <a name="set-up-application-specific-parameters"></a>設定應用程式特定參數

特定於應用程序的參數選項允許用戶根據配置在生成的報告的每一行中建立稅收交易如何分類和計算的標準 **代扣代繳稅項目組** 或在查找定義中建立的其他標準。

預扣稅申報表 41 包含一個特定欄目，在該欄目中，預扣稅交易必須按照指定的稅務機關分類進行分類 **折扣碼類型**. 在過帳交易時，不會將這些新分類作為新條目數據包括在內，而是將根據引入的不同查找來確定分類。**配置** > **設置特定於應用程序的參數** > **設置** 以滿足埃及預扣報告的要求。 

以下配置用於對扣繳申報表 41 報表中的交易進行分類：

- **DiscountTaxTypeLookup**-> 18 號欄 

完成以下步驟以設置用於生成增值稅申報和相關書籍報告的不同查找。 

1. 在裡面 **電子報告** 工作區，選擇 **配置** > **設置** 制定規則以識別交易在預扣稅申報報告中的分類方式。 
2. 選擇當前版本，然後在 **查找** FastTab，選擇查找名稱。 例如，**DiscountTaxTypeLookup**。 此查找標識稅務機關要求的折扣類型列表。
3. 在 **狀況** 快速選項卡，選擇 **添加** 並在新行中 **查找結果** 列，選擇代表分類的相關行 **18 欄**.
4. 在裡面 **代扣代繳稅項目組** 列，選擇用於標識分類的相關代碼。 例如，**允許折扣**。  
5. 對所有可用的查找重複步驟 3 和 4。
6. 再次選擇 **新增** 包括最後的記錄行，並在 **查找結果** 列，選擇 **不適用**。 
7. 在其餘列中，選擇 **非空白**。 

> [!NOTE]

## <a name="set-up-general-ledger-parameters"></a>設置總帳參數

若要在 Microsoft Excel 中生成預扣稅申報表報告，請在 **總帳參數** 頁面上定義 ER 格式。

1. 前往 **稅務** >  **設定**  >  **總帳參數**。
2. 在 **扣繳稅款** 索引標籤的 **WHT 申報格式對應** 欄位中，選擇 **WHT 申報 Excel (EG)**。 如果您將該欄位留空，將以 SSRS 格式生成標准銷售稅報告。


![申報表單。](media/egypt-wht-declaration-setup1.png)

## <a name="generate-the-withholding-declaration-forms"></a>生成預扣稅申報表
為特定期間準備和提交預扣稅申報表的過程基於在結算或繳稅後工作期間過帳的扣繳稅款交易。 有關全球預扣稅的更多資訊，請參閱[全球預扣稅](../general-ledger/global-withholding-tax-overview.md).

完成以下步驟以生成納稅申報報告。

1. 前往 **稅務** > **申報** > **扣繳稅款** > **扣繳稅款付款*。
2. 選擇結算期間，然後選擇報告的起始日期。 
3. 輸入交易日期，然後選擇 **確定**。
4. 在打開的對話框中，選擇一種或多種表單類型 **表單 41**、**表單 11** 或 **沒有**。 如果您選擇 **沒有**，生成標準報告。 
5. 選取語言。 所有報告都翻譯成 **en-us** 和 **ar-eg**。
6. 輸入將支付稅款的銀行的分行和名稱。
7. 選擇業務類型，然後輸入支票和單據編號。 
8. 輸入實體類型。 
9. 輸入註冊分配表格的人的姓名，然後選擇 **好的** 確認報告生成。 

 
[!INCLUDE[footer-include](../../includes/footer-banner.md)]
