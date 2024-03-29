---
title: 財務分析
description: 財務分析使用 Microsoft Power BI 來匯集財務關鍵績效指標 (KPI)、圖表和財務報表。
author: kweekley
ms.date: 08/24/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 106233
ms.assetid: 517e6a88-e7a1-4398-9971-b22fa83306ba
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: 4dc6cb7c0d6c04371ada611626415d87e9f149f0
ms.sourcegitcommit: 259ba130450d8a6d93a65685c22c7eb411982c92
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/24/2021
ms.locfileid: "8460217"
---
# <a name="financial-analysis"></a>財務分析

[!include [banner](../includes/banner.md)]

**財務分析** 使用 Microsoft Power BI 來匯集財務關鍵績效指標 (KPI)、圖表和財務報表。 將 Power BI 嵌入在應用程式中。 **財務分析** 的重點是分析報告。 整個組織的角色可以查看、研究、理解和行動。 

**財務分析** 結合總帳和分類帳中的資料，更全面地了解組織的財務狀況。

> [!NOTE]
> 本文件使用以下 Power BI 術語：
> 
> - **報告** – 所有索引標籤上的所有視覺效果都儲存到的單個 .pbix 檔案。
> - **頁面** – 單個 .pbix 檔案中的索引標籤。 每個頁面可以包含一個或多個視覺效果。
> - **視覺效果** – 單一資料來源，例如卡片、KPI、圖表、圖形、矩陣或財務報表。 由於所報告資料的大小，將財務報表作為視覺效果的頁面不能有其他視覺效果。

**財務分析** 工作區專注於讓您查看和篩選現有報告中的資料。 您可以將新的視覺效果新增到 **財務分析** 工作區。 **財務分析** 工作區可供目前的公司以及所有公司使用，以顯示所有法律實體的資料，無論該角色有權存取的法律實體如何。

- [在儀表板上新增或編輯 Power BI 視覺效果](/powerapps-docs/user/add-powerbi-dashboards.md)

## <a name="dynamics-365-finance-setup"></a>Dynamics 365 Finance 設定
**總分類帳**

主科目類型和主科目類別用於在 **資產負債表** 財務報表和 **財務分析** 中的各種 **損益表** 財務報表上填入適當的預設主科目。

在 **主科目** 頁面上，您必須定義您的主科目，以便為其指派以下類型之一：

- 收入
- 費用
- 資產
- 負債
- 衡平

不要將任何其他主科目類型，例如 **資產負債表** 或 **收益與損失**，指派到您的主科目。 當指派其他主科目類型時，報告無法確定主科目的類型，因為它們不夠精細。 必須確定主科目的類型以在財務報告中將負債和收入顯示為正數。

若要出現在財務報表上並包含在各種其他視覺效果中，例如 KPI，必須為每個主科目指派一個主科目類別。 主科目類別已得到增強，因此它們包括顯示順序。 顯示順序專門用於 **財務分析** 中的財務報表。 編輯或新增新的主科目類別後，您可以更改 **顯示順序** 值來定義主科目類別應在財務報表中顯示的順序。 如果您必須更改許多主科目類別的顯示順序，您可以使用在 Excel 中打開功能快速編輯更改並將更改發佈回應用程式。

## <a name="entity-store"></a>實體儲存
**財務分析** 的資料是從實體儲存 (**系統管理**\>**設定**\>**實體儲存**) 中取出的。 如果您打開 **CFO 概述** 或 **財務分析** 工作區，並且視覺效果中出現以下警告訊息，則必須更新實體。

![警告。](./media/Cantdisplay.png)

您必須更新以下實體才能查看 **財務分析** 工作區：

- 財務報告交易資料版本 3 
- 信用與收款 V2
- LedgerCovLiquidityMeasurement
- 採購立方體
- 銷售立方體

您可以定義定期批次來定期更新實體中的資料。 由於每個實體在更新期間都會完全重建，因此請謹慎選取實體更新的時間和頻率。 用於財務報表的主要實體是 FinancialReportingTransactionData 實體。 因此，您可能決定更頻繁地更新該實體。

## <a name="security"></a>安全性
目前，內嵌 Power BI 報表上的資料不能僅限於使用者有權存取的法律實體。 因此，內嵌 Power BI 報告透過安全設定中的責任進行控制。 定義的責任允許存取所有法律實體或僅啟用中公司的資料。 下表顯示了存在的責任和指派給他們的角色。 根據組織的要求，可以刪除責任或將責任指派給不同的角色。

