---
title: 使用功能設定
description: 本主題說明如何設定電子發票功能。
author: dkalyuzh
ms.date: 12/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkalyuzh
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 41ffc9c7009291a55392e50c5e490d3288d122bc
ms.sourcegitcommit: ffdb6794746ffe5461f9dcf34ed8e64976d22d2d
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/02/2022
ms.locfileid: "8451680"
---
# <a name="work-with-feature-setups"></a>使用功能設定

[!include [banner](../includes/banner.md)]

若要設定電子文件的生成和其他處理步驟 (例如，對文件進行數字簽名、將其提交到政府 Web 服務並接收回應或儲存)，請設定電子文件的處理管道、適用性規則和變量發票功能。

設定資訊組合在 *功能設定* 概念，並且可以建立、刪除、調整。 對於電子發票功能的完整版本，還可以查看資訊。

您可以根據需要建立任意數量的功能設定項目，以定義生成、處理和接收電子文件的不同場景。 儘管這些功能設定項具有獨立的處理動作和執行條件，但它們是作為單個電子發票功能的一部分建立的，並繼承其生命週期和部署過程。

## <a name="add-a-feature-setup"></a>新增功能設定

1. 登入您的 Regulatory Configuration Service (RCS) 帳戶。
2. 在 **全球化功能** 工作區的 **功能** 部分中，選擇 **電子發票** 圖格。
3. 在 **電子發票功能** 頁面上，選擇狀態為 **草稿** 的電子發票功能版本。
4. 在 **設定** 索引標籤上，選取 **新增**。
5. 在 **建立功能設定** 下拉式對話方塊的 **新增** 欄位群組中，選擇以下選項之一：
 
    - **自訂設定** – 根據設定類型，建立具有空通道、空處理管道列表、適用性規則的空部分和一組預設變量的新功能設定。
    - **從功能設定** – 在目前電子發票功能範圍內建立另一個功能設定的副本。

6. 如果您選擇了 **自訂設定** 在最後一步的選項中，輸入功能設定項的名稱和描述，然後，在 **設定類型** 欄位組，請選擇以下選項之一：

    - **處理管道** – 選擇此選項以生成和處理出站電子文件。 對於這種設定類型，系統會建立一個空的處理管道列表、一個適用性規則的空部分和一組預設變量。 您將無法使用入站電子文檔的管道。
    - **資料通道** - 選擇此選項可設定從定義的通道之一接收入站電子文檔並將其直接傳遞到 Microsoft Dynamics 365 Finance 或 Dynamics 365 Supply Chain Management 的流程，無需執行其他動作。 對於這種設定類型，系統會為數據通道建立預定義的參數列表、適用性規則的空白部分和一組預設變量。 您將無法在處理管道中新增任何動作。
    - **資料管道和處理管道** - 此設定類型類似於 **資料通道** 設定類型。 但是，在將入站電子文檔傳遞到 Finance 或 Supply Chain Management 之前，您可以在處理管道中設定其他動作。

7. 如果您選擇了 **數據通道** 或 **數據通道和處理管道** 最後一步中的選項，在 **選擇數據通道** 欄位，您必須選擇要整合的通道。
8. 選取 **建立**。

建立功能設定後，您可以選擇 **編輯** 進行設定。

## <a name="edit-a-feature-setup"></a>編輯功能設定

根據功能設定的類型，您可以配置生成出站電子文件並將其提交到外部管道，或接收入站文檔並將其傳遞到您的 Finance 或 Supply Chain Management 應用程式的過程。

### <a name="data-channel"></a>資料管道

一種 *數據通道* 獲取電子檔案，然後對其進行處理或直接將其傳遞給 Finance 或 Supply Chain Management 。 此選項不適用於 **處理管道** 類型的功能設定。

若要設定數據通道，請輸入通道的名稱。 然後根據所選通道類型定義參數。 數據通道標識符必須是指專門為識別數據通道而建立的變量。 這將能作為 Finance 或 Supply Chain Management 中的參考。

在 **附件篩選器** 索引標籤中，您應該定義一組篩選器以從通道中獲取特定文件。 如果您希望文件具有不同的檔案副檔名，或者如果文件必須根據文件名進行不同的處理，您可以建立多行。 以下是主要參數：

- **姓名** – 輸入系統在處理過程中將引用的檔案名稱。 在 Finance 和 Supply Chain Management 應用程式中，您將能夠看到提交日誌中的檔案。
- **篩選** – 定義篩選器以選擇檔案。
- **選用** – 如果清除此核取方塊，則需要該檔案。 在這種情況下，如果通道不包含與篩選器對應的檔案，系統將顯示錯誤訊息。 此參數適用於電子郵件。

如果通道是郵箱，並且入站電子郵件包含多個附件，您可以配置規則來定義服務應如何處理附件。 此服務可以將每個附件視為單獨的電子發票，也可以將一個附件視為主發票，將所有其他附件視為附加。

### <a name="processing-pipeline"></a>處理管線

一種 *處理管道* 是一組 *動作* 依次執行，直到成功完成。 您可以使用處理管道來設定生成電子檔案和執行其他步驟的流程 (例如，對文件進行數字簽名、將提交到外部 Web 服務並解析回應，以及接收和處理入站文件)。

動作列表是預定義的。 您可以使用 **新的** 和 **刪除** 按鈕，來指定在邏輯上定義提交或接收文件所需流程的動作組合。

動作的順序很重要。 您可以使用 **向上** 和 **向下** 按鈕。

