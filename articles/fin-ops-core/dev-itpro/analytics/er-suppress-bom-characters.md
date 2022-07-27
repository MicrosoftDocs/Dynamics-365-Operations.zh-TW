---
title: 設計 ER 設定以抑制產生檔案中的 BOM 字元
description: 本主題說明如何設定電子報表 (ER) 格式以產生抑製字節順序標記 (BOM) 字元的報表。
author: NickSelin
ms.date: 01/04/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: EROperationDesigner
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-01-01
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b9265578deaff4100eb5987eb6090eaa12876044
ms.sourcegitcommit: d5d6b81bd8b08de20cc018c2251436065982489e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/17/2022
ms.locfileid: "8460562"
---
# <a name="design-er-configurations-to-suppress-bom-characters-in-generated-files"></a>設計 ER 設定以抑制產生檔案中的 BOM 字元

[!include [banner](../includes/banner.md)]

您可以設計[電子報表 (ER)](general-electronic-reporting.md) [解決方案](er-quick-start1-new-solution.md)來產生傳出文件。 若要將文件產生為文字或 XML 檔案，解決方案必須包含一個包含 ER 格式組件的 ER [設定](general-electronic-reporting.md#Configuration)。 若要指定表示產生檔案中字元集的 [字元編碼](/windows/win32/intl/character-sets)，ER 格式必須包含 **Common\\File** 格式元素。 若要設定 ER 格式組件，請在 ER 格式設計工具中打開 ER 設定的 [草稿](general-electronic-reporting.md#component-versioning)版本，然後新增 **Common\\File** 元素。 在 **編碼** 欄位，指定使用此組件在執行階段產生的出站檔案的編碼。

> [!NOTE]
> 如果格式包含不正確的編碼名稱，則在儲存對格式設定的更改時會引發錯誤。

![在格式設計工具頁面上新增根元素。](./media/er-suppress-bom-characters-image1.gif)

如果您指定 **UTF-8**、**UTF-16** 或 **UTF-32** 作為編碼，則 **抑制 BOM 字元** 選項變為可用。 將此選項設定為 **是** 可在執行可編輯 ER 格式時在執行階段產生的傳出檔案中抑制[位元順序標記 (BOM) 字元](/globalization/encoding/byte-order-mark)。

> [!NOTE]
> 如果將 **編碼** 欄位留空，則使用預設的 **UTF-8** 編碼。

![在格式設計工具頁面上設定抑制 BOM 字元選項。](./media/er-suppress-bom-characters-image2.gif)

若要在執行階段查看函數，請完成相應的程序。 例如，完成[遞延執行 ER 格式的 XML 元素](er-defer-xml-element.md)主題中的步驟。 完成該主題的[修改格式以便計算基於產生的輸出](er-defer-xml-element.md#modify-the-format-so-that-the-calculation-is-based-on-generated-output)章節中的步驟後，請執行這些附加步驟。

1. 指定 UTF 編碼：

    1. 選取 **Common\\File** 類型的 **報表** 元素。
    2. 在 **編碼** 欄位，指定 **UTF-8** 編碼。

2. 產生一個包含 BOM 字元的 XML 檔案：

    1. 將 **抑制 BOM 字元** 選項設定為 **否** 以在產生的 XML 檔案中包含 BOM 字元。
    2. 完成 [遞延執行 ER 格式的 XML 元素](er-defer-xml-element.md)主題的 [遞延執行匯總 XML 元素以便使用計算的總數](er-defer-xml-element.md#defer-the-execution-of-the-summary-xml-element-so-that-the-calculated-total-is-used)章節中的步驟，並將產生的檔案另存為 **SampleXmlReport.xml**。

3. 產生一個不包含 BOM 字元的 XML 檔案：

    1. 將 **抑制 BOM 字元** 選項設定為 **是** 以在產生的 XML 檔案中抑制 BOM 字元。
    2. 完成 [遞延執行 ER 格式的 XML 元素](er-defer-xml-element.md)主題的 [遞延執行匯總 XML 元素以便使用計算的總數](er-defer-xml-element.md#defer-the-execution-of-the-summary-xml-element-so-that-the-calculated-total-is-used)章節中的步驟，並將產生的檔案另存為 **SampleXmlReport.xml (1)**。

4. 在檔案比較公用程式中，比較產生的檔案。

    您會注意到的第一個區別是檔案名稱。 SampleXmlReport.xml 檔案包含一個 BOM 字元，而 SampleXmlReport (1).xml 檔案沒有。

    ![使用檔案比較公用程式比較產生的檔案。](./media/er-suppress-bom-characters-image3.png)

## <a name="see-also"></a>另請參閱

- [遞延執行 ER 格式的 XML 元素](er-defer-xml-element.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