| 責任                                    | 角色 | 描述 |
|-----------------------------------------|-------|------------|
| 檢視目前公司的財務分析 | <ul><li>會計</li><li>會計經理</li><li>會計主管</li><li>稽核員</li><li>預算管理員</li><li>執行長</li><li>財務長</li><li>財務總監</li></ul> | 這項責任可存取財務分析。 在預設情況下，啟用中公司用作篩選器。 您不能新增其他法律實體。 |
| 檢視所有公司的財務分析   | 在 Microsoft Dynamics 365 for Finance and Operations，Enterprise Edition 7.3，此責任未指派給角色。 在下一個版本中，此責任將指派給財務長角色。 | 此責任可存取 CFO 概述工作區選單項目。 在預設情況下，啟用中公司用作篩選器。 但是，您可以新增所有法律實體，而不管使用者是否有權存取其他法律實體。 |


## <a name="financial-reporting-vs-financial-analysis"></a>財務報告與財務分析的比較
雖然 **財務分析** 包含財務報表，它不能替代應用程式中的財務報告。 **財務分析** 中的預設財務報表範圍有限，不包括所有類型的財務報表。 財務報告仍然是設計、建立和產生法定財務報表的主要工具。

以下比較圖表將有助於區分這兩個選項：


| 功能                                                   | Financial Reporting                                               | 財務分析 |
|----------------------------------------------------------|-------------------------------------------------------------------|--------------------|
| **編輯預設報表**                                 | 是                                                               | 否 |
| **建立新報表**                                   | 是                                                               | 否 |
| **列印報表**                                        | 是                                                               | 否 |
| **匯出到 Excel**                                      | 是                                                               | 將原始資料匯出到 Excel，而不是格式化報告 |
| **支援報告階層/組織階層**   | 是                                                               | 否 |
| **子分類帳資料報告**                             | 是，僅限於廠商、客戶                              | 是，廠商、客戶、廠商/客戶組、廠商/客戶地址等。 |
| **報表貨幣**                                   | 是，記帳貨幣並轉換為報告貨幣       | 否，僅限記帳貨幣 |
| **安全性**                                             | 是，堅持財務報表樹狀結構安全性 | 有限，查看所有公司 (無論財務和營運應用程式安全性) 或僅啟用中公司的報告 |
| **支援不同的會計科目表和會計年度** | 是                                                               | 否 |
| **外部資料報告**                              | 否                                                                | 否 |
| **支援合併**                               | 是                                                               | 有限，可以報告多家公司，但僅使用記帳貨幣 |

可提供以下財務報表：

- 試算表
- 資產負債表
- 按地區劃分的損益表
- 損益表實際值與預算的比較
- 有差異的損益表
- 12 個月趨勢損益表
- 費用三年趨勢
- 廠商費用
- 客戶銷售

## <a name="edit-visuals"></a>編輯視覺效果
在以前的 **財務分析** 版本中，無法編輯任何視覺效果。 在未來的版本中，具有適當安全性的使用者將能夠建立新視覺效果、複製現有視覺效果和編輯視覺效果。 儘管包含報告的 .pbix 檔案可作為資源使用，但我們不建議您編輯預設報告。 將對用於建立財務報表的資料模型、預設報告和自訂財務報表視覺效果進行其他更改。 因此，要在下一版本中利用新功能和對資料模型所做的更改，您必須重做透過 Microsoft Power BI Desktop 對預設報表所做的任何更改。

## <a name="filtering"></a>篩選
使用者可以使用左側的 **篩選器** 窗格篩選報告。 此窗格與透過 Power BI Desktop 提供的窗格相同。 有各種級別的篩選，其中有些可能無法使用，具體取決於您在頁面 (索引標籤) 上選取的內容或您是否使用鑽取功能：

- **報告級別篩選器** – 這些篩選器適用於所有頁面 (索引標籤) 上的所有視覺效果。
- **頁面級別篩選器** – 這些篩選器適用於活動索引標籤上的所有視覺效果。這些篩選器應用在報告級別篩選器之上。
- **視覺效果級別篩選器** – 這些篩選器僅應用於選定的視覺效果。 這些篩選器套用在頁面級別篩選器上。
- **鑽取篩選器** – 當您從來源視覺效果鑽取到目前的視覺效果時，此篩選器從套用於目前視覺效果的「來源」視覺效果中篩選。

![篩選器選項。](./media/filter.png)

