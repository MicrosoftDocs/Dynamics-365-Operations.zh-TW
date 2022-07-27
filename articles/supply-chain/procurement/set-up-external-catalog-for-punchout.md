---
title: 設定發包電子採購的外部目錄
description: 本主題介紹使用外部目錄或發包目錄從廠商處收集報價資訊並將其新增到申請中。
author: Henrikan
ms.date: 11/02/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart, PurchVendorPortalRequests, CatExternalCatalogConfiguration, CatCXMLCartLogList
audience: Application User
ms.reviewer: kamaybac
ms.custom: 30211
ms.assetid: 3c7e0e1c-703c-4bbf-b90c-84d29a131360
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9f1065c68723baa395bc06be6313e45a44661ea3
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8447966"
---
# <a name="set-up-an-external-catalog-for-punchout-e-procurement"></a>設定發包電子採購的外部目錄

[!include [banner](../includes/banner.md)]

透過使用外部目錄，您可以確保隨後在 Supply Chain Management 中處理的產品和價格資訊是準確且最新的。 然後可以核准申請並將其轉換為訂購單，並且可以向廠商下單。

設定好外部目錄且員工正在準備申請時，將可以選擇重新導向到外部網站，即外部目錄，並返回在外部網站建立的購物籃。 這種通訊是以 cXML 通訊協定為基礎，且必須在買賣組織的系統之間建立。

若要建立通訊，您的廠商必須提供一些資訊供您在外部目錄的設定中使用，例如身份、買方公司的網域 (例如 "DUNS" 和 "DUNS 編號")、認證和觸達廠商目錄的 URL。

## <a name="setting-up-an-external-catalog"></a>設定外部目錄

外部目錄應支援輸入採購申請的員工能重新導向到外部網站以選擇產品。 將傳回員工從外部目錄選擇的產品和最新的價格資訊，並且可以從這裡將它們新增到採購申請中。 其目的不是讓員工能夠在外部網站下訂單。 在設定外部目錄時，您需要確保外部目錄可造訪的網站的目的是收集報價資訊，而不是實際下單。

### <a name="to-set-up-an-external-vendor-catalog-complete-the-following-tasks"></a>若要設定外部廠商目錄，請完成以下工作：

