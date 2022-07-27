---
title: 將潛在客戶從資料整合者移轉到現金資料以進行雙重寫入
description: 本主題介紹如何將潛在客戶到現金資料從資料整合者移轉到雙重寫入。
author: RamaKrishnamoorthy
ms.date: 02/01/2022
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-26
ms.openlocfilehash: 82bfb768b0ecac04184f4b806527346d39584d64
ms.sourcegitcommit: 7893ffb081c36838f110fadf29a183f9bdb72dd3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/02/2022
ms.locfileid: "8460558"
---
# <a name="migrate-prospect-to-cash-data-from-data-integrator-to-dual-write"></a>將潛在客戶從資料整合者移轉到現金資料以進行雙重寫入

[!include [banner](../../includes/banner.md)]

可用於資料整合者的從潛在客戶到現金解決方案與雙重寫入不相容。 原因是作為從潛在客戶到現金解決方案的一部分的會計表上的 msdynce_AccountNumber 索引。 如果存在此索引，則您無法在兩個不同的法律實體中建立相同的客戶帳號。 您可以選取透過將從潛在客戶到現金資料從資料整合者移轉到雙重寫入來重新開始雙重寫入，或者您可以安裝從潛在客戶到現金解決方案的最後一個「休眠」版本。 本主題涵蓋了這兩種方法。

## <a name="install-the-last-dorman-version-of-the-data-integrator-prospect-to-cash-solution"></a>安裝資料整和者從潛在客戶到現金解決方案的最後一個「休眠」版本

**P2C 版本 15.0.0.2** 被認為是資料整合者從潛在客戶到現金解決方案的最後一個「休眠」版本。 您可以從[FastTrack for Dynamics 365](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/Dual-write/P2C)下載。

您需要手動安裝它。 安裝後，一切都保持不變，除了 msdynce_AccountNumber 索引被刪除。

## <a name="steps-to-migrate-prospect-to-cash-data-from-data-integrator-to-dual-write"></a>將從潛在客戶到現金資料從資料整合者移轉到雙重寫入的步驟

若要將從潛在客戶到現金資料從資料整合者移轉到雙重寫入，請執行以下步驟。

