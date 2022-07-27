---
title: 表對應健康檢查的錯誤代碼
description: 本主題介紹表對應健康檢查的錯誤代碼。
author: nhelgren
ms.date: 10/04/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: nhelgren
ms.search.validFrom: 2021-10-04
ms.openlocfilehash: 916f3cfca3bae7a073ce4e956a12080ee01c8d31
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8460587"
---
# <a name="errors-codes-for-the-table-map-health-check"></a>表對應健康檢查的錯誤代碼

[!include [banner](../../includes/banner.md)]



本主題介紹表對應健康檢查的錯誤代碼。

## <a name="error-100"></a>錯誤 100

錯誤訊息是「執行財務和營運建議所需的最低財務和營運平台版本是 PU 43。」

該功能需要對財務和營運應用程式版本 10.0.19 或更高版本進行平台更新。

## <a name="error-400"></a>錯誤 400

錯誤訊息是「找不到實體\{財務和營運 UniqueEntityName\}的商業事件註冊資料，這意味著地圖未執行或所有欄位對應都是單向的。」

## <a name="error-500"></a>錯誤 500

錯誤訊息是「找不到專案\{專案名稱\}的專案設定。 這可能是專案未啟用，或者所有欄位對應都是從客戶參與到財務和營運的單向對應。」

檢查資料表地圖的對應。 如果它們是從客戶業務開發應用程式到財務和營運應用程式的單向，則不會產生從財務和營運應用程式到 Dataverse 的即時同步流量。

## <a name="error-900"></a>錯誤 900

錯誤訊息是「實體\{財務和營運 UniqueEntityName\}的來源篩選器\{sourceFilter\}格式無效。」

在資料表地圖中為財務和營運應用程式指定的來源篩選器在語法上不正確。 若要驗證篩選條件，請參閱[解決即時同步問題](dual-write-troubleshooting-live-sync.md#live-synchronization-issues-that-are-caused-by-incorrect-query-filter-syntax-on-the-dual-write-maps)。

## <a name="error-1000"></a>錯誤 1000

錯誤訊息是，「用於雙重寫入即時同步的實體\{財務和營運 UniqueEntityName\}查詢是\{財務和營運 EntityFilterQueryString\}。 符合查詢條件的記錄將被提取進行即時同步。」

回傳的實體查詢是實體的支援 SQL 查詢。 檢查查詢中的內部聯結或篩選器，以確定為即時同步而提取的業務資料。 內部聯結和篩選器是必須滿足的強制性條件，對於為雙重寫入即時同步而提取的每條記錄都必須滿足這些條件。

## <a name="error-1300"></a>錯誤 1300

錯誤訊息是「可能無法追蹤實體\{財務和營運 EntityMetadata.EntityProperties.LogicalEntityName\}的虛擬欄位\{s.EntityFieldName\}以進行雙重寫入。」

財務和營運表中的虛擬欄位未啟用追蹤。 即時同步可以同步資料，但無法提取對列所做的更改。

## <a name="error-1500"></a>錯誤 1500

錯誤訊息是，「應該至少有一個欄位對應到客戶參與的非查詢欄位，以啟用對資料來源\{datasource.DataSourceName\}的追蹤。」

來自實體的資料來源沒有為雙重寫入對應的任何欄位。 對於雙重寫入，不會追蹤對基礎表的更改。

## <a name="error-1600"></a>錯誤 1600

錯誤訊息是，「實體\{財務和營運 EntityMetadata.EntityProperties.LogicalEntityName\}的資料來源：\{datasource.DataSourceName\}有一個範圍。 只有滿足範圍條件的記錄才會被提取用於出站。」

財務和營運應用程式中的實體可以具有啟用了篩選範圍的資料來源。 這些範圍定義了作為即時同步的一部分提取的記錄。 如果某些記錄從財務和營運應用程式跳過到 Dataverse，請檢查記錄是否滿足實體上的範圍條件。 執行此檢查的一種簡單方法是執行類似於以下範例的 SQL 查詢。

```sql
select * from <EntityName> where <filter criteria for the records> on SQL.
```

## <a name="error-1700"></a>錯誤 1700

錯誤訊息是「資料表：實體\{datasourceTable.Key.entityName\}的表：\{zdatasourceTable.Key.subscribedTableName\}被追蹤實體\{origTableToEntityMaps.EntityName\}。 為多個實體追蹤的相同表可能會影響即時同步交易的系統效能。」

如果同一個表被多個實體追蹤，對錶的任何更改都將觸發連結實體的雙重寫入評估。 儘管篩選子句將僅發送有效記錄，但如果存在長時間執行的查詢或未最佳化的查詢計劃，則評估可能會導致效能問題。 從業務角度來看，這個問題可能無法避免。 但是，如果跨多個實體有許多相交表，則應考慮簡化實體或檢查實體查詢的最佳化。

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
