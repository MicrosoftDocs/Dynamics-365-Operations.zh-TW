---
title: 設計新的 ER 解決方案以列印自訂報表
description: 本主題說明如何設計電子報表 (ER) 解決方案以列印自訂報表。
author: NickSelin
ms.date: 08/10/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERParameters, ERDataModelDesigner, ERModelMappingTable, ERModelMappingDesigner, EROperationDesigner, ERVendorTable
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom:
- "220314"
- intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 36998d299e166709778bfaa7bfd0d8980890d4fe
ms.sourcegitcommit: d5d6b81bd8b08de20cc018c2251436065982489e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/17/2022
ms.locfileid: "8460225"
---
# <a name="design-a-new-er-solution-to-print-a-custom-report"></a>設計新的 ER 解決方案以列印自訂報表

[!include[banner](../includes/banner.md)]

以下步驟說明了系統管理員、電子報表開發人員或電子報表函數顧問角色的使用者如何設定 ER 架構的參數，設計新 ER 解決方案所需的 ER 設定以存取特定業務域的資料， 並產生 Microsoft Office 格式的自訂報表。 這些步驟可以在 **USMF** 公司。

- [設定 ER 架構](#ConfigureFramework)

    - [設定 ER 參數](#ConfigureParameters)
    - [啟用 ER 設定提供者](#ActivateProvider)

        - [查看 ER 設定提供者清單](#ReviewProvidersList)
        - [新增新的 ER 設定提供者](#AddProvider)
        - [啟用 ER 設定提供者](#ActivateAddedProvider)

- [設計特定領域的資料模型](#DesignModel)

    - [匯入新的資料模型設定](#ImportDataModel)
    - [建立新的資料模型設定](#DesignDataModel)

        - [命名資料模型](#NameDataModel)
        - [新增資料模型欄位](#FieldsEntry)
        - [完成資料模型的設計](#CompleteDataModel)

- [為設定的資料模型設計模型對應](#DesignMapping)

    - [匯入新的模型對應設定](#ImportModelMapping)
    - [建立新模型對應設定](#CreateModelMapping)

        - [設計新的模型對應組件](#DesignMappingComponent)
        - [新增資料來源以存取應用程式表](#AddMmDataSource1)
        - [新增資料來源以存取應用程式列舉](#AddMmDataSource2)
        - [新增 ER 標籤以產生指定語言的報表](#AddMmLabels)
        - [新增資料來源以將列舉值比較結果轉換為文字值](#AddMmDataSource3)
        - [將資料來源繫結到資料模型欄位](#AddMmBindings1)
        - [完成模型對應的設計](#CompleteModelMapping)

- [為自訂報表設計範本](#DesignReportTemplate)
- [設計格式](#DesignFormat)

    - [匯入設計的格式設定](#FormatImport)
    - [建立新的格式設定](#FormatCreate)

        - [匯入報表的範本](#ImportReportTemplate)
        - [設定格式](#ConfigureFormat)
        - [定義報表標題的資料繫結](#DefineFormatBindings)
        - [查看模型資料來源](#ReviewModelDataSource)
        - [將格式元素繫結到資料來源欄位](#BindFormatElements)

    - [從 ER 執行設計的格式](#RunFormatFromER)

- [調整設計的格式](#TuneFormat)

    - [修改格式以更改產生文件的名稱](#ModifyToChangeName)
    - [修改格式以更改問題的順序](#ModifyToOrder)
    - [從 ER 執行修改的格式](#RunFormatFromER2)
    - [完成格式設計](#CompleteFormat)

- [開發應用程式構件以調用設計的報表](#DevelopCustomCode)

    - [修改原始程式碼](#ModifySourceCode)

        - [新增資料合約類](#DataContractClass)
        - [新增 UI 建立器類](#UIBuilderClass)
        - [新增資料提供者類](#DataProviderClass)
        - [新增標籤檔案](#LabelsFile)
        - [新增報表服務類](#ServiceClass)
        - [新增報表控制器類](#ControllerClass)
        - [新增選單項目](#MenuItem)
        - [將選單項目新增到選單](#Menu)
        - [構建 Visual Studio 專案](#BuildVSProject)

    - [從應用程式執行格式](#RunFormatFromApp)

- [調整設計的 ER 解決方案](#TuneSolution)

    - [修改模型對應](#ModifyModelMapping)

        - [新增資料來源以存取資料合約物件](#AddDataSource1)
        - [新增資料來源以存取 ER 格式對應記錄](#AddDataSource2)
        - [新增資料來源以存取正在執行的 ER 格式的格式對應記錄](#AddDataSource3)
        - [在資料模型中輸入正在執行的 ER 格式的名稱](#AddBinding)
        - [完成模型對應的設計](#CompleteModelMapping2)

    - [修改格式](#ModifyFormat)

        - [新增新的格式元素](#AddFormatElement)
        - [繫結新增的格式元素](#BindAddedFormatElement)
        - [完成格式設計](#CompleteFormat2)

    - [從應用程式執行格式](#RunFormatFromApp2)
    - [從 ER 執行格式](#RunFormatFromER3)
    - [為螢幕上預覽設定格式目的地](#ConfigureDestination)
    - [從應用程式執行格式以將其預覽為 PDF 文件](#RunFormatFromApp3)

- [其他資源](#References)

在此範例中，您將為[問卷](../../../human-resources/hr-learning-questionnaires.md)模組建立一個新的 ER 解決方案。 這個新的 ER 解決方案允許您使用 Microsoft Excel 工作表作為範本來設計報表。 除了產生現有的 SQL Server Reporting Services (SSRS) 報表外，您還可以產生 Excel 或 PDF 格式的 **問卷** 報表。 您也可以稍後根據要求修改新報表。 無需編碼。

1. 若要執行現有報表，請進入 **問卷**\>**設計**\>**問卷報表**。

    ![選取問卷模組中的問卷報表選單項以執行現有的 SSRS 報表。](./media/er-quick-start1-application-menu-origin.png)

2. 在 **問卷報表** 對話方塊，指定選取標準。 套用篩選器，以便報表僅包含 **SBCCrsExam** 問卷。

    ![在問卷報表對話方塊中指定選取標準。](./media/er-quick-start1-ssrs-report-dialog.png)

下圖顯示了為 **SBCCrsExam** 問卷產生的 SSRS 報表版本。

![產生的 SSRS 報表。](./media/er-quick-start1-ssrs-report.png)

## <a name="configure-the-er-framework"></a><a name="ConfigureFramework"></a>設定 ER 架構

作為電子報表開發人員角色的使用者，您必須先設定最少的 ER 參數集，然後才能開始使用 ER 架構來設計新的 ER 解決方案。

### <a name="configure-er-parameters"></a><a name="ConfigureParameters"></a>設定 ER 參數

1. 進入 **組織管理**\>**工作區**\>**電子報表**。
2. 在 **電子報表** 工作區，選取 **電子報表參數**。
3. 在 **電子報表參數** 頁的 **一般** 索引標籤上，將 **啟用設計模式** 選項設定為 **是**。
4. 在 **附件** 索引標籤上設定下列參數：

    - 將 **USMF** 公司的 **設定** 欄位設定為 **檔案**。
    - 將 **作業封存**、**臨時**、**基準** 和 **其他** 欄位設定為 **檔案**。

如需 ER 參數的相關資訊，請參閱[設定 ER 架構](electronic-reporting-er-configure-parameters.md)。

### <a name="activate-an-er-configuration-provider"></a><a name="ActivateProvider"></a>啟用 ER 設定提供者

每個 ER 設定都被標記為歸 ER 設定提供者所有。 因此，您必須先在 **電子報表** 工作區中啟動 ER 設定提供者，然後才能開始新增或編輯任何 ER 設定。

> [!NOTE]
> 只有 ER 設定的所有者可以對其進行編輯。 因此，在可以編輯 ER 設定之前，必須在 **電子報表** 工作區中啟動相應的 ER 設定提供者。

#### <a name="review-the-list-of-er-configuration-providers"></a><a name="ReviewProvidersList"></a>查看 ER 設定提供者清單

1. 進入 **組織管理**\>**工作區**\>**電子報表**。
2. 在 **電子報表** 工作區，在 **相關連結** 部分，選取 **設定提供者**。
3. 在 **設定提供者** 頁面，每個設定提供者記錄都有一個唯一的名稱和 URL。 查看此頁面的內容。 如果 **Litware, Inc.** (`https://www.litware.com`) 的記錄已存在，請跳過下一個程序[新增新的 ER 設定提供者](#ActivateProvider)。

#### <a name="add-a-new-er-configuration-provider"></a><a name="AddProvider"></a>新增新的 ER 設定提供者

1. 在 **設定提供者** 頁面上，選取 **新建**。
2. 在 **名稱** 欄位中，輸入 **Litware, Inc.**
3. 在 **網址** 欄位，輸入 `https://www.litware.com`。
4. 選取 **儲存**。

#### <a name="activate-an-er-configuration-provider"></a><a name="ActivateAddedProvider"></a>啟用 ER 設定提供者

1. 進入 **組織管理**\>**工作區**\>**電子報表**。
2. 在 **電子報表** 工作區中，選取 **Litware, Inc.** 設定提供者。
3. 選取 **設定為作用中**。

如需 ER 設定提供者的相關資訊，請參閱[建立設定提供者並將其標記為有效](tasks/er-configuration-provider-mark-it-active-2016-11.md)。

## <a name="design-a-domain-specific-data-model"></a><a name="DesignModel"></a>設計特定領域的資料模型

您必須建立一個新的 ER 設定，其中包含 **問卷** 業務領域的資料模型組件。 此資料模型稍後將在您設計 ER 格式以產生 **問卷** 報表時用作資料來源。

透過完成[匯入新資料模型設定](#ImportDataModel)部分中的步驟，您可以從提供的 XML 檔案中匯入所需的資料模型。 或者，您可以完成[建立新資料模型設定](#DesignDataModel)部分中的步驟，從頭開始設計此資料模型。

### <a name="import-a-new-data-model-configuration"></a><a name="ImportDataModel"></a>匯入新的資料模型設定

1. 下載[Questionnaires model.version.1.xml](https://download.microsoft.com/download/b/6/3/b633bd34-d200-4422-96d9-8f62eb5218f8/Questionnaires_model.version.1.xml)檔案，並將其儲存到本地電腦。
2. 進入 **組織管理**\>**工作區**\>**電子報表**。
3. 在 **電子報表** 工作區中，選取 **報表設定**。
4. 在動作窗格上，選取 **交換**\>**從 XML 檔案載入**。
5. 選取 **瀏覽**，然後找到並選取 **Questionnaires model.version.1.xml** 檔案。
6. 選取 **確定** 以匯入設定。

若要繼續，請跳過下一個程序，[建立新的資料模型設定](#DesignDataModel)。

### <a name="create-a-new-data-model-configuration"></a><a name="DesignDataModel"></a>建立新的資料模型設定

1. 進入 **組織管理**\>**工作區**\>**電子報表**。
2. 在 **電子報表** 工作區中，選取 **報表設定**。
3. 選取 **建立設定**。
4. 在下拉式對話方塊中，在 **名稱** 欄位中，輸入 **Questionnaire model**。
5. 選取 **建立設定** 以建立設定。

#### <a name="name-the-data-model"></a><a name="NameDataModel"></a>命名資料模型

1. 在 **設定** 頁面上，在設定樹狀結構中，選取 **問卷模型**。
2. 選取 **設計工具**。
3. 在 **資料模型設計工具** 頁面的 **一般** FastTab 上的 **名稱** 欄位中，輸入 <a name="DataModeName"></a>**Questionnaires**。

#### <a name="add-new-data-model-fields"></a><a name="FieldsEntry"></a>新增新的資料模型欄位

1. 在 **資料模型設計工具** 頁面上，選取 **新建**。
2. 在新增資料模型節點的下拉式對話方塊中，執行以下步驟：

    1. 選取 **模型根** 作為新節點的類型。
    2. 在 **名稱** 欄位中，輸入 <a name="RootDefinitionName"></a>**Root**。
    3. 選取 **新增** 以新增新節點。

    此根描述項將用於為 **問卷** 報表提供資料。 單個資料模型可以有多個描述項。 可以為單個 ER 格式指定每個描述項，以識別產生報表所需的資料。

3. 再次選取 **新建**，然後在新增資料模型節點的下拉式對話方塊中，執行以下步驟：

    1. 選取 **有效節點的子系** 作為新節點的類型。
    2. 在 **名稱** 欄位中，輸入 **CompanyName**。
    3. 在 **項目類型** 欄位中，選取 **字串**。
    4. 選取 **新增** 以新增新欄位。

    需要此欄位才能將現行公司的名稱傳遞給使用此資料模型作為資料來源的 ER 報表。

4. 再次選取 **新建**，然後在新增資料模型節點的下拉式對話方塊中，執行以下步驟：

    1. 選取 **有效節點的子系** 作為新節點的類型。
    2. 在 **名稱** 欄位中，輸入 **Questionnaire**。
    3. 在 **項目類型** 欄位中，選取 **記錄清單**。
    4. 選取 **新增** 以新增新欄位。

    此欄位將用於將調查問卷清單傳遞給使用此資料模型作為資料來源的 ER 報表。

5. 選取 **問卷** 節點。
6. 繼續以相同的方式新增可編輯資料模型的必填欄位，直到完成以下資料模型結構。

    | 欄位路徑                                                    | 資料類型   | 欄位指定/回傳值 |
    |---------------------------------------------------------------|-------------|----------------------------------|
    | 根                                                          |             | 請求問卷資料的參考點。 |
    | Root\\CompanyName                                             | 字串      | 現行公司的名稱。 |
    | Root\\ExecutionContext                                        | 記錄      | 格式化執行詳情。 |
    | Root\\ExecutionContext\\FormatName                            | 字串      | 正在執行的 ER 格式的名稱。 |
    | Root\\Questionnaire                                           | 記錄清單 | 問卷清單 |
    | Root\\Questionnaire\\Active                                   | 字串      | 現行問卷的狀態。 |
    | Root\\Questionnaire\\Code                                     | 字串      | 現行問卷的代碼。 |
    | Root\\Questionnaire\\Description                              | 字串      | 現行問卷的描述。 |
    | Root\\Questionnaire\\QuestionnaireType                        | 字串      | 現行問卷的類型。 |
    | Root\\Questionnaire\\QuestionOrder                            | 字串      | 現行問卷的數字順序。 |
    | Root\\Questionnaire\\ResultsGroup                             | 記錄      | 現行問卷的結果參數。 |
    | Root\\Questionnaire\\ResultsGroup\\Code                       | 字串      | 現行結果組的識別碼。 |
    | Root\\Questionnaire\\ResultsGroup\\Description                | 字串      | 現行結果群組的描述。 |
    | Root\\Questionnaire\\ResultsGroup\\MaxNumberOfPoints          | 真實        | 可以獲得的最大分數。 |
    | Root\\Questionnaire\\Question                                 | 記錄清單 | 現行問卷的問題清單。 |
    | Root\\Questionnaire\\Question\\CollectionSequenceNumber       | 整數     | 現行答案集合的序號。 |
    | Root\\Questionnaire\\Question\\Id                             | 字串      | 現行問題的識別碼。 |
    | Root\\Questionnaire\\Question\\MustBeCompleted                | 字串      | 指示是否必須回答現行問題的標幟。 |
    | Root\\Questionnaire\\Question\\PrimaryQuestion                | 字串      | 指示現行問題是否為主要問題的標幟。 |
    | Root\\Questionnaire\\Question\\SequenceNumber                 | 整數     | 現行問題的序號。 |
    | Root\\Questionnaire\\Question\\Text                           | 字串      | 現行問題的文字。 |
    | Root\\Questionnaire\\Question\\Answer                         | 記錄清單 | 現行問題的解答清單。 |
    | Root\\Questionnaire\\Question\\Answer\\CorrectAnswer          | 字串      | 指示現行答案是否正確的標幟。 |
    | Root\\Questionnaire\\Question\\Answer\\Points                 | 真實        | 選取現行答案時獲得的分數。 |
    | Root\\Questionnaire\\Question\\Answer\\SequenceNumber         | 整數     | 現行答案的序號。 |
    | Root\\Questionnaire\\Question\\Answer\\Text                   | 字串      | 現行答案的文字。 |

    下圖顯示了 **資料模型設計工具** 頁面上已完成的可編輯資料模型。

    ![在 ER 資料模型設計工具中設定的資料模型。](./media/er-quick-start1-model2.png)

7. 儲存您的變更。
8. 關上 **資料模型設計工具** 頁面。

#### <a name="complete-the-design-of-the-data-model"></a><a name="CompleteDataModel"></a>完成資料模型的設計

1. 進入 **組織管理**\>**電子報表**\>**設定**。
2. 在 **設定** 頁面上，在設定樹狀結構中，選取 **問卷模型**。
3. 在 **版本** FastTab 上，選取狀態為 **草稿** 的設定版本。
4. 請選取 **變更狀態**\>**完成**。

此設定的版本 1 的狀態從 **草稿** 更改為 **已完成**。 版本 1 無法再更改。 此版本包含已設定的資料模型，可用作其他 ER 設定的基礎。 此設定的版本 2 已建立，狀態為 **草稿**。 您可以編輯此版本以調整 **問卷** 資料模型。

![設定頁面上可編輯設定的版本。](./media/er-quick-start1-model-configuration.png)

如需 ER 設定的版本控制的相關資訊，請參閱[電子報表 (ER) 概述](general-electronic-reporting.md#component-versioning)。

> [!NOTE]
> 設定的資料模型是您對 **問卷** 業務領域的抽象表示，並且不包含與特定於 Microsoft Dynamics 365 Finance 的人工製品的關係。

## <a name="design-a-model-mapping-for-the-configured-data-model"></a><a name="DesignMapping"></a>為設定的資料模型設計模型對應

作為電子報表開發人員角色的使用者，您必須建立新的 ER 設定，其中包含 **問卷** 資料模型的模型對應組件。 因為該組件實現了 Finance 的設定資料模型，所以它是特定於 Finance 的。 您必須設定模型對應組件以指定必須用於在執行階段用應用程式資料填入設定的資料模型的應用程式對象。 若要完成此工作，您必須了解 Finance 中 **問卷** 業務領域的資料結構的實現細節。

透過完成以下[匯入新模型對應設定](#ImportModelMapping)部分中的步驟，您可以從提供的 XML 檔案中匯入所需的模型對應設定。 或者，您可以完成[建立新模型對應設定](#CreateModelMapping)部分中的步驟，從頭開始設計此模型對應。

### <a name="import-a-new-model-mapping-configuration"></a><a name="ImportModelMapping"></a>匯入新的模型對應設定

1. 下載[Questionnaires mapping.version.1.1.xml](https://download.microsoft.com/download/7/b/2/7b258e4e-4bd5-46a4-8114-27419ae4acd8/Questionnaires_mapping.version.1.1.xml)檔案，並將其儲存到本地電腦。
2. 進入 **組織管理**\>**工作區**\>**電子報表**。
3. 在 **電子報表** 工作區中，選取 **報表設定**。
4. 在動作窗格上，選取 **交換**\>**從 XML 檔案載入**。
5. 選取 **瀏覽**，然後找到並選取 **Questionnaires mapping.version.1.1.xml** 檔案。
6. 選取 **確定** 以匯入設定。

若要繼續，請跳過下一個程序，[建立新的模型對應設定](#CreateModelMapping)。

### <a name="create-a-new-model-mapping-configuration"></a><a name="CreateModelMapping"></a>建立新模型對應設定

1. 進入 **組織管理**\>**電子報表**\>**設定**。
2. 在 **設定** 頁面上，在設定樹狀結構中，選取 **問卷模型**。
3. 選取 **建立設定**。
4. 在下拉式對話方塊中，執行以下步驟：

    1. 在 **新建** 欄位中，選取 **根據資料模型問卷的模型對應**。
    2. 在 **名稱** 欄位中，輸入 **Questionnaire mapping**。
    3. 在 **資料模型定義** 欄位，選取 **根** 定義。
    4. 選取 **建立設定** 以建立設定。

#### <a name="design-a-new-model-mapping-component"></a><a name="DesignMappingComponent"></a>設計新的模型對應組件

1. 在 **設定** 頁面上，在設定樹狀結構中，選取 **問卷對應**。
2. 選取 **設計工具** 開啟對應清單。
3. 選取為 **根** 定義自動新增的 **問卷對應** 對應
4. 選取 **設計工具** 開始設定所選對應。

為 **根** 定義自動新增一個新對應。 此對應具有 **建模** 方向。 因此，此對應可用於將所需資料填入到資料模型中。

#### <a name="add-data-sources-to-access-application-tables"></a><a name="AddMmDataSource1"></a>新增資料來源以存取應用程式表

您必須設定資料來源以存取包含問卷詳情的應用程式表。

1. 在 **模型對應設計工具** 頁，在 **資料來源類型** 窗格，選取 **Dynamics 365 for Operations\\Table records**。
2. 新增將用於存取 KMCollection 表的新資料來源，其中每條記錄代表一個問卷：

    1. 在 **資料來源** 窗格中，選取 **新增根**。
    2. 在下拉式對話方塊中，在 **名稱** 欄位中，輸入 **Questionnaire**。
    3. 在 **資料表** 欄位中，輸入 **KMCollection**。
    4. 將 **要求查詢** 選項設定為 **是**。 然後，您將能夠在執行階段在系統查詢對話方塊中為此表指定[篩選](../../fin-ops/get-started/advanced-filtering-query-options.md)選項。
    5. 選取 **確定** 以新增新資料來源。

3. 在 **資料來源類型** 窗格中，選取 **Dynamics 365 for Operations\\Table records**。
4. 新增將用於存取 KMQuestion 表的新資料來源，其中每條記錄代表問卷中的一個問題：

    1. 在 **資料來源** 窗格中，選取 **新增根**。
    2. 在下拉式對話方塊中，在 **名稱** 欄位中，輸入 **Question**。
    3. 在 **資料表** 欄位中，輸入 **KMQuestion**。
    4. 選取 **確定** 以新增新資料來源。

5. 在 **資料來源類型** 窗格中，選取 **Dynamics 365 for Operations\\Table records**。
6. 新增將用於存取 KMAnswer 表的新資料來源嘗試，其中每條記錄代表對問卷中問題的單個答案：

    1. 在 **資料來源** 窗格中，選取 **新增根**。
    2. 在 **名稱** 欄位中，輸入 **Answer**。
    3. 在 **資料表** 欄位中，輸入 **KMAnswer**。
    4. 選取 **確定** 以新增新資料來源。

7. 在 **資料來源類型** 窗格中，選取 **Functions\\Calculated field**。
8. 新增一個新的導出欄位，該欄位將用於從父 KMCollection 表的每條記錄中存取 KMQuestionResultGroup 表的記錄：

    1. 在 **資料來源** 窗格中，選取 **Questionnaire**。
    2. 選取 **新增**。
    3. 在下拉式對話方塊中，在 **名稱** 欄位中，輸入 **\$ResultGroup**。
    4. 選取 **編輯公式**。
    5. 在 [ER 公式編輯器](general-electronic-reporting-formula-designer.md)的 **公式** 欄位中，輸入 **FIRSTORNULL (\@.\<Relations'.KMQuestionResultGroup)** 以使用 KMCollection 和 KMQuestionResultGroup 表之間的一對多關係[路徑](er-formula-language.md#Paths)。
    6. 選取 **儲存**，關閉公式編輯器。
    7. 選取 **確定** 以新增新的導出欄位。

9. 在 **資料來源類型** 窗格中，選取 **Functions\\Calculated field**。
10. 新增一個新的導出欄位，該欄位將用於從父 KMCollectionQuestion 表的每條記錄中存取 KMQuestion 表的問題記錄：

    1. 在 **資料來源** 窗格中，選取 **Questionnaire**。
    2. 展開包含 KMCollection 表的一對多關係的 **\<關係** 節點。
    3. 選取相關的 **KMCollectionQuestion** 表，然後選取 **新增**。
    4. 在下拉式對話方塊中，在 **名稱** 欄位中，輸入 **\$Question**。
    5. 選取 **編輯公式**。
    6. 在公式編輯器的 **公式** 欄位中，輸入 **FIRSTORNULL (FILTER (Question, Question.kmQuestionId = \@.kmQuestionId))** 以從 KMQuestion 表中回傳相應的問題記錄。
    7. 選取 **儲存**，關閉公式編輯器。
    8. 選取 **確定** 以新增新的導出欄位。

11. 在 **資料來源類型** 窗格中，選取 **Functions\\Calculated field**。
12. 新增一個新的導出欄位，該欄位將用於從父 KMQuestion 表的每條記錄中存取 KMAnswer 表的答案記錄：

    1. 在 **資料來源** 窗格，選取 **Questionnaire.\<Relations.KMCollectionQuestion.\$Question**，並選取 **新增**。
    2. 在下拉式對話方塊中，在 **名稱** 欄位中，輸入 **\$Answer**。
    3. 選取 **編輯公式**。
    4. 在公式編輯器的 **公式** 欄位中，輸入 **FILTER (Answer, Answer.kmAnswerCollectionId = \@.kmAnswerCollectionId)** 以從 KMAnswer 表中回傳相應的答案記錄。
    5. 選取 **儲存**，關閉公式編輯器。
    6. 選取 **確定** 以新增新的導出欄位。

13. 在 **資料來源類型** 窗格中，選取 **Dynamics 365 for Operations\\Table**。
14. 新增將用於存取 CompanyInfo 表的方法的新資料來源。 請注意，此表的 **find ()** 方法回傳一條記錄，該記錄表示在內容中調用此對應的現行 Finance 執行個體的公司。

    1. 在 **資料來源** 窗格中，選取 **新增根**。
    2. 在下拉式對話方塊中，在 **名稱** 欄位中，輸入 **CompanyInfo**。
    3. 在 **資料表** 欄位中，輸入 **CompanyInfo**。
    4. 選取 **確定** 以新增新資料來源。

#### <a name="add-data-sources-to-access-application-enumerations"></a><a name="AddMmDataSource2"></a>新增資料來源以存取應用程式列舉

您必須設定資料來源以存取應用程式列舉並將其值與應用程式表中 **列舉** 類型的欄位的值進行比較。 您必須使用比較結果來填入資料模型的適當欄位。

1. 在 **模型對應設計工具** 頁，在 **資料來源類型** 窗格，選取 **Dynamics 365 for Operations\\Enumeration**。
2. 新增將用於存取 **EnumAppNoYes** 列舉值的新資料來源：

    1. 在 **資料來源** 窗格中，選取 **新增根**。
    2. 在下拉式對話方塊中，在 **名稱** 欄位中，輸入 **EnumAppNoYes**。
    3. 在 **列舉** 欄位中，輸入 **NoYes**。
    4. 選取 **確定** 以新增新資料來源。

3. 在 **資料來源類型** 窗格中，選取 **Dynamics 365 for Operations\\Enumeration**。
4. 新增將用於存取 **KMCollectionQuestionMode** 列舉值的新資料來源：

    1. 在 **資料來源** 窗格中，選取 **新增根**。
    2. 在下拉式對話方塊中，在 **名稱** 欄位中，輸入 **EnumAppQuestionOrder**。
    3. 在 **列舉** 欄位中，輸入 **KMCollectionQuestionMode**。
    4. 選取 **確定** 以新增新資料來源。

#### <a name="add-er-labels-to-generate-a-report-in-a-specified-language"></a><a name="AddMmLabels"></a>新增 ER 標籤以產生指定語言的報表

您可以新增 ER 標籤來設定某些資料來源以回傳取決於模型對應調用內容中定義的語言的值。

1. 在 **模型對應設計工具** 頁，在 **資料來源** 窗格，選取 **答案**，然後選取 **編輯**。
2. 啟用 **標籤** 欄位。
3. 選取 **翻譯**。
4. 在 **文字翻譯** 對話方塊中，請按照下列步驟操作：

    1. 在 **標籤識別碼** 欄位，輸入 **PositiveAnswer**。
    2. 在 **預設語言的文字** 欄位，輸入 **Yes**。
    3. 選取 **翻譯**。
    4. 在 **標籤識別碼** 欄位，輸入 **NegativeAnswer**。
    5. 在 **預設語言的文字** 欄位，輸入 **No**。
    6. 選取 **翻譯**。

5. 關閉 **文字翻譯** 對話方塊。
6. 選取 **取消**。

![為可編輯模型對應新增 ER 標籤。](./media/er-quick-start1-adding-labels.png)

您只為預設語言輸入了 ER 標籤。 如需如何將 ER 標籤翻譯成其他語言的相關資訊，請參閱[設計多語言報表](er-design-multilingual-reports.md)。

#### <a name="add-a-data-source-to-transform-the-results-of-comparing-enumeration-values-to-a-text-value"></a><a name="AddMmDataSource3"></a>新增資料來源以將列舉值比較結果轉換為文字值

因為對於差異來源，您必須多次轉換列舉值和文字值之間的比較結果，所以最好將此邏輯設定為單個資料來源。 但是，要使此資料來源可重用，您必須將其設定為參數化資料來源。 如需相關資訊，[支援導出欄位類型的 ER 資料來源的參數化調用](er-calculated-field-type.md)。

1. 在 **模型對應設計工具** 頁，在 **資料來源類型** 窗格，選取 **General\\Empty container**。
2. 新增新的容器資料來源：

    1. 在 **資料來源** 窗格中，選取 **新增根**。
    2. 在下拉式對話方塊中，在 **名稱** 欄位中，輸入 **Helper**。
    3. 選取 **確定** 以新增新容器資料來源。

3. 在 **資料來源類型** 窗格中，選取 **Functions\\Calculated field**。
4. 新增新的資料來源：

    1. 在 **資料來源** 窗格中，選取 **協助程式**。
    2. 選取 **新增**。
    3. 在下拉式對話方塊中，在 **名稱** 欄位中，輸入 **NoYesEnumToString**。
    4. 選取 **編輯公式**。
    5. 在公式編輯器中，選取 **參數**。
    6. 按照以下步驟為設定的運算式指定參數：

        1. 選取 **新增**。
        2. 在下拉式對話方塊中，在 **名稱** 欄位中，輸入 **Argument**。
        3. 在 **類型** 欄位中，選取 **布林值** 資料類型。
        4. 選取 **確定**。

    7. 在 **公式** 欄位中，輸入 **IF (Argument = true, \@"GER\_LABEL:PositiveAnswer", \@"GER\_LABEL:NegativeAnswer")** 回傳相應 ER 標籤的文字，具體取決於執行內容的語言和指定參數的值。
    8. 選取 **儲存**，關閉公式編輯器。
    9. 選取 **確定** 以新增新資料來源。

![在 ER 模型對應設計工具中設定的模型對應。](./media/er-quick-start1-added-data-sources.png)

#### <a name="bind-data-sources-to-data-model-fields"></a><a name="AddMmBindings1"></a>將資料來源繫結到資料模型欄位

您必須將設定的資料來源繫結到資料模型的欄位，以指定資料模型在執行階段將如何填入應用程式資料。

1. 在 **模型對應設計工具** 頁，在 **資料模型** 窗格，選取 **CompanyName**。
2. 在 **資料來源** 窗格，展開 **CompanyInfo**，然後按照以下步驟操作：

    1. 展開表示 CompanyInfo 表的 **find ()** 方法的 **CompanyInfo.find ()** 節點。
    2. 選取 **CompanyInfo.find ().Name**。
    3. 選取 **繫結** 以填入執行階段在內容中調用設定的模型對應的公司名稱。

3. 在 **資料模型** 窗格中，選取 **Questionnaire**。
4. 在 **資料來源** 窗格，選取 **Questionnaire**，並選取 **繫結** 以填入問卷記錄。
5. 在 **資料模型** 窗格，展開 **Questionnaire**，然後按照以下步驟操作：

    1. 在 **資料模型** 窗格中，選取 **Active**。
    2. 在 **資料模型** 窗格中，選取 **Edit**。
    3. 在 **公式** 欄位，輸入 **Helper.NoYesEnumToString (\@ .Active = EnumAppNoYes.Yes)** 填入列舉值之間比較的文字相關和語言相關的結果。

6. 繼續以相同的方式將資料來源繫結到資料模型欄位，直到達到以下結果。

    | 欄位路徑                                              | 資料類型   | 動作 | 繫結運算式 |
    |---------------------------------------------------------|-------------|--------|--------------------|
    | CompanyName                                             | 字串      | 繫結   | CompanyInfo.'find ()'.Name |
    | 問卷                                           | 記錄清單 | 繫結   | 問卷 |
    | Questionnaire\\Active                                   | 字串      | 編輯   | Helper.NoYesEnumToString (\@.active = EnumAppNoYes.Yes) |
    | Questionnaire\\Code                                     | 字串      | 繫結   | \@.kmCollectionId |
    | Questionnaire\\Description                              | 字串      | 繫結   | \@.Description |
    | Questionnaire\\QuestionnaireType                        | 字串      | 繫結   | \@.'&gt;Relations'.kmCollectionTypeId.Description |
    | Questionnaire\\QuestionOrder                            | 字串      | 編輯   | CASE (\@.questionMode,<br>EnumAppQuestionOrder.Conditional, "Conditional",<br>EnumAppQuestionOrder.Random, "Random (percentage in questionnaire)",<br>EnumAppQuestionOrder.RandomGroup, "Random (percentage in result groups)",<br>EnumAppQuestionOrder.Sequence, "Sequential",<br>"") |
    | Questionnaire\\ResultsGroup                             | 記錄      |        | |
    | Questionnaire\\ResultsGroup\\Code                       | 字串      | 繫結   | \@.'\$ResultGroup'.kmQuestionResultGroupId |
    | Questionnaire\\ResultsGroup\\Description                | 字串      | 繫結   | \@.'\$ResultGroup'.description |
    | Questionnaire\\ResultsGroup\\MaxNumberOfPoints          | 真實        | 繫結   | \@.'\$ResultGroup'.maxPoint |
    | Questionnaire\\Question                                 | 記錄清單 | 繫結   | \@.'&lt;Relations'.KMCollectionQuestion |
    | Questionnaire\\Question\\CollectionSequenceNumber       | 整數     | 繫結   | \@.answerCollectionSequenceNumber |
    | Questionnaire\\Question\\Id                             | 字串      | 繫結   | \@.kmQuestionId |
    | Questionnaire\\Question\\MustBeCompleted                | 字串      | 編輯   | Helper.NoYesEnumToString (\@.mandatory = EnumAppNoYes.Yes) |
    | Questionnaire\\Question\\PrimaryQuestion                | 字串      | 繫結   | \@.parentQuestionId |
    | Questionnaire\\Question\\SequenceNumber                 | 整數     | 繫結   | \@.SequenceNumber |
    | Questionnaire\\Question\\Text                           | 字串      | 繫結   | \@.'\$Question'.text |
    | Questionnaire\\Question\\Answer                         | 記錄清單 | 繫結   | \@.'\$Question'.'\$Answer' |
    | Questionnaire\\Question\\Answer\\CorrectAnswer          | 字串      | 編輯   | Helper.NoYesEnumToString (\@.correctAnswer = EnumAppNoYes.Yes) |
    | Questionnaire\\Question\\Answer\\Points                 | 真實        | 繫結   | \@.point |
    | Questionnaire\\Question\\Answer\\SequenceNumber         | 整數     | 繫結   | \@.sequenceNumber |
    | Questionnaire\\Question\\Answer\\Text                   | 字串      | 繫結   | \@.text |

    下圖顯示了 **模型對應設計工具** 頁面上已設定模型對應的最終狀態。

    ![ER 模型對應設計工具中完全設定的模型對應。](./media/er-quick-start1-mapping2.png)

7. 儲存您的變更。
8. 關上 **模型對應設計工具** 頁面。

#### <a name="complete-the-design-of-the-model-mapping"></a><a name="CompleteModelMapping"></a>完成模型對應的設計

1. 進入 **組織管理**\>**電子報表**\>**設定**。
2. 在 **設定** 頁面上，在設定樹狀結構中，選取 **問卷對應**。
3. 在 **版本** FastTab 上，選取狀態為 **草稿** 的設定版本。
4. 請選取 **變更狀態**\>**完成**。

此設定的版本 1.1 的狀態從 **草稿** 更改為 **已完成**。 版本 1.1 無法再更改。 此版本包含已設定的模型對應，可用作其他 ER 設定的基礎。 此設定的版本 1.2 已建立，狀態為 **草稿**。 您可以編輯此版本以調整 **問卷對應** 設定。

![設定頁面上可編輯 ER 設定的版本。](./media/er-quick-start1-mapping-configuration.png)

> [!NOTE]
> 設定的模型對應是您的 Finance 對代表 **問卷** 業務領域的抽象資料模型的具體實現。

## <a name="design-a-template-for-a-custom-report"></a><a name="DesignReportTemplate"></a>為自訂報表設計範本

ER 架構使用預定義的範本以 Microsoft Office 格式 (Excel 活頁簿或 Word 文件) 產生報表。 在產生所需的報表時，會根據設定的資料流程用所需的資料填入範本。 因此，您必須先為您的自訂報表設計一個範本。 此範本必須設計為 Excel 活頁簿，其結構代表自訂報表的配置。 您必須使用所需資料命名您計畫填入的每個 Excel 項目。

1. 下載[Questionnaires report template.xlsx](https://download.microsoft.com/download/3/8/2/382c3cf0-87bb-473f-b7bb-3015b4facb74/Questionnaires_report_template.xlsx)檔案，並將其儲存到本機電腦。
2. 在 Excel 中打開檔案，然後查看活頁簿的結構。

如下圖所示，下載的範本旨在列印指定的問卷，其中包含問卷的問題和適當的答案。

![用於列印指定問卷的 Excel 範本。](./media/er-quick-start1-template-layout.png)

Excel 名稱已新增到此範本中以填入問卷詳情。 您可以使用名稱管理員查看 Excel 名稱。

![使用名稱管理員查看提供的 Excel 範本中的 Excel 名稱。](./media/er-quick-start1-template-names.png)

報表標籤已新增為英文的固定文字。 您可以使用 ER 格式[標籤](#AddMmLabels)將報表標籤替換為新的 Excel 名稱，這些名稱使用與語言相關的文字填入標籤，就像在設定的模型對應中對語言相關的運算式所做的那樣。 在這種情況下，必須以可編輯的 ER 格式新增 ER 標籤。

如下圖所示，已指定自訂報表標題以啟用 Excel 進行分頁。

![提供的 Excel 範本中的自訂報表標題。](./media/er-quick-start1-template-header.png)

## <a name="design-a-format"></a><a name="DesignFormat"></a>設計格式

作為電子報表函數顧問角色的使用者，您必須建立新的 ER 設定，其中包含格式組件。 您必須設定格式組件以指定如何在執行階段使用所需資料填入報表範本。

透過完成[匯入設計好的格式設定](#FormatImport)部分中的步驟，您可以從提供的 XML 檔案中匯入所需的格式。 或者，您可以完成[建立新的格式設定](#FormatCreate)部分中的步驟，從頭開始設計此格式。

### <a name="import-a-designed-format-configuration"></a><a name="FormatImport"></a>匯入設計的格式設定

1. 下載[Questionnaires format.version.1.1.xml](https://download.microsoft.com/download/1/b/a/1ba39ec2-257a-44d8-972f-25bf7d18fb41/Questionnaires_format.version.1.1.xml)檔案，並將其儲存到本地電腦。
2. 進入 **組織管理**\>**工作區**\>**電子報表**。
3. 在 **電子報表** 工作區中，選取 **報表設定**。
4. 在動作窗格上，選取 **交換**\>**從 XML 檔案載入**。
5. 選取 **瀏覽**，然後找到並選取 **Questionnaires format.version.1.1.xml** 檔案。
6. 選取 **確定** 以匯入設定。

若要繼續，請跳過下一個程序，[建立新的格式設定](#FormatCreate)。

### <a name="create-a-new-format-configuration"></a><a name="FormatCreate"></a>建立新的格式設定
 
1. 進入 **組織管理**\>**電子報表**\>**設定**。
2. 在 **設定** 頁面上，在設定樹狀結構中，選取 **問卷模型**。
3. 選取 **建立設定**。
4. 在下拉式對話方塊中，執行以下步驟：

    1. 在 **新建** 欄位中，選取 **根據資料模型問卷的格式**。
    2. 在 **名稱** 欄位中，輸入 **Questionnaire report**。
    3. 在 **資料模型版本** 欄位，選取 **1**。

        > [!NOTE]
        > - 如果您選取特定版本的基礎資料模型，則相應版本的資料模型的結構將以建立的格式作為 **模型** 資料來源的結構呈現給您。
        > - 您可以將此欄位留空。 在這種情況下，資料模型 **草稿** 版本的結構將以建立的格式作為 **模型** 資料來源的結構呈現給您。 然後，您可以調整模型並立即以您的格式查看這些調整。 當您同時設定資料模型、模型對應和格式時，這種方法可能會提高 ER 解決方案設計的效率。
        > - 如果您選取基礎資料模型的特定版本，您可以稍後在開始編輯格式時切換到使用 **草稿** 版本。

    4. 在 **資料模型定義** 欄位，選取 **根** 定義。

5. 選取 **建立設定** 以建立設定。

#### <a name="import-a-report-template"></a><a name="ImportReportTemplate"></a>匯入報表的範本

1. 在 **設定** 頁面上，在設定樹狀結構中，選取 **問卷報表**。
2. 選取 **設計工具** 開始設定自訂格式。
3. 在 **格式設計工具** 頁面上，在動作窗格上，選取 **匯入**\>**從 Excel 匯入**。
4. 在對話方塊中，執行以下步驟：

    1. 選取 **新增範本**。
    2. 尋找並選取本機儲存的 **Questionnaires report template.xslx** 檔案，然後選取 **開啟**。
    3. 選取 **確定** 以匯入範本。

    ![匯入報表範本。](./media/er-quick-start1-template-import.png)

**Excel\\File** 格式元素作為根元素自動新增到可編輯格式中。 此外，會自動為匯入範本的每個識別的 Excel 名稱新增 **Excel\\Range** 格式元素或 **Excel\\Cell** 格式元素。 具有巢狀 **字串** 元素的 **Excel\\Header** 格式會自動新增以反映匯入範本的標題設定。

![包含在 ER Operation 設計工具中自動新增的元素的格式結構。](./media/er-quick-start1-template-import2.png)

#### <a name="configure-a-format"></a><a name="ConfigureFormat"></a>設定格式

1. 在 **公式設計工具** 頁面上，在左窗格的格式結構樹狀結構中，選取 **Excel** 根元素。
2. 在頁面右側的 **格式** 索引標籤上，在 **名稱** 欄位中，輸入 <a name="AddFormatRootElement"></a>**報表**。
3. 在 **語言偏好** 欄位中，選取 **使用者偏好** 以使用者的偏好語言執行報表。
4. 在 **文化偏好** 欄位中，選取 **使用者偏好** 以使用者的偏好文化執行報表。

    如需如何為 ER 流程指定語言和文化背景的相關資訊，請參閱[設計多語言報表](er-design-multilingual-reports.md)。

    ![在 ER Operation 設計工具中為設計的報表設定語言和文化設定。](./media/er-quick-start1-template-format-structure1.png)

5. 在格式樹狀結構中，展開根節點，然後選取 **ResultsGroup**。
6. 在 **格式** 索引標籤，在 **複寫方向** 欄位中，選取 **無複寫**，因為您不希望單個問卷有多個結果組。

    ![在 ER Operation 設計工具中定義 Range 格式元素的複寫方向。](./media/er-quick-start1-template-format-structure2.png)

7. 選取 **儲存**。

#### <a name="define-the-data-binding-for-a-report-title"></a><a name="DefineFormatBindings"></a>定義報表標題的資料繫結

您必須為用於填入產生報表的標題的格式元素指定資料繫結。

1. 在 **格式設計工具** 頁，在右側的 **對應** 索引標籤，選取 **Report\\ReportTitle** 元素。
2. 選取 **編輯公式**。
3. 在公式編輯器中，選取 **翻譯**。
4. 在 **文字翻譯** 對話方塊中，請按照下列步驟操作：

    1. 在 **標籤識別碼** 欄位，輸入 **ReportTitle**。
    2. 在 **預設語言的文字** 欄位，輸入 **Questionnaires report**。
    3. 選取 **翻譯**，然後選取 **儲存**。
    4. 選取 **翻譯** 關閉 **文字翻譯** 對話方塊。

5. 關閉公式編輯器。

    ![設定繫結以填入產生報表的標題。](./media/er-quick-start1-add-report-title-label.png)

您可以使用此技術使現行範本的所有其他標籤與語言相關。 如需如何將單個 ER 設定的新增標籤翻譯成所有支援的語言的相關資訊，請參閱[設計多語言報表](er-design-multilingual-reports.md)。

#### <a name="review-model-data-source"></a><a name="ReviewModelDataSource"></a>查看模型資料來源

1. 在 **格式設計工具** 頁面的 **對應** 索引標籤上，選取表示此 ER 格式的基本資料模型的 <a name="ModelDSName"></a>**模型** 資料來源。
2. 選取 **編輯**。
3. 查看 **資料來源屬性** 對話方塊中的資訊。 此資料來源表示位於 **問卷模型** ER 設定中的 **問卷** 資料模型組件的版本 1。

![ER Operation 設計工具中模型資料來源的屬性。](./media/er-quick-start1-model-data-source.png)

#### <a name="bind-format-elements-to-data-source-fields"></a><a name="BindFormatElements"></a>將格式元素繫結到資料來源欄位

若要指定如何在執行階段填入範本，您必須將與適當的 Excel 名稱相關的每個格式元素繫結到此格式資料來源的單個欄位。

1. 在 **公式設計工具** 頁面上，在格式樹狀結構中，選取 **Report\\CompanyName** 格式元素。
2. 在 **對應** 索引標籤上，選取 **字串** 類型的 **model.CompanyName** 資料來源欄位。
3. 選取 **繫結** 在範本中輸入公司名稱。
4. 在格式樹狀結構中，選取 **Report\\Questionnaire** 元素。
5. 在 **對應** 索引標籤上，選取 **記錄清單** 類型的 **model.Questionnaire** 資料來源欄位。
6. 選取 **繫結**。
7. 選取 **顯示詳情** 查看格式元素的更多詳情。

    **問卷** 範圍格式元素設定為垂直複寫。 當它繫結到 **記錄清單** 類型的資料來源時，Excel 範本的相應 **問卷** 範圍會針對繫結資料來源的每條記錄重複。
 
    ![將問卷範圍格式元素繫結到 ER Operation 設計工具中的相應記錄清單資料來源。](./media/er-quick-start1-bindings1.png)

    因為 Excel 範本的 **問卷** 範圍在第 5 列到第 14 列之間定義，這些行對每個報表的調查問卷都重複。

    ![Excel 範本中將在產生的報表中為記錄清單資料來源的每條記錄重複的資料列。](./media/er-quick-start1-template-questionnaire-range.png)

8. 為其餘格式元素設定類似的繫結，如下表所述。

    > [!NOTE]
    > 在此資料表中，「資料來源路徑」欄中的資訊假定[相對路徑](relative-path-data-bindings-er-models-format.md) ER 功能已打開。

    | 格式化元素路徑                                      | 資料來源路徑 |
    |----------------------------------------------------------|------------------|
    | Excel\\ReportTitle                                       | **\@"GER\_LABEL:ReportTitle"** |
    | Excel\\CompanyName                                       | **model.CompanyName** |
    | Excel\\Questionnaire                                     | **model.Questionnaire** |
    | Excel\\Questionnaire\\Active                             | **\@.Active**, where **\@** is **model.Questionnaire** |
    | Excel\\Questionnaire\\Code                               | **\@.Code** |
    | Excel\\Questionnaire\\Description                        | **\@.Description** |
    | Excel\\Questionnaire\\QuestionnaireType                  | **\@.QuestionnaireType** |
    | Excel\\Questionnaire\\QuestionOrder                      | **\@.QuestionOrder** |
    | Excel\\Questionnaire\\ResultsGroup\\Code\_               | **\@.ResultsGroup.Code** |
    | Excel\\Questionnaire\\ResultsGroup\\Description\_        | **\@.ResultsGroup.Description** |
    | Excel\\Questionnaire\\ResultsGroup\\MaxNumberOfPoints    | **\@.ResultsGroup.MaxNumberOfPoint** |
    | Excel\\Questionnaire\\Question                           | **\@.Question** |
    | Excel\\Questionnaire\\Question\\CollectionSequenceNumber | **\@.CollectionSequenceNumber**, where **\@** is **model.Questionnaire.Question** |
    | Excel\\Questionnaire\\Question\\Id                       | **\@.Id** |
    | Excel\\Questionnaire\\Question\\MustBeCompleted          | **\@.MustBeCompleted** |
    | Excel\\Questionnaire\\Question\\PrimaryQuestion          | **\@.PrimaryQuestion** |
    | Excel\\Questionnaire\\Question\\SequenceNumber           | **\@.SequenceNumber** |
    | Excel\\Questionnaire\\Question\\Text                     | **\@.Text** |
    | Excel\\Questionnaire\\Question\\Answer                   | **\@.Answer** |
    | Excel\\Questionnaire\\Question\\Answer\\CorrectAnswer    | **\@.CorrectAnswer**, where **\@** is **model.Questionnaire.Answer** |
    | Excel\\Questionnaire\\Question\\Answer\\Points           | **\@.Points** |
    | Excel\\Questionnaire\\Question\\Answer\\Text             | **\@.Text** |

9. 完成後，選取 **儲存**。

下圖顯示了 **格式設計工具** 頁面上已設定資料繫結的最終狀態。

![在 ER Operation 設計工具中設定的資料繫結。](./media/er-quick-start1-bindings2.png)

> [!IMPORTANT]
> 指定資料來源和繫結的整個集合表示已設定格式的格式對應組件。 當您執行設定的報表產生格式時，會調用此格式對應。

### <a name="run-a-designed-format-from-er"></a><a name="RunFormatFromER"></a>從 ER 執行設計的格式

您現在可以從 **設定** 頁面執行設計的格式以進行測試。

1. 進入 **組織管理**\>**電子報表**\>**設定**。
2. 在 **設定** 頁面的設定樹狀結構中，展開 **問卷模型**，然後選取 **問卷報表**。
3. 為具有 **草稿** 狀態的格式版本選取 **設計工具**。
4. 在 **格式設計工具** 頁面上，選取 **執行**。
5. 在 **ER 參數** 對話方塊中的 **要包括的記錄** FastTab 上，設定篩選選項，以便只加入 **SBCCrsExam** 問卷。
6. 選取 **確定** 以確認篩選選項。
7. 選取 **確定** 以執行報表。
8. 查看產生的報表。

透過[預設](electronic-reporting-destinations.md#default-behavior)，產生的報表以 Excel 檔案的形式提供，您可以下載該檔案。 下圖顯示了產生的 Excel 格式報表的兩頁。

![Excel 格式的產生報表範例，第 1 頁。](./media/er-quick-start1-report1a.png)

![Excel 格式的產生報表範例，第 2 頁。](./media/er-quick-start1-report1b.png)

## <a name="tune-a-designed-format"></a><a name="TuneFormat"></a>調整設計的格式

### <a name="modify-a-format-to-change-the-name-of-a-generated-document"></a><a name="ModifyToChangeName"></a>修改格式以更改產生文件的名稱

在預設情況下，產生的文件使用現行使用者的別名命名。 透過修改格式，您可以更改此行為，以便根據您的自訂邏輯命名產生的文件。 例如，產生的文件的名稱可以基於現行工作階段日期和時間，以及報表的標題。

1. 在 **格式設計工具** 頁面，選取 **報表** 根項目。
2. 在 **對應** 索引標籤上，選取 **編輯檔案名稱**。
3. 在 **公式** 欄位，輸入 **CONCATENATE (\@"GER\_LABEL:ReportTitle", " - ", DATETIMEFORMAT (SESSIONNOW (), "yyyy-MM-dd hh-mm-ss"))**。
4. 選取 **儲存**，關閉公式編輯器。
5. 選取 **儲存**。

### <a name="modify-a-format-to-change-the-order-of-questions"></a><a name="ModifyToOrder"></a>修改格式以更改問題的順序

這些問題在產生的報表中沒有正確排序。 您可以透過修改格式來更改順序。

1. 在 **格式設計工具** 頁面，選取 **報表** 根項目。
2. 在 **對應** 索引標籤，在格式樹狀結構中，展開 **Report\\Questionnaire\\Question**。

    ![範圍類型的問題格式元素 ER Operation 設計工具。](./media/er-quick-start1-bindings3.png)

3. 在 **對應** 索引標籤上，選取 **model.Questionnaire**。
4. 選取 **新增**\>**函數\\導出欄位**，然後，在 **名稱** 欄位，輸入 **OrderedQuestions**。
5. 選取 **編輯公式**。
6. 在公式編輯器中的 **公式** 欄位中，輸入 **ORDERBY (model.Questionnaire.Question, model.Questionnaire.Question.SequenceNumber)** 按順序編號對現行問卷的問題清單進行排序。
7. 選取 **儲存**，關閉公式編輯器。
8. 選取 **確定** 完成新導出欄位的輸入。
9. 在 **對應** 索引標籤上，選取 **model.Questionnaire.OrderedQuestions**。
10. 在格式樹狀結構中，選取 **Excel\\Questionnaire\\Question**。
11. 選取 **繫結**，然後確認巢狀元素的所有繫結中現行的 **model.Questionnaire.Questions** 路徑被新的 **model.Questionnaire.OrderedQuestions** 路徑替換。
12. 選取 **儲存**。

![將 Question 格式元素繫結到 ER Operation 設計工具中設定的 OrderedQuestions 資料來源。](./media/er-quick-start1-bindings4.png)

### <a name="run-a-modified-format-from-er"></a><a name="RunFormatFromER2"></a>從 ER 執行修改的格式

您現在可以從 ER 架構執行修改後的格式以進行測試。

1. 在 **格式設計工具** 頁面上，選取 **執行**。
2. 在 **ER 參數** 對話方塊中的 **要包括的記錄** FastTab 上，設定篩選選項，以便只加入 **SBCCrsExam** 問卷。
3. 選取 **確定** 以確認篩選選項。
4. 選取 **確定** 以執行報表。
5. 查看產生的報表。

下圖顯示了產生的 Excel 格式報表，其中問題的順序正確。

![產生的 Excel 格式的報表具有正確排序的問題。](./media/er-quick-start1-report2.png)

### <a name="complete-the-format-design"></a><a name="CompleteFormat"></a>完成格式設計

1. 進入 **組織管理**\>**電子報表**\>**設定**。
2. 在 **設定** 頁面的設定樹狀結構中，展開 **問卷模型**，然後選取 **問卷報表**。
3. 在 **版本** FastTab 上，選取狀態為 **草稿** 的設定版本。
4. 請選取 **變更狀態**\>**完成**。

此設定的版本 1.1 的狀態從 **草稿** 更改為 **已完成**。 版本 1.1 無法再更改。 此版本包含設定的格式，可用於列印您的自訂報表。 此設定的版本 1.2 已建立，狀態為 **草稿**。 您可以編輯此版本以調整 **問卷** 報表的格式。

![設定頁面上的可編輯 ER 設定。](./media/er-quick-start1-format-configuration.png)

> [!NOTE]
> 設定的格式是您對 **問卷** 報表的設計，不包含與特定於 Finance 的構件的關係。

## <a name="develop-application-artefacts-to-call-the-designed-report"></a><a name="DevelopCustomCode"></a>開發應用程式構件以調用設計的報表

作為系統管理員角色的使用者，您必須開發新的邏輯，以便可以從應用程式使用者介面 (UI) 調用設定的 ER 格式來產生您的自訂報表。 目前，ER 不提供任何設定此類邏輯的功能。 因此，需要進行一些工程作業。 

若要開發新邏輯，您必須部署支援持續構建的拓撲。 如需相關資訊，請參閱[部署支援持續構建和測試自動化的拓撲](../perf-test/continuous-build-test-automation.md)。 您還必須有權存取此拓撲的開發環境。 如需可用 ER API 的相關資訊，請參閱 [ER 架構 API](er-apis-app73.md)。

### <a name="modify-source-code"></a><a name="ModifySourceCode"></a>修改原始程式碼

#### <a name="add-a-data-contract-class"></a><a name="DataContractClass"></a>新增資料合約類

將新的 **QuestionnairesErReportContract** 類新增到您的 Microsoft Visual Studio 項目中，並編寫代碼來指定應該用於執行設定的 ER 格式的資料協定。

```xpp
/// <summary>
///     This class is the data contract class for the <c>QuestionnairesErReportDP</c> class.
/// </summary>
/// <remarks>
///    This is the data contract class for the Questionnaires ER report.
/// </remarks>
[
    DataContractAttribute,
    SysOperationContractProcessingAttribute(classStr(QuestionnairesErReportUIBuilder))
    ]
    public class QuestionnairesErReportContract extends ERFormatMappingRunBaseContract implements SysOperationValidatable
{
    ERFormatMappingId formatMapping;

    /// <summary>
    ///    Validates the report parameters.
    /// </summary>
    /// <returns>
    ///    true if no errors; otherwise, false.
    /// </returns>
    public boolean validate()
    {
        boolean ret = true;
        if (!formatMapping)
        {
            ret = checkFailed(strFmt("@SYS26332", new SysDictType(extendedTypeNum(ERFormatMappingId)).label()));
        }
        return ret;
    }
    [
        DataMemberAttribute('FormatMapping'),
        SysOperationLabelAttribute(literalstr("@ElectronicReporting:FormatMapping")),
        SysOperationHelpTextAttribute(literalstr("@ElectronicReporting:FormatMapping"))
    ]
    public ERFormatMappingId parmFormatMapping(ERFormatMappingId _formatMapping = formatMapping)
    {
        formatMapping = _formatMapping;
        return formatMapping;
    }
}
```

#### <a name="add-a-ui-builder-class"></a><a name="UIBuilderClass"></a>新增 UI 建立器類

將新的 **QuestionnairesErReportUIBuilder** 類新增到您的 Visual Studio 項目中，並編寫代碼以產生一個執行階段對話方塊，該對話方塊將用於查詢必須執行的 ER 格式的格式對應 ID。 提供的代碼僅查詢包含 **資料模型** 類型的資料來源的 ER 格式，該資料模型類型透過使用 **[根](#RootDefinitionName)** 定義參考 **[問卷](#DataModeName)** 資料模型。

> [!NOTE]
> 或者，您可以使用 ER 整合點來篩選 ER 格式。 如需相關資訊，請參閱[顯示格式對應查詢的 API](er-apis-app10-0-11.md#api-to-show-a-format-mapping-lookup)。

```xpp
/// <summary>
/// The UIBuilder class for Questionnaires ER report
/// </summary>
class QuestionnairesErReportUIBuilder extends SysOperationAutomaticUIBuilder
{
    public const str ERQuestionnairesModel = 'Questionnaires';
    public const str ERQuestionnairesDataContainer = 'Root';

    /// <summary>
    /// Action after build of the dialog UI.
    /// </summary>
    public void postBuild()
    {
        DialogField formatMapping;
        super();
        formatMapping = this.bindInfo().getDialogField(this.dataContractObject(),
            methodStr(QuestionnairesErReportContract, parmFormatMapping));
        formatMapping.registerOverrideMethod(
            methodStr(FormReferenceControl, lookupReference),
            methodStr(QuestionnairesErReportUIBuilder, formatMappingLookup),
            this);
    }

    /// <summary>
    /// Performs the lookup form for format mapping.
    /// </summary>
    /// <param name="_referenceGroupControl">
    /// The control to perform lookup form.
    /// </param>
    public void formatMappingLookup(FormReferenceControl _referenceGroupControl)
    {
        ERObjectsFactory::createFormatMappingTableLookupForControlAndModel(
            _referenceGroupControl,
            ERQuestionnairesModel,
            ERQuestionnairesDataContainer).performFormLookup();
    }
}
```

#### <a name="add-a-data-provider-class"></a><a name="DataProviderClass"></a>新增資料提供者類

將新的 **QuestionnairesErReportDP** 類新增到您的 Visual Studio 項目中，並編寫代碼來引入應該用於執行設定的 ER 格式的資料提供者。 提供的代碼僅包含此資料提供者的資料合同。

```xpp
/// <summary>
/// Data provider class for Questionnaires ER report.
/// </summary>
public class QuestionnairesErReportDP
{
    QuestionnairesErReportContract contract;
    public static QuestionnairesErReportDP construct()
    {
        QuestionnairesErReportDP  dataProvider;
        dataProvider = new QuestionnairesErReportDP();
        return dataProvider;
    }
}
```

#### <a name="add-a-labels-file"></a><a name="LabelsFile"></a>新增標籤檔案

將新的 **QuestionnairesErReportLabels\_en-US** 標籤檔案新增到您的 Visual Studio 專案，並為新的 UI 資源指定以下標籤：

- 包含以下美國英文 (en-US) 文字之新選單項的 **\@QuestionnairesReport** 標籤：**問卷報表 (由 ER 提供)**
- 如果選定的 ER 格式計畫作為批次處理作業執行，則批次處理作業標題的 **\@QuestionnairesReportBatchJobDescription** 標籤

#### <a name="add-a-report-service-class"></a><a name="ServiceClass"></a>新增報表服務類

將新的 **QuestionnairesErReportService** 類新增到您的 Visual Studio 專案中，並編寫調用 ER 格式的代碼，透過格式對應 ID 標識它，並提供資料協定作為參數。

```xpp
using Microsoft.Dynamics365.LocalizationFramework;
/// <summary>
/// The electronic reporting service class for Questionnaires ER report
/// </summary>
class QuestionnairesErReportService extends SysOperationServiceBase
{
    public const str ERModelDataSourceName = 'model';
    public const str DefaultExportedFileName = 'Questionnaires report';
    public const str ParametersDataSourceName = 'RunTimeParameters';

    /// <summary>
    /// Generates report by using Electronic reporting framework
    /// </summary>
    /// <param name = "_contract">The Questionnaires report contract</param>
    public void generateReportByGER(QuestionnairesErReportContract _contract)
    {
        ERFormatMappingId formatMappingId;
        QuestionnairesErReportDP  dataProvider;
        dataProvider = QuestionnairesErReportDP::construct();
        formatMappingId = _contract.parmFormatMapping();
        if (formatMappingId)
        {
            try
            {
                ERIModelDefinitionParamsAction parameters = new ERModelDefinitionParamsUIActionComposite()
                    .add(new ERModelDefinitionObjectParameterAction(ERModelDataSourceName, ParametersDataSourceName, _contract, true));

                // Call ER to generate the report.
                ERIFormatMappingRun formatMappingRun = ERObjectsFactory::createFormatMappingRunByFormatMappingId(formatMappingId, DefaultExportedFileName);
                if (formatMappingRun.parmShowPromptDialog(true))
                {
                    formatMappingRun.withParameter(parameters);
                    formatMappingRun.withFileDestination(_contract.getFileDestination());
                    formatMappingRun.run();
                }
            }
            catch
            {
                // An error occurred while exporting data.
                error("@SYP4861341");
            }
        }
        else
        {
            // There is no data available.
            info("@SYS300117");
        }
    }
}
```

當您必須使用執行應用程式資料的 ER 格式時，您必須在格式對應中設定 **資料模型** 類型的資料來源。 此資料來源透過使用單個根定義來參考指定資料模型的特定部分。 執行 ER 格式時，它會調用此資料來源來存取為給定模型和根定義設定的適當 ER 模型對應。

您可能在源代碼中準備並作為資料協定的一部分儲存的所有資訊都可以透過使用此類型的 ER 模型對應傳遞到正在執行的 ER 格式。 在 ER 模型對應中，您必須設定參考 **[QuestionnairesErReportContract](#DataContractClass)** 類的 **物件** 類型的資料來源。 若要識別模型對應，您必須指定調用此模型對應的資料來源。 在提供的代碼中，此資料來源由具有 **[模型](#ModelDSName)** 值的 **ERModelDataSourceName** 常數指定。 若要確定使用哪個資料來源在模型對應中公開資料協定，您必須指定資料來源名稱。 在提供的代碼中，此名稱由具有 <a name="DataContractDSName"></a>**RunTimeParameters** 值的 **ParametersDataSourceName** 常數指定。

> [!NOTE]
> 在新環境中，您可能必須刷新 ER 中繼資料，以便此類類在 ER 模型對應設計工具中可用。 如需相關資訊，請參閱[設定 ER 架構](electronic-reporting-er-configure-parameters.md#frequently-asked-questions)。

#### <a name="add-a-report-controller-class"></a><a name="ControllerClass"></a>新增報表控制器類

將新的 **QuestionnairesErReportController** 類新增到您的 Visual Studio 專案中，並根據您的喜好在基於提供的 **QuestionnairesErReportUIBuilder** 類的邏輯構建的對話方塊中編寫以同步模式或批次處理模式執行 ER 格式的代碼。

```xpp
/// <summary>
/// The controller for Questionnaires ER report
/// </summary>
class QuestionnairesErReportController extends ERFormatMappingRunBaseController
{
    /// <summary>
    /// The main entrance of the controller
    /// </summary>
    /// <param name = "args">The arguments</param>
    public static void main(Args args)
    {
        QuestionnairesErReportController operation;
        operation = new QuestionnairesErReportController(
            classStr(QuestionnairesErReportService),
            methodStr(QuestionnairesErReportService, generateReportByGER),
            SysOperationExecutionMode::Synchronous);
        operation.startOperation();
    }

    /// <summary>
    /// Gets caption of the dialog.
    /// </summary>
    /// <returns>Caption of the dialog</returns>
    public ClassDescription defaultCaption()
    {
        ClassDescription batchDescription;
        batchDescription = "Questionnaires report (powered by ER)";
        return batchDescription;
    }
}
```

#### <a name="add-a-menu-item"></a><a name="MenuItem"></a>新增選單項目

將新的 **QuestionnairesErReport** 選單項新增到 Visual Studio 專案。 在 **物件** 屬性中，此選單項是指 **QuestionnairesErReportController** 類，用於指定使用者選取和執行 ER 格式的權限。 在 **標籤** 屬性中，這個選單項是指您之前建立的 **\@QuestionnairesReport** 標籤，以便在應用程式 UI 中顯示正確的文字。

#### <a name="add-a-menu-item-to-a-menu"></a><a name="Menu"></a>將選單項目新增到選單

將現有的 **KM** 選單新增到您的 Visual Studio 專案。 您必須將 **輸出** 類型的新 **QuestionnairesErReport** 項目新增到此選單。 此項目必須參考上一節中描述的 **QuestionnairesErReport** 選單項目。

#### <a name="build-a-visual-studio-project"></a><a name="BuildVSProject"></a>構建 Visual Studio 專案

構建您的專案以便讓使用者可以使用新的選單項目。

### <a name="run-a-format-from-the-application"></a><a name="RunFormatFromApp"></a>從應用程式執行格式

1. 進入 **問卷**\>**設計**\>**問卷報表 (由 ER 提供)**。

    ![選取問卷模組中的問卷報表 (由 ER 提供) 選單項以執行設定好的 ER 格式。](./media/er-quick-start1-application-menu-modified.png)

2. 在對話方塊中，在 **格式對應** 欄位，選取 **問卷報表**。
3. 選取 **確定**。
4. 在 **電子報表參數** 對話方塊中的 **要包括的記錄** FastTab 上，設定篩選選項，以便只加入 **SBCCrsExam** 問卷。
5. 選取 **確定** 以確認篩選選項。
6. 選取 **確定** 以執行報表。

    ![在電子報表對話方塊中指定選取標準。](./media/er-quick-start1-report-run-dialog-page.png)

7. 查看產生的報表。

## <a name="tune-a-designed-er-solution"></a><a name="TuneSolution"></a>調整設計的 ER 解決方案

您可以修改設定的 ER 解決方案，使其使用您開發的資料提供者類來存取正在執行的 ER 格式的詳情，並在產生的報表中輸入此 ER 格式的名稱。

### <a name="modify-a-model-mapping"></a><a name="ModifyModelMapping"></a>修改模型對應

#### <a name="add-data-sources-to-access-a-data-contract-object"></a><a name="AddDataSource1"></a>新增資料來源以存取資料合約物件

1. 進入 **組織管理**\>**電子報表**\>**設定**。
2. 在 **設定** 頁面的設定樹狀結構中，展開 **問卷模型**，然後選取 **問卷對應**。
3. 選取 **設計工具** 以開啟 **模型到資料來源的對應** 頁面。
4. 選取 **設計工具** 在模型對應設計工具中打開選定的對應。
5. 在 **模型對應設計工具** 頁，在 **資料來源類型** 窗格，選取 **Dynamics 365 for Operations\\Object**。
6. 在 **資料來源** 窗格中，選取 **新增根**。
7. 在對話方塊的 **名稱** 欄位中，輸入 **[RunTimeParameters](#DataContractDSName)**，如 **QuestionnairesErReportService** 類的原始程式碼中所定義。
8. 在 **類別** 欄位，輸入之前編碼的 **[QuestionnairesErReportContract](#DataContractClass)**。
9. 選取 **確定**。
10. 展開 **RunTimeParameters**。

新增的資料來源提供有關正在執行的 ER 格式對應的記錄 ID 的資訊。

![在 ER 模型對應設計工具中新增了資料來源。](./media/er-quick-start1-mapping3.png)

#### <a name="add-a-data-source-to-access-er-format-mapping-records"></a><a name="AddDataSource2"></a>新增資料來源以存取 ER 格式對應記錄

透過新增資料來源以存取 ER 格式對應記錄，繼續編輯選定的模型對應。

1. 在 **模型對應設計工具** 頁，在 **資料來源類型** 窗格，選取 **Dynamics 365 for Operations\\Table records**。
2. 在 **資料來源** 窗格中，選取 **新增根**。
3. 在下拉式對話方塊中，在 **名稱** 欄位中，輸入 **ER1**。
4. 在 **資料表** 欄位中，輸入 **ERFormatMappingTable**。
5. 選取 **確定**。

#### <a name="add-a-data-source-to-access-a-format-mapping-record-of-a-running-er-format"></a><a name="AddDataSource3"></a>新增資料來源以存取正在執行的 ER 格式的格式對應記錄

透過新增資料來源以存取正在執行的 ER 格式的格式對應記錄，繼續編輯選定的模型對應。

1. 在 **模型對應設計工具** 頁，在 **資料來源類型** 窗格，選取 **Functions\\Calculated field**。
2. 在 **資料來源** 窗格中，選取 **新增根**。
3. 在下拉式對話方塊中，在 **名稱** 欄位中，輸入 **ER2**。
4. 選取 **編輯公式**。
5. 在公式編輯器的 **公式** 欄位中，輸入 **FIRSTORNULL (FILTER (ER1, ER1.RecId = RunTimeParameters.parmFormatMapping))**。
6. 選取 **儲存**，關閉公式編輯器。
7. 選取 **確定**。

#### <a name="enter-the-name-of-the-running-er-format-in-the-data-model"></a><a name="AddBinding"></a>在資料模型中輸入正在執行的 ER 格式的名稱

繼續編輯選定的模型對應，以便在資料模型中輸入正在執行的 ER 格式的名稱。

1. 在 **模型對應設計工具** 頁面的 **資料模型** 窗格中，展開 **ExecutionContext**，然後選取 **ExecutionContext\\FormatName**。
2. 在 **資料模型** 窗格，選取 **編輯** 為所選資料模型的欄位設定資料繫結。
3. 在公式編輯器的 **公式** 欄位中，輸入 **FIRSTORNULL (ER2.'\>Relations'.Format).Name**。
4. 選取 **儲存**，關閉公式編輯器。

因為您使用了 **FormatName** 欄位，設定的模型對應現在公開了在執行期間調用此模型對應的 ER 格式的名稱。

![將資料模型欄位繫結到 ER 模型對應設計工具中新增的資料來源的方法。](./media/er-quick-start1-mapping4.png)

#### <a name="complete-the-design-of-the-model-mapping"></a><a name="CompleteModelMapping2"></a>完成模型對應的設計

1. 在 **模型對應設計工具** 頁面上，選取 **儲存**。
2. 關閉頁面。
3. 關上模型對應頁面。
4. 在 **設定** 頁面上，在設定樹狀結構中，確保仍然選取 **問卷對應** 設定。 之後，在 **版本** FastTab 上，選取狀態為 **草稿** 的設定版本。
5. 請選取 **變更狀態**\>**完成**。

此設定的版本 1.2 的狀態從 **草稿** 更改為 **已完成**。 版本 1.2 無法再更改。 此版本包含已設定的模型對應，可用作其他 ER 設定的基礎。 此設定的版本 1.3 已建立，狀態為 **草稿**。 您可以編輯此版本以調整 **問卷** 模型對應。

### <a name="modify-a-format"></a><a name="ModifyFormat"></a>修改格式

您可以修改設定的 ER 格式，使其名稱顯示在執行 ER 格式時產生的報表的頁尾中。

#### <a name="add-a-new-format-element"></a><a name="AddFormatElement"></a>新增新的格式元素

1. 進入 **組織管理**\>**電子報表**\>**設定**。
2. 在 **設定** 頁面的設定樹狀結構中，展開 **問卷模型**，然後選取 **問卷報表**。
3. 選取 **設計工具**。
4. 在 **格式設計工具** 頁面，選取 **報表** 根項目。
5. 選取 **新增** 為選定的 **報表** 根項目新增新的巢狀格式元素。
6. 選取 **Excel\\Footer**。
7. 在 **名稱** 欄位中，輸入 **Footer**。
8. 選取 **Report\Footer**，然後選取 **新增**。
9. 選取 **Text\\String**。

#### <a name="bind-the-added-format-element"></a><a name="BindAddedFormatElement"></a>繫結新增的格式元素

1. 在 **格式設計工具** 頁的 **對應** 索引標籤上，在格式樹狀結構中，針對有效的 **Footer\\String** 元素，選取 **編輯公式**。
2. 在公式編輯器的 **公式** 欄位中，輸入 **CONCATENATE ("\&C\&10", FORMAT ("Generated by'\%1' ER solution", model.ExecutionContext.FormatName))**。
3. 選取 **儲存**，關閉公式編輯器。
4. 選取 **儲存**。

現在已修改設定的格式，以便使用 **Footer\\String** 元素將其名稱輸入到產生的報表的頁尾中。

![將頁尾格式元素新增到 ER Operation 設計工具中的設定格式。](./media/er-quick-start1-template-format-structure3.png)

#### <a name="complete-the-format-design"></a><a name="CompleteFormat2"></a>完成格式設計

1. 關上 **格式設計工具** 頁面。
2. 在 **設定** 頁面上，在設定樹狀結構中，確保仍然選取 **問卷報表** 設定。 之後，在 **版本** FastTab 上，選取狀態為 **草稿** 的設定版本。
3. 請選取 **變更狀態**\>**完成**。

此設定的版本 1.2 的狀態從 **草稿** 更改為 **已完成**。 版本 1.2 無法再更改。 此版本包含已設定的格式，可用作其他 ER 設定的基礎。 此設定的版本 1.3 已建立，狀態為 **草稿**。 您可以編輯此版本以調整 **問卷** 報表。

### <a name="run-a-format-from-the-application"></a><a name="RunFormatFromApp2"></a>從應用程式執行格式

1. 進入 **問卷**\>**設計**\>**問卷報表 (由 ER 提供)**。
2. 在對話方塊中，在 **格式對應** 欄位，選取 **問卷報表**。
3. 選取 **確定**。
4. 在 **ER 參數** 對話方塊中的 **要包括的記錄** FastTab 上，設定篩選選項，以便只加入 **SBCCrsExam** 問卷。
5. 選取 **確定** 以確認篩選選項。
6. 選取 **確定** 以執行報表。
7. 查看產生的 Excel 格式的報表。

請注意，產生的報表的頁尾包含用於產生它的 ER 格式的名稱。

![已產生的 Excel 格式的報表。](./media/er-quick-start1-report4.png)

### <a name="run-a-format-from-er"></a><a name="RunFormatFromER3"></a>從 ER 執行格式

1. 進入 **組織管理**\>**電子報表**\>**設定**。
2. 在 **設定** 頁面的設定樹狀結構中，展開 **問卷模型**，然後選取 **問卷報表**。
3. 在動作窗格中，選取 **執行**。
4. 在 **電子報表參數** 對話方塊中的 **要包括的記錄** FastTab 上，設定篩選選項，以便只加入 **SBCCrsExam** 問卷。
5. 選取 **確定** 以確認篩選選項。
6. 選取 **確定** 以執行報表。
7. 查看產生的 Excel 格式的報表。

注意，產生的報表的頁尾不包含用於產生報表的 ER 格式的名稱，因為資料協定物件在被從 ER 中執行的 ER 格式調用時沒有傳遞給執行的模型對應。

### <a name="configure-a-format-destination-for-on-screen-preview"></a><a name="ConfigureDestination"></a>為螢幕上預覽設定格式目的地

1. 進入 **組織管理**\>**電子報表**\>**電子報表目的地**。
2. 在 **電子報表目的地** 頁面，為設定的 **問卷報表** ER 格式新增目的地記錄。
3. 在 **檔案目的地** FastTab 上，為 [已新增](#AddFormatRootElement)為已設定 **問卷報表** ER 格式的根元素 **報表** 格式組件設定 **螢幕**[目的地](er-destination-type-screen.md)。
4. 在 **PDF 轉換設定** FastTab 上，設定目的地以將報表轉換為使用 **橫向** 頁面方向的 [PDF 格式](electronic-reporting-destinations.md#OutputConversionToPDF)。

![在電子報表目的地頁面上為 ER 格式設定自訂螢幕目的地。](./media/er-quick-start1-destination.png)

### <a name="run-a-format-from-the-application-to-preview-it-as-a-pdf-document"></a><a name="RunFormatFromApp3"></a>從應用程式執行格式以將其預覽為 PDF 文件

1. 進入 **問卷**\>**設計**\>**問卷報表 (由 ER 提供)**。
2. 在對話方塊中，在 **格式對應** 欄位，選取 **問卷報表**。
3. 選取 **確定**。
4. 在 **電子報表參數** 對話方塊中的 **要包括的記錄** FastTab 上，設定篩選選項，以便只加入 **SBCCrsExam** 問卷。
5. 選取 **確定** 以確認篩選選項。

    在 **目的地** FastTab 上，請注意 **輸出** 欄位已設定為 **螢幕**。 如果要更改設定的目的地，請選取 **變更**。

    ![ER 報表執行階段對話方塊，您可以在其中更改設定的目的地。](./media/er-quick-start1-run-settings.png)

6. 選取 **確定** 以執行報表。
7. 查看產生的 PDF 格式的報表。

    ![以 PDF 格式在螢幕上預覽產生的報表。](./media/er-quick-start1-preview-PDF.png)

## <a name="additional-resources"></a><a name="References"></a>其他資源

- [電子報表概觀](general-electronic-reporting.md)
- [電子報表公式語言](er-formula-language.md)
- [設計多語言報表](er-design-multilingual-reports.md)
- [ER 架構 API](er-apis-app73.md)
- [CASE 函數](er-functions-logical-case.md)
- [CONCATENATE 函數](er-functions-text-concatenate.md)
- [DATETIMEFORMAT 函數](er-functions-datetime-datetimeformat.md)
- [FILTER 函數](er-functions-list-filter.md)
- [FIRSTORNULL 函數](er-functions-list-firstornull.md)
- [FORMAT 函數](er-functions-text-format.md)
- [IF 函數](er-functions-logical-if.md)
- [ORDERBY 函數](er-functions-list-orderby.md)
- [SESSIONNOW 函數](er-functions-datetime-sessionnow.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
