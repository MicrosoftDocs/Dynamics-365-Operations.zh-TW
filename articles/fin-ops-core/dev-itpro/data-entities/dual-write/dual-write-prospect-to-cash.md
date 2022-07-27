---
title: 雙重寫入中的從潛在客戶到現金流程
description: 本主題提供有關雙重寫入中的從潛在客戶到現金流程的資訊。
author: RamaKrishnamoorthy
ms.date: 01/07/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-27
ms.openlocfilehash: 7c53bcd1084d89b59d0f6b2674a85d7c3481a9bf
ms.sourcegitcommit: 9acfb9ddba9582751f53501b82a7e9e60702a613
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/10/2021
ms.locfileid: "8460205"
---
# <a name="prospect-to-cash-in-dual-write"></a>雙重寫入中的從潛在客戶到現金流程

[!include [banner](../../includes/banner.md)]

大多數企業的重要目標是將潛在客戶轉化為客戶，然後與這些客戶保持持續的業務關係。 在 Microsoft Dynamics 365 應用程式中，從潛在客戶到現金的流程透過報價或訂單處理工作流程進行，並且對財務進行核對和確認。 潛在客戶到現金與雙重寫入的整合建立了一個工作流程，該工作流程採用源自 Dynamics 365 Sales 或 Dynamics 365 Supply Chain Management 的報價和訂單，並使報價和訂單在兩個應用程式中都可用。

在應用程式介面中，您可以即時存取處理狀態和發票資訊。 因此，您可以在 Supply Chain Management 中更輕鬆地管理產品庫存、庫存處理和履明細等函數，而無需重新建立報價單和訂單。

![潛在客戶到現金流程中的雙重寫入資料流程。](../dual-write/media/dual-write-prospect-to-cash[1].png)

如需客戶和聯絡人整合的相關資訊，請參閱[整合的客戶主資料](customer-mapping.md)。 如需產品整合的相關資訊，請參閱[統一的產品體驗](product-mapping.md)。

> [!NOTE]
> 在 Dynamics 365 Sales 中，潛在客戶和客戶都參考 **客戶** 表中的記錄，其中 **RelationshipType** 欄是 **潛在客戶** 或 **客戶**。 如果您的業務邏輯包括一個 **客戶** 資格流程，其中先建立 **客戶** 記錄並使其成為潛在客戶，然後成為客戶，則該記錄僅在它是客戶時才會同步到財務和營運應用程式 (`RelationshipType=Customer`)。 如果您希望 **客戶** 資料列作為潛在客戶進行同步，那麼您需要一個自訂對應來整合潛在客戶資料。

## <a name="prerequisites-and-mapping-setup"></a>先決條件和對應安裝

在您可以同步銷售報價之前，您必須更新以下設定。

### <a name="setup-in-sales"></a>Sales 中的安裝

在 Sales 中，進入 **設定\>管理\>系統設定\>銷售**，並確保使用以下設定：

- 將 **使用系統定價計算** 系統選項設定為 **是**。
- **折扣計算方法** 資料明細設為 **明細項**。

### <a name="sites-and-warehouses"></a>地點和倉庫

在 Supply Chain Management 中，報價單明細和訂單明細需要 **地點** 和 **倉庫** 資料欄。 如果您在預設訂單設定中設定地點和倉庫，則當您將產品新增到報價單明細或訂單明細時，這些資料欄將自動設定。 

### <a name="number-sequences-for-quotations-and-orders"></a>報價單和訂單的編號規則

在 Sales and Supply Chain Management 中建立和同步報價單和訂單時，Supply Chain Management 和 Sales 的編號規則未連線。 如果在 Sales 中建立的銷售訂單同步到 Supply Chain Management，則它在 Supply Chain Management 中具有相同的銷售訂單編號。 若要幫助確保銷售訂單編號不重複，您必須在兩個應用程式中使用不同的編號規則係統。

