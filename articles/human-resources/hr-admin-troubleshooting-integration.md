---
title: 整合 Finance 的常見問答集
description: 本主題說明整合人力資源和財務整合時會同步的資料。
author: twheeloc
ms.date: 08/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 308e2a538666522edf4a76be13b93c82c3f3a774
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452670"
---
# <a name="integration-with-finance-faq"></a>整合 Finance 的常見問答集


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



本主題回答有關整合 Dynamics 365 Human Resources 與 Dynamics 365 Finance 時同步資料的常見問題。

## <a name="can-i-edit-the-dynamics-365-talent-application-user-in-power-apps"></a>我可以在 Power Apps 編輯 Dynamics 365 Talent 應用程式使用者？

編號 如果您編輯人力資源應用程式使用者，人力資源和 Dataverse 之間的整合可能會失敗。 下表顯示 Talent 應用程式使用者的預設設定。

| 全名 | 應用程式識別碼 | Azure AD 對象識別碼 | 應用程式識別碼 URI |
| --- | --- | --- | --- |
| Dynamics365 for Talent | f9be0c49-aa22-4ec6-911a-c5da515226ff | 27fd8129-4b3c-43f7-b1bf-47495d3a049b | f9be0c49-aa22-4ec6-911a-c5da515226ff |

![Talent 應用程式使用者的預設設定。](media/DynamicsApplicationUser.png)

## <a name="is-all-data-synchronized-or-just-some-data-entities"></a>是所有資料實體同步或者只有一些同步？

資料子集合會同步。 關於所有實體清單，請參閱[整合 Dynamics 365 Finance](hr-admin-integration-finance.md)。

## <a name="why-dont-i-see-any-data-synced-to-dataverse"></a>為何我看不到任何資料同步到 Dataverse？

預設情況下，Dataverse 整合在不包括提供示範資料的新環境是關閉的。 預設情況下，它在包括示範資料的新環境會開啟，並且在佈建環境時開始進行資料同步。 待您的環境準備好資料同步後，您就可以開啟整合功能。 更多資訊，請參閱[配置 Dataverse 整合](hr-admin-integration-common-data-service.md)。

## <a name="can-i-create-a-new-mapping-without-using-the-templates"></a>我可以在不用範本情況下建立新測繪嗎？

範本是起點。 您可以建立自己的範本，但建立整合專案時始終需要範本。 更多有關資料整合器 (DI)、範本和專案的資訊，請參閱[整合資料到 Microsoft Dataverse](/powerapps/administrator/data-integrator)。

## <a name="can-i-map-financial-dimensions-to-transfer-between-human-resources-and-finance"></a>我可以測繪財務維度以便在人力資源和財務之間轉移嗎？

財務維度目前不在 Dataverse，因此不是預設範本的一部分。 本實體是原先規劃好的，但目前尚未公布發行版本時間表。

長駐 Finance 但人力資源不存在的資訊方面，請使用人力資源的 **配置連結** 選項連結兩套系統。

![測繪財務維度。](media/MapFinancialDimensions.png)

## <a name="sometimes-when-i-import-employees-they-go-into-inactive-workers-in-finance-why"></a>偶爾當我匯入員工時，他們會成為 Finance 的閑置員工。 為什麼？

如果員工在人力資源沒有有效的雇用詳細資料，您可能會發生這項錯誤。 若要解決這個問題，請前往 **人事管理\>員工\>雇用歷程\>日期管理器**，驗證是否已有有效的雇用詳細記錄。

## <a name="if-i-select-to-map-only-a-subset-of-fields-will-changes-made-to-non-mapped-fields-trigger-a-sync"></a>如果我選取只測繪欄位子集合，未測繪欄位的變更會觸發同步動作嗎？

資料同步按照執行排程進行。 如果變更記錄中的任何欄位，不論此欄位是否為整合測繪的一部分，整合都會揀選記錄。

## <a name="how-can-i-send-only-active-worker-changes-and-not-the-terminated-records"></a>我如何只傳送變更內容給有效背景工作角色而不傳送已經終止的記錄？

憑藉 “進階查詢” 功能，您可以在將來源資源傳遞給目的地之前先過濾和重塑。

![有效背景工作角色的進階查詢。](media/MapOnlyActiveWorkersAdvancedQuery.png)

## <a name="can-i-specify-which-fields-to-send-to-finance-for-a-specific-entity"></a>我可以指定要傳送到 Finance 特定實體的欄位嗎？

