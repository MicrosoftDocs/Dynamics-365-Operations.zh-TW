---
title: 電子報表進階公式編輯器
description: 本主題介紹如何使用進階公式編輯器在電子報表 (ER) 模型對應和格式組件中設定運算式。
author: NickSelin
ms.date: 06/17/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERExpressionDesignerFormula
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-04-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 58d7a936f94e1cd453c904ef6404e0db65083c54235c8420b9cfa561bcde1584
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460307"
---
# <a name="electronic-reporting-advanced-formula-editor"></a>電子報表進階公式編輯器

[!include [banner](../includes/banner.md)]

除了[電子報表](general-electronic-reporting.md)[公式編輯器](general-electronic-reporting-formula-designer.md)之外，您還可以使用進階電子報表公式編輯器來改進設定電子報表 (ER) 運算式的體驗。 進階編輯器基於瀏覽器並由[摩納哥編輯器](https://microsoft.github.io/monaco-editor)提供支援。 本主題介紹了最常用的進階編輯器函數：

- [代碼自動格式化](#Autoformatting)
- [IntelliSense](#IntelliSense)
- [代碼完成](#CodeCompletion)
- [代碼導覽](#CodeNavigation)
- [代碼結構化](#CodeStructuring)
- [尋找及取代](#FindAndReplace)
- [資料貼上](#DataPasting)
- [句法著色](#SyntaxColorization)

## <a name=""></a><a name="ActivateAdvEditor">啟用進階公式編輯器</a>

完成以下步驟以開始在您的 Microsoft Dynamics 365 Finance 實體中使用進階公式編輯器。

1.  進入 **組織管理**\>**電子報表**\>**設定**。
2.  在 **設定** 頁面上，在動作窗格上，在 **設定** 索引標籤上，在 **進階設定** 組中，選取 **使用者參數**。
3.  在 **使用者參數** 對話方塊，在 **執行追蹤** 部分，將 **啟用進階公式編輯器** 參數設定為 **是**。

[![使用者參數對話方塊，啟用進階公式編輯器參數突顯。](./media/ER-AdvEditor-Activate.png)](./media/ER-AdvEditor-Activate.png)

> [!NOTE]
> 請注意，此參數是特定於使用者和公司的。

從 Microsoft Dynamics 365 Finance 10.0.19 版開始，您可以控制預設提供的 ER 公式編輯器。 完成以下步驟，為現行 Finance 實體的所有使用者和公司啟用進階公式編輯器。

1.  打開 **函數管理** 工作區。
2.  在清單中尋找並選取 **將 ER 進階公式編輯器設定為所有使用者的預設編輯器** 函數，然後選取 **立即啟用**。
3.  進入 **組織管理** > **電子報表** > **設定**。
4.  在 **設定** 頁面上，在動作窗格上，在 **設定** 索引標籤上，在 **進階設定** 組中，選取 **使用者參數**。
5.  在 **使用者參數** 對話方塊中，尋找 **停用進階公式編輯器** 參數並驗證它是否設定為 **否**。

[![使用者參數對話方塊，停用進階公式編輯器參數突顯。](./media/ER-AdvEditor-Activate2.png)](./media/ER-AdvEditor-Activate2.png)

> [!NOTE]
> **啟用進階公式編輯器** 和 **停用高級公式編輯器** 的參數值對每個使用者都是獨立的，並根據 **將 ER 進階公式編輯器設為所有使用者的預設值** 函數的狀態在 **使用者參數** 對話方塊中提供。

## <a name=""></a><a name="Autoformatting">代碼自動格式化</a>

當您編寫由多行代碼組成的複雜運算式時，新輸入行的縮進將基於前一行的縮進自動進行。 您可以透過輸入 **Tab** 或 **Shift+Tab** 來選取行並更改其縮進。

[![ER 公式編輯器 gif 顯示選取行和更改縮進。](./media/ER-AdvEditor-Indentation.gif)](./media/ER-AdvEditor-Indentation.gif)

自動格式化允許您保持整個運算式的格式正確，從而使進一步的維護更容易，並簡化對設定邏輯的理解。

## <a name=""></a><a name="IntelliSense">IntelliSense</a>

編輯器提供單詞補全函數，幫助您更快地寫入運算式並避免拼寫錯誤。 當您開始新增新文字時，編輯器會自動提供包含您輸入的字元的 ER 函數支援的函數清單。 您還可以透過輸入 **Ctrl+Space** 在設定運算式的任何位置觸發 IntelliSense。

[![ER 公式編輯器 gif 顯示觸發 IntelliSense。](./media/ER-AdvEditor-Intelisense.gif)](./media/ER-AdvEditor-Intelisense.gif)

## <a name=""></a><a name="CodeCompletion">代碼完成</a>

編輯器透過以下方式自動提供代碼完成：

- 輸入左括號時插入右括號，將光標保持在括號內。
- 輸入第一個引號時插入第二個引號，將鼠標保持在引號內。
- 在輸入第一個雙引號時插入第二個雙引號，將鼠標保持在引號內。

[![ER 公式編輯器 gif 顯示自動提供代碼完成的編輯器。](./media/ER-AdvEditor-CodeCompletion.gif)](./media/ER-AdvEditor-CodeCompletion.gif)

當您指向輸入的括號時，該對的第二個括號會自動突顯以顯示它們支援的結構。

## <a name=""></a><a name="CodeNavigation">代碼導覽</a>

您可以透過使用命令面板或內容選單輸入 **前往** 命令在運算式中找到所需的符號或行。

例如，若要跳轉到第 **8** 行，請執行以下操作：

- 按 **Ctrl+G**，輸入值 **8**，然後按 **Enter**。

  -或-

- 按 **F1**，輸入 **G**，選取 **Go to line**，輸入值 **8**，然後按 **Enter**。

[![ER 公式編輯器 gif 顯示如何使用命令面板定位運算式的各個部分。](./media/ER-AdvEditor-Goto.gif)](./media/ER-AdvEditor-Goto.gif)

## <a name=""></a><a name="CodeStructuring">代碼結構化</a>

某些函數 (例如 [IF](er-functions-logical-if.md) 或 [CASE](er-functions-logical-case.md)) 的代碼是自動結構化的。 您可以展開和折疊此代碼的任何或所有折疊區域，以減少運算式的可編輯部分，以便只關注需要您注意的代碼片段。 可以使用切換折疊/展開命令。

例如，若要折疊所有區域，請執行以下操作：

- 按 **Ctrl+K**

  -或-

- 按 **F1**，按 **FO**，選取 **全部折疊**，然後按 **Enter**

若要展開所有區域，請執行以下操作：

- 按 **Ctrl+J**

  -或-
  
- 按 **F1**，輸入 **UN**，選取 **全部展開**，然後按 **Enter**

[![ER 公式編輯器 gif 顯示正在展開的代碼。](./media/ER-AdvEditor-ToggleFold.gif)](./media/ER-AdvEditor-ToggleFold.gif)

## <a name=""></a><a name="FindAndReplace">尋找及取代</a>

若要尋找特定文字的出現，請選取運算式中的文字，然後執行以下操作：

- 按 **Ctrl+F**，然後按 **F3** 尋找所選文字的下一個符合項目，或按 **Shift+F3** 尋找上一個符合項目。

  -或-
  
- 按 **F1**，輸入 **F**，然後選取所需選項以尋找所選文字。

若要替換出現的特定文字，請選取運算式中的文字，然後執行以下操作：

- 按 **Ctrl+H**。 輸入替代文字並選取替換選項以替換所選文字或現行運算式中所有出現的該文字。

  -或-
  
- 按 **F1**，輸入 **R**，然後選取所需選項以替換所選文字。 輸入替代文字並選取替換選項以替換所選文字或現行運算式中所有出現的該文字。

若要更改特定文字的所有符合項目，請選取運算式中的文字，然後執行以下操作：

- 按 **Ctrl+F2**，然後輸入替代文字。

  -或-
  
- 按 **F1**，輸入 **C**，然後選取所需選項以更改所選文字。 輸入替代文字。

[![ER 公式編輯器 gif 顯示尋找和替換。](./media/ER-AdvEditor-Find.gif)](./media/ER-AdvEditor-Find.gif)

## <a name=""></a><a name="DataPasting">資料來源和函數貼上</a>

您可以選取 **新增資料來源**，這會將現行在 **資料來源** 左側面板上選取的資料來源貼上到現行運算式。 類似地，您可以選取 **新增函數**，這會將 **函數** 右側面板上現行選取的函數貼上到現行運算式中。 如果您使用 ER 公式編輯器，所選函數或所選資料來源將一律貼到設定運算式的末尾。 當您使用進階 ER 公式編輯器時，可以將選定的函數或選定的資料來源貼到已設定運算式的任何部分。 您將需要使用鼠標來指定要貼資料的位置。

[![ER 公式編輯器 gif 顯示新增資料來源和貼上函數。](./media/ER-AdvEditor-PasteValue.gif)](./media/ER-AdvEditor-PasteValue.gif)

## <a name=""></a><a name="SyntaxColorization">句法著色</a>

現行，使用不同的顏色來突顯運算式的以下部分：

- 雙括號中的文字，可以表示文字常數的標籤 ID。

[![ER 公式編輯器。](./media/ER-AdvEditor-SyntaxColorization.png)](./media/ER-AdvEditor-SyntaxColorization.png)

## <a name="limitations"></a>限制

以下網路瀏覽器現行支援該編輯器：

- Chrome
- Edge
- Firefox
- Opera
- Safari

## <a name="additional-resources"></a>其他資源

- [電子報表 (ER) 概觀](general-electronic-reporting.md)
- [電子報表中的公式設計工具](general-electronic-reporting-formula-designer.md)
- [摩納哥編輯器](https://microsoft.github.io/monaco-editor)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