例如，Supply Chain Management 中的編號規則是 **1, 2, 3, 4, 5, ...**，而 Sales 中的編號規則是 **100, 99, 98, ...**。如果您在 Sales 中建立 100 個銷售訂單，最終將產生一個已存在於 Supply Chain Management 中的訂單號。 換言之，隨著在 Supply Chain Management 和 Sales 中建立銷售訂單，這兩個編號規則最終會重疊。 相反，您可以在 Supply Chain Management 中使用 **F1、F2、F3、...** 等編號規則，在 Sales 中使用 **C1、C2、C3、...** 等編號規則。 這些編號規則永遠不會產生重複的銷售訂單編號。

## <a name="sales-quotations"></a>銷售報價

銷售報價單可以在 Sales 或 Supply Chain Management 中建立。 如果您在 Sales 中建立報價單，它會即時同步到 Supply Chain Management。 同樣，如果您在 Supply Chain Management 中建立報價單，它會即時同步到 Sales。 請注意以下幾點：

+ 您可以在報價單上為產品新增折扣。 在這種情況下，折扣將同步到 Supply Chain Management。 抬頭上的 **折扣**、**費用** 和 **稅金** 資料欄由 Supply Chain Management 中的安裝控制。 此安裝不支援整合對應。 而是在 Supply Chain Management 中維護和處理 **價格**、**折扣**、**費用** 和 **稅金** 資料欄。
+ 銷售報價單抬頭上的 **折扣 %**、**折扣** 和 **貨運金額** 資料欄是讀取專用資料欄。
+ **貨運條款**、**交貨條款**、**運送方式** 和 **交貨模式** 資料欄不是預設對應的一部分。 若要對應這些資料明細，必須設定特定於在其中同步資料表之組織中的資料值對應。

如果您還使用 Field Service 解決方案，請確保重新啟用 **報價明細快速建立** 參數。 重新啟用該參數可讓您繼續使用快速建立函數建立報價明細。

1. 瀏覽到您的 Dynamics 365 Sales 應用程式。
2. 選取頂部瀏覽列中的設定圖示。
3. 選取 **進階設定**。
4. 選取 **自訂系統** 選項。
5. 選取 **報價明細** 選單項目。
6. 進入 **資料服務** 區段並選取 **允許快速建立** 核取方塊。

## <a name="sales-orders"></a>銷售訂單

銷售訂單可以在 Sales 或 Supply Chain Management 中建立。 如果您在 Sales 中建立銷售訂單，它會即時同步到 Supply Chain Management。 同樣，如果您在 Supply Chain Management 中建立銷售訂單，它會即時同步到 Sales。 請注意以下幾點：

+ Dynamics 365 Sales 中的寫入產品將在 Dynamics 365 Supply Chain Management 中顯示為產品類別。
+ 折扣計算和進位：

    - Sales 中的折扣計算模型與 Supply Chain Management 中的折扣計算模型不同。 在 Supply Chain Management 中，銷售明細的最終折扣金額可以是折扣金額和折扣百分比的組合結果。 如果此最終折扣金額除以明細中的數量，則可能會發生進位。 但是，如果進位的單位折扣金額與銷售額同步，則不考慮此進位。 若要幫助確保 Supply Chain Management 中銷售明細的全部折扣金額正確同步到 Sales，必須在不除以明細數量的情況下同步全部金額。 因此，您必須在 Sales 中將折扣計算方法定義為 **明細項目**。
    - 當銷售訂單明細從 Sales 同步到 Supply Chain Management 時，將使用完整明細折扣金額。 因為 Supply Chain Management 沒有可以儲存完整折扣金額的資料欄，所以金額除以數量並儲存在 **明細折扣** 資料欄中。 在此劃分期間發生的任何進位都儲存在銷售明細的 **銷售費用** 資料欄中。

### <a name="example-synchronization-from-sales-to-supply-chain-management"></a>範例：從 Sales 到 Supply Chain Management 的同步

您有以下銷售訂單：

+ **Sales：** 數量 = 3，每明細折扣 = $10.00
+ **Supply Chain Management：** 數量 = 3，明細折扣金額 = $3.33，銷售費用 = -$0.01

