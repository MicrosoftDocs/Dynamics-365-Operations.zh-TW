---
title: 請選擇資料整合技術
description: 本主題提供有關整合人力資源管理資料的資訊。
author: twheeloc
ms.date: 08/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 24ddd242185d736287f61ec250c631ab65e08c95
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452091"
---
# <a name="choose-a-data-integration-technology"></a>請選擇資料整合技術


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



本主題提供與 Dynamics 365 Human Resources 管理的資料整合的資訊 。 它說明不同的整合技術，可幫助您決定最適合您的需求的技術。

## <a name="data-integration-background"></a>資料整合背景

業務資料是讓您的公司與眾不同的關鍵資產。 您的業務資料非常有價值。 您可以使用整個企業彙總的資料間關係改善貴組織的業務流程和商業智慧。 無論來自哪個系統，我們都努力為您提供簡單、安全且穩定的業務資料存取權。

從歷史記錄來看，多套系統間的整合資料一直困難重重。 Microsoft 正採取各個步驟讓資料整合更容易，而朝向這個確定目標邁出的一大步會透過 [Dataverse](/powerapps/maker/common-data-service/data-platform-intro) 實現。

人力資源部正在使 Dataverse 成為人力資源資料的最佳首選公共介面。 隨著時間發展，我們期望人力資源管理的所有最重要資料都會在 Dataverse 揭露。 我們推薦 Dataverse 成為大多數整合應用程式的首選技術。

我們領悟到 Dataverse 可能尚未包含您的應用程式所需的所有資料。 我們也領悟到您的專案時間表可能需要替代技術。 當 Dataverse 無法符合您的整合需求時，請務必讓我們知道。

## <a name="integration-technologies"></a>整合技術

下面章節說明可用於人力資源的不同資料整合技術。

### <a name="dataverse-tables"></a>Dataverse 資料表

