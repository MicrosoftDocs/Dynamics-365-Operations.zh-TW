---
title: 規劃您的組織階層
description: 在設定組織和組織階層之前，請確保您了解如何最好地為您的業務建模。
author: sericks007
ms.date: 02/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: OMHierarchyManager, OMLegalEntity, OMOperatingUnit
audience: Application User
ms.reviewer: sericks
ms.custom: 17404
ms.assetid: babde0c6-bb5d-45ae-95ca-2af75a0ea292
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ef906c0d60639da763f2a9c1e1adf508b0849b8978dff17cd0e7b3936fc4779e
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460543"
---
# <a name="plan-your-organizational-hierarchy"></a>規劃您的組織階層

[!include [banner](../includes/banner.md)]

在設定組織和組織階層之前，請確保您計劃如何為您的業務建模。 組織模型對實作和業務流程有重大影響。

組織階層表示組成企業的組織之間的關係。 因此，在對組織進行建模時，最重要的考慮因素是您的業務結構。 我們建議您根據財務和會計、人力資源、營運、採購、銷售和行銷等職能領域的主管和資深經理的意見回饋來定義組織結構。

在規劃階層時，考慮組織階層和財務維度之間的關係也很重要。 您可以設定多個組織階層來代表您業務的不同檢視表。 透過使用財務維度，您可以基於這些檢視表建立報表。 與您的合作夥伴一起建立滿足組織和法定報表需求的階層。

> [!NOTE]
> 儘管您可以使用財務維度來表示法律實體而無需建立法律實體，但財務維度並非旨在滿足法律實體的營運或業務需求。 單位間會計函數旨在僅處理由每筆交易建立的會計分錄。

> [!IMPORTANT]
> 您不應該僅根據本文中的資訊來決定如何對組織進行建模。 本文件是一個指南。 您可以與您的合作夥伴一起尋求更多指導。 您的合作夥伴在各個行業和整個客戶群中積累了經驗。

## <a name="decide-whether-to-model-internal-organizations-as-legal-entities-or-operating-units"></a>決定是否將內部組織建模為法律實體或營運單位

您必須至少有一個法律實體來代表您的業務。 法律實體可以簽訂法律合約，並需要編制報表其業績的財務報表。

法律實體可用於交易業務或合併。 這代表財務和營運應用程式中的法律實體不一定代表您業務中的真實實體。 例如，參與交易的公司可以擁有子公司法律實體。 在這種情況下，交易需要法律實體，需要虛擬法律實體來合併子公司法律實體的業績和餘額。

您企業中的內部組織 (例如地區辦事處) 可以表示為附加法律實體，或主要法律實體的營運單位。 營運單位不必是法定組織。 營運單位用於控制業務中的經濟資源和營運流程。 例如，部門和成本中心是營運單位。

根據組織是法律實體還是營運單位，某些函數的工作方式會有所不同。 在做出決定時，請仔細考慮下面描述的函數。

### <a name="master-data"></a>主資料

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>如果該組織被建模為法律實體

必須為每個法律實體設定一些主資料，例如客戶、付款條件、稅務機關和特定地點的庫存訂購。 有些主資料，例如使用者、產品和大多數人力資源資料，在所有法律實體之間共用。

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>如果組織被建模為一個營運單位

主資料在營運單位之間共用。

### <a name="module-parameters"></a>模組參數

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>如果該組織被建模為法律實體

必須為每個法律實體設定模組的參數，例如應收帳款參數、應付帳款參數以及現金和銀行管理參數。 由於法律實體的模組設定是獨立的，因此每個子公司都可以遵守當地的法定要求和商業慣例。 例如，專業服務法律實體和製造法律實體可以具有不同的模組參數，即使它們向同一母公司報表。

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>如果組織被建模為一個營運單位

模組參數在營運單位之間共用。

### <a name="data-security"></a>資料安全

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>如果該組織被建模為法律實體

大多數資料由公司 ID 自動保護。 公司 ID 是與法律實體關聯資料的唯一識別碼。 一間公司只能與一個法律實體關聯，一個法律實體只能與一個公司關聯。 使用者只能存取他們有權存取的公司的資料。 您不需要按公司 ID 來自訂安全資料。

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>如果組織被建模為一個營運單位

透過建立自訂的資料安全策略，可以保護每個營運單位的資料。 資料安全策略用於限制存取資料。 例如，假設僅允許使用者在特定營運單位中建立訂購單。 可以建立資料安全策略以防止使用者從任何其他營運單位存取訂購單資料。 交易量和安全策略的數量會影響效能。 設計安全策略時，別忘了考慮到效能。

### <a name="ledgers"></a>分類帳

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>如果該組織被建模為法律實體

每個法律實體都需要一個提供會計科目表、記帳貨幣、報表貨幣和會計行事曆的分類帳。 只能為法律實體建立資產負債表。 主科目、維度、帳戶結構、科目表和會計準則可由多個法律實體使用。

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>如果組織被建模為一個營運單位