每個動作都有一組可以設定或調整的參數。 具體的參數集取決於動作的類型。

- **動作** - 請選取動作類型。
- **動作名稱** – 輸入動作名稱。 此名稱將出現在提交紀錄以及 Finance 和 Supply Chain Management 應用程式的訊息中。
- **描述** – 提供相關流程中動作目標的更多詳細資訊。
- **啟用重試** – 如果選中此核取方塊，您可以在 **重試動作** 欄位並設定附加參數 **重試參數** 索引標籤。

    如果無法運行特定動作，重試功能可讓您配置服務的行為。 例如，如果您嘗試連接的外部 Web 服務沒有響應，您可以指定係統應重新嘗試連接的次數、間隔時間以及處理管道中的動作。

- **匯出結果** – 您可以選中此核取方塊 *一個* 處理管道中的動作。 動作在 Finance 或 Supply Chain Management 應用程式中生成的電子檔案，可以從 **電子檔案提交紀錄** 頁匯出。

### <a name="applicability-rules"></a>適用性規則

*適用性規則* 是可設定的條款，為透過電子發票功能集執行電子發票功能提供內文。
從 Finance 或 Supply Chain Management 提交到電子發票的商業文件不帶有顯式引用，該引用使電子發票功能集能夠叫用特定電子發票功能版本和特定功能設定項來處理提交。 但是，當商業文件設定正確時，它包含使電子發票能夠確定必須選擇和運行哪個電子發票功能版本和處理管道所需的元素。

適用性規則使電子發票服務能夠找到必須用於處理提交的確切電子發票功能。 為了找到正確的特徵，**內文** 提交的商業文檔中的欄位與適用性規則中的條款匹配。

您可以通過以下方式使用適用性規則：

- 選擇 **新的**，將新子句新增到一組適用性規則中。
- 選擇 **刪除**，刪除一個子句。
- 選擇幾條記錄，然後使用 **團體** 或 **取消組合** 按鈕以建立項目或邏輯語句的組合。 例如，選擇要分組的行，然後選擇 **群組子句**。 對子句進行分組時，會在網格中新增一個資料行。 此列指定分組子句的邏輯運算子。 目前支援下列類型的運算子：

    - Equal
    - Not equal
    - 大於/小於
    - 大於等於/小於等於
    - Contains
    - 開始於

    > [!NOTE]
    > 取消組合子句時，始終從最裡面的分組級別開始。

### <a name="variables"></a>變數

*變數* 在設定處理管道和動作之間的資料流程時為您提供更大的靈活性。 您可以在某些動作參數中引用變數來臨時儲存資料或電子檔案。 一些變數會用於在 Finance 或 Supply Chain Management 應用程式和電子發票服務之間傳遞數據。

系統預設建立一些變數。 例如，**BusinessDocumentDataModel** 變數包含 JavaScript 對象表示法 (JSON) 結構中的商業數據，該結構在提交過程中來自連接的應用程式的叫用。

變數具備以下類型：

- **持續**–用於儲存用於處理管道動作的臨時資料容器。
- **來自客戶端** – 執行提交過程時從 Dynamics 365 客戶端獲取變數的內容。
- **送至客戶端** – 執行提交程序時，Dynamics 365 客戶端可以匯入該變數的內容。
- **資料類型** – 選擇儲存在變數中的資訊資料類型。

### <a name="parameters"></a>參數

**禁用商業資料縮減** 選項用於優化在電子檔案提交期間，來自 Finance 或 Supply Chain Management 應用程式的商業資料有效負載的結構。 最佳化有助於減少進入電子發票服務的資料，以便進一步轉換為所需的電子檔案。 預設值為 **否**。

- **是的** –  Finance 或 Supply Chain Management 將發送在 **電子報告** 模組中定義的 **發票模型** 或 **財務模型** (適用於巴西) 結構的 JSON 檔案。 無論最終的電子檔案結構如何，模型的所有元素都填充了應用程式端的商業資料。 模型通常包含比目標文件結構所需的更多商業資料，並且在應用程式中生成這些資料可能需要更多時間。 數值 **是的** 因為在極少數情況下，您需要在一個電子發票功能和功能設定中生成不同的輸出檔案時需要此選項。 數值 **是的** 在對場景、電子檔案的結構和商業資料的完整性進行故障排除時非常有用。
- **否** –  Finance 或 Supply Chain Management 將在沒有任何商務資料的情況下首次叫用該服務。 此叫用的目標是取得相關電子報告 (ER) 設定的資訊，該設定將用於處理管道中的電子檔案轉換。 此資訊會返回給應用程式，應用程式使用它來確定應包含在 JSON 文件中的商業資料子集 **發票模型** 或 **財政模型** (巴西)結構。 此選項的值 **否** 有助於減少應用程式提交給服務的商務資料量，因為應用程式只能提交成功生成電子檔案所需的商業資料。

### <a name="validate-a-feature-setup"></a>驗證功能設定

您可以執行驗證來檢查整個設定的一致性。 例如，如果某個動作的強制參數留空，驗證會檢測到這種不一致，並且您會收到一條警告訊息。

- 在 **功能版本設定** 頁面，在動作窗格上，選擇 **證實**。

## <a name="delete-a-feature-setup"></a>刪除功能設定

1. 在 **電子發票功能** 頁面上，選擇狀態為 **草稿** 的電子發票功能版本。
2. 在 **設定** 索引標籤上，選取 **刪除**。
3. 在出現的訊息方塊中，選擇 **是的** 以確認您要刪除的功能設定。