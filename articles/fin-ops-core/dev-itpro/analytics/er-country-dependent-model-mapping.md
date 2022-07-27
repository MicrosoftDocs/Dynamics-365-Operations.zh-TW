---
title: 設定依賴於 ER 模型對應的國家內容
description: 本主題說明如何設定 ER 模型對應，以便它們依賴於控制其用途之法律實體的國家/地區內容。
author: NickSelin
ms.date: 11/11/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-01-01
ms.dyn365.ops.version: Release 8.1.2
ms.openlocfilehash: 5b26c605bd64b8d8e5a90f4389261e8e56825111
ms.sourcegitcommit: 25b3dd639e41d040c2714f56deadaa0906e4b493
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/06/2021
ms.locfileid: "8460416"
---
# <a name="configure-country-context-dependent-er-model-mappings"></a>設定依賴於 ER 模型對應的國家內容

[!include[banner](../includes/banner.md)]

您可以設定電子報表 (ER) 模型對應，以便它們實現常用 ER 資料模型，但僅供 Dynamics 365 Finance 使用。 本主題說明如何為 ER 資料模型設計多個 ER 模型對應，以便控制其用途，透過從具有不同國家/地區內容的公司執行的相應 ER 格式。

## <a name="prerequisites"></a>先決條件

若要完成本主題中的範例，您必須具有以下存取權限：

- 以下其中一個角色的 Finance 存取權限：
    - 電子報表開發人員
    - 電子報表函數
    - 系統管理員

- 存取已為與 Finance 相同的租用戶提供的以下其中一個角色的 Regulatory Configuration Services (RCS) 執行個體：
    - 電子報表開發人員
    - 電子報表函數
    - 系統管理員

本主題中的某些步驟需要執行 ER 格式。 在某些情況下，ER 格式的執行會受到您現行登入的公司所在國家/地區內容的影響。 如果具有所需國家/地區內容的公司在 RCS 中有提供，您可以在現行 RCS 執行個體中執行 ER 格式。 否則，您必須將使用 ER 資料模型的 ER 模型對應和 ER 格式設定的完整版本上傳到您的 Finance 執行個體，然後在該 Finance 執行個體中執行 ER 格式。 如需如何將駐留在 RCS 中的設定匯入 Finance 執行個體的相關資訊，請參閱[從 RCS 匯入設定](rcs-download-configurations.md)。

## <a name="single-model-mapping-case"></a>單模型對應案例

