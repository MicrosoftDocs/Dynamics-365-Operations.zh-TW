---
title: 使用 Power BI Embedded 即可將分析新增至工作區
description: 本主題展示如何在工作區的分析索引標籤上嵌入 Power BI 報告。
author: RichdiMSFT
ms.date: 06/21/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: richdi
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: ed562dca621acea24efa3f157f695257cb919cdda577cf9ae6dd0b0c942e1b70
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460525"
---
# <a name="add-analytics-to-workspaces-by-using-power-bi-embedded"></a>使用 Power BI Embedded 即可將分析新增至工作區

[!include [banner](../includes/banner.md)]

> [!NOTE]
> Finance and Operations (7.2 版及更高版本) 支援此函數。

## <a name="introduction"></a>簡介
本主題展示如何在工作區的 **分析** 索引標籤上嵌入 Microsoft Power BI 報告。 對於此處給出的範例，我們將展開 Fleet Management 應用程式中的 **保留管理** 工作區，將分析工作區嵌入到 **分析** 索引標籤上。

## <a name="prerequisites"></a>先決條件
+ 存取執行 Platform update 8 或更高版本的開發人員環境。
+ 使用 Microsoft Power BI Desktop 建立的分析報告 (.pbix 檔案)，並且具有來自實體儲存資料庫的資料模型。

## <a name="overview"></a>概觀
無論您是展開現有的應用程式工作區還是引入自己的新工作區，您都可以使用嵌入式分析檢視來提供具有深入解析和互動式的業務資料檢視。 新增分析工作區索引標籤的流程有四個步驟。

1. 將 .pbix 檔案新增為 Dynamics 365 資源。
2. 定義分析工作區索引標籤。
3. 在工作區索引標籤上嵌入 .pbix 資源。
4. 選用：新增擴充函數以自訂檢視。

