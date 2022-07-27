---
title: 對初始同步期間的問題進行疑難排解
description: 本主題提供的疑難排解資訊可幫助您解決初始同步期間可能出現的問題。
author: RamaKrishnamoorthy
ms.date: 03/16/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 030e565ffff561f6c1efbdd0de9928f70c7c46c0
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8460201"
---
# <a name="troubleshoot-issues-during-initial-synchronization"></a>對初始同步期間的問題進行疑難排解

[!include [banner](../../includes/banner.md)]



本主題提供有關財務和營運應用程式與 Dataverse 之間的雙重寫入整合的疑難排解信息。 具體來說，它提供的資訊可幫助您解決初始同步期間可能出現的問題。

> [!IMPORTANT]
> 本主題解決的一些問題可能需要系統管理員角色或 Microsoft Azure Active Directory (Azure AD) 租使用者管理員認證。 每個問題的部分說明是否需要特定角色或認證。

## <a name="check-for-initial-synchronization-errors-in-a-finance-and-operations-app"></a>檢查財務和營運應用程式中的初始同步錯誤

啟用對應範本後，該對應的狀態應為 **執行中**。 如果狀態是 **不執行**，初始同步期間發生錯誤。 若要查看錯誤，請選取 **雙重寫入** 頁面上的 **初始同步詳情** 索引標籤。

![初始同步詳情索引標籤上的錯誤。](media/initial_sync_status.png)

## <a name="you-cant-complete-initial-synchronization-400-bad-request"></a>您無法完成初始同步：400 錯誤要求

**解決問題所需的角色：** 系統管理員

當您嘗試執行對應和初始同步時，您可能會收到以下錯誤訊息：

*(\[錯誤要求\]，遠端伺服器回傳錯誤：(400) 錯誤要求。)，AX 匯出遇到錯誤。*

這是完整錯誤訊息的範例。

```console
Dual write Initial Sync completed with status: Error. Following are the details:
Executed leg: From AX Financial dimensions to CRM msdyn_dimensionattributes
with exported records count: 0, ImportRecordsErrorCount: 0,
ImportRecordsInsertedCount: 0 and ImportRecordsUpdatedCount: 0
ErrorsDetails:
Dual write Initial sync failed
Message: ([Bad Request], The remote server returned an error: (400) Bad Request.), AX export encountered an error
Stacktrace: at
Microsoft.Dynamics.Integrator.QueryGenerator.AxClient.\<ExportAxPackage\>d__16.MoveNext()
in X:\\bt\\1024532\\repo\\src\\Core\\QueryGenerator\\AxClient.cs:line 265
\--- End of stack trace from previous location where exception was thrown ---
at System.Runtime.ExceptionServices.ExceptionDispatchInfo.Throw()
at System.Runtime.CompilerServices.TaskAwaiter.HandleNonSuccessAndDebuggerNotification(Task task)
at Microsoft.D365.ServicePlatform.Context.ServiceContext.Activity.\<ExecuteAsync\>d__11\`2.MoveNext()
\--- End of stack trace from previous location where exception was thrown ---
```

如果此錯誤持續出現，並且您無法完成初始同步，請按照以下步驟解決此問題。

1. 登入到財務和營運應用程式的虛擬機器 (VM)。
2. 開啟 Microsoft 管理控制台。
3. 在 **服務** 窗格中，確保 Microsoft Dynamics 365 資料匯入匯出架構服務正在執行。 如果它已停止，請重新啟動它，因為初始同步需要它。

## <a name="initial-synchronization-error-403-forbidden"></a>初始同步錯誤：403 禁止

在初始同步期間，您可能會收到以下錯誤訊息：

*(\[禁止\]，遠端伺服器回傳錯誤：(403) 禁止。)，AX 匯出遇到錯誤*

若要修復問題，請按照以下步驟操作。

1. 登入到財務和營運應用程式。
2. 在 **Azure Active Directory 應用程式** 頁面上，刪除 **DtAppID** 使用者端，然後重新新增。

![Azure AD 應用程式清單中的 DtAppID 使用者端。](media/aad_applications.png)

## <a name="self-reference-or-circular-reference-failures-during-initial-synchronization"></a>初始同步期間的自助餐考或循環參考失敗

如果您的任何對應具有自助參考或循環參考，您可能會收到錯誤訊息。 錯誤分為以下幾類：