1. 執行從潛在客戶到現金資料整合者作業以進行最後一次完全同步。 透過這種方式，您可以確保兩個系統 (財務和營運應用程式和客戶業務開發應用程式) 都擁有所有資料。
2. 若要幫助防止潛在的資料遺失，請將 Microsoft Dynamics 365 Sales 中的從潛在客戶到現金資料匯出到 Excel 檔案或逗號分隔值 (CSV) 檔案。 從以下實體匯出資料：

    - [客戶](#account-table)
    - [連絡人](#contact-table)
    - [發票](#invoice-table)
    - 發票產品
    - [訂單](#order-table)
    - [訂單產品](#order-products-table)
    - [產品](#products-table)
    - [報價](#quote-and-quote-product-tables)
    - [報價產品](#quote-and-quote-product-tables)

3. 從 Sales 環境中解除安裝從潛在客戶到現金解決方案。 此步驟將刪除從潛在客戶到現金解決方案引入的資料欄和相應資料。
4. 安裝雙重寫入解決方案。
5. 在財務和營運應用程式和一個或多個法律實體的客戶業務開發應用程式之間建立雙重寫入連線。
6. 啟用雙重寫入表對應，並為所需的參考資料執行初始同步。 (如需相關資訊，請參閱[初始同步的注意事項](initial-sync-guidance.md)。) 所需資料的範例包括客戶組、付款條件和付款時間表。 不要為需要初始化的表啟用雙重寫入對應，例如帳戶、報價、報價明細、訂單和訂單明細表。
7. 在客戶業務開發應用程式中，進入 **進階設定\>系統設定\>資料管理\>重複偵測規則**，並停用所有規則。
8. 初始化步驟 2 中列出的表。 如需說明，請參閱本主題的其餘區塊。
9. 開啟財務和營運應用程式，並啟用資料表對應，例如帳戶、報價、報價明細、訂單和訂單明細表對應。 然後執行初始同步。 (如需相關資訊，請參閱[初始同步的注意事項](initial-sync-guidance.md)。) 此過程將同步來自財務和營運應用程式的其他資訊，例如處理狀態、發貨和帳單地址、站點和倉庫。

## <a name="account-table"></a>帳戶資料表

1. 在 **公司** 欄，輸入公司名稱，如 **USMF**。
2. 在 **關係類型** 欄，輸入 **客戶** 作為靜態值。 您可能不想在業務邏輯中將每個帳戶記錄都分類為客戶。
3. 在 **客戶組 ID** 欄，輸入財務和營運應用程式中的客戶組編號。 從潛在客戶到現金解決方案的預設值為 **10**。
4. 如果您使用從潛在客戶到現金解決方案而沒有任何自訂 **帳號**，在 **當事人編號** 欄輸入一個 **帳號** 值。 如果有自訂，並且您不知道合作對象編號，請從財務和營運應用程式中提取此資訊。

## <a name="contact-table"></a>聯絡表

1. 在 **公司** 欄，輸入公司名稱，如 **USMF**。
2. 根據 CSV 檔案中的 **IsActiveCustomer** 值設定以下資料欄：

    - 如果在 CSV 檔案中將 **IsActiveCustomer** 設定為 **是**，請將 **可銷售** 欄設定為 **是**。 在 **客戶組 ID** 欄，輸入財務和營運應用程式中的客戶組編號。 從潛在客戶到現金解決方案的預設值為 **10**。
    - 如果在 CSV 檔案中將 **IsActiveCustomer** 設定為 **否**，請將 **可銷售** 欄設定為 **否**，並將 **聯絡人** 欄設定為 **客戶**。

3. 如果您使用從潛在客戶到現金解決方案而沒有自訂 **聯絡號碼**，請設定以下資料欄：

    - 將聯絡人號碼從 CSV 檔案 (**msdynce\_contactnumber**) 移轉到 **聯絡人** 表 (**msdyn\_contactnumber**) 中的聯絡人號碼。
    - 使用 **合作對象編號** 欄中 **聯絡人編號** 表中的值。
    - 使用 **帳號/聯絡人識別碼** 欄中 **聯絡人編號** 表中的值。

## <a name="invoice-table"></a>發票資料表

由於 **發票** 表中的資料設計為以一種方式流動，從財務和營運應用程式到客戶業務開發應用程式，因此不需要初始化。 執行初始同步以將所有必需的資料從財務和營運應用程式移轉到客戶業務開發應用程式。 如需相關資訊，請參閱[初始同步的注意事項](initial-sync-guidance.md)。

## <a name="order-table"></a>訂單表

1. 在 **公司** 欄，輸入公司名稱，如 **USMF**。
2. 將 CSV 檔案中 **訂單編號** 欄的值複製到 **銷售訂單編號** 欄。
3. 將 CSV 檔案中 **客戶** 欄的值複製到 **發票客戶編號** 欄。
4. 將 CSV 檔案中的 **運送到國家/地區** 欄的值複製到 **運送到國家/地區** 欄。 此值的範例包括 **US** 和 **美國**。
5. 設定 **要求收據日期** 欄。 如果您沒有使用收據日期，請使用 CSV 檔案中的 **要求的交貨日期**、**履行日期** 和 **送出日期** 欄。 此值的一個範例是 **2020-03-27T00:00:00Z**。
6. 設定 **語言** 欄。 此值的一個範例是 **en-us**。
7. 使用 **基於項目** 的欄設定 **訂單類型** 欄。

## <a name="order-products-table"></a>訂單產品表

- 在 **公司** 欄，輸入公司名稱，如 **USMF**。

## <a name="products-table"></a>產品表

由於 **產品** 表中的資料設計為以一種方式流動，從財務和營運應用程式到客戶業務開發應用程式，因此不需要初始化。 執行初始同步以將所有必需的資料從財務和營運應用程式移轉到客戶業務開發應用程式。 如需相關資訊，請參閱[初始同步的注意事項](initial-sync-guidance.md)。

## <a name="quote-and-quote-product-tables"></a>報價和報價產品表

如需 **報價** 表，請按照本主題前面的[訂單表](#order-table)章節的說明。 如需 **報價** 產品，請按照[訂單產品表](#order-products-table)章節的說明。


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