若要刪除特定篩選器值，請選取它旁邊的橡皮擦符號。 不要透過選取 X 來刪除篩選器。如果您選取 X，您正在篩選的欄位將作為篩選器選項被刪除。 如果您不小心從篩選器中刪除了某個欄位，請關閉工作區，然後重新打開它。 將重新套用預設篩選器設定。

在預設情況下，當您首次打開工作區時，啟用中法律實體將用作報表級別的篩選器。 根據他們的安全性，使用者可能可以新增其他法律實體或更改在篩選器中選取的預設法律實體。

**會計行事曆** 篩選器為必要，以便為視覺效果使用正確的行事曆。 在預設情況下，報表級別篩選器設定為啟用中法律實體的會計行事曆。 如果您將篩選器更改為具有不同開始日期或結束日期的會計行事曆，則將不包括期初餘額。 因此，您的 **資產負債表** 財務報表不會顯示正確的餘額。 如果您在篩選器中選取額外的會計行事曆，您將擁有一組額外的資料欄。 每組額外的資料欄顯示不同會計行事曆的金額。

**過帳層** 篩選器也是必要的。 在預設情況下，將篩選器設定為目前。 您可以在篩選器中選取其他過帳層以顯示彙總金額。

篩選器也可用於 **日期** 和 **會計年度** 欄位。 通常，這些篩選器會在頁面級別套用。 在預設情況下，**日期** 篩選器可使用您可以更改的關係日期。 您還可以刪除關係日期篩選器並改用 **會計年度** 篩選器。

## <a name="currency"></a>貨幣

報告總帳資料的所有視覺效果都以記帳貨幣顯示金額。 因此，當您篩選法律實體時，您必須小心只包括具有相同記帳貨幣的法律實體。 否則，您將聚合不同貨幣的資料。

報告子分類帳資料的所有視覺效果，例如 **現金流量預測** 和 **前 10 名** 視覺效果，以系統貨幣顯示金額。 系統貨幣和系統匯率類型在 **系統參數** 頁面上定義。

**銀行帳戶餘額** 視覺效果使用銀行帳戶貨幣的金額。

## <a name="dimensions"></a>維度

預設財務報表不包括任何財務維度，而僅關注主科目。 當報告處於可編輯狀態時，將在未來的版本中提供對財務維度的支援。 然後，組織將能夠篩選財務維度值。

有些財務報表包含基於子分類帳交易的維度。 新財務報表的目標是啟用對未設定為財務維度的維度進行篩選。 例如，預設的廠商費用報表允許您向下擴展主科目，以便您可以查看按廠商細分的餘額。 廠商未設定為財務維度。 相反，系統回傳原始子分類帳交易以查詢廠商。

以下維度用於預設報表。 這些維度都不是財務維度。

- 廠商
- 廠商群組
- 客戶
- 客戶群組
- 國家/地區
- 縣/市
- 城市

> [!IMPORTANT] 
> 如果您使用財務日記帳將多個廠商或客戶的交易匯總到一張憑證中，則資料將不正確。 該報告流程無法確定哪個廠商或客戶與日記帳分錄中的特定分類帳科目有關，因為這些資訊並沒有儲存在任何地方。 因此，我們不建議您在一張憑證中輸入多個廠商、客戶、固定資產或專案。

## <a name="drill-on-data"></a>鑽取資料

Power BI 提供各種級別的鑽取。 每個級別都有不同的名稱和不同的函數。 您還可以鑽取資料列和資料欄。 本節以 **試算表** 財務報表為例討論各種選項，並展示如何鑽取資料列。 資料欄也存在相同的函數。 您只需要更改 **鑽取** 設定。

在下圖中，**試算表** 報表被摺疊到列階層的最高級別，即主科目類型。

![試算報表。](./media/trial-balance.png)

若要查看階層的下一級，即主科目類別，您可以將 **鑽取** 欄位設定為 **資料列**，然後選取 **展開** 按鈕 (鑽取欄位之後的第三個按鈕)。 您現在看到所有主科目類別都已展開。 目前，Power BI 不允許您僅展開一列或一欄，但仍能看到所有其他列或欄。

![試算表向下切入資料列。](./media/trial-balance2.png)

若要展開到所有行的主科目，您可以再次使用 **展開** 按鈕。 但是，要向下切入到僅一列的主科目，請先選取 **向下切入** 按鈕 (視窗右側的單個向下箭頭)，然後選取要向下鑽取的資料列。 下圖顯示了在選取 **向下切入** 按鈕後選取 **銷售** 列時的結果。

![試算表展開按鈕。](./media/trial-balance3.png)

