---
title: 合作對象和全球通訊錄
description: 本主題介紹雙重寫入的合作對象和全球通訊錄函數。
author: RamaKrishnamoorthy
ms.date: 03/10/2022
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2021-02-22
ms.openlocfilehash: 2e0d16b29a71da23acc925c09c87f0bb4776759c
ms.sourcegitcommit: 6dc2b877cf8ea9185a07964ec05c5ddb7a78471b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/12/2022
ms.locfileid: "8460570"
---
# <a name="party-and-global-address-book"></a>合作對象和全球通訊錄

[!include [banner](../../includes/banner.md)]



*合作對象* 和 *全球通訊錄* 是財務和營運應用程式中的概念。 合作對象可以是組織或個人。 全域性地儲存和管理合作對象的屬性，如名稱、語言、聯絡人和位址，非常方便。 然後，當某個地方的屬性值發生變化時，該變化會反映在該方所涉及的所有地方。

## <a name="party"></a>合作對象

合作對象是參與業務的個人或組織。 當使用合作對象概念時，個人或組織可以在企業中扮演多個角色 (例如，工人、客戶、廠商或聯絡人)。 該角色以內容和目的為主。 以下是來自兩個虛構公司 Contoso 和 Fabrikam 的一些角色範例：

+ **工人** - 一個員工。 例如，Contoso 的一名員工。
+ **廠商** – 向企業提供商品或服務的廠商組織或獨資經營者。 例如，如果 Fabrikam 向 Contoso 銷售耗材，則 Fabrikam 是 Contoso 的廠商。
+ **聯絡人** - 要聯絡的人。 例如，如果 Contoso 從 Fabrikam 購買耗材，Contoso 的員工將聯絡 Fabrikam 的聯絡人。
+ **客戶** – 從公司購買東西的個人或公司。 例如，如果 Contoso 從 Fabrikam 購買耗材，則 Contoso 是 Fabrikam 的客戶。

合作對象模型經常被用來表示組織和人之間的中、複雜關係，特別是當合作對象扮演一個以上的角色時。 這裡有一些常用範例：

+ 合作對象既可以是客戶也可以是廠商。 例如，在北美洲，Fabrikam 向 Contoso 銷售電線，並從 Contoso 購買組裝好的喇叭。 在歐洲，Fabrikam 向 Contoso 銷售零件，但它不從 Contoso 購買任何東西。
+ 合作對象既可以是員工，也可以是客戶。 例如，Contoso 的一名員工從 Contoso 購買電子產品供個人使用。
+ 個人和組織之間可以存在多對多 (N:N) 關係。 例如，Fabrikam 提供服務專家並僱用一名人員設定員。 人員設定專員將服務專家與 Fabrikam 的幾個客戶的工作請求進行匹配。 Contoso 是 Fabrikam 的客戶之一。 當 Contoso 需要服務專家時，它會聯絡人員設定專員，然後由該專員協助提出請求。 因為人員設定專員處理所有客戶的請求，所以涉及 N:N 關係。

下圖顯示了合作對象的資料模型。

![合作對象的資料模型。](media/party-gab-image1.png)

> [!TIP]
> 當您嘗試建立新帳戶記錄時，請使用 **合作對象** 欄位按名稱搜尋記錄。 在此情況下，如果您找到記錄，您只需選取它。 然後系統自動填入該方的所有資料。 您不必手動設定所有必填欄位。 此行為可以在立即可用的 **帳戶**、**聯絡人** 和 **廠商** 頁面上找到。

雙重寫入不支援財務和營運應用程式的所有合作對象角色。 如需合作對象角色的完整清單，請參閱[全球通訊錄概述](../../../fin-ops/organization-administration/overview-global-address-book.md)。

### <a name="global-address-book"></a>全球通訊錄

全球通訊錄是參與業務的組織和個人的郵寄和電子郵件地址的目錄。