按照本主題[附錄 1](#appendix1)中的步驟設計所需的 ER 組件。 您現在擁有 **對應 (一般)** 模型對應設定，其中包含供 **進入點 1** 定義使用的模型對應。

![ER 設定頁面，學習對應設定的格式。](./media/RCS-Context-specific-mapping-Tree.PNG)

### <a name="run-the-configured-format"></a>執行設定的格式

1.  在 **設定頁面** 上，在 **版本** FastTab，選取 **執行**。
2.  選取 **確定**。

請注意，網路瀏覽器提供下載由執行的 ER 格式產生的文字檔。 因為這種格式被設定為使用 **進入點 1** 定義，並且現行只有單模型對應可用於包含此定義對應的基本模型，執行的 ER 格式將 **對應 (一般)** 設定的 **對應 (一般)** 模型對應用作資料來源。 因此，下載的文件包含 **常用函數 1** 文字。

## <a name="multiple-shared-model-mappings-case"></a>多個共用模型對應案例

按照本主題[附錄 2](#appendix2)中的步驟設計所需的 ER 組件。 您現在擁有 **對應 (一般)** 和 **對應 (一般) 自訂** 模型對應設定，每個都包含供 **進入點 1** 定義使用的模型對應。

![ER 設定頁面，對應一般自訂設定。](./media/RCS-Context-specific-mapping-TreeCustom.PNG)

### <a name="run-the-configured-format"></a>執行設定的格式

1.  在 **設定** 頁面，在設定樹狀結構中，選取 **學習對應的格式**。
2.  在 **版本** FastTab 上，選取 **執行**。
3.  選取 **確定**。

請注意，所選 ER 格式的執行不成功。 一條錯誤訊息通知您存在多個 **學習對應的模型** 模型的模型對應，以及 **對應 (一般)** 和 **對應 (一般) 自訂** 模型對應設定中的 **進入點 1** 定義。 該訊息還建議您選取其中一種設定作為預設設定。

![帶有錯誤訊息的 ER 設定頁面。](./media/RCS-Context-specific-mapping-FormatRunCustomFailed.PNG)

### <a name="define-a-default-mapping-configuration"></a>定義預設對應設定

按照以下步驟定義 **對應 (一般) 自訂** 模型對應設定作為預設設定，以便其對應可以用作資料來源 **學習對應的格式** ER 格式。

1.  在 **設定** 頁面，在設定樹狀結構中，選取 **對應 (一般) 自訂**。
2.  根據需要，選取 **編輯** 使現行頁面準備好進行編輯。
3.  將 **模型對應的預設值** 選項設定為 **是**。
4.  選取 **儲存**。

![ER 設定頁面，將模型對應滑桿的預設設定為是。](./media/RCS-Context-specific-mapping-MappingsCustomDefault.PNG)

### <a name="run-the-configured-format"></a>執行設定的格式

1.  在 **設定** 頁面，在設定樹狀結構中，選取 **學習對應的格式**。
2.  在 **版本** FastTab 上，選取 **執行**。
3.  選擇 **確定**。

請注意，所選 ER 格式執行成功。 網路瀏覽器提供下載由執行的 ER 格式產生的文字檔。 因為此格式被設定為使用 **輸入資料 1** 定義，並且 **對應 (一般) 自訂** 模型對應設定被選為預設設定，所以執行的 ER 格式使用 **對應 (一般) 自訂** 設定的 **對應 (一般) 複製** 模型對應作為資料來源。 因此，下載的文件包含 **常用函數 1 自訂** 文字。

> [!NOTE]
> 如果您更改現行登入的公司並再次執行此 ER 格式，您將在產生的檔案中獲得相同的內容，因為預設的 ER 模型對應設定不包含任何與公司相關的限制。

## <a name="multiple-mixed-model-mappings-case"></a>多個混合模型對應案例

按照本主題[附錄 3](#appendix3)中的步驟設計所需的 ER 組件。 您現在擁有 **對應 (一般)**、**對應 (一般) 自訂**，以及包含供 **進入點 1** 定義使用的 **對應 (FR) 模型對應** 設定。

請注意，已設定好 **對應 (FR)** 模型對應設定的版本 1，使其僅適用於在具有法國國家/地區內容的金融公司中執行的 **學習對應的模型** 模型。

![ER 設定頁面，模型對應 (FR) 設定。](./media/RCS-Context-specific-mapping-TreeFR.PNG)

### <a name="run-the-configured-format"></a>執行設定的格式

1.  將公司更改為 **FRSI**。
2.  在 **設定** 頁面，在設定樹狀結構中，選取 **學習對應的格式**。
3.  在 **版本** FastTab 上，選取 **執行**。
4.  選取 **確定**。

請注意，所選 ER 格式執行成功。 網路瀏覽器提供下載由執行的 ER 格式產生的文字檔。 因為此格式被設定為使用 **輸入資料 1** 定義，並且 **對應 (一般) 自訂** 模型對應設定被選為預設設定，所以執行的 ER 格式使用 **對應 (一般) 自訂** 設定的 **對應 (一般) 複製** 模型對應作為資料來源。 因此，下載的文件包含 **常用函數 1 自訂** 文字。

### <a name="define-the-france-specific-mapping-configuration-as-the-default-configuration"></a>將法國特定的對應設定定義為預設設定

按照以下步驟定義自訂 **對應 (FR)** 模型對應設定為預設設定。 請注意，由於此對應是法國專用，它將被視為所有在 **ISO 國家/地區代碼** 欄位中指定了 **FR** 國家代碼的模型對應設定之間的預設對應。

1.  在 **設定** 頁面上，在設定樹狀結構中，選取 **對應 (FR)**。
2.  根據需要，選取 **編輯** 使現行頁面準備好進行編輯。
3.  將 **模型對應的預設值** 選項設定為 **是**。
4.  選取 **儲存**。

![ER 設定頁面，對應 (FR) 設定，將模型對應滑桿的預設設定為是。](./media/RCS-Context-specific-mapping-TreeFRDefault.PNG)

### <a name="run-the-configured-format"></a>執行設定的格式

1.  在 **設定** 頁面，在設定樹狀結構中，選取 **學習對應的格式**。
2.  在 **版本** FastTab 上，選取 **執行**。
3.  選取 **確定**。

請注意，所選 ER 格式執行成功。 網路瀏覽器提供下載由執行的 ER 格式產生的文字檔。 因為此格式被設定為使用 **輸入資料 1** 定義，並且 **對應 (FR)** 模型對應設定被選為預設設定，所以執行的 ER 格式使用 **對應 (FR)** 設定的 **對應 (FR)** 模型對應作為資料來源。 因此，下載的文件包含 **FR 函數 1** 文字。

> [!NOTE]
> 如果您更改現行登入的公司並再次執行此 ER 格式，則輸出將取決於所選公司的國家/地區內容。

## <a name="other-model-mapping-cases"></a>其他模型對應案例

如您所見，為執行 ER 格式選取模型對應的工作方式如下：

- 指定 ER 格式使用的模型對應定義 (在本主題的範例中 **進入點 1**)。
- 所有包含具有指定定義的對應，並滿足設定的任何國家/地區內容限制的對應設定，都有可能被用來執行 ER 格式 (本主題範例中的 **對應 (一般)**、**對應 (一般) 自訂** 和 **對應 (FR)**)。
- 任何具有國家/地區內容限制的預設模型對應都具有最高的優先選取順序 (在本主題範例中的 **對應 (FR)**)。
- 任何不具有國家/地區內容限制的預設模型對應都具有最高的次級選取順序 (在本主題範例中的 **對應 (一般) 自訂**)。
- 任何具有國家/地區內容限制的模型對應比沒有國家/地區內容限制的模型對應具有更高的優先選取順序。

下表提供了針對所有可能情況的模型對應，模型對應選取結果的相關資訊：

- 第 1 欄表示第一個模型對應是否沒有國家/地區內容限制 (例如，共享 **對應 (一般)** 對應)，如果是，是否為了它將 **模型對應的預設值** 選項設定為 **是**。
- 第 2 欄表示第二個模型對應是否沒有國家/地區內容限制 (例如，共享 **對應 (一般) 自訂** 對應)，如果是，是否為了它將 **模型對應的預設值** 選項設定為 **是**。
- 第 3 欄表示第一個模型對應是否有國家/地區 A 內容限制 (例如，法國特定 **對應 (FR)** 對應)，如果是，是否為了它將 **模型對應的預設值** 選項設定為 **是**。
- 第 4 欄表示第二個模型對應是否有國家/地區 A 內容限制，如果是，是否為了它將 **模型對應的預設值** 選項設定為 **是**。
- 第 5 欄顯示了模型對應選取的結果，用於在具有國家/地區 A 內容的公司的控制下執行 ER 格式。
- 第 6 欄顯示了模型對應選取的結果，用於在具有國家/地區 B 內容的公司的控制下執行 ER 格式。

在表中，加號 (+) 表示模型對應設定存在於 Microsoft Azure 服務的現行執行個體中，該服務用於執行 ER 格式 ( Finance 或 RCS)。

| 案例 | 沒有國家/地區內容 (MM1) 的模型對應 1 | 沒有國家/地區內容 (MM2) 的模型對應 2 | 有國家/地區 A 內容 (MM1A) 的模型對應 1 | 有國家/地區 A 內容 (MM2A) 的模型對應 2 | 在具有國家/地區 A 內容的公司的控制下執行 | 在具有國家/地區 B 內容的公司的控制下執行 |
|---------|---------|---------|---------|---------|---------------------------|----------------------------|
|         |     1   |     2   |    3    |    4    |           5               |            6               |
|     1   |         |         |         |         | 錯誤 (缺少對應)   | 錯誤 (缺少對應)    |
|     2   |     +   |         |         |         | MM1                       | MM1                        |
|     3   |     +   |     +   |         |         | 錯誤 (多個對應) | 錯誤 (多個對應)  |
|     4   |     +   |         |    +    |         | MM1A                      | MM1                        |
|     5   |     +   |         |    +    |    +    | 錯誤 (多個對應) | MM1                        |
|     6   |     +   | 預設 |    +    |    +    | MM2                       | MM2                        |
|     7   |     +   |         | 預設 |         | MM1A                      | MM1                        |
|     8   |     +   |         | 預設 |    +    | MM1A                      | MM1                        |
|     9   |     +   |         | 預設 | 預設 | 錯誤 (多個對應) | MM1                        |
|    10   | 預設 |         |         |         | MM1                       | MM1                        |
|    11   | 預設 |    +    |         |         | MM1                       | MM1                        |
|    12   | 預設 |         |    +    |         | MM1                       | MM1                        |
|    13   | 預設 | 預設 |         |         | 錯誤 (多個對應) | 錯誤 (多個對應)  |
|    14   | 預設 |         | 預設 |         | MM1A                      | MM1                        |
|    15   | 預設 |         | 預設 | 預設 | MM1A                      | MM2A                       |
|    16   |         |         |    +    |    +    | MM1A                      | MM2A                       |
|    17   |         |         | 預設 | 預設 | MM1A                      | MM2A                       |

## <a name="learn-what-mapping-was-used-in-the-execution-of-an-er-format"></a>了解在執行 ER 格式時使用了什麼對應

### <a name="configure-er-user-parameters"></a>設定 ER 使用者參數

1.  在 **設定** 頁面上，在動作窗格上，在 **設定** 索引標籤上，選取 **使用者參數**。
2.  將 **在偵錯模式下執行** 選項設定為 **是**。
4.  選取 **確定**。

### <a name="run-the-configured-format"></a>執行設定的格式

1.  在 **設定** 頁面，在設定樹狀結構中，選取 **學習對應的格式**。
2.  在 **版本** FastTab 上，選取 **執行**。
3.  選取 **確定**。

### <a name="review-the-er-debug-log"></a>查看 ER 偵錯記錄

1.  在瀏覽窗格中，進入 **模組\>組織管理\>電子報表\>設定偵錯記錄**。
2.  選取 **重新載入此頁面** 按鈕。

![ER 執行記錄頁面。](./media/RCS-Context-specific-mapping-DebugLog.PNG)

請注意，已將新記錄新增到 ER 偵錯記錄中，用於執行 ER 格式。 由於此記錄的 **等級** 欄位被設定為 **資訊**，因此該記錄是資訊性的。 因為格式組件欄位被設定為 **對應設定**，該記錄通知您在執行 **學習對應的格式** ER 格式時使用的模型對應 (在 **設定名稱** 欄位中選取)。 **產生的文字** 欄位的內容通知您，駐留在 **對應 (FR)** 設定中的 **對應 (FR)** 對應組件已被用於執行此報告。

## <a name="appendix-1"></a><a name="appendix1"></a>附錄 1

### <a name="configure-a-sample-data-model"></a>設定樣本資料模型

登入到您的 RCS 執行個體。

在此範例中，您將為樣本公司 Litware, Inc 建立設定。若要完成這些步驟，您必須先在 RCS 中完成[建立設定提供者並將其標記為有效](tasks/er-configuration-provider-mark-it-active-2016-11.md)程序中的步驟。

#### <a name="create-an-er-data-model-configuration"></a>建立 ER 資料模型設定

1.  在預設儀表板上，選取 **電子報表**。
2.  選取 **報告設定** 圖格。
3.  在 **設定** 頁面上，選取 **建立設定**。
4.  在下拉式對話方塊中，在 **名稱** 欄位中，輸入 **Model to learn mappings**。
5.  選取 **建立設定**。
6.  選取 **設定組件** FastTab。

請注意，此 ER 設定的草稿版本 1 已準備好進行編輯。 此版本包含資料模型組件。

#### <a name="design-a-sample-data-model"></a>設計樣本資料模型

1.  在 **設定頁面** 上，選取 **設計工具**。
2.  選取 **新建**。
3.  在下拉式對話方塊中，在 **名稱** 欄位中，輸入 **Entry point 1**。
4.  選取 **新增**。
5.  選取 **新建**。
6.  在下拉式對話方塊中，在 **名稱** 欄位中，輸入 **Functionality description**。
7.  選取 **新增**。
8.  選取 **新建**。
9.  在下拉式對話方塊中，在 **新節點** 欄位群組中，選取 **模型根**。
10. 在 **名稱** 欄位中，輸入 **Entry point 2**。
11. 選取 **進入點 2**。
12. 選取 **新增**。
13. 選取 **新建**。
14. 在下拉式對話方塊中，在 **名稱** 欄位中，輸入 **Functionality description**。
15. 選取 **新增**。

    ![ER 資料模型設計工具頁面。](./media/RCS-Context-specific-mapping-Model.PNG)

16. 選取 **儲存**。
17. 關閉頁面。

#### <a name="complete-the-modified-version-of-the-model-configuration"></a>完成模型設定的修改版本

1.  在 **設定** 頁面上，在 **版本** FastTab 上，選取 **更改狀態**。

    > 將設計模型設定的狀態從 **草稿** 更改到 **已完成**，以便它可以用於設計所需的模型對應和格式。

2.  選取 **完成**。
3.  選擇 **確定**。

請注意，您建立的設定儲存為已完成的版本 1。

### <a name="configure-a-sample-model-mapping"></a>設定樣本模型對應

#### <a name="create-an-er-model-mapping-configuration"></a>建立 ER 模型對應設定

1.  在 **設定** 頁面上，選取 **建立設定**。
2.  在下拉式對話方塊中，在 **新建** 欄位群組，選取 **根據資料模型的模型對應，學習對應的模型**。
3.  在 **名稱** 欄位中，輸入 **Mapping (General)**。
4.  在 **資料模型定義** 欄位，選取 **資料輸入點 1**。
5.  選取 **建立設定**。

請注意，此 ER 設定的草稿版本 1 已準備好進行編輯。 此版本包含模型對應組件。

#### <a name="design-a-sample-model-mapping"></a>設計樣本模型對應

1.  在 **設定** 頁面上，選取 **設計工具**。

    請注意，**模擬** 方向類型的模型對應已自動新增到此 **資料輸入點 1** 定義的組件。
    
2.  選取 **設計工具** 開始編輯新增的模型對應。
3.  在 **資料模型** 區段，選取 **編輯**。
4.  在 **公式** 欄位中，輸入 **"Generic functionality 1"**。
5.  選取 **儲存**。
6.  關上 **公式設計工具** 頁面。

    ![ER 模型對應設計工具頁面，進入點 1 定義。](./media/RCS-Context-specific-mapping-Mapping1.PNG)

7.  選取 **儲存**。
8.  關上 **模型對應設計工具** 頁面。
9.  選取 **新建**。
10. 在 **定義** 欄位中，選取 **資料輸入點 2**。
11. 在 **名稱** 欄位中，輸入 **Mapping (General) 2**。
12. 選取 **設計工具**。
13. 在 **資料模型** 區段，選取 **編輯**。
14. 在 **公式** 欄位中，輸入 **"Generic functionality 2"**。
15. 選取 **儲存**。
16. 關上 **公式設計工具** 頁面。

    ![ER 模型對應設計工具頁面，進入點 2 定義。](./media/RCS-Context-specific-mapping-Mapping2.PNG)

17. 選取 **儲存**。
18. 關上 **模型對應設計工具** 頁面。

    ![ER 模型對應頁面加上進入點定義。](./media/RCS-Context-specific-mapping-Mappings.PNG)

19. 關上 **模型對應** 頁面。

#### <a name="complete-the-modified-version-of-the-model-mapping-configuration"></a>完成模型對應設定的修改版本

1.  在 **設定頁面** 上，在 **版本** FastTab 上，選取 **更改狀態**。

    > 將設計模型對應設定的狀態從 **草稿** 更改到 **已完成**，以便它可以由 ER 格式使用。

2.  選取 **完成**。
3.  選擇 **確定**。

請注意，建立的設定儲存為已完成的版本 1。

### <a name="configure-a-sample-format"></a>設定樣本格式

#### <a name="create-an-er-format-configuration"></a>建立 ER 格式設定

1.  在 **設定** 頁面上，在設定樹狀結構中，選取 **學習對應的模型**。
2.  選取 **建立設定**。
3.  在下拉式對話方塊中，在 **新建** 欄位群組，選取 **根據資料模型模擬學習對應的格式**。
4.  在 **名稱** 欄位中，輸入 **Format to learn mappings**。
5.  在 **資料模型定義** 欄位，選取 **資料輸入點 1**。
6.  選取 **建立設定**。

請注意，此 ER 設定的草稿版本 1 已準備好進行編輯。 此版本包含格式組件。

#### <a name="design-a-sample-format"></a>設計樣本格式

1.  在 **設定** 頁面上，選取 **設計工具**。
2.  選取 **新增根**。
3.  在 **文字** 群組中，選取 **字串** 項目。
4.  選擇 **確定**。

#### <a name="bind-format-elements-to-a-data-source"></a>將格式元素綁定到資料來源

1.  在 **格式設計工具** 頁面上，在 **對應** 索引標籤上，展開模型資料來源。
2.  選取 **函數描述** 欄位。
3.  選取 **綁定**。

    ![ER 格式設計工具頁面。](./media/RCS-Context-specific-mapping-Format.PNG)

4.  選取 **儲存**。
5.  關閉頁面。

## <a name="appendix-2"></a><a name="appendix2"></a>附錄 2

### <a name="configure-a-sample-model-mapping-for-general-customization"></a>為一般自訂設定樣本模型對應

您可能想要自訂設定提供者 (合作夥伴) 提供給您的模型對應，然後將自訂版本用作 ER 格式的資料來源。 在這種情況下，您必須建立自訂 ER 模型對應設定才能對現有模型對應進行所需的更改。 本附錄中的程序使用 **對應 (一般)** 模型對應為例。

#### <a name="create-an-er-model-mapping-configuration"></a>建立 ER 模型對應設定

1.  在 **設定** 頁面上，在設定樹狀結構中，選取 **對應 (一般)**。
2.  選取 **建立設定**。
3.  在下拉式對話方塊中，在 **新建** 欄位組，選取 **名稱衍生：對應 (一般)，Litware, Inc.**。
4.  在 **名稱** 欄位中，輸入 **Mapping (General) custom**。
5.  選取 **建立設定**。

請注意，此 ER 設定的草稿版本 1 已準備好進行編輯。

#### <a name="design-a-sample-model-mapping"></a>設計樣本模型對應

1.  在 **設定** 頁面上，選取 **設計工具**。

    > 請注意，基本設定的模型對應已自動複製到此設定。

2.  選取 **對應 (一般) 複製** 對應。
3.  選取 **設計工具**。
4.  在 **資料模型** 區段，選取 **編輯**。
5.  在 **公式** 欄位中，輸入 **"Generic functionality 1 custom"**。
6.  選取 **儲存**。
7.  關閉頁面。

    ![ER 模型對應設計工具頁面，常用函數 1 自訂公式。](./media/RCS-Context-specific-mapping-Mapping1Custom.PNG)

8.  選取 **儲存**。
9.  關閉頁面。
10. 選取 **對應 (一般) 2 複製** 對應。
11. 選取 **設計工具**。
12. 在 **資料模型** 區段，選取 **編輯**。
13. 在 **公式** 欄位中，輸入 **"Generic functionality 2 custom"**。
14. 選取 **儲存**。
15. 關閉頁面。

    ![ER 模型對應設計工具頁面，常用函數 2 自訂公式。](./media/RCS-Context-specific-mapping-Mapping2Custom.PNG)

16. 選取 **儲存**。
17. 關閉頁面。

    ![用於對應 (一般) 複製對應的 ER 模型到資料來源對應頁面。](./media/RCS-Context-specific-mapping-MappingsCustom.PNG)

18. 關閉頁面。

#### <a name="complete-the-modified-version-of-the-model-mapping-configuration"></a>完成模型對應設定的修改版本

1.  在 **設定** 頁面上，在 **版本** FastTab 上，選取 **更改狀態**。

    > 將設計模型對應設定的狀態從 **草稿** 更改到 **已完成**，以便它可以由 ER 格式使用。

2.  選取 **完成**。
3.  選擇 **確定**。

請注意，建立的設定儲存為已完成的版本 1。

## <a name="appendix-3"></a><a name="appendix3"></a>附錄 3

### <a name="configure-a-sample-model-mapping-for-countryregion-specific-customization"></a>為國家/地區特定自訂設定樣本模型對應

對於某些 ER 格式，可能存在特定於國家/地區的資料準備要求。 在這種情況下，您可以管理單獨的 ER 模型對應設定，並將這些特定於國家/地區要求的實施與一般實施隔離開來。 本附錄中的程序使用 **學習對應的格式** ER 格式和特定於法國的要求為例。

#### <a name="create-an-er-model-mapping-configuration"></a>建立 ER 模型對應設定

首先，建立新的 ER 模型對應設定來實現特定於國家/地區的要求。 使用您的自訂 ER 模型對應設定作為基礎。

1.  在 **設定** 頁面，在設定樹狀結構中，選取 **對應 (一般) 自訂**。
2.  選取 **建立設定**。
3.  在下拉式對話方塊中，在 **新建** 欄位組，選取 **名稱衍生：對應 (一般) 自訂，Litware, Inc.**。
4.  在 **名稱** 欄位中，輸入 **Mapping (FR)**。
5.  選取 **建立設定**。

請注意，此 ER 設定的草稿版本 1 已準備好進行編輯。

#### <a name="design-a-sample-model-mapping"></a>設計樣本模型對應

1.  在 **設定** 頁面上，選取 **設計工具**。

    > 請注意，基本設定的模型對應已自動複製到此設定。

2.  選取 **對應 (一般) 複製** 對應。
3.  將它重新命名為 **對應 (FR)**。
4.  選取 **設計工具**。
5.  在 **資料模型** 區段，選取 **編輯**。
6.  在 **公式** 欄位中，輸入 **"FR functionality 1"**。
7.  選取 **儲存**。
8.  關閉頁面。

    ![ER 模型對應設計工具頁面，FR 函數 1 自訂公式。](./media/RCS-Context-specific-mapping-Mapping1FR.PNG)

9.  選取 **儲存**。
10. 關閉頁面。
11. 選取 **對應 (一般) 2 複製** 對應。
12. 將它重新命名為 **對應 (FR) 2**。
13. 選取 **設計工具**。
14. 在 **資料模型** 區段，選取 **編輯**。
15. 在 **公式** 欄位中，輸入 **"FR functionality 2"**。
16. 選取 **儲存**。
17. 關閉頁面。

    ![ER 模型對應設計工具頁面，FR 函數 2 自訂公式。](./media/RCS-Context-specific-mapping-Mapping2FR.PNG)

18. 選取 **儲存**。
19. 關閉頁面。

    ![ER 模型到資料來源對應頁面。](./media/RCS-Context-specific-mapping-MappingsFR.PNG)

20. 關閉頁面。

#### <a name="specify-countryregion-context-restrictions-for-use"></a>指定使用的國家/地區內容限制

1.  在 **設定** 頁面上，在 **ISO 國家/地區代碼** FastTab 上，選取 **新建**。
2.  在 **ISO** 欄位中，選取 **FR**。
3.  選取 **儲存**。

請注意，您必須登入到 Finance 中的特定公司才能執行 ER 格式。 因此，該公司可以被認為是控制 ER 格式執行和選取基本 ER 資料模型的正確 ER 模型對應的一方。 透過新增 **FR** 國碼 (地區碼)，您指定此模型對應僅當基礎資料模型的 ER 格式在具有法國國家/地區內容的公司的控制下執行時才可供選擇。

您可以為單個版本的 ER 模型對應設定新增多個國家/地區代碼。 這樣，駐留在該模型對應設定中的模型對應可用於在具有不同國家/地區內容的公司的控制下執行的 ER 格式。

請注意，國家/地區代碼清單是為每個版本的 ER 模型對應設定指定的，並且可能因版本而異。

#### <a name="complete-the-modified-version-of-the-model-mapping-configuration"></a>完成模型對應設定的修改版本

1.  在 **設定** 頁面上，在 **版本** FastTab 上，選取 **更改狀態**。

    > 將設計模型對應設定的狀態從 **草稿** 更改到 **已完成**，以便它可以由 ER 格式使用。

2.  選取 **完成**。
3.  選擇 **確定**。

請注意，建立的設定儲存為已完成的版本 1。

## <a name="additional-resources"></a>其他資源

[電子報表 (ER) 概觀](general-electronic-reporting.md)

[在單獨的 ER 設定中管理 ER 模型對應](./tasks/er-manage-model-mapping-configurations-july-2017.md)

[套用國家/地區內容](../lcs-solutions/apply-country-context.md)

## <a name="frequently-asked-questions"></a>常用問題

#### <a name="i-configured-two-shared-er-model-mapping-configurations-in-rcs-and-marked-one-of-them-as-the-default-model-mapping-configuration-i-successfully-ran-an-er-format-that-was-created-for-the-same-base-er-data-model-configuration-to-test-model-mappings-i-then-imported-the-whole-er-solution-er-data-model-two-er-model-mapping-configurations-and-er-format-configuration-into-finance-why-do-i-receive-an-error-message-when-i-try-to-run-the-same-er-format-in-finance"></a>我在 RCS 中設定了兩個共享的 ER 模型對應設定，並將其中一個標記為預設模型對應設定。 我成功執行了為相同的基本 ER 資料模型設定建立的 ER 格式，以測試模型對應。 然後，我將整個 ER 解決方案 (ER 資料模型、兩個 ER 模型對應設定和 ER 格式設定) 匯入到 Finance 中。 當我嘗試在 Finance 中執行相同的 ER 格式時，為什麼會收到錯誤訊息？
預設模型對應設定是環境專用。 它在 RCS 中設定，但未匯出到 Finance。 若要成功執行此 ER 格式，您還必須將其中一個 ER 模型對應設定標記為 Finance 中的預設模型對應設定。

#### <a name="i-configured-one-model-mapping-as-a-shared-model-mapping-and-completed-the-draft-version-of-it-i-then-added-a-new-model-mapping-configuration-for-same-data-model-and-configured-it-as-french-specific-why-is-the-shared-model-mapping-selected-when-i-run-an-er-format-even-though-this-er-format-uses-the-correct-root-definition-and-execution-is-done-under-the-control-of-the-company-that-has-french-countryregion-context"></a>我將一個模型對應設定為共享模型對應並完成了它的草稿版本。 然後，我為相同的資料模型新增了新的模型對應設定，並將其設定為法語專用。 為什麼在我執行 ER 格式時選取共享模型對應，即使此 ER 格式使用正確的根定義並且執行是在具有法國國家/地區內容的公司的控制下完成的？
確保共享模型對應設定為標記為預設模型對應設定。 否則，在對應選取時將具有更高的優先順序。 還要確保在 ER 格式執行期間選取對應時考慮法語特定的模型對應設定。 只有滿足以下條件之一，才能選取ER 模型對應設定：
- 至少一個版本的 ER 模型對應設定具有 **已完成** 或 **共享** 狀態。 在這種情況下，具有最高版本編號的版本將用於執行 ER 格式。
- ER 模型對應設定的 **執行草稿** 選項已打開。 在這種情況下，具有 **草稿** 狀態的版本將用於執行 ER 格式。
> 當 **執行設定** ER 使用者參數打開時，每個 ER 模型對應設定的 **執行草稿** 選項在 **設定** 頁面上提供。


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