營運單位不能有自己的分類帳資訊。 如果您的內部組織不需要唯一的分類帳，您可以將它們建模為營運單位。 將為階層中的母法律實體設定分類帳資訊。 可以為法律實體內的營運單位或母法律實體建立損益表。

### <a name="fiscal-calendars"></a>會計行事曆

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>如果該組織被建模為法律實體

每個法律實體都有自己的會計行事曆。 如果您的內部組織使用不同的會計年度和會計行事曆，您必須將組織建模為法律實體。

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>如果組織被建模為一個營運單位

營運單位必須分享一個會計行事曆。 如果您的內部組織可以使用相同的會計年度和會計行事曆，您可以將組織建模為營運單位。

### <a name="consolidation"></a>彙總

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>如果該組織被建模為法律實體

為了編制財務報表，您必須將地區辦事處的財務結果合併為一個單一的合併公司。

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>如果組織被建模為一個營運單位

不需要合併，因為資料已經在營運單位之間共用。

### <a name="centralized-payments"></a>集中付款

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>如果該組織被建模為法律實體

必須設定集中付款，以便所有子系法律實體的發票可以支付給或從單個母法律實體支付。

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>如果組織被建模為一個營運單位

不需要集中付款，因為所有發票都記錄在一個法律實體中。

### <a name="intercompany-transactions"></a>公司間交易

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>如果該組織被建模為法律實體

公司間銷售訂單、訂購單、付款或收據可以相互套用。 您不需要使用日記帳憑證。 您可以查看子分類帳級別的公司間交易 (應收帳款、應付帳款)。 以下範例說明了如何處理公司間交易。

##### <a name="example-1-headquarters-provides-services-to-regional-offices-and-must-charge-the-costs-of-those-services-to-the-regional-offices"></a>範例 1：總部向地區辦事處提供服務，並且必須向地區辦事處收取這些服務的費用

如果您將地區辦事處建模為法律實體，您有以下選取：

- 總部建立一個日記帳分錄以交叉收取地區辦事處的費用。 交易不會過期。
- 總部向地區辦事處發送服務訂購單。 銷售訂單會在地區辦事處的法律實體中自動建立，其中包含公司間子分類帳交易。

##### <a name="example-2-headquarters-procures-and-pays-for-service-that-is-delivered-to-a-regional-office"></a>範例 2：總部採購併支付交付給地區辦事處的服務

如果您將地區辦事處建模為法律實體，您有以下選取：

- 發票和付款遵循總部的監管要求。 總部可以建立一個日記帳分錄以交叉收取地區辦事處的費用。 交易不會過期。
- 發票和付款遵循總部的監管要求。 總部可以建立公司間子分類帳交易。

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>如果組織被建模為一個營運單位

僅透過日記帳憑證支援營運單位之間的公司間交易。 一個營運單位不能從同一法律實體的另一個營運單位發出或接收訂購單、銷售訂單或發票。 您無法查看子分類帳級別的公司間交易 (應收帳款、應付帳款)。 以下範例說明了如何處理公司間交易。

##### <a name="example-1-headquarters-provides-services-to-regional-offices-and-must-charge-the-costs-of-those-services-to-the-regional-offices"></a>範例 1：總部向地區辦事處提供服務，並且必須向地區辦事處收取這些服務的費用

如果您將地區辦事處建模為營運單位，則總部會輸入費用交易並將其編碼到地區辦事處。

##### <a name="example-2-headquarters-procures-and-pays-for-service-that-is-delivered-to-a-regional-office"></a>範例 2：總部採購併支付交付給地區辦事處的服務

如果您將地區辦事處建模為營運單位，則發票和付款遵循總部的監管要求。 發票可以編碼到地區辦事處。 在損益表中，使用平衡財務維度來報表地區辦事處的成本。

### <a name="local-tax-requirements"></a>本地稅金要求

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>如果該組織被建模為法律實體

法律實體須遵守法律實體註冊所在國家/地區稅務機關的稅法。 例如，在丹麥註冊的法律實體受丹麥稅法和法規的約束。 一個法律實體只能屬於一個國家/地區。 您為法律實體的主要地址選取的國家/地區控制了該法律實體可用的國家/地區特定功能。 例如，如果法律實體的主要地址在丹麥，則與丹麥稅法和法規相關的功能將可用。 因此，如果您的組織位於不同的國家/地區並需要不同的當地稅收選項，您必須將組織設定為單獨的法律實體。

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>如果組織被建模為一個營運單位

營運單位使用母公司法律實體的國家/地區背景。 同一法律實體中的營運單位不能有不同的國家/地區特定要求。 如果您的組織位於同一國家/地區並使用相同的稅收選項，您可以將它們設定為運營單位。

### <a name="statutory-reporting-for-a-countryregion"></a>國家/地區的法定報表

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>如果該組織被建模為法律實體