全球通訊錄儲存和處理所需數量的郵寄和電子郵件地址。 例如，Fabrikam 在 50 個地點設有加油站。 每個位置都有不同的郵寄地址、電子郵件地址和電話號碼。 所有商業購買都向主要加油站收費，但直接運送到需要購買的特定加油站。 全球通訊錄將主要加油站儲存為 Fabrikam 的帳單地址，並將每個加油站儲存為送貨地址。 這些地址可以儲存一次，然後在報價和訂單需要時擷取。

根據業務環境，個人或組織可能扮演多個角色，並且所有角色可能使用相同的郵寄和電子郵件地址。 在這種情況下，一個角色更改後的地址應該出現在所有其他角色中。 全球通訊錄在全球範圍內儲存和處理地址。

下圖顯示了全球通訊錄的資料模型。

![全球通訊錄的資料模型。](media/party-gab-image2.png)

## <a name="contact"></a>連絡人

在客戶業務開發應用程式中，聯絡人就是一個人。 但是，**聯絡人** 表已超載以表示個人、入口網站使用者、企業對消費者 (B2C) 客戶或廠商。 該表示是隱含的，除非您檢查相關交易，否則您無法區分差異。 **聯絡人** 表已被限制為與 **帳戶** 表的一對一 (1:1) 關係。 屬於合作對象和全球通訊錄模型的雙重寫入引入了分類的明確屬性，並允許作為個人和組織 (**帳戶** 或 **廠商** 實體) 的聯絡人之間的 N:N 關係。

有兩種類型的 **聯絡人** 列：

+ **串接的聯絡人** - **公司** 欄位具有強制值的 **聯絡人** 列。
+ **未串接的聯絡人** - **公司** 欄位為空白的 **聯絡人** 列。

**聯絡人** 表可以儲存以下類型的資料列。

| 資料列類型 | 描述 |
|----------|-------------|
| 作為客戶的人 (例如，可銷售的聯絡人或 B2C 客戶) | 串接的聯絡人記錄，其中 **公司** 欄位不為空白，並且 **是客戶** 欄位設定為 **是**。 |
| 作為廠商的人 (例如，廠商等獨資經營者) | 串接的聯絡人記錄，其中 **公司** 欄位不為空白，並且 **是廠商** 欄位設定為 **是**。 |
| 個人既可以是客戶也可以是廠商 | 串接的聯絡人記錄，其中 **公司** 欄位不為空白，**是客戶** 欄位設定為 **是**，並且 **是廠商** 欄位設定為 **是**。 個人既可以是一種產品的生產者，也可以是另一種產品的消費者。 財務和營運應用程式以及雙重寫入都支援這種關係。 |
| 作為組織的聯絡人但不是客戶或廠商的人 | 未串接的聯絡人記錄，其中 **公司** 欄位為空白，**是客戶** 欄位設定為 **否**，並且 **是廠商** 欄位設定為 **否**。 |

## <a name="contact-for-party-table"></a>合作對象表聯絡人

**合作對象聯絡人** 表儲存和處理 **帳戶** 列和 **聯絡人** 列之間的 N:N 關係。 它可以從未串接的資料列中篩選掉串接的 **聯絡人** 列，並僅將未串接的 **聯絡人** 列與 **帳戶** 或 **廠商** 列連結。

例如，Natasha Jones 和 Miguel Reyes 是為他們所在地區的農場提供護理的獸醫。 Natasha 服務於西雅圖地區，而 Miguel 服務於肯特地區。 在客戶業務開發應用程式中，農場代表客戶，獸醫代表聯絡人。 Natasha 的單個 **聯絡人** 記錄與 Natasha 合作的所有農場有關聯。 同樣，Miguel 的單個 **聯絡人** 記錄與 Miguel 使用的所有農場有關聯。

將這些關係儲存在 **合作對象的聯絡人** 表中。 您可以在立即可用的 **帳戶**、**聯絡人** 和 **廠商** 頁面上找到資訊：