欄位可以從整合任務新增或移除。 並非所有資料欄位都存在於 Dataverse 資料表，我們將從人力資源填滿。
額外資料可以透過 Power Apps 填滿。

![從整合任務新增或移除欄位。](media/SpecifyFieldsIncludedInIntegration.png)

## <a name="i-set-up-integration-as-a-batch-job-but-human-resources-lost-connection-to-the-destination-system-how-can-i-send-the-same-set-of-changes-to-the-destination-system"></a>我將整合設定成批次工作，但人力資源部失去與目的地系統的連接。 我如何將相同的變更集合傳送到目的地系統？

例外狀況處理程序不需要特殊設定。 資料整合工具將自動捕捉和回報來源和目的地發生的錯誤，並將允許手動重試。 然而它不允許手動資料修正。 如果需要更新資料，應該在來源或目的地進行。

## <a name="can-i-set-up-bi-directional-integration"></a>我可以設定雙向整合嗎？

不行，整合目前是單向的 (人力資源到財務和營運應用程式)。 然而目前從人力資源傳送到 Finance 有開放的預設範本。

## <a name="can-i-allow-record-deletion-as-part-of-my-integration"></a>我可以允許刪除記錄作為整合的環節嗎？

不行，Data Integrator 並不擷取已刪除的記錄進行資料傳輸。 目前只包括資料建立和更新 (UPSERT)。

## <a name="can-i-rerun-the-errored-execution-if-so-will-it-send-a-full-file-or-only-the-changes"></a>我可以重新執行發生錯誤的執行動作嗎？ 如果可以，它會傳送完整檔案或者只傳發送變更內容？

Data Integrator 的第一次執行始終是完整執行。 後續執行以追蹤修訂為主。 執行錯誤執行時，它會提取執行範圍內的記錄，並從 Dataverse 傳出最近的變更內容。

## <a name="when-i-save-the-project-i-get-the-error-project-has-mapping-errors-what-do-i-do"></a>儲存專案時，我會收到錯誤訊息：“本專案發生測繪錯誤。” 我該如何處理？

請檢查整合金鑰的設定，對設定進行任何必要的變更，然後重新整理專案裡的實體。

使用預設範本時將自動匯入整合金鑰。 當新任務新增到既有範本時可能會出現這個問題。

## <a name="if-i-have-n-number-of-legal-entities-where-workers-have-employments-do-i-need-to-create-a-mapping-for-each-of-them"></a>如果我有 N 個法人實體，其中雇用背景工作角色，我需要為每個人建立測繪嗎？

是的，Finance 中的每個法人實體您將需要在資料整合中分開整合專案。

## <a name="i-need-to-transfer-data-that-is-not-part-of-the-default-template-provided-by-microsoft-can-i-do-this"></a>我需要傳輸不屬於 Microsoft 提供的預設範本資料。 我可以這麼做嗎？

是的，您可以從既有範本新增或移除欄位。 您可以修改範本成包括其他 Dataverse 資料表的額外資料。 實體必須在 Dataverse 裡才能納入範本。 

## <a name="i-just-created-new-finance-and-human-resources-environments-and-im-getting-the-error-the-data-value-violates-integrity-constraints-why"></a>我剛建立新的 Finance and Human Resources 環境並且我收到 "資料值違反一致性限制式" 的錯誤訊息。 為什麼？

這個錯誤的原因會包括：

- 資料傳輸導致來源 (Dataverse) 出現重覆性的記錄擷取。

- 資料傳輸欄位有財務和營運應用程式需要的空值。 驗證 Dataverse 裡的資料並符合財務和營運應用程式要求。

## <a name="if-there-are-execution-errors-and-the-employee-id-didnt-sync-how-do-i-find-the-history-job-which-has-the-failed-employee-record"></a>如果出現執行錯誤而且員工識別碼並未同步，我如何找到有員工失敗記錄的歷程工作？

Data Integrator 將在 Finance 建立多項專案。 Data Integrator 任務和 Finance 專案之間的關係是一對一。

從 Data Integrator 執行歷程追蹤時間並在 Finance 尋找索引 -1 專案。 如果 Data Integrator 的任務編號為 9，則 Finance 的索引為 8。

1. 從 Data Integrator 擷取任務索引 (本範例為 “9”)。

    ![從 Data Integrator 擷取任務索引。](media/CaptureTaskIndex.png)

