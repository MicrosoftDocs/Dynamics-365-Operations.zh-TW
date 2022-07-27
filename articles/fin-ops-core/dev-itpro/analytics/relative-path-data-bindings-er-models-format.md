---
title: 在 ER 模型和格式的資料繫結中使用相對路徑
description: 電子報表工具可讓您定義電子格式結構，然後描述應如何填入這些結構。
author: NickSelin
ms.date: 07/03/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERModelMappingDesigner, EROperationDesigner, ERExpressionDesignerFormula
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: af3a646e24976d50f83d8564e3006fc2c50d8e2a
ms.sourcegitcommit: 8bcb9c13eccb14e61c39ca6578d135b64090fad2
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/17/2022
ms.locfileid: "8460326"
---
# <a name="use-a-relative-path-in-data-bindings-of-er-models-and-formats"></a>在 ER 模型和格式的資料繫結中使用相對路徑

[!include[banner](../includes/banner.md)]

電子報表 (ER) 工具允許使用者定義電子格式結構，然後描述應如何使用應用程式中存在的資料和演算法填入這些結構。 如需相關資訊，請參閱[建立電子報表 (ER) 設定](electronic-reporting-configuration.md)。 若要指定用於擷取財務和營運資料並使用它產生電子文件的資料流程，您需要執行以下動作：

- 將設定的資料來源繫結到設計的特定領域資料模型的元素。 模型結構和選定的資料來源可能是複雜階層的一部分。 因此，最終繫結可能非常大，並且包含許多不同類型的元素 (例如，關係、資料表和方法)。 繫結可能會變得沒那麼可讀，並且審查和理解起來非常複雜，尤其是對於非擁有者而言。 
- 將資料模型元素與格式組件繫結，以定義將從資料模型填入到產生格式輸出的資料。

為了提高 ER 對應設計人員的可用性，已發佈[相對路徑](er-formula-language.md#relative-path)功能。 在預設情況下，對於啟用了 ER 設計體驗的應用程式的任何新執行個體 (Microsoft Dynamics 365 Finance、Microsoft Regulatory Configuration Service)，相對路徑表示選項都是打開的。 我們實作了相對路徑參數，以便使用者在使用此 ER 繫結表示時可以繼續使用完整路徑。

[![使用者參數。](./media/relative-path-01.png)](./media/relative-path-01.png)

 
當打開相對路徑使用參數時，單個 @ 字元會替換目前模型元素繫結中父項目的路徑。 整個繫結路徑變得更短，這使得整個對應更明顯，更容易理解。 在大多數情況下，ER 設計工具不需要額外的滾動來查看資料模型的所有繫結。

[![模型對應設計工具。](./media/relative-path-02.png)](./media/relative-path-02.png)
 
當您開始設計新的 ER 運算式時，您只需輸入一個字元即可定義與父項目的繫結。

[![公式設計工具。](./media/relative-path-03.png)](./media/relative-path-03.png)
 
當您決定使用絕對路徑使用更改父模型項目的資料來源時，您必須手動將此模型項目以及所有巢狀項重新繫結到新資料來源。 啟用相對路徑使用時，如果您選取要繫結到父項的新資料來源，系統會為您提供一個選項，一鍵自動重新繫結該父項目的所有巢狀元素。

[![替換現有路徑訊息。](./media/relative-path-04.png)](./media/relative-path-04.png)
 
如果您確認重新繫結巢狀項，則新的父項將被放置到包含現有父項的每個巢狀項的路徑中。
此功能不會破壞 ER 架構的回溯相容性。 所有以前設計的 ER 設定都可以使用此新功能，無需升級或轉換。

> [!NOTE]
> 透過對模型對應中巢狀元素的繫結進行大規模修改而引入的所有更改都正確儲存在設定增量 (更改追蹤) 中。 這允許客戶將其模型對應的衍生版本重新設定為已使用此新功能修改的任何新基礎版本。

## <a name="additional-resources"></a>其他資源

[ER 公式語言](er-formula-language.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