> [!NOTE]
> 如需如何建立分析報告的相關資訊，請參閱[Power BI Desktop 使用者入門](https://powerbi.microsoft.com/documentation/powerbi-desktop-getting-started/)。 此頁面是獲取深入解析的重要來源，可幫助您建立引人注目的分析報告解決方案。

## <a name="add-a-pbix-file-as-a-resource"></a>將 .pbix 檔案新增為資源
在開始之前，您必須建立或獲取您將嵌入至工作區的 Power BI 報告。 如需如何建立分析報告的相關資訊，請參閱[Power BI Desktop 使用者入門](https://powerbi.microsoft.com/documentation/powerbi-desktop-getting-started/)。

按照以下步驟將 .pbix 檔案新增為 Visual Studio 專案成品。

1. 在適當的模型中建立一個新專案。
2. 在解決方案 Explorer 中，選取專案、按按右鍵點選，然後選取 **新增**\>**新項目**。
3. 在 **新增項目** 對話方塊中，在 **營運成品** 下，選取 **資源** 範本。
4. 在 X++ 中繼資料中輸入將用於參考報告的名稱，然後點選 **新增**。

    ![新增項目對話方塊。](media/analytical-workspace-add.png)

5. 找到包含分析報告定義的 .pbix 檔案，然後點選 **開啟**。

    ![選取資源檔案對話方塊。](media/analytical-workspace-select-resource.png)

現在您已將 .pbix 檔案新增為 Dynamics 365 資源，您可以將報告嵌入工作區並使用選單項目新增直接連結。

## <a name="add-a-tab-control-to-an-application-workspace"></a>將索引標籤控制項新增到應用程式工作區
在這個範例中，我們將展開 Fleet Management 模型中的 **保留管理**，方法是將 **分析** 索引標籤新增到 **FMClarkWorkspace** 表單的定義。

下圖顯示了 **FMClarkWorkspace** 表單看起來像 Microsoft Visual Studio 的設計工具。

![更改前的 FMClarkWorkspace 表單。](media/analytical-workspace-definition-before.png)

按照以下步驟展開 **保留管理** 工作區的表單定義。

1. 打開表單設計工具以展開設計定義。
2. 在設計定義中，選取標記為 **設計 | 模式：工作區營運** 的首要元素。
3. 按右鍵點選，然後選取 **新增**\>**索引標籤** 來新增一個名為 **FormTabControl1** 的新控制項。
4. 在表單設計工具中，選取 **FormTabControl1**。
5. 按右鍵點選，然後選取 **新分頁** 來新增一個新的分頁。
6. 將分頁重新命名為有意義的名稱，例如 **工作區**。
7. 在表單設計工具中，選取 **FormTabControl1**。
8. 按右鍵點選，然後選取 **新分頁**。
9. 將分頁重新命名為有意義的名稱，例如 **分析**。
10. 在表單設計工具中，選取 **分析 (索引標籤頁)**。
11. 將 **字幕** 屬性設定為 **分析**，並將 **自動申報** 屬性設定為 **是的**。
12. 按右鍵點選控制項，然後選取 **新增**\>**群組** 以新增表單組控制項。
13. 將表單組重新命名為有意義的名稱，例如 **powerBIReportGroup**。
14. 在表單設計工具中，選取 **PanoramaBody (索引標籤)**，然後將控制項拖曳到 **工作區** 索引標籤。
15. 在設計定義中，選取標記為 **設計 | 模式：工作區營運** 的首要元素。
16. 按右鍵點選，然後選取 **移除模式**。
17. 再次按右鍵點選，然後選取 **新增模式**\>**工作區 Tab 鍵**。
18. 執行組建以驗證您的更改。

下圖顯示了套用這些更改後設計的外觀。

![更改後的 FMClarkWorkspace。](media/analytical-workspace-definition-after.png)

現在您已經新增了將用於嵌入工作區報告的表單控制項，您必須定義父代控制項的大小以使其適應配置。 在預設情況下，**篩選條件窗格** 頁面和 **索引標籤** 頁面將在報告中顯示。 但是，您可以根據報告的目標消費者更改這些控制項的可見性。

> [!NOTE]
> 對於內嵌式工作區，我們建議您使用擴充函數來隱藏 **篩選條件窗格** 和 **索引標籤** 頁面，以保持一致性。

您現在已經完成了展開申請表定義的任務。 如需如何使用擴充函數自訂的相關資訊，請參閱[透過擴充函數和疊加自訂 ](../extensibility/customization-overlayering-extensions.md)。

## <a name="add-x-business-logic-to-embed-a-viewer-control"></a>新增 X++ 業務邏輯以嵌入檢視器控制項
按照以下步驟新增業務邏輯，用於初始化嵌入在 **保留管理** 工作區的 Report Viewer 控制項。

1. 打開 **FMClerkWorkspace** 表單設計工具以展開設計定義。
2. 按 F7 存取代碼定義背後的代碼。
3. 新增以下 X++ 代碼。

    ```xpp
    [Form] 
    public class FMClerkWorkspace extends FormRun
    {
        private boolean initReportControl = true;
        protected void initAnalyticalReport()
        {
            if (!initReportControl)
            {
                return;
            }
            // Note: secure entry point into the Workspace's Analytics report
            if (Global::hasMenuItemAccess(menuItemDisplayStr(FMClerkWorkspace), MenuItemType::Display))
            {
                // initialize the PBI report control using shared helper
                PBIReportHelper::initializeReportControl('FMPBIWorkspaces', powerBIReportGroup);
            }
            initReportControl = false;
        }
        /// <summary>
        /// Initializes the form.
        /// </summary>
        public void init()
        {
            super();
            this.initAnalyticalReport();
        }
    }
    ```

4. 執行組建以驗證您的更改。

您現在已經完成了新增業務邏輯以初始化嵌入式 Report Viewer 控制項的任務。 下圖顯示了套用這些更改後工作區的外觀。

![嵌入至工作區的報告。](media/analytical-workspace-final.png)

> [!NOTE]
> 您可以使用頁面標題下方的工作區索引標籤存取現有的營運檢視。

## <a name="reference"></a>參考

### <a name="pbireporthelperinitializereportcontrol-method"></a>PBIReportHelper.initializeReportControl 方法
本節提供有關用於將 Power BI 報告 (.pbix 資源) 嵌入至表單組控制項中的輔助類別的資訊。

#### <a name="syntax"></a>句法
```xpp
public static void initializeReportControl(
    str                 _resourceName,
    FormGroupControl    _formGroupControl,
    str                 _defaultPageName = '',
    boolean             _showFilterPane = false,
    boolean             _showNavPane = false,
    List                _defaultFilters = new List(Types::Class))
```

#### <a name="parameters"></a>參數

| 姓名             | 描述                                                                                                  |
|------------------|--------------------------------------------------------------------------------------------------------------|
| resourceName     | .pbix 資源的名稱。                                                                              |
| formGroupControl | 要套用 Power BI 報告控制的表單組控制項。                                              |
| defaultPageName  | 預設頁面名稱。                                                                                       |
| showFilterPane   | 一個布林值，表示篩選條件窗格是否應顯示 (**True**) 或隱藏 (**False**)。     |
| showNavPane      | 一個布林值，表示瀏覽窗格是否應顯示 (**True**) 或隱藏 (**False**)。 |
| defaultFilters   | Power BI 報告的預設篩選條件。                                                                 |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]