+ 在 **帳戶** 頁面上，您可以使用 **相關聯絡人** 索引標籤將一個或多個聯絡人與 **帳戶** 列連結。 透過這種方式，您可以為組織指派聯絡人。 然後，您可以選取一位聯絡人作為該帳戶的主要聯絡人。 如果您使用 **快速建立** 頁面，您只能選取一個聯絡人。 當您使用 **廠商** 頁面並且記錄類型為 **組織** 時，該行為是相同的。
+ 在 **聯絡人** 頁面上，當該列是客戶、廠商或兩者 (串接的聯絡人) 時，您可以使用 **相關聯絡人** 索引標籤關聯一個或多個聯絡人。 透過這種方式，您可以為 B2C 客戶或廠商指派聯絡人。 然後，您可以選取一位聯絡人作為主要聯絡人。 如果您使用 **快速建立** 頁面，您只能選取一個聯絡人。
+ 在 **聯絡人** 頁面上，當該列是聯絡人 (未串接的聯絡人) 時，您可以使用 **相關組織** 索引標籤與一個或多個客戶或廠商連結。 透過這種方式，您可以將客戶或廠商指派給基礎聯絡人。 客戶或廠商可以是組織、個人或兩者兼具。 您一次只能在四個欄位之一中選取一個值：

    + 如果您在 **合作對象 ID** 欄位中選取一個值，則基礎聯絡人將指派給所選合作對象的所有角色。
    + 如果您在 **相關聯絡人** 欄位中選取一個值，則您選取的是 **人員** 類型的串接聯絡人。
    + 如果您在 **相關帳戶** 或 **相關廠商** 欄位中選取一個值，則您選取的是一個組織。

    ![聯絡人頁面上的相關組織索引標籤。](media/party-gab-image3.png)

    無論您的選取如何，該關聯都是在派對級別建立的，它適用於合作對象的所有角色，並且儲存在 **合作對象聯絡人** 實體。

> [!NOTE]
> 客戶業務開發應用程式中 **合作對象聯絡人** 表的顯示名稱是 **客戶/廠商聯絡人**。

當您開啟 **是客戶** 欄位和 **是廠商** 都設定為 **否** 的 **聯絡人** 列時，將顯示 **相關組織** 索引標籤。 使用此索引標籤建立一個或多個客戶或廠商組織與聯絡人的關聯。

當您開啟 **是客戶** 欄位或 **是廠商** 欄位設定為 **是** 的 **聯絡人** 列時，將顯示 **關聯的聯絡人** 索引標籤。 使用此索引標籤建立一個或多個聯絡人的關聯。

## <a name="postal-addresses"></a>郵寄地址

**帳戶**、**聯絡人** 和 **廠商** 頁面上引入了新的 **地址** 索引標籤。 此索引標籤透過使用格線支援多個郵寄地址，如下圖所示。

![郵寄地址格線。](media/party-gab-image4.png)

格線包括的資料欄如下：

+ **郵寄地址角色** – 郵寄地址的用途。
+ **是主要的** – 表示地址是否為主地址的值。
+ **地址號碼** – 地址順序。

您可以使用格線上方的 **新地址** 按鈕建立任意數量的郵寄地址。

**帳戶** 頁面 **摘要** 索引標籤上的 **地址 1** 和 **地址 2** 欄位分別對應於 **交貨** 地址和 **發票** 地址。

![郵寄地址的摘要索引標籤。](media/party-gab-image5.png)

**聯絡人** 頁面 **摘要** 索引標籤上的 **地址 1**、**地址 2** 和 **地址 3** 欄位分別對應於 **商務**、**交貨** 地址和 **發票** 地址。

## <a name="electronic-addresses"></a>電子郵件地址

**帳戶**、**聯絡人** 和 **廠商** 頁面上引入了新的 **電子郵件地址** 索引標籤。 此索引標籤透過使用格線支援多個電子郵件地址，如下圖所示。

![電子郵件地址格線。](media/party-gab-image6.png)

格線包括的資料欄如下：

