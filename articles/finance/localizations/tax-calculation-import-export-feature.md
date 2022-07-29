---
title: 匯入及匯出稅務計算
description: 本主題提供有關稅務計算服務的匯入和匯出功能的資訊。
author: Kai-Cloud
ms.date: 11/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-11-15
ms.dyn365.ops.version: 10.0.23
ms.openlocfilehash: 76ea99510455e984d94a93d87ee788fdcf00c376
ms.sourcegitcommit: c85eac17fbfbd311288b50664f9e2bae101c1fe6
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/03/2021
ms.locfileid: "8451281"
---
# <a name="import-and-export-tax-calculations"></a>匯入及匯出稅務計算

本主題提供有關稅務計算服務的匯入和匯出功能的資訊。 此功能有助於確保靈活高效的設定體驗。

## <a name="import-and-export-tax-codes"></a>匯入及匯出稅碼

### <a name="export-templates"></a>匯出範本

1. 登入 [Regulatory Configuration Service (RCS)](https://marketing.configure.global.dynamics.com/)。
2. 請在 **全球化功能** 工作區選取 **功能**，接著選取 **稅務計算** 圖格。
3. 選取現有功能，或[建立新功能](global-get-started-with-tax-calculation-service.md#set-up-tax-calculation-in-rcs)。
4. 在 **版本** 格線內選擇 **編輯**。
5. 在 **稅務計算** 功能頁面，設置[設定版本](global-get-started-with-tax-calculation-service.md#set-up-tax-calculation-in-rcs)。
6. 在 **稅碼** 索引標籤選擇 **匯入**。
7. 選擇 **匯出稅碼範本**，下載 **TaxCodesTemplate.zip** 檔案。
8. 將 **TaxCodesTemplate.zip** 解壓縮。 根據 **計算來源** 值將稅碼範本分別解壓縮。
9. 將 **By Net Amount.zip** 解壓縮以獲取下列逗號分隔值 (CSV) 檔案: 

    - **TaxCode.csv**–輸入稅碼。
    - **TaxLimit.csv**–輸入每個稅碼的稅金限制。
    - **TaxRate.csv**–輸入每個稅碼的稅率。

> [!NOTE]
> 依預設，可在範本中使用 **樣本** 稅碼項目。 如果 **樣本** 稅碼沒有從 CSV 檔案刪除，它將會被匯入到功能中。

### <a name="import-tax-codes"></a>匯入稅碼

按照以下步驟將範本中的 **樣本** 稅碼匯入至您的稅務計算功能中。

1. 在 RCS 中，在 **稅務計算** 功能頁面的 **稅碼** 索引標籤選擇 **匯入**。
2. 選擇 **瀏覽**, 尋找並選擇 **TaxCode.csv** 檔案，然後在 **目標資料表** 欄位選擇 **稅碼**。
3. 選擇 **確定** 以匯入稅碼。
4. 尋找並選擇 **TaxRate.csv** 檔案，然後在 **目標資料表** 欄位選擇 **稅率**。
5. 選擇 **確定** 以匯入稅率。
6. 尋找並選擇 **TaxLimit.csv** 檔案，然後在 **目標資料表** 欄位選擇 **稅金限制**。
7. 選擇 **確定** 以匯入稅金限制。

您也可以直接匯入包含所有三個 CSV 檔案的 ZIP 檔案。 如此一來，您可以快速輕鬆地完成匯入。

1. 在 RCS 中，在 **稅務計算** 功能頁面的 **稅碼** 索引標籤選擇 **匯入**。
2. 選擇 **瀏覽**，尋找並選擇 **By Net Amount.zip** 檔案，然後選擇 **確定**。

### <a name="export-tax-codes"></a>匯出稅碼

1. 在 RCS 中，在 **稅務計算** 功能頁面的 **稅碼** 索引標籤選擇 **匯出**。

    在 **稅碼** 格線至少有一個稅碼時可使用此 **匯出** 按鈕。

2. 選擇 **確定** 將功能的所有稅碼以 ZIP 檔案匯出。

> [!NOTE]
> 使用匯出的檔案作為範本，將稅碼匯入相應的功能。

## <a name="import-and-export-applicability-rules"></a>匯入及匯出適用性規則

### <a name="export-applicability-rules"></a>匯出適用性規則

1. 登入 [RCS](https://marketing.configure.global.dynamics.com/)。
2. 請在 **全球化功能** 工作區選取 **功能**，接著選取 **稅務計算** 圖格。
3. 選取現有功能，或[建立新功能](global-get-started-with-tax-calculation-service.md#set-up-tax-calculation-in-rcs)。
4. 在 **版本** 格線內選擇 **編輯**。
5. 在 **稅務計算** 功能頁面，設置[設定版本](global-get-started-with-tax-calculation-service.md#set-up-tax-calculation-in-rcs)。
6. 在 **稅組適用性** 索引標籤，選擇 **設定稅組適用性** 格線內的列。
7. 選擇 **開啟 Microsoft Office** 按鈕，然後選擇 **稅務服務動態適用性矩陣**。

    [![將適用性規則匯出到稅收計算功能頁面上的 Microsoft Excel。](./media/tax-cal-import-export-1.png)](./media/tax-cal-import-export-1.png)

8. 選擇 **下載** 將選定的列匯出到 Microsoft Excel工作表。

### <a name="import-applicability-rules"></a>匯入適用性規則

您下載的 Excel 工作表包含 **設定稅組適用性** 格線的架構。 您可以直接在工作表中新增新規則。 完成後，按照以下步驟將新規則匯入回 **設定稅組適用性** 格線。

1. 在 Excel 工作表中，選擇並複製要匯入的列。
2. 在 RCS 中，在 **稅務計算** 功能頁面，在 **稅組適用性** 索引標籤，選擇 **新增** 以在 **設定稅組適用性** 格線底部插入一條空記錄。
3. 選擇 **Ctrl+V** 將複製的列貼至格線內。
4. 選擇 **儲存**。
