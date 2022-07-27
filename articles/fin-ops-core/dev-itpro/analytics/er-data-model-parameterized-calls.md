---
title: 支援 ER 資料模型的參數化調用
description: 本主題說明如何實現電子報表 (ER) 資料模型的參數化調用。
author: NickSelin
ms.date: 03/14/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERModelMappingDesigner, EROperationDesigner, ERExpressionDesignerFormula, ERDataModelDesigner
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-10-01
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 968b0769607e9fdbed57c25b727ed44988a92913
ms.sourcegitcommit: 399d0d3f8e2ebb81b6b9d640365ebe182690bab2
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/15/2022
ms.locfileid: "8460597"
---
# <a name="support-parameterized-calls-of-er-data-models"></a>支援 ER 資料模型的參數化調用

[!include [banner](../includes/banner.md)]

若要產生商業文件，您需要設定包含以下 ER 組件的[電子報表 (ER)](general-electronic-reporting.md)解決方案：

- **[格式](er-overview-components.md#format-component)** – 此組件指定商業文件的結構。
- **格式對應** – 此組件控制如何在執行時填入商業文件。
- **[模型對應](er-overview-components.md#model-mapping-component)** – 此組件指定資料從應用程式中提取到格式對應中的內容。
- **[資料模型](er-overview-components.md#data-model-component)** – 此組件在各個組件之間傳遞資訊。

當您執行 ER 格式時，每個格式元素都會從根格式元素開始執行。 每當執行的格式元素包含與[資料來源](general-electronic-reporting.md#configuring-data-model-mappings-for-outgoing-documents)，執行資料來源以傳遞預期的資料並使用它來填入格式元素。 當調用 *模型* 的資料來源時，調用適當的模型對應以根據模型對應設定從應用程式中提取資料。

以前，這些模型對應調用無法參數化以使它們依賴於執行格式的邏輯。 僅支援以下資料流程。

<table>
<tbody>
<tr align="center">
<td>
<b>格式</b><br>
格式&nbsp;元素<br>
&nbsp;
</td>
<td>
<i>繫結程序</i><br>
&gt;&nbsp;要求&nbsp;&gt;<br>
&lt;&nbsp;值&nbsp;&lt;
</td>
<td><b>格式&nbsp;對應</b><br>
資料來源<br>
&nbsp;
</td>
<td>
<i>資料&nbsp;模型</i><br>
&gt;&nbsp;要求&nbsp;&gt;<br>
&lt;&nbsp;值&nbsp;&lt;
</td>
<td>
<b>模型&nbsp;對應</b><br>
資料&nbsp;來源<br>
&nbsp;
</td>
<td>
<i>繫結程序</i><br>
&gt;&nbsp;要求&nbsp;&gt;<br>
&lt;&nbsp;值&nbsp;&lt;
</td>
<td>
<b>表格</b><br>
記錄<br>
欄位
</td>
</tr>
</tbody>
</table>

但是在 10.0.15 及更新的版本中，您可以設定資料模型欄位，這些欄位只有在提供了設定參數的值時才能調用。 當從格式組件設定和調用此類欄位時，必須在格式繫結中提供所需的參數作為調用的參數。 在這些情況下，可以根據特定格式的值指定參數的值。 因此，您可以使用 **動態執行階段參數化** 用於資料模型調用以支援以下資料流程。

<table>
<tbody>
<tr align="center">
<td>
<b>格式</b><br>
格式&nbsp;元素&nbsp;1<br>
<br>
格式&nbsp;元素&nbsp;2<br>
&nbsp;<br>
&nbsp;
</td>
<td>
<i>繫結程序</i><br>
&gt;&nbsp;要求&nbsp;1&nbsp;&gt;<br>
&lt;&nbsp;值&nbsp;1&nbsp;&lt;<br>
&gt;&nbsp;要求&nbsp;2&nbsp;&gt;<br>
&lt;&nbsp;值&nbsp;3&nbsp;&lt;<br>
&nbsp;
</td>
<td>
<b>格式&nbsp;對應</b><br>
資料&nbsp;來源&nbsp;1<br>
&nbsp;<br>
<b>value2=Func(value1)</b><br>
&nbsp;<br>
&nbsp;
</td>
<td>
<i>資料&nbsp;模型</i><br>
&gt;&nbsp;field1&nbsp;&gt;<br>
&lt;&nbsp;值&nbsp;1&nbsp;&lt;<br>
<b>&gt;&nbsp;field2(value2)&nbsp;&gt;</b><br>
&lt;&nbsp;值&nbsp;3&nbsp;&lt;<br>
&nbsp;
</td>
<td>
<b>模型&nbsp;對應</b><br>
資料&nbsp;來源&nbsp;1<br>
<br>
資料&nbsp;來源&nbsp;2<br>
&nbsp;<br>
&nbsp;
</td>
<td>
<i>繫結程序</i><br>
&gt;&nbsp;要求&nbsp;1&nbsp;&gt;<br>
&lt;&nbsp;值&nbsp;1&nbsp;&lt;<br>
&gt;&nbsp;要求&nbsp;2&nbsp;&gt;<br>
&lt;&nbsp;值&nbsp;3&nbsp;&lt;<br>
&nbsp;
</td>
<td>
<b>資料表&nbsp;1</b><br>
記錄&nbsp;1<br>
欄位&nbsp;1<br>
<b>資料表&nbsp;2</b><br>
記錄&nbsp;2<br>
欄位&nbsp;2
</td>
</tr>
</tbody>
</table>

新函數允許您參數化對任何資料模型欄位的調用 [*記錄*](er-formula-supported-data-types-composite.md#record)或 [*記錄清單*](er-formula-supported-data-types-composite.md#record-list)類型。 資料模型欄位的參數支援以下資料類型：

- [布林值](er-formula-supported-data-types-primitive.md#boolean)
- [容器](er-formula-supported-data-types-composite.md#container)
- [日期](er-formula-supported-data-types-primitive.md#date)
- [日期時間](er-formula-supported-data-types-primitive.md#datetime)
- [GUID](er-formula-supported-data-types-primitive.md#guid)
- [Int64](er-formula-supported-data-types-primitive.md#int64)
- [整數](er-formula-supported-data-types-primitive.md#integer)
- [實數](er-formula-supported-data-types-primitive.md#real)
- [字串](er-formula-supported-data-types-primitive.md#string)

您可以指定資料模型欄位的每個參數，其參數可以作為已定義資料類型的單個值提供，並且 [*清單*](er-formula-supported-data-types-composite.md#record-list)這樣的值。

> [!NOTE]
> 不支援資料模型欄位參數的預設值。 如果您在資料模型中的某個欄位中新增參數，並且該資料模型的版本已經推出和發佈，您必須[重訂基底](general-electronic-reporting.md#upgrading-a-format-selecting-a-new-version-of-base-format-rebase)所有對應的模型對應和格式到這個模型的新版本，因為這個資料模型的改變是不向後相容的。

您可以設定參數化資料模型欄位以使模型對應調用特定於格式。 這種方法可以幫助您減少必須為單資料模型的多種格式設定的模型對應的數量。 您還可以使用此方法來提高格式的執行效能並減少產生商業文件所需的時間。 若要進一步了解此函數，請完成本主題中的範例。

## <a name="example-use-parameterized-calls-of-er-data-models"></a>範例：使用 ER 資料模型的參數化調用

以下步驟說明了系統管理員或電子報表開發人員角色的使用者如何設計包含資料模型、模型對應和格式 ER 組件的 ER 解決方案，這些組件設定為透過提供調用的參數，其值是在執行時使用執行格式的公式計算出來的。 

這些步驟可以在 **DEMF** 公司。 無需修改代碼。 

在此範例中，您將建立 **Litware, Inc.** 樣本公司的所需的 ER[設定](general-electronic-reporting.md#Configuration)。 確保 **Litware, Inc.** (`http://www.litware.com`) 樣本公司的設定提供者列在 ER 架構，並且被標記為 **有效**。 如果此設定提供者未列出，或者未標記為 **有效**，按照[建立設定提供者並將其標記為有效](tasks/er-configuration-provider-mark-it-active-2016-11.md)中的步驟。

### <a name="business-scenario"></a>業務案例

您有包含您可以執行格式的 ER 解決方案來產生用於稽核目的的電子文件。 此格式包含與銷售訂單和訂購單相關的稅務交易，並且具有所需的詳情，例如交易日期和稅值。 在新的會計年度，本文件的結構發生了變化。 您現在必須送出擴展文件，其中包含交易在產生的報告中顯示的所有各方 (客戶和廠商) 的其他詳情 (名稱)。 因此，您必須修改您的 ER 解決方案，以便它產生符合此新要求的文件。

### <a name="configure-the-er-framework"></a>設定 ER 架構

按照[設定 ER 架構](er-quick-start2-customize-report.md#ConfigureFramework)中的步驟設定最小的 ER 參數集。 在開始使用 ER 架構設計新的 ER 解決方案之前，您必須完成此安裝。

### <a name="design-a-domain-specific-data-model"></a>設計特定領域的資料模型

您必須建立包含所需資料模型組件的新 ER 設定。 稍後，當您設計 ER 格式以產生稽核報表時，此資料模型將用作資料來源。

按照以下步驟從 Microsoft 提供的 XML 檔案匯入所需的資料模型。

1. 下載[樣本稽核模型.版本.1.xml](https://download.microsoft.com/download/7/1/9/719b0132-fed7-4c73-8afa-90cac29c2fee/Sample-audit-model.version.1.xml)檔案，並將其儲存到本地電腦。
2. 進入 **組織管理**\>**工作區**\>**電子報表**。
3. 在 **電子報表** 工作區中，選取 **報表設定**。
4. 在 **設定** 頁面上，在動作窗格上，選取 **Exchange**\>**從 XML 檔案載入**。
5. 選取 **瀏覽**，然後找到並選取 **樣本稽核模型.版本.1.xml** 檔案。
6. 選取 **確定** 以匯入設定。

    ![在設定頁面上匯入 ER 資料模型設定。](./media/er-data-model-parameterized-calls-imported-model.png)

下圖顯示了 **資料模型設計工具** 頁面上已設定資料模型的可編輯版本。

![資料模型設計工具頁面上 ER 資料模型的結構。](./media/er-data-model-parameterized-calls-model1.png)

現行，該模型旨在僅公開具有所需詳情的稅務交易。

### <a name="design-a-model-mapping-for-the-configured-data-model"></a>為設定的資料模型設計模型對應

作為電子報表開發人員角色的使用者，您必須建立新的 ER 設定，其中包含樣本稽核資料模型的模型對應組件。 此組件為 Microsoft Dynamics 365 Finance 實施已設定資料模型並且特定於該應用程式。 您必須設定模型對應組件以指定必須用於在執行階段用應用程式資料填入設定的資料模型的應用程式對象。 若要完成此任務，您必須了解稅務業務領域的資料結構在 Finance 中是如何實現的。

按照以下步驟從 Microsoft 提供的 XML 檔案匯入所需的模型對應。

1. 下載 [樣本稽核模型.對應.1.1.xml](https://download.microsoft.com/download/c/0/3/c03a4673-b1b1-4ef8-96d0-bf96518be6e0/Sample-audit-model-mapping.version.1.1.xml) 檔案，並將其儲存到本地電腦。
2. 進入 **組織管理**\>**工作區**\>**電子報表**。
3. 在 **電子報表** 工作區中，選取 **報表設定**。
4. 在 **設定** 頁面上，在動作窗格上，選取 **Exchange**\>**從 XML 檔案載入**。
5. 選取 **瀏覽**，然後找到並選取 **樣本稽核模型對應.版本.1.1.xml** 檔案。
6. 選取 **確定** 以匯入設定。

    ![在設定頁面上匯入 ER 模型對應設定。](./media/er-data-model-parameterized-calls-imported-mapping.png)

下圖顯示了 **模型對應設計工具** 頁面上已設定模型對應的可編輯版本。

![模型對應設計工具頁面上 ER 模型對應的結構。](./media/er-data-model-parameterized-calls-mapping1.png)

現行，該模型對應旨在公開具有所需詳情的稅務交易。 它透過使用設定的 `TaxTrans` 和 `TaxTransFiltered` ER 資料來源從 `TaxTrans` 應用程式申請表中獲取這些資訊。

### <a name="design-a-new-format"></a>設計新格式

作為電子報表函數顧問角色的使用者，您必須建立新的 ER 設定，其中包含格式組件。 您必須設定格式組件以使用包含所有必需詳情的稅務交易記錄填入產生的報告。

按照以下步驟從 Microsoft 提供的 XML 檔案匯入所需的格式。

1. 下載[樣本稽核格式.版本.1.1.xml](https://download.microsoft.com/download/e/b/7/eb7e126e-2bb3-4bbb-a735-ffd4c48920b1/Sample-audit-format.version.1.1.xml)檔案，並將其儲存到本地電腦。
2. 進入 **組織管理**\>**工作區**\>**電子報表**。
3. 在 **電子報表** 工作區中，選取 **報表設定**。
4. 在 **設定** 頁面上，在動作窗格上，選取 **Exchange**\>**從 XML 檔案載入**。
5. 選取 **瀏覽**，然後找到並選取 **樣本稽核格式.版本.1.1.xml** 檔案。
6. 選取 **確定** 以匯入設定。

    ![在設定頁面上匯入 ER 格式設定。](./media/er-data-model-parameterized-calls-imported-format.png)

下圖顯示了在 **格式設計工具** 頁面上設定的格式的可編輯版本。

![在格式設計工具頁面上的 ER 格式結構。](./media/er-data-model-parameterized-calls-format1.png)

將 ER 格式設定為以逗號分隔值 (CSV) 格式產生文字檔報告。

### <a name="run-the-imported-format"></a>執行已匯入的格式

1. 在 **設定** 頁面上，選取 **樣本稽核格式** 設定，然後在動作窗格中，選取 **執行**。
2. 在 **電子報表參數** 對話方塊中，在 **要納入的記錄** 索引標籤，選取 **篩選**。
3. 指定要選取 **PIV-110000004** 和 **INV-10000001** 憑證的稅務交易的條件。
4. 選取 **確定**。
5. 選取 **確定**。
6. 查看包含所選憑證稅務交易的已產生文件。

    ![預覽包含稅務交易的已產生文件。](./media/er-data-model-parameterized-calls-output1.png)

### <a name="adjust-the-imported-er-solution"></a>調整匯入的 ER 解決方案

根據新的要求，您必須送出的文件必須包含其交易的客戶和廠商的名字。 因此，您必須修改匯入的 ER 解決方案，以便它產生符合此新要求的文件。

決定您希望如何對匯入的 ER 組件進行所需的修改。

顯而易見的方法是實施以下修改：

- 在您的資料模型中，新增 *字串* 類型新 `Transaction.Party.Name` 資料模型欄位。
- 在您的模型對應中，透過使用可用的資料表關係存取新資料模型欄位的相關記錄來設定新資料模型欄位的繫結程序。`DirPartyTable` 應用程式資料表並從中擷取 `Name` 欄位的值。

雖然這種方法可行，但它可能會導致 SQL 資料庫出現效能問題，因為 `TaxTrans` 是交易資料表，因此可以包含大量記錄。 在這種情況下，調用 `DirPartyTable` 次數必須等於可能導致效能問題的 `TaxTrans` 資料表中的記錄數量。

或者，您可以實施以下修改：

- 在您的資料模型中，新增新的 `Party` 根和新的 `Party.Name` 欄位。
- 在您的模型對應中，新增新的資料來源，該資料來源將連結資料表關係中使用的所有表記錄，以存取 `DirPartyTable` 應用程式資料表的相關記錄，從 `TaxTrans` 資料表開始。

雖然這種方法可行，但它可能會導致一些記憶體消耗問題。 即使當新的[JOIN](er-join-data-sources.md)資料來源作為對應用程式資料庫的單個 SQL 要求來執行，以防止資料庫效能問題，結果必須被擷取到應用程式伺服器的記憶體中。 因為記錄的數量和這些記錄中的欄位數量會很大，這種方法可能會導致非常大的記憶體消耗。 甚至可能會引發記憶體不足的執行階段異常。

當執行格式在記憶體中收集將在產生的報告上顯示的所有稅務交易的客戶和廠商的唯一識別代碼時，您可以實施修改。 因為應該只保留唯一的代碼，所以最終的代碼集不會大到影響記憶體消耗。 然後，這組代碼將作為另一個 *模型* 類型資料來源調用的參數傳遞給模型對應。 基於該調用，模型對應將執行新的 ER 資料來源，向應用程式資料庫發出一個 SQL 要求，從 `DirPartyTable` 資料表中擷取僅在所提供的代碼集中出現的那些當事方的記錄。

### <a name="adjust-the-imported-data-model"></a>調整匯入的資料模型

1. 進入 **組織管理**\>**電子報表**\>**設定**。
2. 在 **設定** 頁面上，在左側窗格中的設定樹狀結構中，選取 **樣本稽核模型**。
3. 在 **版本** FastTab 上，選取 **[草稿](general-electronic-reporting.md#component-versioning)** 狀態的版本 **2**。
4. 選取 **設定組件** FastTab。
5. 選取 **設計工具** 打開資料模型進行編輯。
6. 在 **資料模型** 頁面上，請確保選取`Root` 欄位，然後選取 **新建**。
7. 在下拉式對話方塊中，執行以下步驟：

    1. 在 **新節點為** 欄位組中，選取 **有效節點的子系** 選項。
    2. 在 **名稱** 欄位中，輸入 **Party**。
    3. 在 **項目類型** 欄位中，選取 **記錄清單**。
    4. 選取 **新增** 完成新欄位。

8. 確保選取`Root.Party` 欄位，然後，在 **節點** 索引標籤上，選取 **參數**。
9. 在 **參數** 對話方塊中，請按照下列步驟操作：

    1. 在 **參數** 索引標籤上，選取 **新建**。
    2. 在 **名稱** 欄位中，輸入 **PartyRefRecId**。
    3. 在 **類型** 欄位中，選取 **Int64**。
    4. 選取 **清單** 核取方塊。
    5. 選取 **確定** 完成輸入參數。

    > [!NOTE]
    > 您剛剛將 `Root.Party` 資料模型欄位設定為欄位，當 **PartyRefRecId** 參數中提供某個值時，該欄位就會被調用。 這個值必須出現在包含 *Int64* 資料類型的 `Value` 欄位的記錄清單中。

    ![參數對話方塊。](./media/er-data-model-parameterized-calls-model2a.png)

10. 確保仍選取`Root.Party` 欄位，然後選取 **新建**。
11. 在下拉式對話方塊中，執行以下步驟：

    1. 在 **新節點為** 欄位組中，選取 **有效節點的子系** 選項。
    2. 在 **名稱** 欄位中，輸入 **Name**。
    3. 在 **項目類型** 欄位中，選取 **字串**。
    4. 選取 **新增** 完成新欄位。

12. 選取 **儲存**，關閉 **資料模型** 頁面。

    ![資料模型設計工具頁面上已調整 ER 資料模型的結構。](./media/er-data-model-parameterized-calls-model2b.png)

13. 在 **版本** FastTab 上，針對版本 **2**，選取 **更改狀態**\>**完成**。 然後選取 **確定**。

    > [!NOTE]
    > 您的資料模型更改儲存在第二個修訂版的 **樣本稽核模型** 資料模型組件，並位於 **樣本稽核模型** ER 設定的第二個版本。

![更新設定頁面上的 ER 資料模型設定。](./media/er-data-model-parameterized-calls-updated-model.png)

### <a name="adjust-the-imported-model-mapping"></a>調整匯入的資料對應

1. 在 **設定** 頁面上，在左側窗格中的設定樹狀結構中，展開 **樣本稽核模型**。
2. 選取 **樣本稽核模型對應**，然後，在 **版本** FastTab 上，選取基於第一個資料模型版本的第二個對應版本 (版本 **1.2**)，並且其狀態為 **草稿**。
3. 選取 **重訂基底**。
4. 在 **目標版本** 欄位中，離開 **樣本稽核模型** 基底模型的版本 **2**。
5. 選取 **確定** 重訂基底並將您的模型對應與最近的資料模型更改對齊。

    請注意，可編輯模型對應的版本編號已從 **1.2** 更改到 **2.2** 來表示現行使用第二個模型版本作為基礎。

6. 選取 **設計工具**。
7. 在 **資料來源對應的模型** 頁面上，選取現行模型對應的 **設計工具**。
8. 按照以下步驟新增新的資料來源存取 `DirPartyTable` 應用程式資料表：

    1. 在 **資料來源類型** 窗格中，選取 **Dynamics 365 for Operations\>資料表記錄**。
    2. 在 **資料來源** 窗格中，選取 **新增根**。
    3. 在 **名稱** 欄位中，輸入 **PartyTable**。
    4. 在 **資料表** 欄位中，輸入 **DirPartyTable**。
    5. 選取 **確定** 完成新增新的資料來源。

9. 按照以下步驟新增新的資料來源以要求 `DirPartyTable` 記錄，根據提供的記錄識別碼清單：

    1. 在 **資料來源類型** 窗格中，選取 **一般\>空白容器**。
    2. 在 **資料來源** 窗格中，選取 **新增根**。
    3. 在 **名稱** 欄位中，輸入 **Data**。
    4. 選取 **確定** 完成新增新的資料來源。
    5. 在 **資料來源** 窗格中，選取 **資料** 資料來源。
    6. 在 **資料來源類型** 窗格中，選取 **函數\>導出欄位**。
    7. 在 **資料來源** 窗格中，選取 **新增**。
    8. 在 **名稱** 欄位中，輸入 **DirParty**。
    9. 選取 **編輯公式**。
    10. 在 **公式設計工具** 頁面上，選取 **參數**。
    11. 在 **參數** 對話方塊中，請按照下列步驟操作：

        1. 在 **參數** 索引標籤上，選取 **新建**。
        2. 在 **名稱** 欄位中，輸入 **DirPartyId**。
        3. 在 **類型** 欄位中，選取 **Int64**。
        4. 選取 **清單** 核取方塊。
        5. 選取 **確定**。

        > [!NOTE]
        > 您剛設定了這個導出欄位，以便它在執行階段接受單個參數的引數，該參數設定為具有 *Int64* 類型的單個 `Value` 欄位的記錄清單。

    12. 在 **公式** 欄位中，輸入以下運算式：

        `FILTER(PartyTable, VALUEINLARGE(PartyTable.RecId, DirPartyId, DirPartyId.Value))`

        > [!NOTE]
        > 您剛設定了 `DirParty` 導出欄位，只擷取 `DirPartyTable` 記錄，其中記錄識別碼包括在 `DirPartyId` 清單中，該清單在調用 `DirParty` 欄位時作為引數提供。

        ![從公式設計工具頁面上的應用程式資料表中擷取合作對象名稱的公式。](./media/er-data-model-parameterized-calls-formula1.png)

    13. 選取 **儲存**，關閉 **公式設計工具** 頁面。
    14. 選取 **儲存**，然後選取 **確定** 完成新增新的資料來源。

10. 按照以下步驟將新資料來源繫結到新資料模型欄位，以便使用資料模型公開合作對象名稱：

    1. 在 **資料模型** 窗格中，選取`Root.Party` 資料模型欄位。
    2. 在 **資料模型** 窗格中，選取 **Edit**。
    3. 在 **公式設計工具** 頁面上，在 **公式** 欄位中，輸入運算式 `Data.DirParty(PartyRefRecId)`。
    4. 選取 **儲存**，關閉 **公式設計工具** 頁面。

        > [!NOTE]
        > 您剛設定了繫結來調用設定好的 `Data.DirParty` 資料來源，並提供記錄識別碼的清單，當 `Root.Party` 資料模型欄位被調用時，這些識別碼將被指定格式。

    5. 在 **資料模型** 窗格中，選取`Root.Party.Name` 資料模型欄位。
    6. 在 **資料模型** 窗格中，選取 **Edit**。
    7. 在 **公式設計工具** 頁面上，在 **資料來源** 窗格中，展開 **Data\>DirParty**，並選取 **名稱**。
    8. 選取 **新增資料來源**。
    9. 選取 **儲存**，關閉 **公式設計工具** 頁面。

    ![模型對應設計工具頁面上已調整 ER 模型對應的結構。](./media/er-data-model-parameterized-calls-mapping2.png)

11. 選取 **儲存**，關閉 **模型對應設計工具** 頁面。
12. 關閉 **資料來源對應的模型** 頁面。
13. 在 **版本** FastTab 上，針對版本 **2.2**，選取 **更改狀態\>完成**。 然後選取 **確定**。

### <a name="adjust-the-imported-format"></a>調整已匯入的格式

1. 在 **設定** 頁面上，選取 **樣本稽核格式**。
2. 在 **版本** FastTab 上，選取 **草稿** 狀態的版本 **1.2**。
3. 選取 **重訂基底**。
4. 在 **目標版本** 欄位中，離開 **樣本稽核模型** 基底模型的版本 **2**。
5. 選取 **確定** 重訂基底並將您的格式與最近的資料模型更改對齊。
6. 選取 **設計工具**。
7. 在 **公式設計工具** 頁面上，在左窗格的格式結構樹中，選取 **展開/折疊**。
8. 按照以下步驟新增新的格式元素，以收集其交易在產生的報告中呈現的各方的記錄識別碼。

    1. 在格式結構樹中，選取 **Report.Row.Trans** 序資料列元素。
    2. 選取 **新增**。
    3. 在 **新增** 對話方塊中，選取 **資料來源\>項目**。
    4. 在下拉式 **組件屬性** 對話方塊中，在 **名稱** 欄位中，輸入 **Id**。
    5. 在 **資料類型** 欄位中，選取 **Int64**。
    6. 選擇 **確定**。

    > [!NOTE]
    > **資料來源\>項目** 元素只能在執行格式範圍內進行內部計算和資料轉換。 因此，透過新增此格式元素，您不會更改已產生文件的內容。

9. 按照以下步驟新增新的格式元素以在已產生報告中輸入參與方名稱：

    1. 選取 **Report.Row** 序資料列元素。
    2. 選取 **新增**。
    3. 在 **新增** 對話方塊中，選取 **文字\>序列**。
    4. 在下拉式 **組件屬性** 對話方塊中，在 **名稱** 欄位中，輸入 **Party**。
    5. 選擇 **確定**。
    6. 選取 **Report.Row.Party** 序資料列元素。
    7. 選取 **新增**。
    8. 在 **新增** 對話方塊中，選取 **文字\>字串**。
    9. 在下拉式 **組件屬性** 對話方塊中，在 **名稱** 欄位中，輸入 **Name**。
    10. 選取 **確定**。

10. 按照以下步驟新增新的資料來源，以收集其交易在產生的報告中呈現的各方的記錄識別碼：

    1. 在 **對應** 索引標籤上，選取 **新增根**。
    2. 在 **新增資料來源** 對話方塊中，選取 **函數\>資料收集**。
    3. 在 **「資料收集」資料來源屬性** 對話方塊中，在 **名稱** 欄位中，輸入 **PartyIds**。
    4. 在 **項目類型** 欄位中，選取 **Int64**。
    5. 選擇 **確定**。

11. 按照以下步驟新增新的繫結程序，以收集其交易在產生的報告中呈現的各方的記錄識別碼：

    1. 在格式結構樹中，選取 **Report.Row.Trans.Id** 資料項目元素。
    2. 選取 **編輯公式**。
    3. 在 **公式設計工具** 頁面上，輸入運算式 `PartyIds.Collect(model.Transaction.Party.RecId)`。
    4. 選取 **儲存**，關閉 **公式設計工具** 頁面。

12. 按照以下步驟新增新的繫結程序以在已產生報告中輸入參與方名稱：

    1. 在格式結構樹中，選取 **Report.Party** 序列元素。
    2. 選取 **編輯公式**。
    3. 在 **公式設計工具** 頁面上，輸入運算式 `model.Party(PartyIds.Result)`。
    4. 選取 **儲存**，關閉 **公式設計工具** 頁面。
    5. 在格式結構樹中，選取 **Report.Party.Name** 序列元素。
    6. 在 **對應** 索引標籤上，選取`model.Party.Name` 資料模型欄位。
    7. 選取 **綁定**。

    ![在格式設計工具頁面上已調整 ER 格式的結構。](./media/er-data-model-parameterized-calls-format2.png)

13. 選取 **儲存**，關閉 **格式設計工具** 頁面。
14. 關閉 **資料來源對應的模型** 頁面。
15. 在 **版本** FastTab 上，針對版本 **2.2**，選取 **更改狀態**\>**完成**。 然後選取 **確定**。

### <a name="run-the-adjusted-format"></a>執行已調整的格式

1. 在 **設定** 頁面上，選取 **樣本稽核格式**，然後在動作窗格中，選取 **執行**。
2. 在 **電子報表參數** 對話方塊中，在 **要納入的記錄** 索引標籤，選取 **篩選**。
3. 指定要選取 **PIV-110000004** 和 **INV-10000001** 憑證的稅務交易的條件。
4. 選擇 **確定**。
5. 選擇 **確定**。
6. 查看已產生的文件，其中包含所選憑證的稅務交易以及相應客戶和廠商的名稱。

    ![預覽包含稅務交易和合作對象名稱的已產生文件。](./media/er-data-model-parameterized-calls-output2.png)

7. 進入 **應付帳款**\>**廠商**\>**所有廠商**，並查看所選 **PIV-110000004** 憑證的詳情，包括廠商名稱。

    ![查看所有廠商和發票日記帳頁面上的購買憑證詳情。](./media/er-data-model-parameterized-calls-review1.gif)

8. 進入 **應收帳款**\>**客戶**\>**所有客戶**，並查看所選 **INV-10000001** 憑證的詳情，包括客戶名稱。

    ![查看所有客戶和已過帳銷售稅頁面上的銷售憑證詳情。](./media/er-data-model-parameterized-calls-review2.gif)

如需 ER 解決方案執行的相關詳情，請使用 ER 內建[效能追蹤](trace-execution-er-troubleshoot-perf.md)剖析器。

## <a name="additional-resources"></a>其他資源

- [支援導出欄位類型的 ER 資料來源的參數化調用](er-calculated-field-type.md)
- [追蹤 ER 格式的執行以解決效能問題](trace-execution-er-troubleshoot-perf.md)
- [以電子報表格式使用資料收集資料來源](er-data-collection-data-sources.md)
- [ValueInLarge ER 函數](er-functions-logical-valueinlarge.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