如果您從 Supply Chain Management 同步到 Sales，您將獲得以下結果：

+ **Supply Chain Management：** 數量 = 3，明細折扣金額 = $3.33，銷售費用 = -$0.01
+ **Sales：** 數量 = 3，每明細折扣 = (3 × $3.33) + $0.01 = $10.00

## <a name="dual-write-solution-for-sales"></a>Sales 的雙重寫入解決方案

新資料欄已新增到 **訂單** 表並顯示在頁面上。 這些資料欄中的大多數出現在 Sales 的 **整合** 索引標籤上。 若要進一步了解如何對應狀態資料欄，請參閱[設定銷售訂單狀態資料欄的對應](sales-status-map.md)。

+ **銷售訂單** 頁面上的 **建立發票** 和 **取消訂單** 按鈕在 Sales 中隱藏。
+ **銷售訂單狀態** 值將保持 **Active** 狀態，以幫助確保來自 Supply Chain Management 的更改可以流向 Sales 中的銷售訂單。 若要控制此明細為，請將預設 **Statecode\[Status\]** 值設定為 **Active**。

## <a name="invoices"></a>發票

銷售發票在 Supply Chain Management 中建立並同步到 Sales。 請注意以下幾點：

+ **發票編號** 資料欄已新增到 **發票** 表並顯示在頁面上。
+ **銷售訂單** 頁面上的 **建立發票** 按鈕已隱藏，因為發票將在 Supply Chain Management 中建立並同步到 Sales。 無法編輯 **發票** 頁面，因為發票將從 Supply Chain Management 同步。
+ 當相關發票從 Supply Chain Management 同步到 Sales 後，**銷售訂單狀態** 值會自動變更為 **已開立發票**。 此外，建立發票之銷售訂單的擁有者被指定為發票的擁有者。 因此，銷售訂單的擁有者可以查看發票。
+ **貨運條款**、**交貨條款** 和 **交貨模式** 資料欄不包含在預設對應中。 若要對應這些資料明細，必須設定特定於在其中同步資料表之組織中的資料值對應。

## <a name="templates"></a>範本

從潛在客戶到現金的流程包括一組在資料交互期間協同工作的核心表對應，如下表所示。

| 財務和營運應用程式 | Customer Engagement 應用程式 | 描述 |
|-----------------------------|-----------------------------------|-------------|
[所有產品](mapping-reference.md#138) | msdyn_globalproducts | |
[客戶 V3](mapping-reference.md#101) | 客戶 | |
[客戶 V3](mapping-reference.md#116) | 聯絡人 | |
[聯絡人 V2](mapping-reference.md#221) | msdyn_contactforparties | |
[CDS 銷售訂單抬頭](mapping-reference.md#217) | salesorders | |
[CDS 銷售訂單明細](mapping-reference.md#216) | salesorderdetails | |
[CDS 銷售報價單抬頭](mapping-reference.md#215) | 報價 | |
[CDS 銷售報價單明細](mapping-reference.md#214) | quotedetails | |
[已發佈產品 V2](mapping-reference.md#189) | msdyn_sharedproductdetails | |
[銷售發票抬頭 V2](mapping-reference.md#118) | 發票 | 財務和營運應用程式中的銷售發票抬頭 V2 表包含銷售訂單和普通發票的發票。 在 Dataverse 中套用了一個過濾器來進行雙重寫入，該過濾器將過濾掉任何普通發票文件。 |
[銷售發票明細 V2](mapping-reference.md#117) | invoicedetails | |
[銷售訂單原始程式碼](mapping-reference.md#186) | msdyn_salesorderorigins | |

如需價格清單的相關資訊，請參閱[統一的產品體驗](product-mapping.md)。

## <a name="limitations"></a>限制

- 不支援退貨訂單。
- 不支援折讓單。
- 必須為主資料設定財務維度，例如客戶和廠商。 將客戶新增到報價單或銷售訂單時，與客戶記錄相關的財務維度會自動流向訂單。 現行雙重寫入不包括主資料的財務維度資料。

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