在單列向下切入後，需要多次點選才能回傳到完整的試算表。 **向上切入** 按鈕 (**切入** 欄位之後的第一個按鈕) 僅在 **銷售** 類別的內容中向上切入，如下圖所示。

![試算表向上切入按鈕。](./media/trial-balance4.png)

您可以繼續使用 **向上切入** 按鈕回傳到資料列的最高匯總級別。

Power BI 還有按鈕，可讓您轉到階層中的下一個級別 (**鑽取** 欄位之後的第二個按鈕)。 此按鈕的效果不同於 **展開** 按鈕 (**鑽取** 欄位之後的第三個按鈕) 的效果，後者用於展開階層。 展開階層時，階層會在報表上保持不變。 例如，如前所述，如果您展開主科目類型，您仍會在報告中看到主科目類型。 但是，當您轉到階層中的下一個級別時，報表不再顯示階層中的父級，如下圖所示。

![試算表回頭切入按鈕。](./media/trial-balance5.png)

若要查看匯總餘額背後的交易詳情，您可以選取一些金額以回頭切入到 Financial and Operations。

財務報表的回頭切入將您帶到會計來源瀏覽器 (ASE)，而不是憑證交易。 ASE 不僅僅顯示總帳中的會計分錄。 相反，它顯示子分類帳交易的詳情。 因此，您可以獲得有關原始交易的更多詳情，並可以將其用於分析。 例如，您可以看到廠商或客戶是誰，客戶買了什麼或廠商賣了什麼，甚至交易中的項目。

財務報表中的以下篩選器將發送到 ASE，以便 ASE 顯示匯總的交易：

篩選用的必填欄位：

- 法律實體
- 會計行事曆
- 年
- 主科目識別碼

篩選用的選取性欄位：

- 季
- 月
- 期間

如果您沒有對資料列向下擴展足夠的程度，向下切入則無法運作。 例如，如果您僅向下擴展至主科目類別，則無法向下切入餘額上的 ASE，因為主科目是 ASE 中篩選的必填欄位。

如果您在資料列中向下擴展太多，財務報表上的附加篩選器不會發送到 ASE。 因此，您可能會看到您的數字有所不同。 例如，如果您在按地區劃分的損益表財務報表的行中向下擴展至國家或地區，則國家或地區不會作為篩選器包含在 ASE 中。

> [!NOTE]
> 您可以對財務報表的資料列或資料欄深入挖掘，而不是 ASE 目前支援的篩選。 因此，在某些情況下，ASE 中詳細交易的總和與您要回頭切入的餘額不相符。 此函數將在未來繼續增強。

## <a name="hierarchies"></a>階層

預設財務報表使用兩個階層來切入和擴展資料。 一個階層用於資料列，另一個階層用於資料欄。 這兩個階層都是在財務報表的設計中預先定義的。 對於大多數財務報表，該資料列階層是 **主科目類型**\>**主科目類別**\>**主科目**。 但是，某些報告具有其他欄位，例如國家和地區。 階層的附加節點基於每個交易的子分類帳資料。

對於資料欄，階層側重於法律實體和會計期間。 對於大多數財務報表，該資料欄階層是 **法律實體**\>**會計行事曆**\>**會計年度**\>**季度**\>**期間**。

目前，財務報表不支援組織階層，它可以讓您彙總資料。

## <a name="data-limitations"></a>資料限制
財務報表視覺效果對可以顯示的資料列數有限制。 目前，將該限制設定為 30,000。 如果您超過此限制，該視覺效果將有警告符號來通知您這種情況。

![資料限制。](./media/data-limit.png)

如果超過最大值，財務報表上顯示的總計將不正確，因為並非所有資料列都已載入到視覺效果中。

### <a name="empty-rows"></a>空白資料列
Power BI 不提供隱藏和顯示空白資料列的選項。 如果資料列沒有任何資料，則該資料列不會出現在視覺效果中。


## <a name="additional-resources-for-power-bi"></a>Power BI 的其他資源

在生產環境中啟用 **財務分析** 工作區的嵌入式報告不需要以下資源中的資訊。 相反，如果您想嵌入您自己的 Power BI 報告，它們對開發方塊很有幫助。

- [在 1-box 環境中存取分析工作區和報告](/archive/blogs/dynamicsaxbi/accessing-analytical-workspaces-on-1box-environment)

- [使用 Power BI Embedded 即可將分析新增至工作區](/dynamics365/unified-operations/dev-itpro/analytics/add-analytics-tab-workspaces)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