1. 設定採購類別階層。 有關詳細資訊，請參閱[設定採購類別階層的原則](tasks/set-up-policies-procurement-category-hierarchies.md)。
2. 在 Supply Chain Management 中登記廠商。 您必須先在 Microsoft Dynamics 365 中設定廠商和廠商連絡人，才能設定配置以存取外部廠商的目錄。 外部目錄的廠商也必須新增到選取的採購類別中。 如需登記廠商的詳細資訊，請參閱[管理廠商共同作業使用者](manage-vendor-collaboration-users.md)。 有關如何將廠商指派到採購類別的資訊，請參閱[核准特定採購類別的廠商](tasks/approve-vendors-specific-procurement-categories.md)。
3. 確保設定廠商使用的測量單位和貨幣。 有關如何建立計量單位的資訊，請參閱[管理測量單位](../pim/tasks/manage-unit-measure.md)。
4. 使用廠商外部目錄網站的要求設定外部廠商目錄。 有關此工作的更多詳細資訊，請參閱[設定外部廠商目錄](#configure-the-external-vendor-catalog)。
5. 測試廠商的外部目錄設定以驗證設定是否有效，且您可以存取廠商的外部目錄。 使用 **驗證設定** 動作來驗證您定義的要求設定訊息。 此訊息會導致廠商外部目錄網站在瀏覽器視窗中打開。 在驗證期間，無法從廠商處訂購商品和服務。 若要訂購商品和服務，必須從採購申請存取廠商目錄。
6. 使用 **外部目錄** 頁面上的 **啟用目錄** 按鈕來啟用外部目錄。 必須先啟用外部目錄，員工才能使用它。 您可以隨時停用外部目錄。


## <a name="configure-the-external-vendor-catalog"></a>設定外部廠商目錄

本節提供有關上一節中工作 4 的更多詳細資料。

1. 輸入廠商外部目錄的名稱和描述。 您輸入的名稱將出現在代表外部目錄的購物車上，顯示給建立申請的員工。 員工可以點選購物車以打開廠商外部目錄網站上的目錄。
2. 使用 **外部目錄影像** 動作新增影像。 該影像將出現在代表外部目錄的購物車上，顯示給建立申請的員工。 請注意，影像的寬度和高度必須相等。 否則影像將無法正確顯示。
3. 選擇廠商的外部目錄網站是否應顯示在與員工建立申請時的相同瀏覽器視窗中，或者是否應在新視窗中打開。
4. 選擇目錄的廠商。 在 **法人實體** 清單中，每個法人都有一行用於設定廠商。 若要允許使用者直接從某些法律實體 (而不從其他法律實體) 的廠商目錄中要求產品，您可以對您希望提供或不提供目錄的各個法人實體使用 **禁止存取** 或 **允許存取** 按鈕。
5. 在 **預設到期 (天數)** 欄位，輸入從外部目錄收到的報價有效且可用於從外部廠商處採購的天數。 從廠商的外部目錄網站建立和檢索報價單時，報價單自目前系統日期起有效，並在您在此欄位中輸入的天數內一直有效。
6. 點選 **新增** 按鈕開始將採購類別對應到外部目錄。 然後，在類別名稱清單中，選擇一個類別。 類別清單是廠商已在為廠商設定的所有法人實體中對應到的採購類別的超集。

    > [!NOTE]
    > 採購原則用於允許或限制採購法人實體或接收營運單位之類別的存取權。 發包到外部目錄要求允許存取至少一個對應到目錄的採購類別。

7. 設定將發送給廠商的 cXML 設定要求訊息。 自動產生的訊息格式是啟動工作階段所需的最小範本。 填入標籤的值。

您可以隨時點選 **還原訊息格式** 來重新載入系統產生的訊息範本。 請注意，如果您還原訊息格式，則目前的訊息將由自動產生的訊息格式取代，該格式具有空標籤。

### <a name="cxml-setup-message"></a>cXML 設定訊息
您可以在下方找到範本中包含的標籤的描述：

| 欄位 | 描述 | 
|---------|---------|
|< Header >< From >< Credential domain=”” >|採購員公司的網域。|
|< Header >< From >< Credential>< Identity >< /Identity > | 採購員公司的身分識別。|
|< Header >< To >< Credential domain=”” > | 廠商公司的網域。|
|< Header >< To >< Credential>< Identity >< /Identity> | 廠商公司的身分識別。|
|< Header >< Sender >< Credential domain=”” > | 採購員公司的網域。|
|< Header >< Sender >< Credential >< Identity >< /Identity> | 採購員公司的身分識別。|
|< Header >< Sender >< Credential >< SharedSecret >< /SharedSecret >|採購員公司的共用密碼。|
|< Request deploymentMode=”” >|測試或生產部署。|
|< Request >< PunchOutSetupRequest >< SupplierSetup >< URL >< /URL>|廠商的發包端點的 URL。|

### <a name="extrinsic-elements"></a>外部元素

外部元素是附加資訊，例如根據發包使用者的使用者名稱。外部元素在發生發包時設定，並且可以在要求設定訊息中發送。
您的廠商可能需要在設定要求中接收外部元素。 在這種情況下，您應該將外部元素新增到 **外部目錄** 頁面 **訊息格式** 區段中的外部元素清單。
指定廠商可以識別，並將其對應到值的外部元素的名稱。 值的選項有：使用者名稱、使用者電子郵件或隨機值。
有關 cXML 通訊協定的更多資訊，請參閱 [cXML.org 網站](http://cxml.org/)。

## <a name="post-back-message"></a>回傳訊息
回傳訊息是當使用者從外部網站登出並返回 Supply Chain Management 時從廠商處收到的訊息。 無法設定回傳訊息。 訊息是以 cXML 通訊協定定義為基礎。 以下資訊可以是在申請行中收到的回傳訊息的一部分。

| 從廠商處收到的訊息 | 已複製到申請行|
|------------------------------|----------------------------------------------------------|
|< ItemIn quantity=”” > |數量|
|< ItemIn>< ItemID >< SupplierPartID >< /SupplierPartID >|外部品項識別碼|
|< ItemDetail>< UnitPrice >< Money currency=”” >| 貨幣|
|< ItemDetail >< UnitPrice >< Money >< /Money >| 單價|
|< ItemDetail >< Description ShortName=”” >|產品名稱|
|< ItemDetail >< Description >< /Description >|包含在品項描述中; 如果未指定 ShortName，則為產品名稱。|
|< ItemDetail >< UnitOfMeasure >< /UnitOfMeasure >|單位|
|< ItemDetail >< Classification >< /Classification >|包含在品項描述中|
|< ItemDetail >< Classification domain=”” >|包含在品項描述中|

## <a name="delete-an-external-catalog"></a>刪除外部目錄
使用頁面上的 [刪除] 動作刪除外部目錄。

如果已要求外部廠商目錄中的產品，則無法刪除外部廠商目錄。 相反，外部廠商目錄的狀態會設定為非使用中。 如果您想移除對外部廠商目錄網站的存取權，但不刪除它，請將外部目錄狀態變更為非使用中。

## <a name="additional-resources"></a>其他資源

- [採購 cXML 增強功能](purchasing-cxml-enhancements.md)
- [對發包電子採購使用外部目錄](use-external-catalogs-for-punchout.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]