+ **類型** – 電子郵件地址的類型。
+ **是主要的** 表示地址是否為主地址的值。
+ **目的** – 電子郵件地址的用途。

您可以使用格線上方的 **新電子郵件地址** 按鈕建立任意數量的地址。

電子郵件地址僅在此格線中提供。 在未來的版本中，所有郵寄地址和電子郵件地址欄位都將從其他索引標籤中刪除，例如 **摘要** 和 **詳情** 索引標籤。 **詳情** 索引標籤上顯示的聯絡詳情是主要電子郵件地址的僅供讀取副本，例如主要電話、主要電子郵件、主要電話、主要傳真和主要 Twitter ID。 在潛在客戶資格認證過程中，您可以同時提供公司電話號碼和手機號碼。 如果 **IsMobile=No**，則將商務電話號碼視為主要電話，如果 **IsMobile=Yes**，則將手機電話號碼視為輔助電話。

> [!TIP]
> 使用 **帳戶** 和 **聯絡人** 表上的 **地址** 和 **電子郵件地址** 索引標籤來管理郵寄地址和電子郵件地址。 這可確保地址資料與財務和營運應用程式同步。

## <a name="setup"></a>設定

1. 開啟您的客戶業務開發應用程式環境。

2. 安裝[雙重寫入應用程式協調解決方案](https://aka.ms/dual-write-app)最新版本 (2.2.2.60 或更高版本)。

3. 安裝[雙重寫入方和全球通訊錄解決方案](https://aka.ms/dual-write-gab)。

4. 開啟財務和營運應用程式。 導覽到資料管理模組並選取雙重寫入索引標籤。雙重寫入管理頁面打開。

5. 使用[套用解決方案](link-your-environment.md)函數應用在步驟 2 和 3 中安裝的解決方案。

6. 停止以下地圖，因為不再需要它們。 相反，執行 `Contacts V2 (msdyn_contactforparties)` 地圖。

    + CDS Contacts V2 和 Contacts (指客戶聯絡人)
    + CDS Contacts V2 和 Contacts (指廠商聯絡人)

7. 以下實體對應已針對合作對象函數進行了更新，因此必須將最新版本應用於這些對應。

    地圖 | 更新到這個版本 | 變更
    ---|---|---
    `CDS Parties (msdyn_parties)`| 1.0.0.0 | 這是屬於此版本的新地圖。
    `Contacts V2 (msdyn_contactforparties)`| 1.0.0.5 | 這是屬於此版本的新地圖。
    `Customers V3 (accounts)` | 1.0.0.5 |刪除了 `PartyNumber` 和其他與合作對象相關的欄位，例如姓名、個人詳情、郵寄地址欄位和電子郵件地址。
    `Customer V3 (contacts)` | 1.0.0.5 | 刪除了 `PartyNumber` 和其他與合作對象相關的欄位，例如姓名、個人詳情、郵寄地址欄位和電子郵件地址。
    `Vendors V2 (msdyn_vendors)` | 1.0.0.6 | 刪除了 `PartyNumber` 和其他與合作對象相關的欄位，例如姓名、個人詳情、郵寄地址欄位和電子郵件地址。
    `CDS Sales quotation headers (quotes)` | 1.0.0.7 | 將聯絡人替換為 `ContactforParty` 參考。
    `Sales invoice headers V2 (invoices)` | 1.0.0.4 | 將聯絡人替換為 `ContactforParty` 參考。
    `CDS Sales order headers (salesorders)` | 1.0.0.5 | 將聯絡人替換為 `ContactforParty` 參考。
    `CDS Party postal address locations (msdyn_partypostaladdresses)` | 1.0.0.1  | 這是屬於此版本的新地圖。
    `CDS postal address history V2 (msdyn_postaladdresses)` | 1.0.0.1 | 這是屬於此版本的新地圖。
    `CDS postal address locations (msdyn_postaladdresscollections)` | 1.0.0.0 | 這是屬於此版本的新地圖。
    `Party Contacts V3 (msdyn_partyelectronicaddresses)` | 1.0.0.0 | 這是屬於此版本的新地圖。
    `Complimentary Closings ( msdyn_compliemntaryclosings)` | 1.0.0.0 | 這是屬於此版本的新地圖。
    `Decision making roles (msdyn_decisionmakingroles)` | 1.0.0.0 | 這是屬於此版本的新地圖。
    `Loyalty levels (msdyn_loyaltylevels)` | 1.0.0.0 | 這是屬於此版本的新地圖。
    `Contact person titles (msdyn_salescontactpersontitles)` | 1.0.0.0 | 這是屬於此版本的新地圖。
    `Personal character types (msdyn_personalcharactertypes)` | 1.0.0.0 | 這是屬於此版本的新地圖。
    `Salutations (msdyn_salutations)` | 1.0.0.0 | 這是屬於此版本的新地圖。
    `Employment job functions (msdyn_employmentjobfunctions)` | 1.0.0.0 | 這是屬於此版本的新地圖。

8. 在執行上述地圖之前，您必須按照以下步驟手動更新整合金鑰。 然後選取 **儲存**。

    | 地圖 | 金鑰 |
    |-----|------|
    | 客戶 |  accountnumber [帳號]<br>msdyn_company.cdm_companycode [公司 (公司代碼)] |
    | 連絡人 | msdyn_contactpersonid [帳號/聯絡人 ID]<br>msdyn_company.cdm_companycode [公司 (公司代碼)] |
    | 客戶/廠商聯絡資料 | msdyn_contactforpartynumber [合作對象聯絡號碼]<br>msdyn_associatedcompanyid.cdm_companycode [附屬公司 (公司代碼)] |
    | 廠商 | msdyn_vendoraccountnumber [廠商帳號]<br>msdyn_company.cdm_companycode [公司 (公司代碼)]|

9. 在 Dataverse，重複偵測規則字元限制已從 450 個字元增加到 700 個字元。 此限制允許您向重複偵測規則新增一個或多組金鑰。 透過設定以下欄位來展開 **帳戶** 表的重複偵測規則。

    | 欄位 | 值 |
    |-------|-------|
    | 姓名 | 具有相同帳戶名稱的帳戶。 |
    | 描述 | 偵測帳戶名稱屬性中具有相同值的帳戶記錄。 |
    | 基礎記錄類型 | 客戶 |
    | 比對記錄類型 | 客戶 |
    | 帳戶名稱 (欄位) | 完全相符 |
    | 公司 (欄位) | 完全相符 |
    | 關聯性類型 (欄位) | 完全相符 |
    | 合作對象 ID (欄位) | 完全相符 |
    | 選取 (欄位) | (空白) |

    ![帳戶的重複規則。](media/duplicate-rule-1.PNG)

10. 透過設定以下欄位來展開 **聯絡人** 表的重複偵測規則。

    | 欄位 | 值 |
    |-------|-------|
    | 姓名 | 具有相同名字和姓氏的聯絡人。 |
    | 描述 | 偵測在名字和姓氏欄位中具有相同值的聯絡人記錄。 |
    | 基礎記錄類型 | 連絡人 |
    | 比對記錄類型 | 連絡人 |
    | 名字 (欄位) | 完全相符 |
    | 姓氏 (欄位) | 完全相符 |
    | 公司 (欄位) | 完全相符 |
    | 合作對象 ID (欄位) | 完全相符 |
    | 選取 (欄位) | (空白) |

    ![聯絡人的重複規則。](media/duplicate-rule-2.PNG)

11. 如果您是現有雙重寫入使用者，請按照[升級到合作對象和全球通訊錄模型](upgrade-party-gab.md)中的說明進行資料升級。 **在未完成此步驟的情況下，請勿繼續執行第 12 步。** 如果您是新的雙重寫入使用者，請繼續執行步驟 12。

12. 如果您是現有的雙重寫入使用者，請完成第 11 步，然後您可以按以下順序執行對應。 如果您是新的雙重寫入客戶，則可以直接進行。 如果您看到一條錯誤訊息指出「專案驗證失敗。 缺少目的地欄位…」，開啟地圖並選取 **重新整理資料表**，然後執行地圖。

    財務和營運應用程式 | 客戶業務開發應用程式  
    ----------------------------|------------------------
    [CDS 方](mapping-reference.md#220) | msdyn_parties
    [CDS 郵寄地址位置](mapping-reference.md#234) | msdyn_postaladdresscollections
    [CDS 郵寄地址歷史記錄 V2](mapping-reference.md#235) | msdyn_postaladdresses
    [CDS 方郵寄地址位置](mapping-reference.md#233) | msdyn_partypostaladdresses
    [參與方聯絡方式 V3](mapping-reference.md#236) | msdyn_partyelectronicaddresses
    [客戶 V3](mapping-reference.md#101) | 客戶
    [客戶 V3](mapping-reference.md#116) | 聯絡人
    [廠商 V2](mapping-reference.md#202) | msdyn_vendors
    [聯絡人個人稱謂](mapping-reference.md#223) | msdyn_salescontactpersontitles
    [免費結算](mapping-reference.md#222) | msdyn_complimentaryclosings
    [稱謂](mapping-reference.md#228) | msdyn_salutations
    [決策角色](mapping-reference.md#224) | msdyn_decisionmakingroles
    [就業職務](mapping-reference.md#225) | msdyn_employmentjobfunctions
    [忠誠度](mapping-reference.md#226) | msdyn_loyaltylevels
    [個人角色類型](mapping-reference.md#227) | msdyn_personalcharactertypes
    [聯絡人 V2](mapping-reference.md#221) | msdyn_contactforparties
    [CDS 銷售報價單抬頭](mapping-reference.md#215) | 報價
    [CDS 銷售訂單抬頭](mapping-reference.md#217) | salesorders
    [銷售發票抬頭 V2](mapping-reference.md#118) |  張發票

> [!NOTE]
> `CDS Contacts V2 (contacts)` 地圖是您在步驟 1 中停止的地圖。 當您嘗試執行其他地圖時，這 2 個地圖可能會出現在家屬清單中。 不要執行這些地圖。
>
> 如果安裝了合作對象和全球通訊錄解決方案，則必須禁用名為 `Microsoft.Dynamics.SCMExtended.Plugins.Plugins.LeadPrimaryContactPostCreate: QualifyLead of lead` 的外掛程式。 如果您解除安裝了合作對象和全球通訊錄解決方案，那麼您必須重新啟用該外掛程式。
>
> 不應繼續使用包含在 **帳戶**、**聯絡人** 和 **廠商** 表中的 `msdyn_*partynumber` 欄位 (單行文字欄位)。 為清楚起見，標籤名稱具有 **(Deprecated)** 前綴。 而是使用 **msdyn_partyid** 欄位。 該欄位是對 **msdyn_party** 表的查詢。

> 資料表名稱 | 舊欄位 | 新欄位
> --------|-------|--------
> 客戶 | `msdyn_partynumber` | `msdyn_partyid`
> 連絡人 | `msdyn_partynumber` | `msdyn_partyid`
> msdyn_vendor | `msdyn_vendorpartynumber` | `msdyn_partyid`

## <a name="templates"></a>範本

一組資料表對應一起運作，用於合作對象和全球通訊錄互動，如下表所示。

| 財務和營運應用程式 | 客戶業務開發應用程式 | 描述 |
|----------------------------|-------------------------|-------------|
| [聯絡人個人稱謂](mapping-reference.md#223) | msdyn\_salescontactpersontitles |
| [客戶 V3](mapping-reference.md#101) | 客戶 |
| [客戶 V3](mapping-reference.md#116) | 聯絡人 |
| [CDS 方](mapping-reference.md#220) | msdyn\_parties |
| [CDS 方郵寄地址位置](mapping-reference.md#233) | msdyn\_partypostaladdresses |
| [CDS 郵寄地址歷史記錄 V2](mapping-reference.md#235) | msdyn\_postaladdresses |
| [CDS 郵寄地址位置](mapping-reference.md#234) | msdyn\_postaladdresscollections |
| [CDS 銷售報價單抬頭](mapping-reference.md#215) | 報價 |
| [CDS 銷售訂單抬頭](mapping-reference.md#217) | salesorders |
| [免費結算](mapping-reference.md#222) | msdyn\_complimentaryclosings |
| [聯絡人 V2](mapping-reference.md#221) | msdyn\_contactforparties |
| [決策角色](mapping-reference.md#224) | msdyn\_decisionmakingroles |
| [就業職務](mapping-reference.md#225) | msdyn\_employmentjobfunctions |
| [忠誠度](mapping-reference.md#226) | msdyn\_loyaltylevels |
| [參與方聯絡方式 V3](mapping-reference.md#236) | msdyn\_partyelectronicaddresses |
| [個人角色類型](mapping-reference.md#227) | msdyn\_personalcharactertypes |
| [銷售發票抬頭 V2](mapping-reference.md#118) |  張發票 |
| [稱謂](mapping-reference.md#228) | msdyn\_salutations |
| [廠商 V2](mapping-reference.md#202) | msdyn\_vendors |

如需相關資訊，請參閱[雙重寫入對應參考](mapping-reference.md)。

## <a name="known-issues-and-limitations"></a>已知問題和限制

+ 在財務和營運應用程式中，當您建立客戶連同地址並儲存時，地址可能不會同步到 **地址** 資料表。 這是因為雙重寫入平台排序問題。 作為一種解決方法，請先建立客戶並儲存。 然後新增地址。
+ 在財務和營運應用程式中，當客戶記錄具有主地址並且您為該客戶建立新聯絡人時，聯絡人記錄會從關聯的客戶記錄繼承主地址。 廠商聯絡人也會發生這種情況。 Dataverse 目前不支援這種行為。 如果啟用了雙重寫入，則使用財務和營運應用程式的主地址繼承的客戶聯絡人及其地址將同步到 Dataverse。
+ 在 **帳戶**、**聯絡人** 和 **廠商** 表的電子地址索引標籤上設定的電子地址來自 `msdyn_partyelectronicaddress` 表。 此資訊不會流向它的關聯交易，如銷售訂單、報價單和訂購單。 我們計畫在增量版本中解決此問題。 帳戶和聯絡人記錄中電子地址欄位上的現有資料將繼續適用於銷售訂單、報價單和訂購單等交易。
+ 在財務和營運應用程式中，您可以從 **新增聯絡人** 表建立聯絡人記錄。 當您嘗試從 **查看聯絡人** 表建立新聯絡人時，該動作失敗。 這是一個已知的問題。

    ![新增聯絡人的已知問題。](media/party-gab-contact-issue.png)

+ **初始同步** 不支援 **ContactForParty** 上的 **提供來源** 和 **提供對象** 時間欄位，因為 DIXF 將值轉換為字串而不是整數。 轉換觸發錯誤 `Cannot convert the literal '<say 08:00:00>’ to the expected type edm.int32`。
+ 當郵寄地址用於多個原因時，例如企業通訊地址和帳單地址，它應顯示為 `Business;Invoice`，如下圖所示。 如果在值之間新增空格，則會出現錯誤。

    ![該地址的已知問題。](media/party-gab-address-issue.png)

+ 您無法使用具有雙重寫入功能的財務和營運應用程式輸入遠期郵寄地址，因為 Dataverse 不支援日期有效性。 如果您使用財務和營運應用程式輸入一個未來日期的郵寄地址，它會完全同步到 Dataverse，您將立即在使用者介面上看到該地址。 由於是未來日期，對此記錄的任何更新都將導致錯誤，而不是財務和營運應用程式中的最新資訊。
