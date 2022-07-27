---
title: 以電子報表格式使用資料收集資料來源
description: 本主題說明如何使用電子報表 (ER) 格式的資料收集資料來源。
author: NickSelin
ms.date: 08/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EROperationDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2021-01-01
ms.dyn365.ops.version: AX 10.0.16
ms.openlocfilehash: 185fb9a33cb4cc655dfdf640b4c239d617426c64
ms.sourcegitcommit: d5d6b81bd8b08de20cc018c2251436065982489e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/17/2022
ms.locfileid: "8460581"
---
# <a name="use-data-collection-data-sources-in-electronic-reporting-formats"></a>以電子報表格式使用資料收集資料來源

[!include [banner](../includes/banner.md)]

您可以使用[電子報表 (ER)](general-electronic-reporting.md) 架構的運營設計工具來設定用於產生不同格式的輸出文件的 ER 解決方案的格式組件。 設定格式組件的階層由各種類型的格式元素組成。 這些格式元素用於在執行階段用所需資訊填入產生的文件。 在預設情況下，當您執行 ER 格式時，格式元素的執行順序與它們在格式階層中的顯示順序相同：一個接一個，從上到下。

當 ER 執行包含繫結的格式元素時，將執行該繫結的公式，並且格式元素將值新增到產生的文件中。 例如，繫結可以將資料模型欄位的值傳遞給格式元素。 您可以設定資料收集資料來源以在執行階段收集資料模型欄位的值，進行值求和，並使用收集的值填入產生的文件。 要使用此方法，請更改初始繫結，以便使用設定的資料收集資料來源將資料模型欄位的值傳遞給格式元素。 透過資料收集資料來源傳遞值，您可以收集所需的詳情以供進一步使用。

設定資料收集資料來源時，請指定將在資料來源中管理的值類型。 現行支援以下[資料類型](er-formula-supported-data-types-primitive.md)來收集值：

- 布林值
- 日期
- 日期時間
- GUID
- Int64
- 整數
- 實數
- 字串
- 時間

您可以使用資料收集資料來源的 `Collect(Value)` 方法將值傳遞給資料來源進行收集。 在此方法中，`Value` 引數是常數，或是相關資料類型的資料來源欄位的有效路徑。