2. 追蹤專案的執行時間。

    ![追蹤專案的執行時間。](media/CaptureTimeOfExecution.png)

3. 在 Finance 辨別索引 - 1。 本範例中，後綴詞為 “8” 且索引 “0” 專案的執行時間符合步驟 2 的執行時間。

    ![辨別索引。](media/IdentifyIndex.png)

## <a name="after-integrating-human-resources-and-finance-i-dont-see-my-human-resources-data-in-finance-what-do-i-do"></a>整合人力資源和 Finance 後，我無法在 Finance 看到我的人力資源資料。 我該如何處理？

整合 Finance 是兩步驟流程。 首先，驗證人力資源資料是否已在 Dataverse 更新並且開放使用。 這是幾近即時的同步，可在 Power Apps 中藉由查看資料表內的資料驗證。

![Dataverse 裡的資料。](media/DataInCDS.png)

如果資料未如預期在 Dataverse 出現，則驗證該實體是否支援整合。 將額外資料納入 Dataverse 需要變更 Microsoft 端。

如果支援實體並且可在 Dataverse 使用資料，則驗證 Data Integrator 的測繪是否正確。 如果整合工具測繪看起來沒問題，則驗證資料管理工作是否執行成功。 執行批次工作間可能發生錯誤。 更多有關資料管理的資訊，請參閱[資料管理](/dynamics365/unified-operations/dev-itpro/data-entities/data-entities-data-packages?toc=%2ffin-and-ops%2ftoc.json)。

## <a name="the-addresses-for-my-employees-are-incorrect-after-i-import-them-into-finance-what-should-i-do"></a>我將員工地址匯入 Finance 後發現地址不正確。 我應該如何處理？

**位置識別碼** 的編號順序在人力資源和財務使用相同模式。 兩邊的編號順序皆須唯一，因此整合 Dataverse 資料到財務和營運應用程式時不會發生地址衝突。

落實人力資源期間，驗證 Human Resources and Finance 的編號順序是否不同。 驗證兩套系統皆可維護資料的所有編號順序都不相同。

## <a name="when-creating-my-connection-set-i-am-unable-to-see-the-connection-in-the-connection-drop-down-list-what-do-i-do"></a>建立我的連接集合時，我無法在連線下拉式清單看到連線。 我該如何處理？

確定建立您的連線時，您選擇 Dynamics 365 Finance 和 Dataverse。

## <a name="when-syncing-employments-i-get-the-errors-companyinfo_fk-doesnt-exist-or-the-value-12312154-115959-pm-in-field-employment-end-date-is-not-found-in-the-related-table-employment-what-should-i-do"></a>同步就業時，我收到 "CompanyInfo_FK 不存在" 或 "相關資料表 '就業' 中找不到 “就業結束日期” 欄位值 '12/31/2154 11:59:59 pm' 的錯誤訊息。” 我應該如何處理？

確保您正在測繪正確的法人實體。 法人實體同步並不是預設範本的一部分，因此預期人力資源的每個法人實體和 Dataverse 也會出現在 Finance。 此外，請確定您正為關聯的連線集合選取正確的法人實體。

## <a name="after-setting-up-my-project-the-field-mapping-for-finance-appears-to-be-empty-what-should-i-do"></a>待設定我的專案後，Finance 欄位的測繪看似空白。 我應該如何處理？

藉由前往 **資料管理\>框架參數\>實體設定\>重新整合實體清單。** 重新整合 Finance 中的資料實體 這應該需要幾分鐘才能完成，然後您應該會看到這些測繪結果。 當建立新專案時會出現這個問題。

![漏掉欄位測繪。](media/MissingFieldMapping.png)

## <a name="additional-resources"></a>其他資源

- Data Integrator (DI)： 

  - [整合資料到 Microsoft Dataverse](/powerapps/administrator/data-integrator)

  - [Data Integrator 錯誤管理和排除障礙](/powerapps/administrator/data-integrator-error-management)

  - [回應系統產生的 DSR 記錄要求，位於 Power Apps、Microsoft Power Automate 和 Dataverse](/powerapps/administrator/powerapps-gdpr-dsr-guide-systemlogs)

- 資料管理：

  - [資料管理](/dynamics365/unified-operations/dev-itpro/data-entities/data-entities-data-packages?toc=%2ffin-and-ops%2ftoc.json)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