對於受支援的國家/地區，可以建立大多數法定報表。 

> [!NOTE]
> 總帳中的過帳層允許您對使用不同於子公司會計標準的母公司進行調整分錄。 例如，對於使用英國公認會計實務 (UK GAAP) 的公司，您可以在過帳層中進行調整分錄。 這些分錄可以合併到使用美國公認會計原則 (GAAP) 的母公司中。 調整分錄不影響 UK GAAP 報表。

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>如果組織被建模為一個營運單位

法定報表必須使用其他應用程式建立。 您必須確保在財務和營運應用程式中捕獲資料，以支援每個運營單位的要求，因為它們與總部的要求不同。

### <a name="currency"></a>貨幣

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>如果該組織被建模為法律實體

如果您的組織必須使用不同的函數貨幣，您必須將組織建模為法律實體。 函數貨幣是按法律實體設定的。 但是，您可以輸入多種貨幣的交易。

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>如果組織被建模為一個營運單位

如果您的組織可以使用單一函數貨幣，您可以將組織建模為運營單位。 營運單位必須分享一個函數性貨幣。 但是，您可以以多種貨幣輸入交易並建立報表。

### <a name="year-end-closing"></a>年終結算

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>如果該組織被建模為法律實體

如果您所在組織所在國家/地區的法律和會計實務不同，您可能需要每個組織不同的年終程序。 這代表您必須將組織建模為法律實體。 每個法律實體都有自己的年終程序。

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>如果組織被建模為一個營運單位

如果您所在組織所在國家/地區的法律和會計實務相同，您可以使用一套年終程序。 這代表您可以將組織建模為運營單位。 所有運營單位必須使用相同的年終結算程序。

### <a name="number-sequences"></a>數字序列

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>如果該組織被建模為法律實體

可以為每個法律實體設定一些參考的編號規則。 有些編號規則可以共用。

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>如果組織被建模為一個營運單位

可以為每個營運單位設定一些參考的編號規則。 有些編號規則可以共用。

### <a name="products"></a>產品

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>如果該組織被建模為法律實體

產品定義是共用的，並且必須先發布給各個法律實體，然後才能包含在交易中。 每個法律實體都有自己的一組已發布產品，可以包含在交易文件中。 如果您的內部組織必須使用不同的產品集，則必須將組織建模為法律實體。

> [!NOTE]
> 儘管產品定義是共用的，但在已發布產品的每個法律實體中，您都可以在每個庫存站點為項目指定不同的銷售、採購和庫存參數。

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>如果組織被建模為一個營運單位

所有運營單位共享同一套產品。 如果您的內部組織可以共享同一組產品，您可以將這些組織建模為運營單位。

### <a name="inquiry-and-reporting"></a>查詢和報表

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>如果該組織被建模為法律實體

您必須手動更改公司以在多個法律實體中輸入交易和執行查詢。 由於資料安全邊界，綜合查詢和報表可能是資源密集型和耗時的。

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>如果組織被建模為一個營運單位

您無需更改公司即可存取來自多個運營單位的資料。 合併查詢和報表以及單獨的區域查詢更容易、更快速。

## <a name="best-practices-for-modeling-organizations-and-hierarchies"></a>建模組織和階層的最佳做法

實作組織階層時，請考慮以下最佳做法：

- 建立一個部門來模擬法律實體和事業單位之間的交叉點。 然後，您可以將資料從部門匯總到法律實體以進行法定報表，從部門匯總到事業單位以進行內部報表。 部門可以作為利潤中心。 如果您使用部門，則不必將法律實體和經營單位用作帳戶結構中的維度。 您可以只使用部門作為維度。 但是，如果成本中心僅用作成本累計器，而部門用於收入確認，則必須同時使用成本中心和部門作為帳戶結構中的維度。
- 如果您對報表損益有復雜的要求，請為運營單位建模多個階層。
- 在單個法律實體中，不要為同一階層目的對多個階層進行建模。
- 不要為每個目的建立階層。 通常，您可以將一個階層用於多種目的。 例如，可以將一個營運單位階層指派給所有與策略相關的目的。
- 建立平衡的階層。 在階層中，與根節點距離相同的所有節點都被定義為一個級別。 在一個平衡的階層中，每一層只能出現一種類型的營運單位，並且從根節點到每一層的距離是一致的。 如果部門與法律實體或事業單位之間存在中間級別，則可能需要預留位置組織來建立平衡的階層。
- 如果法律實體的結構也是您的營運結構，則不要為單獨的運營單位階層建模。 法律實體和營運單位的混合階層可以同時滿足這兩個目的。
- 在對主要重組方案進行建模之前，請使用階層的生效日期來執行影響分析和驗證測試。
- 在生產環境中發布新版本之前，使用草稿模式更改階層。
- 限制有權在生產環境中從階層中新增或刪除組織的人數。 較小的數字可以減少發生代價高昂的錯誤和必須進行更正的機會。


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
