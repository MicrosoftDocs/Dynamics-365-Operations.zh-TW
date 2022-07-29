---
title: 上線常見問答集
description: 本主題列出有關如何上線使用 Dynamics 365 Human Resources 落實專案的常見問答集。
author: rachel-profitt
ms.date: 10/13/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: raprofit
ms.search.validFrom: 2020-10-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: c449ae6eb84fb4150072c386d02b100ca3cca219
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452322"
---
# <a name="go-live-faq"></a>上線常見問答集 


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



本主題列出有關如何上線使用 Dynamics 365 Human Resources 落實專案的常見問答集。 

## <a name="when-can-i-configure-and-request-my-production-environment"></a>我何時可以配置和要求我的正式環境？ 

典型作法是先滿足下列條件，再開始部署正式環境：

- 所有客製化的代碼都是完整的。
- 用戶驗收測試 (UAT) 已完成。
- 客戶已簽字認可解決方案。
- 上線沒有阻塞的問題。 

當合格客戶在此階段時，Microsoft FastTrack 團隊將與專案團隊一同上線評估。 

## <a name="what-are-the-prerequisites-to-deploying-a-production-environment"></a>部署正式環境的前提條件？ 

關於前提條件清單，請參閱 [準備上線](hr-admin-go-live-prepare.md)。 

## <a name="what-is-a-go-live-assessment"></a>何謂上線評估？  

上線評估是 [Microsoft FastTrack 計劃](/dynamics365/fasttrack/)。 審查期間，Solution Architect 評估落實專案是否已經準備好成功切換和上線。 在您可以要求在正式環境上線之前，每個落實專案都必須先經過這項審查。 

## <a name="our-sandbox-environments-are-deployed-in-the-central-us-datacenter-we-want-our-production-environments-to-be-deployed-in-the-west-us-datacenter-can-i-select-west-us-as-the-datacenter-in-my-production-configuration"></a>我們的沙箱環境部署在美國中部資料中心。 我們希望我們的正式環境部署在美國西部的資料中心。 我可以在自己的實際執行組態中選取美國西部為資料中心嗎？ 

LCS 不會限制您在部署人力資源環境時選取不同的資料中心，但是我們強烈建議您不要選取不同的資料中心。  

如果您希望您的正式環境在美國資料數據中心，您應該先將您的沙箱環境重新部署到美國西部資料中心測試和簽字認可。 

關於選取正確資料中心的資訊，請參閱[網路要求](../fin-ops-core/fin-ops/get-started/system-requirements.md#network-requirements)。 

## <a name="what-level-of-access-do-i-have-to-the-azure-resources-for-my-human-resources-environments"></a>我具備什麼等級的權限存取人力資源環境的 Azure 資源？  

對人力資源環境的存取有限。 您無法存取虛擬機 (VM) 或 Microsoft Internet Information Services (IIS)。 您也無法透過 Microsoft SQL Server Management Studio 存取資料庫。 

雖然您無法直接存取您的 Azure 資源或 Dynamics 365 Human Resources 環境，但您可以使用其他功能來存取您的資料：

- 您可以在自己的 Azure 租戶中佈署 Azure SQL 資料庫，並使用攜帶自己的資料庫 (BYOD) 功能同步化資料。 更多相關資訊，請參閱[攜帶自己的資料庫 (BYOD)](../fin-ops-core/dev-itpro/analytics/export-entities-to-your-own-database.md)。

- 您可以使用 Dataverse 整合將選取實體同步到 Dataverse 資料庫。 如需更多資訊，請參閱 [Dataverse 表格](hr-developer-entities.md)。 

## <a name="how-often-is-my-production-database-backed-up"></a>我的生產資料庫多久備份一次？ 

資料庫由自動備份功能依下列頻率保護：

| 備份類型 | 頻率 |
| --- | --- |
| 完整資料庫備份 | 每週 |
| 差別性資料庫備份 | 每 12-24 小時 |
| 交易日誌備份 | 每 5 到 10 分鐘 |

Microsoft 保留足夠的備份允許過去 14 天之內進行還原時間點 (PITR)。 

有關更多資訊，請參閱 [了解自動 SQL 資料庫備份](/azure/azure-sql/database/automated-backups-overview?tabs=single-database)。 

## <a name="can-i-request-a-copy-of-the-backup-of-my-production-database"></a>我可以要求我的生產資料庫備份副本嗎？ 

否。 不過您可以提交資料庫重新整理服務要求，將您的正式環境複製到您的沙箱環境。 您可以在自己的 Azure 租戶中佈署 Azure SQL 資料庫，並使用 BYOD 功能將資料從您的正式環境進行同步。 更多相關資訊，請參閱[攜帶自己的資料庫 (BYOD)](../fin-ops-core/dev-itpro/analytics/export-entities-to-your-own-database.md)。 

## <a name="how-do-i-move-my-sandbox-environment-to-production-for-go-live"></a>如何將我的沙箱環境移到正式環境以便上線？ 

因為複製功能無法將您的環境從沙箱移到正式環境，因此您必須使用資料包將資料移到正式環境。  

我們建議維護整個專案裡，在您的沙箱配置的清晰實體清單。 接著測試您上線所需的任何資料包切換和遷移流程。 當您準備好上線時，您必須手動將任何資料包移到正式環境。 

## <a name="what-should-i-do-if-my-production-environment-is-down"></a>要是我的正式環境失靈了怎麼辦？ 

若要回報實際執行斷線，請按照 [回報實際執行斷線](../fin-ops-core/dev-itpro/lifecycle-services/report-production-outage.md)中描述的流程處理。 

 ## <a name="see-also"></a>也請參閱

 [準備好上線](hr-admin-go-live-prepare.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