使用資料收集資料來源的 `Result` 屬性存取收集的值清單。 此屬性回傳[記錄清單](er-formula-supported-data-types-composite.md#record-list)。 記錄清單的記錄包含可用於存取收集的值的 `Value` 欄位。

在預設情況下，資料收集資料來源僅收集唯一值。

若要收集所有值，請將設定的資料收集資料來源的 **收集所有值** 欄位設定為 **是**。 當 **收集所有值** 欄位設定為 **是** 時，`Sum(Flag)` 參數化屬性變為可用。 您可以使用此屬性來獲取所有現行收集的值的總量。 在此屬性中，`Flag` 引數是一個[布林值](er-formula-supported-data-types-primitive.md#boolean)，用於指示是否必須重設總值。

- 當提供值 **False** 時，從先前收集的金額繼續求和。
- 當提供值 **True** 時，將開始新的求和。

現行支援以下資料類型進行求和：

- Int64
- 整數
- 實數

若要進一步了解此函數，請完成以下範例。

## <a name="example-configure-an-er-format-to-do-counting-and-summing-by-using-a-data-collection-data-source"></a>範例：設定 ER 格式以使用資料收集資料來源進行計數和求和

此範例顯示系統管理員或電子報表職能顧問角色的使用者如何設定具有資料收集資料來源的 ER 格式，該資料來源用於計算執行總計和收集總和值。

這個範例中的程序可以在 Microsoft Dynamics 365 Finance 的 USMF 公司中完成。

### <a name="upload-and-use-the-provided-er-solution"></a>上傳並使用提供的 ER 解決方案

1. [匯入樣本 ER 設定](er-defer-sequence-element.md#import-the-sample-er-configurations)。
2. [啟用設定提供者](er-defer-sequence-element.md#activate-a-configurations-provider)。
3. [查閱匯入的資料對應](er-defer-sequence-element.md#review-the-imported-model-mapping)。
4. [查閱已匯入的格式](er-defer-sequence-element.md#review-the-imported-format)。
5. [執行已匯入的格式](er-defer-sequence-element.md#run-the-imported-format)。

### <a name="run-the-format-of-the-provided-er-solution"></a>執行提供的 ER 解決方案的格式

1. 在 **格式設計工具** 頁面上，選取 **執行**。
2. 在 **電子報表參數** 對話方塊中，選取 **確定**。
3. 下載並查看網路瀏覽器提供的檔案。

    ![包含初始格式執行結果的下載檔案](./media/er-data-collection-data-sources-01.png)

### <a name="modify-the-format-of-the-er-solution-to-calculate-the-running-tax-total"></a>修改 ER 解決方案的格式以計算流轉稅總額

如果交易量遠大於現行範例中的量，則求和所需的時間可能會增加並導致效能問題。 透過更改格式設定，您可以幫助防止這些效能問題。 因為您存取稅值以將它們包含在產生的報告中，所以您可以重複使用該資訊來求和稅值。

1. 在 **格式設計工具** 頁，在 **對應** 索引標籤，選取 **新增根**。
2. 在 **新增資料來源** 對話方塊中，選取 **函數**\>**資料收集**。
3. 在 **「資料收集」資料來源屬性** 對話方塊，請按照下列步驟操作：

    1. 在 **名稱** 欄位中，輸入 **CollectedTaxValues**。
    2. 在 **項目類型** 欄位中，選取 **實數**。
    3. 在 **收集所有值** 欄位中，選取 **是**。
    4. 選取 **確定**。

4. 選取 **報告\\明細\\記錄\\營業稅額** 格式元素。

    > [!NOTE]
    > 現行，為該元素設定了 `@.Value` 繫結。 因此，如果填入了來自 `model.Data.List.Value` 欄位的稅值，則會產生一個文件。

5. 選取 **編輯公式**。
6. 請在 **公式設計工具** 頁上按照下列步驟操作：

    1. 在 **公式** 欄位中，將 `@.Value` 替換為 `CollectedTaxValues.Collect(@.Value)`。
    2. 儲存更改，然後關閉頁面。

    > [!NOTE]
    > 新繫結會將相同的稅值傳遞給產生的文件。 但是，這些值也將收集在 **CollectedTaxValues** 資料來源中。

7. 選取 **報告\\明細\\記錄\\RunningTotal** 數字格式元素。
8. 選取 **編輯公式**。
9. 請在 **公式設計工具** 頁上按照下列步驟操作：

    1. 在 **公式** 欄位中，輸入 `CollectedTaxValues.Sum(false)`。
    2. 儲存更改，然後關閉頁面。

    > [!NOTE]
    > 新繫結會將已輸入的稅值總額傳遞給產生的文件。

    ![格式設計工具頁面上已更新繫結的數值元素](./media/er-data-collection-data-sources-02.png)

10. 選取 **儲存**，然後選取 **執行**。
11. 在 **電子報表參數** 對話方塊中，選取 **確定**。
12. 下載並查看網路瀏覽器提供的檔案。

    ![包含已修改格式執行結果的下載檔案](./media/er-data-collection-data-sources-03.png)

### <a name="modify-the-format-to-evaluate-the-list-of-collected-tax-values"></a>修改格式以評估徵收的稅值清單

1. 在 **格式設計工具** 頁，在 **格式** 索引標籤，選取 **報告\\明細\\記錄\\RunningTotal** 數字格式元素，然後按照以下步驟操作：

    1. 在 **數字類型** 欄位，將值從 **實數** 更改到 **整數**。
    2. 在 **數字格式** 欄位，請將值從 **F2** 改為 **F0**。

3. 在 **對應** 索引標籤上，選取 **編輯公式**。
4. 請在 **公式設計工具** 頁上按照下列步驟操作：

    1. 在 **公式** 欄位中，輸入 `COUNT(CollectedTaxValues.Result)`。
    2. 儲存更改，然後關閉頁面。

    > [!NOTE]
    > 新繫結將向產生的文件傳遞清單中收集稅值的記錄數。

5. 選取 **儲存**，然後選取 **執行**。
6. 在 **電子報表參數** 對話方塊中，選取 **確定**。
7. 下載並查看網路瀏覽器提供的檔案。

    ![下載的檔案包含另一個修改格式執行的結果](./media/er-data-collection-data-sources-04.png)

## <a name="frequently-asked-questions"></a>常用問題

### <a name="if-i-have-to-calculate-running-totals-and-collect-data-what-is-the-difference-between-using-a-data-collection-data-source-and-using-the-built-in-data-collection-functions"></a>如果我必須計算執行總計並收集資料，那麼使用資料收集資料來源和使用內建資料收集函數有什麼區別？

資料收集資料來源和內建的[資料收集](er-functions-category-data-collection.md)函數都可用於資料收集、匯總和計數，基於傳遞到產生的輸出文件的資訊。 但是，當您嘗試決定使用哪種技術時，您必須考慮以下幾點。

| 資料來源 | 內建函數 |
|-------------| ------------------ |
| 僅收集值。 | <p>收集已命名的值。 因此，可以為不同的值組計算總額。</p><p>此外，可以將群組擷取為清單。</p><p>也可以收集文字值。</p> |
| 自動收集唯一值。 | 需要其他設定才能從收集的值中擷取唯一值清單。 |
| 效能取決於收集值的數量。 | 在實踐中，效能並不取決於收集值的數量。 |
| 此技術適用於所有類型的輸出文件。 | 此技術僅適用於文字和 XML 文件。 |

## <a name="additional-resources"></a>其他資源

- [設定格式進行計數和求和](./tasks/er-format-counting-summing-1.md)
- [遞延執行 ER 格式的序列元素](er-defer-sequence-element.md#Example)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
