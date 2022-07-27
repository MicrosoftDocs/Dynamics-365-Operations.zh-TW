---
title: 同步處理問題即時疑難排解
description: 本主題提供可幫助您解決即時同步處理問題的疑難排解資訊。
author: RamaKrishnamoorthy
ms.date: 08/19/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: df184decdfa900ccb5c2070575e55052b9dfc547
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8460198"
---
# <a name="troubleshoot-live-synchronization-issues"></a>同步處理問題即時疑難排解

[!include [banner](../../includes/banner.md)]



本主題提供有關財務和營運應用程式和 Microsoft Dataverse 之間雙重寫入整合的疑難排解資訊。 具體來說，本主題提供的資訊可幫助您解決即時同步處理的問題。

> [!IMPORTANT]
> 本主題解決的一些問題可能需要系統管理員角色或 Azure Active Directory (Azure AD) 租戶管理員認證。 每個部分都說明是否需要特定角色或特定認證。

## <a name="live-synchronization-shows-an-error-when-you-create-a-row"></a>即時同步處理在建立資料列時顯示錯誤

在財務和營運應用程式中建立資料列時，您可能會收到以下錯誤訊息：

*\[{\\“錯誤\\“：{\\“代碼\\“：\\ "0x80072560\\"，\\“訊息\\“：\\“使用者不是該組織的成員。\\"}}\]，遠端伺服器回傳錯誤：(403) Forbidden。”}}”。*

若要解決此問題，請按照[系統要求和先決條件 ](requirements-and-prerequisites.md)中的步驟。 若要完成這些步驟，雙重寫入應用程式使用者在 Dataverse 必須具有系統管理員角色。 預設擁有團隊還必須具有系統管理員角色。

## <a name="live-synchronization-shows-an-error-when-you-try-to-save-table-data"></a>當您嘗試儲存表資料時，即時同步顯示錯誤

**解決問題所需的角色：** 系統管理員

在財務和營運應用程式中嘗試儲存資料表資料時，您可能會收到以下錯誤訊息：

*無法將更改儲存到資料庫。工作單元無法送出交易。無法將資料寫入實體 uom。寫入 UnitOfMeasureEntity 失敗並顯示錯誤訊息無法與實體 uoms 同步。*

若要解決此問題，請確保先決條件參考資料存在於財務和營運應用程式和 Dataverse。 例如，如果客戶記錄屬於特定客戶組，請確保客戶組記錄存在於 Dataverse。

如果這兩個地方都存在資料，並且您已確認問題與資料無關，請按照以下步驟操作。

1. 透過使用 Excel 增益集開啟 **DualWriteProjectConfigurationEntity** 實體。 若要使用增益集，請在 Finance and Operations Excel 增益集中啟用設計模式，然後將 **DualWriteProjectConfigurationEntity** 新增到工作表。 如需相關資訊，請參閱[使用 Excel 檢視和更新實體資料](../../office-integration/use-excel-add-in.md)。
2. 選取並刪除雙重寫入對應和專案中存在問題的記錄。 每個雙重寫入對應都會有兩條記錄。
3. 使用 Excel 增益集發布更改。 此步驟很重要，因為它會從實體和基礎表中刪除記錄。

## <a name="handle-read-or-write-privilege-errors-when-you-create-data-in-a-finance-and-operations-app"></a>在財務和營運應用程式中建立資料時處理讀取或寫入權限錯誤

在財務和營運應用程式中建立資料時，您可能會收到「錯誤的要求」錯誤訊息。

![錯誤要求錯誤訊息的範例。](media/error_record_id_source.png)

若要解決此問題，您必須透過將正確的安全角色指派給對應的 Dynamics 365 Sales 或 Dynamics 365 Customer Service 事業單位的團隊來啟用缺少的權限。

1. 在財務和營運應用程式中，找到在資料集成連接集中對應的事業單位。

    ![組織對應。](media/mapped_business_unit.png)

2. 在 Customer Engagement 應用程式中，登入到環境，進入 **設定\>安全性**，並找到對應的事業單位團隊。

    ![對應的事業單位團隊。](media/setting_security_page.png)

3. 開啟團隊頁面進行編輯，然後選取 **管理角色**。

    ![管理角色按鈕。](media/manage_team_roles.png)

4. 在 **管理團隊角色** 對話方塊中，指派對相關資料表具有讀/寫權限的角色，然後選取 **確定**。

## <a name="fix-synchronization-issues-in-an-environment-that-has-a-recently-changed-dataverse-environment"></a>修復最近更改的 Dataverse 環境中的同步問題

**解決問題所需的角色：** 系統管理員

在財務和營運應用程式中建立資料時，您可能會收到以下錯誤訊息：

*{"entityName":"CustCustomerV3Entity","executionStatus":2,"fieldResponses":\[\],"recordResponses":\[{"errorMessage":"**無法為實體 CustCustomerV3Entity 產生有效承載**","logDateTime":"2019-08-27T18:51:52.5843124Z","verboseError":"含錯誤無效 URI 的承載建立失敗：URI 為空白。"}\],"isErrorCountUpdated":true}*

這是 Customer Engagement 應用程式中的錯誤訊息：

> ISV 代碼發生意外錯誤。 (ErrorType = ClientError) 外掛程式意外例外狀況 (執行) ：Microsoft.Dynamics.Integrator.DualWriteRuntime.Plugins.PostCommitPlugin：System.Exception：未能處理實體帳戶 - (連線嘗試失敗，因為連線方沒有正確回應一段時間後，或建立連線失敗，因為連線的主機沒有回應。

如果您試圖在財務和營運應用程式中建立資料時，Dataverse 環境被錯誤地重設，就會出現該錯誤。

> [!IMPORTANT]
> 如果您已重新連結環境，則必須先停止所有實體對應，然後再繼續執行風險降低步驟。

若要解決此問題，您必須完成 Dataverse 及財務和營運應用程式中的兩個步驟。

1. 在財務和營運應用程式中，執行以下步驟：

    1. 透過使用 Excel 增益集開啟 **DualWriteProjectConfigurationEntity** 實體。 若要使用增益集，請在 Finance and Operations Excel 增益集中啟用設計模式，然後將 **DualWriteProjectConfigurationEntity** 新增到工作表。 如需相關資訊，請參閱[使用 Excel 檢視和更新實體資料](../../office-integration/use-excel-add-in.md)。
    2. 選取並刪除雙重寫入對應和專案中存在問題的記錄。 每個雙重寫入對應都會有兩條記錄。
    3. 使用 Excel 增益集發布更改。 此步驟很重要，因為它會從實體和基礎表中刪除記錄。
    4. 若要在您重新連結 Finance and Operations 或 Dataverse 環境時防止錯誤發生中，請確保沒有保留雙重寫入設定。

2. 在 Dataverse 中，請依下列步驟操作：

    1. 登入您的 Dataverse 環境 (例如，`https://*****.crm.dynamics.com/`)。
    2. 進入 **進階設定**\>**進階尋找**。
    3. 選取 **DualWrite 執行階段設定**。
    4. 選取要檢視的資料欄。
    5. 選取 **結果** 查看設定。
    6. 刪除所有實體。

3. 在財務和營運應用程式中，執行以下步驟：

    1. 透過使用 Excel 增益集開啟 **DualWriteProjectConfigurationEntity** 實體。 若要使用增益集，請在 Finance and Operations Excel 增益集中啟用設計模式，然後將 **DualWriteProjectConfigurationEntity** 新增到工作表。 如需相關資訊，請參閱[使用 Excel 檢視和更新實體資料](../../office-integration/use-excel-add-in.md)。
    2. 選取並刪除雙重寫入對應和專案中存在問題的記錄。 每個雙重寫入對應都會有兩條記錄。
    3. 使用 Excel 增益集發布更改。 此步驟很重要，因為它會從實體和基礎表中刪除記錄。
    4. 若要在您重新連結 Finance and Operations 或 Dataverse 環境時防止錯誤發生中，請確保沒有保留雙重寫入設定。

## <a name="live-synchronization-error-after-you-do-a-full-database-copy"></a>執行完整資料庫複製後發生即時同步處理錯誤

從一個系統向另一個系統執行完整資料庫副本，然後嘗試執行資料庫操作後，您可能會收到以下錯誤訊息：

*SecureConfig 組織 (???) 與實際 CRM 組織 (???) 不相符。*

雙重寫入執行階段外掛程式顯示錯誤訊息，以確保在一個系統中設定的雙重寫入設定不能在另一個系統中使用。

若要解決此問題，請還原資料庫後刪除 **msdyn_dualwriterruntimeconfig** 資料表。 如需相關資訊，請參閱[取消連結和重新連結雙重寫入環境](relink-environments.md)。

## <a name="live-synchronization-issues-that-are-caused-by-incorrect-query-filter-syntax-on-the-dual-write-maps"></a>由雙重寫入對應上不正確的查找過濾器句法導致的即時同步處理問題

即使雙重寫入對應過濾器的查找運算式在句法上是正確的，它也可能無法按預期工作。 過濾器運算式位於實體上，而不是查找對象的單個資料來源上。 因此，產生的 SQL 查找不會返回預期的結果。

以下是一個範例。

```dos
Query entity = PROJECTENTITY
Query expression = (ParentProject == "")
```

您可能希望過濾掉沒有父系的專案。但是，過濾器不起作用，因為它已轉換為類似於以下範例的查找。

```sql
SELECT T1.RECID,T1.MODIFIEDDATETIME,T1.RECVERSION,T1.RECID,T1.DIMENSION,
T1.LOCATION,T1.PROJECTCONTROLLER,T1.PROJECTID,T1.PROJECTMANAGER,T1.REFERENCE,
T1.SALESMANAGER,T1.SCHEDULED,T1.RECVERSION#8,T1.RECVERSION#7,
T1.RECVERSION#6,T1.RECVERSION#5,T1.RECVERSION#4,T1.RECVERSION#3,
T1.RECVERSION#2,T1.RECID#8,T1.RECID#7,T1.RECID#6,T1.RECID#5,
T1.RECID#4,T1.RECID#3,T1.RECID#2,T1.PARTITION FROM PROJECTENTITY T1 
WHERE(((((((((((PARTITION=5637144576) AND (DATAAREAID=N'usmf')) AND 
((PARTITION#2=5637144576) OR (PARTITION#2 IS NULL))) AND 
((PARTITION#3=5637144576) OR (PARTITION#3 IS NULL))) AND 
((PARTITION#4=5637144576) OR (PARTITION#4 IS NULL))) AND 
((PARTITION#5=5637144576) OR (PARTITION#5 IS NULL))) AND 
((PARTITION#6=5637144576) OR (PARTITION#6 IS NULL))) AND 
((PARTITION#7=5637144576) OR (PARTITION#7 IS NULL))) AND 
((PARTITION#8=5637144576) OR (PARTITION#8 IS NULL))) AND 
((DATAAREAID#8=N'usmf') OR (DATAAREAID#8 IS NULL))) AND 
(PARENTPROJECT='')) 
ORDER BY T1.PROJECTID
```

實際結果是 `parentProject` 欄位被評估為 `null`。 然而，`null` 與空白字串不同。 由於這種不相符情況，查找過濾器不會返回有效結果。

若要修復問題，請按照以下步驟操作。

1. 新增計算資料資料欄，該資料欄可以新增到擴展模型中，並且由將 `null` 轉換到空白字串的邏輯備份。

    ```dos
    SysComputedColumn::if(SysComputedColumn::isNullExpression(ParentProject), SysComputedColumn::returnLiteral(""), fieldName);
    ```

2. 在新的計算資料資料欄上使用過濾器而不是預設資料欄。

若要在開發環境中評估過濾器，您可以使用以下 X++ 代碼來驗證結果。 將此代碼作為獨立程式執行。 您可以使用它來評估適用於實體的不同類型的過濾器，然後再於雙重寫入對應上使用這些過濾器。 可以針對資料庫執行查找以評估差異。

```xpp
var entityName = "PROJECTENTITY";
var filterExpression = '(ParentProject == "")';
Query query = new Query();
query.literals(NoYes::Yes); 
QueryBuildDataSource qbd = query.addDataSource(tablename2id(entityName));
qbd.addRange(fieldname2id(qbd.table(),identifierStr(RecVersion))).value(filterExpression);
qbd.addSelectionField(fieldname2id(qbd.table(),identifierStr(RecId)));
QueryRun qRun = new QueryRun(query);
// This provides the actual sql statement to execute
var actualSqlStatement = query.getSQLStatement();
while(qRun.next())
{
    var rec = qRun.get(tableName2Id(entityName));
}
```

## <a name="data-from-finance-and-operations-apps-isnt-synced-to-dataverse"></a>財務和營運應用程式中的資料未同步到 Dataverse

在即時同步處理期間，您可能會遇到只有部分資料從財務和營運應用程式同步到 Dataverse，或資料根本不同步。

> [!NOTE]
> 您必須在開發過程中解決此問題。

在開始解決問題之前，請查看以下先決條件：

+ 確保您的自訂更改寫入單個交易範圍。
+ 商業事件和雙重寫入架構不處理 `doinsert()`、`doUpdate()` 和 `recordset()` 作業，或記錄 `skipBusinessEvents(true)` 被標記的地方。 如果您的代碼在這些函數中，則不會觸發雙重寫入。
+ 商業事件必須登記為對應的資料來源。 某些資料來源可能使用外部聯結，並且可能在財務和營運應用程式中標記為讀取專用。 不會追蹤這些資料來源。
+ 僅當修改在對應欄位上時才會觸發更改。 未對應的欄位修改不會觸發雙重寫入。
+ 確保過濾器評估提供有效結果。

### <a name="troubleshooting-steps"></a>疑難排解步驟

1. 查看雙重寫入管理頁面上的欄位對應。 如果欄位未從財務和營運應用程式對應到 Dataverse，就不會被追蹤。 例如，在下圖中，**描述** 欄位可從 Dataverse 中追蹤，但無法從財務和營運應用程式中追蹤。 不會追蹤財務和營運應用程式中對該欄位的任何更改。

    ![追蹤欄位。](media/live-sync-troubleshooting-1.png)

2. 確定是否在商業事件定義中追蹤資料來源。 例如，在下圖中，**DefaultDimensionDAVs** 表和基礎表的任何欄位都不會被追蹤到變化。 不追蹤使用外部聯結並標記為讀取專用的資料來源。

    ![未追蹤的欄位。](media/live-sync-troubleshooting-2.png)

3. 確定對應的資料表欄位是否出現在 **BUSINESSEVENTSDEFINITION** 表中，如下圖所示。 如果在查找結果中沒有找到您要查找的欄位，則不會被雙重寫入觸發。

    ![資料表中的追蹤欄位。](media/live-sync-troubleshooting-3.png)

### <a name="sample-scenario"></a>樣本案例

在財務和營運應用程式中，聯絡人記錄的地址有更新，但地址更改未同步到 Dataverse。 出現這種情況是因為在 **BusinessEventsDefinition** 表具有受影響的資料表和實體的組合。 具體來說，**LogisticsPostalAddress** 表不是 **smmContactpersonCDSV2Entity** 實體的直接資料來源。 **smmContactpersonCDSV2Entity** 實體有 **smmContactPersonV2Entity** 作為資料來源，以及 **smmContactPersonV2Entity**，反過來，有 **LogisticsPostalAddressBaseEntity** 作為資料來源。 **LogisticsPostalAddress** 表是 **LogisticsPostalAddressBaseEntity** 的資料來源。

在某些非標準模式中可能會出現類似情況，例如在財務和營運應用程式中修改的資料表沒有明顯連結到包含它的實體的情況。 例如，主地址資料是在 **smmContactPersonCDSV2Entity** 實體上計算。 雙重寫入架構嘗試確定對基礎表的更改如何對應回實體。 通常，這種方法就足夠了。 但是，在某些情況下，連結非常複雜，您必須具體說明。 您必須確保相關資料表的 **RecId** 可直接在實體上使用。 然後新增靜態方法來監控資料表的更改。

例如，查看 **smmContactPersonCDSV2Entity::getEntityDataSourceToFieldMapping()** 方法。 **CustCustomerV3entity** 和 **VendVendorV2Entity** 已修改來處理這種情況。

若要修復問題，請按照以下步驟操作。

1. 將 **PrimaryPostalAddressRecId** 欄位新增到 **smmContactPersonV2Entity** 實體。 使其成為內部內容。

    ![新增到 smmContactPersonV2Entity 實體的欄位。](media/Troubleshoot_live_sync_issue_1.png)

2. 將相同欄位新增到 **smmContactPersonCDSV2Entity** 實體。

    ![新增到 smmContactPersonCDSV2Entity 實體的欄位。](media/Troubleshoot_live_sync_issue_2.png)

3. 將以下方法新增到 **smmContactPersonCDSV2Entity** 類別。

    ```xpp
    public static container getEntityDataSourceToFieldMapping(container mapping)
    {
        mapping += [[tablestr(smmContactPersonCDSV2Entity), tablenum(LogisticsPostalAddress), fieldstr(smmContactPersonCDSV2Entity, PrimaryPostalAddressRecId)]];
        return mapping;
    }
    ```

4. 同步資料庫，並構建應用程式。
5. 停止在所有 **smmContactPersonCDSV2Entity** 實體上的雙重寫入對應。
6. 啟動對應。 您應該看到新資料表 (本範例中的 **LogisticsPostalAddress**)，您已經開始使用 **RefTableName** 資料欄來追蹤，其中 **Refentityname** 值等於 **BusinessEventsDefinition** 表中的 **smmContactPersonCDSV2Entity**。

## <a name="error-when-you-create-a-record-where-multiple-records-are-sent-from-a-finance-and-operations-app-to-dataverse-in-the-same-batch"></a>建立記錄時出錯，其中多條記錄從財務和營運應用程式傳送到同一批次的 Dataverse

對於任何交易，財務和營運應用程式都會批次建立資料並將其作為批次作業發送到 Dataverse。 如果兩條記錄是作為同一交易的一部分建立的，並且它們相互參考，您可能會在財務和營運應用程式中收到類似於以下範例的錯誤訊息：

*無法將資料寫入實體 aaa_fundingsources。無法查找 ebecsfs_contracts 與值 {PC00...}。無法查找 aaa_fundingsources 與值 {PC00...}。寫入 aaa_fundingsources 失敗，出現錯誤訊息，例外狀況訊息：遠端伺服器回傳錯誤：(400) 錯誤的要求。*

若要解決此問題，請在財務和營運應用程式中建立實體關係以指示兩個實體彼此相關，並且相關記錄在同一交易中處理。

## <a name="enable-verbose-logging-of-error-messages"></a>啟用錯誤訊息的詳細記錄

在財務和營運應用程式中，您可能會遇到與 Dataverse 環境相關的錯誤。 錯誤訊息可能不包含訊息的全文或其他相關資料。 若要取得更多資訊，您可以透過設定 **IsDebugMode** 標幟來啟用詳細的記錄，該標幟存在於財務和營運應用程式中所有專案設定的 **DualWriteProjectConfigurationEntity** 實體上。

1. 透過使用 Excel 增益集開啟 **DualWriteProjectConfigurationEntity** 實體。 若要使用增益集，請在 Finance and Operations Excel 增益集中啟用設計模式，然後將 **DualWriteProjectConfigurationEntity** 新增到工作表。 如需相關資訊，請參閱[使用 Excel 檢視和更新實體資料](../../office-integration/use-excel-add-in.md)。
2. 在專案上將 **IsDebugMode** 標幟設定為 **是**。
3. 執行案例。
4. 詳細記錄在 **DualWriteErrorLog** 資料表中有提供。 若要使用資料表瀏覽器尋找資料，請使用以下 URL：`https://XXXaos.cloudax.dynamics.com/?mi=SysTableBrowser&tableName=DualWriteErrorLog`。
5. 若要在偵錯模式下擷取更多記錄，請將更新安裝在[KB 4595434 (修復了在雙重寫入即時同步中傳播的空白值) ](https://fix.lcs.dynamics.com/Issue/Details?kb=4595434&bugId=527820&dbType=3&qc=c29ce15a80e6b3b4c01a722d9bdae1d7e71aa3662a044cfd0b765f736cfa98e9)。

## <a name="error-when-you-add-an-address-for-a-customer-or-contact"></a>為客戶或聯絡人新增地址時出錯

當您嘗試在財務和營運應用程式或 Dataverse 中新增客戶或聯絡人的地址時，您可能會收到以下錯誤訊息：

*無法將資料寫入實體 msdyn_partypostaladdresses。寫入 DirPartyPostalAddressLocationCDSEntity 失敗，出現錯誤訊息。要求失敗，出現狀態代碼 BadRequest 和 CDS 錯誤代碼：0x80040265 回應訊息：外掛程式中出現錯誤。有屬性值的記錄。位置 ID 已存在。實體金鑰位置 ID 金鑰需要此屬性集加入獨特值。選取獨特值並再試一次。*

若要解決此問題，請安裝雙重寫入協調流程套件版 (2.2.2.60)，以便 **地址** 表的定義如下表所示。

| 屬性 | 值 |
|---|---|
| 顯示名稱 | **位置金鑰** |
| 姓名 | **msdyn_locationkey** |
| 欄位 | **msdyn_locationid**, **parentid** |
| 狀態 | **使用中** |
| 系統作業 | 空白 |

## <a name="error-when-you-add-a-customer-in-dataverse"></a>在 Dataverse 新增客戶時出錯

當您試圖在 Dataverse 中新增客戶時，您可能會收到以下錯誤訊息：

*「RecordError0」：「實體客戶 V3 寫入失敗，出現未知異常 - 未找到合作對象類型「組織」的合作對象記錄」}。*

當客戶於 Dataverse 建立時，會產生新的合作對象號碼。 當客戶記錄與合作對象同步到財務和營運應用程式時，將顯示錯誤訊息，但已有客戶記錄具有不同的合作對象編號。

若要解決此問題，請透過合作對象查找找到客戶。 如果客戶不存在，則建立新的客戶記錄。 如果客戶確實存在，則使用現有合作對象建立新的客戶記錄。

## <a name="error-when-you-create-a-new-customer-vendor-or-contact-in-dataverse"></a>在 Dataverse 建立新客戶、廠商或聯絡人時出錯

當您試圖在 Dataverse 建立新客戶、廠商或聯絡人時，您可能會收到以下錯誤訊息：

*無法將合作對象的類型從「DirOrganization」更新為「DirPerson」，應該先刪除現有的合作對象，然後插入新的類型。*

在 Dataverse 中的 **msdyn_party** 資料表上有數字序列。 在 Dataverse 建立帳戶時，會建立新的合作對象 (例如 **組織** 類型的 **合作對象-001**)。 此資料將發送到財務和營運應用程式。 如果 Dataverse 環境已重設，或 Finance and Operations 環境會連結到不同的 Dataverse 環境，然後在 Dataverse 建立新的聯絡人記錄，則會建立以 **合作對象-001** 開頭的新合作對象值。 這一次，建立的合作對象記錄將是 **人員** 類型的 **合作對象-001**。 同步處理此資料時，財務和營運應用程式會顯示上述錯誤訊息，因為合作對象記錄 **組織** 類型的 **合作對象-001** 已經存在。

若要解決這個問題，請將 Dataverse 中 **msdyn_party** 表的 **msdyn_partynumber** 欄位的自動編號序列改為不同的自動編號序列。

## <a name="performance-issue-with-customer-or-contact-mappings"></a>客戶或聯絡人對應的效能問題

透過自訂 **getEntityDataSourceToFieldMapping** 方法 (在 **CustCustomerV3Entity** 實體中) 方法和 **getEntityDataSourceToFieldMapping** 方法 (在 **smmContactPersonCDSV2Entity** 實體中)，您也許能夠稍微改善客戶和聯絡人的即時同步處理效能。 這些自訂減少了 **BusinessEventsDefinition** 資料表中的記錄數量。 記錄數量的減少反過來又減少了引發的事件的數量。

在 **CustCustomerV3Entity** 實體中的 **getEntityDataSourceToFieldMapping** 方法可以確保客戶的電子位址或郵政位址的更新會觸發商務活動，這樣更新的資料就會被發送到 Dataverse。 如果您不使用所有欄位並且不需要雙重寫入中的資訊，請在方法中用註解蓋掉相應的行列。 在這個方法中新增的每個被追蹤的欄位和資料表都會在 **BusinessEventsDefinition** 表中為被追蹤的資料表和被追蹤的實體的組合新增記錄。

```xpp
public static container getEntityDataSourceToFieldMapping(container mapping)
{
    mapping += [
        [tablestr(DirPartyBaseEntity), tablenum(LogisticsPostalAddress), fieldstr(CustCustomerV3Entity, AddressRecordId)],
        [identifierstr(DirPartyBaseEntity), tablenum(LogisticsElectronicAddress), fieldstr(CustCustomerV3Entity, PrimaryContactURLRecordId)],
        [identifierstr(DirPartyBaseEntity1), tablenum(LogisticsElectronicAddress), fieldstr(CustCustomerV3Entity, PrimaryContactPhoneRecordId)],
        [identifierstr(DirPartyBaseEntity2), tablenum(LogisticsElectronicAddress), fieldstr(CustCustomerV3Entity, PrimaryContactEmailRecordId)],
        [identifierstr(DirPartyBaseEntity3), tablenum(LogisticsElectronicAddress), fieldstr(CustCustomerV3Entity, PrimaryContactFaxRecordId)],
        [identifierstr(DirPartyBaseEntity4), tablenum(DirPartyLocation), fieldstr(CustCustomerV3Entity, DirPartyLocationRecordId)],
        [identifierstr(DirPartyBaseEntity5), tablenum(LogisticsPostalAddress), fieldstr(CustCustomerV3Entity, InvoiceAddressRecordId)],
        [identifierstr(DirPartyBaseEntity6), tablenum(LogisticsPostalAddress), fieldstr(CustCustomerV3Entity, DeliveryAddressRecordId)],
        [identifierStr(DirPartyBaseEntity7), tablenum(DirPartyTable), fieldstr(CustCustomerV3Entity, PartyRecordId)]];
    return mapping;
}
```

在相同情況下，在 **smmContactPersonCDSV2Entity** 實體中的 **getEntityDataSourceToFieldMapping** 方法可以確保聯絡人的電子位址或郵政位址的任何更新會觸發商務活動，這樣更新的資料就會被發送到 Dataverse。 在該方法中，您可以用註解蓋掉您不使用的任何欄位的行列。

```xpp
public static container getEntityDataSourceToFieldMapping(container mapping)
{
    mapping += [
        [tablestr(DirPartyBaseEntity), tablenum(LogisticsPostalAddress), fieldstr(smmContactPersonCDSV2Entity, PrimaryPostalAddressRecId)],
        [identifierStr(DirPartyBaseEntity), tablenum(DirPartyTable), fieldstr(smmContactPersonCDSV2Entity, PrimaryAddressLocation)],
        [identifierStr(DirPartyBaseEntity1), tablenum(LogisticsElectronicAddress), fieldstr(smmContactPersonCDSV2Entity, PrimaryContactEmailRecordId)],
        [identifierStr(DirPartyBaseEntity2), tablenum(LogisticsElectronicAddress), fieldstr(smmContactPersonCDSV2Entity, PrimaryContactFaxRecordId)],
        [identifierStr(DirPartyBaseEntity3), tablenum(LogisticsElectronicAddress), fieldstr(smmContactPersonCDSV2Entity, PrimaryContactPhoneRecordId)],
        [identifierStr(DirPartyBaseEntity4), tablenum(LogisticsElectronicAddress), fieldstr(smmContactPersonCDSV2Entity, PrimaryContactFacebookRecordId)],
        [identifierStr(DirPartyBaseEntity5), tablenum(LogisticsElectronicAddress), fieldstr(smmContactPersonCDSV2Entity, PrimaryContactTwitterRecordId)],
        [identifierStr(DirPartyBaseEntity6), tablenum(LogisticsElectronicAddress), fieldstr(smmContactPersonCDSV2Entity, PrimaryContactURLRecordId)],
        [identifierStr(DirPartyBaseEntity7), tablenum(LogisticsElectronicAddress), fieldstr(smmContactPersonCDSV2Entity, PrimaryContactLinkedInRecordId)],
        [identifierStr(DirPartyBaseEntity8), tablenum(LogisticsElectronicAddress), fieldstr(smmContactPersonCDSV2Entity, PrimaryContactTelexRecordId)],
        [identifierStr(DirPartyBaseEntity9), tablenum(DirPartyTable), fieldstr(smmContactPersonCDSV2Entity, PartyRecordId)]];
    return mapping;
}
```

更新方法後，請按照下列步驟操作。

1. 同步資料庫，並構建應用程式。
2. 停止所有在 **smmContactPersonCDSV2Entity** 和 **CustCustomerV3Entity** 實體上的雙重寫入對應。
3. 啟動對應。 您應該會在 **smmContactPersonCDSV2Entity** 和 **CustCustomerV3Entity** 實體以及 **BusinessEventsDefinition** 表中看到更少記錄，並且效能可能會略有提高。

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