- [廠商 V2–to–msdyn_vendors 表對應中的錯誤](#error-vendor-map)
- [客戶 V3-to-Accounts 表對應中的錯誤](#error-customer-map)

## <a name="resolve-errors-in-the-vendors-v2tomsdyn_vendors-table-mapping"></a><a id="error-vendor-map"></a>解決廠商 V2–to–msdyn_vendors 表對應中的錯誤

如果資料表具有在 **PrimaryContactPersonId** 和 **InvoiceVendorAccountNumber** 欄中有值的現有資料列，您可能會遇到 **廠商 V2** 到 **msdyn\_vendors** 對應的初始同步錯誤。 出現這些錯誤是因為 **InvoiceVendorAccountNumber** 是自助參考資料欄，而 **PrimaryContactPersonId** 是廠商對應中的循環參考。

您收到的錯誤訊息將具有以下形式。

*無法解析欄位的 GUID：\<field\>。未找到查找：\<value\>。嘗試這個 URL 來檢查參考資料是否存在：`https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>`*

這裡有些範例：

- *無法解析欄位的 GUID：msdyn\_vendorprimarycontactperson.msdyn\_contactpersonid。未找到查找：000056。嘗試這個 URL 來檢查參考資料是否存在：`https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'`*
- *無法解析欄位的 GUID：msdyn\_invoicevendoraccountnumber.msdyn\_vendoraccountnumber。未找到查找：V24-1。嘗試這個 URL 來檢查參考資料是否存在：`https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/msdn_vendors?$select=msdyn_vendoraccountnumber,msdyn_vendorid&$filter=msdyn_vendoraccountnumber eq 'V24-1'`*

如果廠商表中的任何資料列在 **PrimaryContactPersonId** 和 **InvoiceVendorAccountNumber** 欄中有值，請按照以下步驟完成初始同步。

1. 在財務和營運應用程式中，刪除 **PrimaryContactPersonId** 和 **InvoiceVendorAccountNumber** 對應中的資料欄，然後儲存對應。

    1. 在 **廠商 V2 (msdyn\_vendors)** 的雙重寫入對應頁面上，在 **資料表對應** 索引標籤上，在左側過濾器中，選取 **財務和營運應用程式.廠商 V2**。 在右側過濾器中，選取 **銷售.廠商**。
    2. 搜尋 **primarycontactperson** 來尋找 **PrimaryContactPersonId** 來源資料欄。
    3. 選取 **動作**，然後選取 **刪除**。

        ![刪除 PrimaryContactPersonId 欄。](media/vend_selfref3.png)

    4. 重複這些步驟刪除 **InvoiceVendorAccountNumber** 欄。

        ![刪除 InvoiceVendorAccountNumber 欄。](media/vend-selfref4.png)

    5. 儲存對對應的更改。

2. 關閉 **廠商 V2** 表的變更追蹤。

    1. 在 **資料管理** 工作區中，選取 **資料表** 圖格。
    2. 選取 **廠商 V2** 資料表。
    3. 在動作窗格上，選取 **選項**，然後選取 **變更追蹤**。

        ![選取變更追蹤選項。](media/selfref_options.png)

    4. 選取 **停用變更追蹤**。

        ![選取停用變更追蹤](media/selfref_tracking.png)

3. 執行 **廠商 V2 (msdyn\_廠商)** 對應的初始同步。 初始同步應該成功執行，沒有任何錯誤。
4. 執行 **CDS 聯絡人 V2 (聯絡人)** 對應的初始同步。 如果要同步廠商表上的主要聯絡人資料欄，則必須同步此對應，因為還必須對聯絡人行進行初始同步。
5. 將 **PrimaryContactPersonId** 和 **InvoiceVendorAccountNumber** 欄新增回 **廠商 V2 (msdyn\_廠商)** 對應，然後儲存對應。
6. 再次執行 **廠商 V2 (msdyn\_廠商)** 對應的初始同步。 因為變更追蹤已關閉，所以所有行都將同步。
7. 重新打開 **廠商 V2** 表的變更追蹤。

## <a name="resolve-errors-in-the-customers-v3toaccounts-table-mapping"></a><a id="error-customer-map"></a>解決客戶 V3-to-Accounts 表對應中的錯誤

如果資料表具有在 **ContactPersonID** 和 **InvoiceAccount** 欄中有值的現有資料列，您可能會遇到 **客戶 V3** 到 **帳戶** 對應的初始同步錯誤。 出現這些錯誤是因為 **InvoiceAccount** 是自助參考資料欄，而 **ContactPersonID** 是廠商對應中的循環參考。

您收到的錯誤訊息將具有以下形式。

*無法解析欄位的 GUID：\<field\>。未找到查找：\<value\>。嘗試這個 URL 來檢查參考資料是否存在：`https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>`*

這裡有些範例：

- *無法解析欄位的 GUID：primarycontactid.msdyn.msdyn\_contactpersonid。未找到查找：000056。嘗試這個 URL 來檢查參考資料是否存在：`https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'`*
- *無法解析欄位的 GUID：msdyn\_billingaccount.accountnumber。未找到查找：1206-1。嘗試這個 URL 來檢查參考資料是否存在：`https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/accounts?$select=accountnumber.account&$filter=accountnumber eq '1206-1'`*

如果客戶表中的任何資料列在 **ContactPersonID** 和 **InvoiceAccount** 欄中有值，請按照以下步驟完成初始同步。 您可以將此方法用於任何立即可用的資料表，例如 **帳戶** 和 **聯絡人**。

1. 在財務和營運應用程式中，從 **客戶 V3 (帳戶)** 對應中刪除 **ContactPersonID** 和 **InvoiceAccount** 欄，然後儲存對應。

    1. 在 **客戶 V3 (帳戶)** 的雙重寫入對應頁面上，在 **資料表對應** 索引標籤上，在左側過濾器中，選取 **財務和營運應用程式.客戶 V3**。 在右側過濾器中，選取 **Dataverse.帳戶**。
    2. 搜尋 **contactperson** 來尋找 **ContactPersonID** 來源資料欄。
    3. 選取 **動作**，然後選取 **刪除**。

        ![刪除 ContactPersonID 欄。](media/cust_selfref3.png)

    4. 重複這些步驟刪除 **InvoiceAccount** 欄。

        ![刪除 InvoiceAccount 欄。](media/cust_selfref4.png)

    5. 儲存對對應的更改。

2. 關閉 **客戶 V3** 表的變更追蹤。

    1. 在 **資料管理** 工作區中，選取 **資料表** 圖格。
    2. 選取 **客戶 V3** 資料表。
    3. 在動作窗格上，選取 **選項**，然後選取 **變更追蹤**。

        ![選取變更追蹤選項。](media/selfref_options.png)

    4. 選取 **停用變更追蹤**。

        ![選取停用變更追蹤](media/selfref_tracking.png)

3. 執行 **客戶 V3 (帳戶)** 對應的初始同步。 初始同步應該成功執行，沒有任何錯誤。
4. 執行 **CDS 聯絡人 V2 (聯絡人)** 對應的初始同步。

    > [!NOTE]
    > 有兩張同名的對應。 請務必在 **詳情** 索引標籤上選取具有以下描述的對應：**用於在 FO.CDS 廠商聯絡人 V2 到 CDS.聯絡人之間同步的雙重寫入範本：需要新套件 \[Dynamics365SupplyChainExtended\]。**

5. 將 **InvoiceAccount** 和 **ContactPersonId** 欄新增回 **客戶 V3 (帳戶)** 對應，然後儲存對應。 **InvoiceAccount** 欄和 **ContactPersonId** 欄現在再次成為即時同步模式的一部分。 在下一步中，您將對這些資料欄進行初始同步。
6. 再次執行 **客戶 V3 (帳戶)** 對應的初始同步。 由於變更追蹤已關閉，因此 **InvoiceAccount** 和 **ContactPersonId** 的資料將從財務和營運應用程式同步到 Dataverse。
7. 若要將 **InvoiceAccount** 和 **ContactPersonId** 的資料從 Dataverse 同步到財務和營運應用程式，您必須使用資料整合專案。

    1. 在 Power Apps 中，於 **Sales.Account** 和 **財務和營運應用程式.客戶 V3** 表之間建立資料整合專案。 資料方向必須從 Dataverse 到財務和營運應用程式。 因為 **InvoiceAccount** 是雙重寫入中的新屬性，您可能希望跳過它的初始同步。 如需相關資訊，請參閱[將資料整合到 Dataverse](/power-platform/admin/data-integrator)。

        下圖顯示了更新的專案 **CustomerAccount** 和 **ContactPersonId**。

        ![要更新 CustomerAccount 和 ContactPersonId 的資料整合專案。](media/cust_selfref6.png)

    2. 在 Dataverse 端的過濾器中新增公司條件，以便僅在財務和營運應用程式中更新與篩選條件相符的資料列。 若要新增過濾器，請選取過濾器按鈕。 那麼，在 **編輯查詢** 對話方塊中，您可以新增過濾查詢，例如 **\_msdyn\_company\_value eq '\<guid\> '**。

        > [注意] 如果過濾器按鈕不存在，請建立支援票證以要求資料整合團隊在您的租使用者上啟用過濾器功能。

        如果您不輸入過濾器查詢 **\_msdyn\_company\_value**，所有資料列將進行同步。

        ![新增過濾器查詢。](media/cust_selfref7.png)

    該資料列的初始同步現已完成。

8. 在財務和營運應用程式中，為 **客戶 V3** 資料表重新打開變更追蹤。

## <a name="initial-sync-failures-on-maps-with-more-than-10-lookup-fields"></a>含超過 10 個查找欄位的對應上的初始同步失敗

當您嘗試在 **客戶 V3 - 帳戶**、**銷售訂單** 對應或具有 10 個以上查找欄位的任何對應上執行初始同步失敗時，您可能會收到以下錯誤訊息：

*CRMExport：套件執行完成。錯誤描述 5 嘗試從 https://xxxxx//datasets/yyyyy/tables/accounts/items?$select=accountnumber, address2_city, address2_country, ... (msdyn_company/cdm_companyid eq 'id')&$orderby=accountnumber asc 取得資料失敗。*

由於查詢的查找限制，當實體對應包含超過 10 個查找時，初始同步將失敗。 如需相關資訊，請參閱[使用查詢取出相關資料表記錄 ](/powerapps/developer/common-data-service/webapi/retrieve-related-entities-query)。

若要修復此問題，請按照以下步驟操作：

1. 從雙重寫入實體對應中刪除可選的查找欄位，以便查找的數量為 10 或更少。
2. 儲存對應並進行初始同步。
3. 第一步的初始同步成功後，新增剩餘的查找欄位並刪除您在第一步中同步的查找欄位。 確保查找欄位的數量為 10 或更少。 儲存對應並執行初始同步。
4. 重複這些步驟，直到所有查找欄位都同步。
5. 將所有查找欄位新增回對應，儲存對應，然後執行對應和 **跳過初始同步**。

此流程可啟用即時同步模式的對應。

## <a name="known-issue-during-initial-sync-of-party-postal-addresses-and-party-electronic-addresses"></a>初始同步合作對象郵政地址和合作對象電子郵件地址期間的已知問題

當您嘗試執行合作對象郵政地址和合作對象電子郵件地址的初始同步時，您可能會收到以下錯誤訊息：

*在 Dataverse 中找不到合作對象編號。*

在財務和營運應用程式中的 **DirPartyCDSEntity** 上設定了一個範圍，用於過濾 **人員** 和 **組織** 類型。 因此，**CDS 方 - msdyn_parties** 對應的初始同步不會同步其他類型的各方，包括 **法律實體** 和 **營運單位**。 當針對 **CDS 方郵寄地址 (msdyn_partypostaladdresses)** 或 **合作對象聯或人 V3 (msdyn_partyelectronicaddresses)** 執行初始同步時，您可能會收到錯誤訊息。

我們正在修復以刪除 Finance and Operations 實體上的參與方類型範圍，以便所有類型的參與方都可以成功地同步到 Dataverse。

## <a name="are-there-any-performance-issues-while-running-initial-sync-for-customers-or-contacts-data"></a>為客戶或聯絡人資料執行初始同步時是否存在任何效能問題？

如果您已為 **客戶** 資料執行初始同步並執行 **客戶** 對應，然後為 **聯絡人** 資料執行初始同步，則在為 **聯絡人** 地址插入和更新 **LogisticsPostalAddress** 和 **LogisticsElectronicAddress** 表期間可能會出現效能問題。 為 **CustCustomerV3Entity** 和 **VendVendorV2Entity** 追蹤相同的全球郵政地址和電子郵件地址表，並且雙重寫入嘗試構建更多查詢以將資料寫入另一端。 如果您已為 **客戶** 執行初始同步，則在為 **聯絡人** 資料執行初始同步時停止相應的對應。 對 **廠商** 資料執行相同的操作。 初始同步完成後，您可以透過跳過初始同步來執行所有對應。

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