Dataverse 是最佳首選的人力資源公共資料介面。 它源自 Dynamics 365 XRM 平台，由[Dynamics 365 Customer Engagement](/dynamics365/?panel=customer-engagement#pivot=business-apps)解決方案使用。

Dataverse 為資料表提供平台和 API。 當您佈署人力資源時，它會連接 Dataverse 執行個體。 人力資源資料實體會部署到 Dataverse 執行個體。 這些資料表及資料可在任何連接 Dataverse 執行個體的應用程式中使用。 人力資源將資料往返同步到 Dataverse 資料表。

> [!NOTE]
> 人力資源實體對應到 Dataverse 資料表。 更多有關 Dataverse (前身為 Common Data Service) 和術語更新的資訊，請參閱[何謂 Microsoft Dataverse？](/powerapps/maker/data-platform/data-platform-intro)

當您的整合應用程式所需的資料表在 Dataverse 時，你可以完全利用 [Dataverse 及它支援的 API](/powerapps/?panel=developer#pivot=home)。 獲得支援的 API 當中，[Dynamics 365 Web API](/dynamics365/customer-engagement/developer/use-microsoft-dynamics-365-web-api) 提供 OData 實施功能存取 Dataverse 資料。

Dataverse 資料表與其關聯 API 是從 Web 應用程式、Web 服務/API 以及任何連接 OData 饋送來源的其他應用程式存取人力資源資料的最佳選項。

> [!NOTE]
> 隨著決定 Dataverse 成為近期相對較新的人力資源首選資料介面，您可能會發現整合所需的人力資源資料實體在 Dataverse 尚無法使用。
> </br>
> 關於 Dataverse 可用的人力資源實體清單，請參閱[人力資源和 Dataverse](/dynamics365/unified-operations/talent/corehrentities)。
> </br>
> 如果還無法使用您整合時所需的人力資源實體，您將需要等待資料實體開放使用或使用下方說明的其中一項他類整合技術。
> </br>
> 預設下，Dataverse 整合在不包括提供的示範資料的新環境是關閉的。 它在包括示範資料的新環境開啟，並且環境在佈建時開始進行資料同步。 待您的環境準備好資料同步後，您就可以開啟整合功能。

### <a name="dmfdixf-entities"></a>DMF/DIXF 實體

與財務和營運應用程式相同平台的主要內建人力資源提供 [Data Management Framework (DMF)](/dynamics365/unified-operations/dev-itpro/data-entities/data-entities-data-packages?toc=%2ffin-and-ops%2ftoc.json)。 DMF 也就是眾所皆知的 Data Import Export Framework (DIXF)。 人力資源提供一整套您可以用來匯入和匯出人力資源資料的資料實體。 由於 Dataverse 資料表是人力資源的最佳首選資料整合介面，DMF 實體在某些場合仍然管用，例如：

- Dataverse 資料表尚未開放使用。

- 整合需要高效能的大量資料匯入/匯出功能。

> [!NOTE]
> 人力資源實體對應到 Dataverse 資料表。 更多有關 Dataverse (前身為 Common Data Service) 和術語更新的資訊，請參閱[何謂 Microsoft Dataverse？](/powerapps/maker/data-platform/data-platform-intro)

DMF 實體目前為人力資源資料提供最完整的資料涵蓋面。

DMF 並非即時整合的適當工具，例如當您需要用戶界面裡用戶立即反饋的時候。 封包操作是排程好的批次工作，往往在批次服務挑出工作執行前至少有 1-2 分鐘的延遲，再加上完成匯入/匯出作業所需的任何時間。

當需要高吞吐量時 (例如排程每晚匯入/匯出數千筆記錄)，DMF 可能是最佳選項。

> [!NOTE]
> DMF 不適用 Attract 和 Onboard。

### <a name="dmf-package-rest-api"></a>DMF 封包 REST API

DMF 提供用來操縱資料包的 [REST API](/dynamics365/unified-operations/dev-itpro/data-entities/data-management-api)。 此 API 可用來以寫程式方式與 DMF 互動，允許的動作例如：

- 匯入資料包。

- 匯出資料包。

- 檢查匯入/匯出作業的狀態。

人力資源完全支援 DMF 封包 REST API。

### <a name="azure-sql-db-byod"></a>Azure SQL DB (BYOD)

DMF 另外提供強大的功能 (稱為[Bring Your Own Database](/dynamics365/unified-operations/dev-itpro/analytics/export-entities-to-your-own-database)或 BYOD)，允許人力資源將資料匯出到您自己的 Microsoft Azure SQL 資料庫。 這種能力提供極大的彈性。 當資料在您自己的 SQL 資料庫時，您可以運用任何連接 SQL 資料儲存設備的應用程式或中介軟體。

BYOD 是主要的唯讀解決方案。 儘管您可以在 Azure SQL 資料庫操縱和儲存想要的任何資料 (例如資料混搭)，但儲存在 Azure SQL 資料庫的資料並不會同步到人力資源。

BYOD 很適合報表解決方案、資料整合、資料混搭，可當作 [Azure 資料工廠](/azure/data-factory/)管道的資料來源。

> [!NOTE]
> BYOD 不適用 Attract 和 Onboard。

### <a name="odata-enabled-entities"></a>啟用 OData 的實體

大多數 DMF 實體也會透過人力資源資料服務 (OData) 啟用存取功能。 針對[財務和營運應用程式 OData 服務](/dynamics365/unified-operations/dev-itpro/data-entities/odata)提供的文件記錄適用 Human Resources，但建立您自己的 OData 公開實體除外。

儘管 Dataverse 和 Dataverse 提供的 OData 施行功能 (透過 [Dynamics 365 Web API](/previous-versions/dynamicscrm-2016/developers-guide/mt593051(v=crm.8))) 優於人力資源資料服務，但目前的人力資源資料服務仍提供人力資源資料更完整的實體涵蓋面。

### <a name="excel-add-in"></a>Excel 增益集

[Excel 增益集](/dynamics365/unified-operations/dev-itpro/office-integration/use-excel-add-in?toc=%2fdynamics365%2funified-operations%2ftalent%2ftoc.json)利用暗中啟用 OData 的實體。 它為最終用戶提供可透過熟悉的 Excel UI 檢索和修改人力資源資料的便利方式。

Excel 增益集適合業務領域專家臨時的資料匯入/匯出。 對於需要程式設計自動化的重複性資料整合，另一種整合技術將更適合。

### <a name="data-integrator"></a>資料整合商

您可以使用[資料整合服務](/powerapps/administrator/data-integrator)整合進出 Dataverse 的資料。 資料整合商允許您定義整合專案，往往根據應用程式開發人員已經專為特定整合制訂的預定義範本進行。 您可以排程整合專案定期自動執行或手動執行它們。

資料整合商專案適用 Dataverse 批次整合。 它們是 Dynamics 365 系列應用程式間整合的最佳選擇。 例如，Microsoft 提供從人力資源整合資料到 Dynamics 365 Finance 的資料整合商範本。 您可以在[從 Dynamics 365 Human Resources 整合到 Dynamics 365 Finance](hr-admin-integration-finance.md) 了解更多有關範本的資訊。

### <a name="power-query"></a>Power Query

資料整合商支援 [Power Query](/power-query/power-query-what-is-power-query) 透過其[進階查詢功能](/powerapps/administrator/data-integrator#advanced-data-transformation-and-filtering)進行。 Power Query 提供強大、靈活的資料過濾和轉換功能，包括豐富的 M 公式語言。 如果您已經開發過 Power BI 報表，可能會很熟悉 Power Query。

## <a name="deciding-on-an-integration-technology"></a>決定整合技術

借助眾多種類不同的整合技術決定使用哪一種整合方法有時讓人無所適從。 隨著 Dataverse 的資料涵蓋面日趨成熟，決定將變得更容易，Dataverse 絕大多數情況下是首選的資料介面。 但在那之前，您可能會發現 Dataverse 還無法滿足您的需求。 下列資料表摘錄整合技術選項的若干關鍵特徵。

| 技術/工具/API    | 定期整合                   | 同步/非同步                    | 透過 API 進行程式設計存取        | 適當的資料量                                   | 資料涵蓋面                       |
|------------------------|------------------------------------------|---------------------------------------------|-------------------------------------------|------------------------------------------------------------|-------------------------------------|
| Dataverse 資料表           | 是，使用資料整合商或中介軟體 | 同步非同步、批次 (透過 資料整合商)  | 是，透過 Dynamics 365 Web API (OData) | 因使用案例而異 (支援分頁後的互動式使用) | 改善<sup>2</sup>                       |
| DMF 實體           | 是，透過中介軟體排程        | 非同步，批次                                | 是，透過 DMF 封包 REST API         | 高 (數十萬筆記錄)                    | 高                                |
| DMF 封包 REST API   | 是，透過中介軟體排程        | 非同步，批次                                | 是                                       | 高 (數十萬筆記錄)                    | API 支援所有 DMF 實體       |
| BYOD                   | 是，由人力資源管理員排程        | 非同步，批次                                | 否<sup>3</sup>                                    | 高 (數十萬筆記錄)                    | 支援所有 DMF 實體           |
| 啟用 OData 的實體 | 是，使用中介軟體                    | 同步                                        | 是，透過人力資源資料服務 (OData)  | 因使用案例而異 (支援分頁後的互動式使用) | 高                                |
| Excel 增益集           | 否                                       | 同步                                        | 否                                        | 適中 (數萬筆記錄)                      | 支援所有啟用 OData 的實體 |
| 資料整合商        | 是，在資料整合商中排程        | 非同步，批次                                | 否                                        | 因使用案例而異                                       | 支援所有 Dataverse 資料表           |

<sup>2</sup>Microsoft 正在鉅資投入增加 Dataverse 資料表的資料涵蓋面。 當在涵蓋範圍內時，我們建議使用 Dataverse。 目前，相較於啟用 OData 的實體，Dataverse 資料涵蓋面較低。

<sup>3</sup>SQL 資料庫可藉由程式設計方式存取。


[!INCLUDE[footer-include](../includes/footer-banner.md)]
