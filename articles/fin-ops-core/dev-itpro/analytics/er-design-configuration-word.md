---
title: 設計新的 ER 設定以產生 Word 格式的報表
description: 本主題說明使用者如何設定新的電子報表 (ER) 格式以將報表產生為 Microsoft Word 文件。
author: NickSelin
ms.date: 12/17/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, EROperationDesigner,  LedgerJournalTable, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-01-01
ms.dyn365.ops.version: Version 10.0.6
ms.openlocfilehash: 27e9e977193f9ff5c8188b780e8de955742c4ebe
ms.sourcegitcommit: d5d6b81bd8b08de20cc018c2251436065982489e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/17/2022
ms.locfileid: "8460557"
---
# <a name="design-a-new-er-configuration-to-generate-reports-in-word-format"></a>設計新的 ER 設定以產生 Word 格式的報表

[!include [banner](../includes/banner.md)]

若要將報表產生為 Microsoft Word 文件，您必須使用例如 Word 桌面應用程式為報表設計範本。 下圖顯示了控制報表的範例範本，可以產生該範本以顯示已處理的廠商付款的詳情。

![Word 桌面應用程式中控制報表的範例範本。](./media/er-design-configuration-word-image1.png)

若要將 Word 文件用作 Word 格式報表的範本，您可以設定新的[電子報表 (ER)](general-electronic-reporting.md) [解決方案](er-quick-start1-new-solution.md)。 此解決方案必須包含一個包含 ER 格式組件的 ER [設定](general-electronic-reporting.md#Configuration)。

> [!NOTE]
> 當您建立新的 ER 格式設定以產生 Word 格式的報表時，您必須在 **建立設定** 下拉式對話方塊中選取 **Word** 作為格式類型或將 **格式類型** 欄位留白。

![在設定頁面上建立格式設定。](./media/er-design-configuration-word-image2.gif)

解決方案的 ER 格式組件必須包含 **Excel\\File** 格式元素，並且該格式元素必須連結到將用作執行階段產生報表的範本的 Word 文件。 若要設定 ER 格式組件，您必須在 ER 格式設計工具中打開建立的 ER 設定的[草稿](general-electronic-reporting.md#component-versioning)版本。 然後新增 **Excel\\File** 元素，將您的 Word 範本附加到可編輯的 ER 格式，並將該範本連結到您新增的 **Excel\\File** 元素。

> [!NOTE]
> 附加範本時，必須使用之前在 ER 參數中[設定](electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents)的[文件類型](../../fin-ops/organization-administration/configure-document-management.md#configure-document-types)來儲存 ER 格式的範本。

![在格式設計工具頁面上附加範本。](./media/er-design-configuration-word-image3.gif)

您可以為 **Excel\\File** 元素新增 **Excel\\Range** 和 **Excel\\Cell** 巢狀元素，以指定將在執行階段在產生的報表中輸入的資料結構。 然後，您必須將這些元素繫結到可編輯 ER 格式的資料來源，以指定將在執行階段在產生的報表中輸入的實際資料。

![在格式設計工具頁面上新增巢狀元素。](./media/er-design-configuration-word-image4.gif)

當您在設計階段將更改儲存為 ER 格式時，分層格式結構將作為名為 **Report** 的[自訂 XML 組件](/visualstudio/vsto/custom-xml-parts-overview)儲存在附加的 Word 範本中。 您必須存取修改後的範本，從 Finance 下載它，將其儲存在本地，然後在 Word 桌面應用程式中打開它。 下圖顯示了包含 **報表** 自訂 XML 組件的控制報表的本地儲存範例範本。

![在 Word 桌面應用程式中預覽範例報表範本。](./media/er-design-configuration-word-image5.gif)

當 **Excel\\Range** 和 **Excel\\Cell** 格式元素的繫結在執行階段執行階段，每個繫結提供的資料作為 **報表** 自訂 XML 組件的單個欄位進入產生的 Word 文件。 若要在產生的文件中輸入自訂 XML 組件的欄位中的值，您必須將適當的 Word [內容控制項](/office/client-developer/word/content-controls-in-word)新增到 Word 範本中，以充當將在執行階段填入的資料的預留位置。 若要指定內容控制項的填入方式，請將每個內容控制項對應到 **報表** 自訂 XML 組件的相應欄位。

![在 Word 桌面應用程式中新增和對應內容控制項。](./media/er-design-configuration-word-image6.gif)

然後，您必須將可編輯 ER 格式的原始 Word 範本替換為修改後的範本，該範本現在包含對應到 **報表** 自訂 XML 組件的欄位的 Word 內容控制項。

![替換格式設計工具頁面上的範本。](./media/er-design-configuration-word-image7.gif)

當您執行設定的 ER 格式時，附加的 Word 範本用於產生新報表。 實際資料作為名為 **報表** 的自訂 XML 組件儲存在 Word 報表中。 打開產生的報表時，Word 內容控制項將填入來自 **報表** 自訂 XML 組件的資料。

## <a name="frequently-asked-questions"></a>常用問題

**題目：** 我設定了 ER 格式來列印包含公司地址的 Word 文件。 在此 ER 格式的 Word 範本中，我插入了 RTF 內容控制項來顯示公司地址。 在財務中，我將公司地址作為多行文字輸入，然後選取 **Enter** 為我輸入的每一行新增一個回車。 因此，我希望公司地址在產生的文件中顯示為多行文字。 但是，地址顯示為包含特殊符號而不是回車的單行文字。 我的設定有什麼問題？

**答案：** 您必須使用純文字內容控制項，而不是使用 RTF 內容控制項，並在控制項的屬性中選取 **允許回車 (多段)** 核取方塊。

## <a name="additional-resources"></a>其他資源

- [透過 Excel 範本重複使用 ER 設定以產生 Word 格式的報表](./tasks/er-design-configuration-word-2016-11.md)
- [在使用 ER 產生的檔案中嵌入圖像和形狀](electronic-reporting-embed-images-shapes.md#embed-an-image-in-a-word-document)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
