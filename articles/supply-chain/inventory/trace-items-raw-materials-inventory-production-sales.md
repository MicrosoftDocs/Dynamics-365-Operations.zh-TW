---
title: 庫存、生產和銷售中的品項和原材料追蹤
description: 本主題介紹如何使用物料追蹤來識別物料或原材料已在何處使用、正在使用或將用於生產和銷售流程的位置。
author: yufeihuang
ms.date: 11/02/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTrackingDimTracing, InventTrackingDimTracingCriteria
audience: Application User
ms.reviewer: kamaybac
ms.custom: 30191
ms.assetid: fdd0939a-855c-430f-a684-94f3baea1df4
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 95f59a3eca20634d03520ad88f71a3096309e23e
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448458"
---
# <a name="item-and-raw-material-tracing-in-inventory-production-and-sales"></a>庫存、生產和銷售中的品項和原材料追蹤

[!include [banner](../includes/banner.md)]

本主題介紹如何使用物料追蹤來識別物料或原材料已在何處使用、正在使用或將用於生產和銷售流程的位置。

物品追踪功能在 **物品追踪** 頁面。 以下部分描述瞭如何使用品項追蹤，以及選項和限制是什麼。

## <a name="what-is-item-tracing"></a>什麼是物品追踪？
物品追踪是一種商業智能 (BI) 工具，可讓您了解供應鏈中物品和原材料的來源和目的地。 製造商可以將物品、原材料或成分追溯到供應商，並透過成品的生產和銷售進行轉發。 品項追蹤能協助製造商遵守法規要求，幫助品質官和生產經理分析並採取行動解決產品和材料質量的差異。 以下是製造商可以使用物品追蹤的一些範例：

-   確認目前庫存中的物品或原材料的數量及其儲存位置。
-   確定已運送了多少物品或原材料，以及運送給了哪些客戶。
-   確定包括該品項或原材料的任何計劃運送。
-   找到使用物料或原材料的生產訂單，以及已計劃、正在進行或報告為已完成的生產訂單。
-   找出物品或原材料的購買地點。
-   調查一個品項或原材料在另一個品項的生產中被消耗在哪裡。

## <a name="what-can-i-trace-and-are-there-any-limitations"></a>我可以追踪什麼，有什麼限制嗎？
您可以根據物料編號和追蹤維度 (例如序號、批號或供應商批號) 追蹤物料和原材料的紀錄庫存交易記錄。 只有分配了追蹤維度，您才能追蹤品項或原材料。 由於追蹤基於庫存交易記錄，因此在追蹤品項時存在一些限制。 例如，存在與專案、固定資產和商業交易相關的限制。 此外，追蹤詳細資訊中會顯示聯產品，但不包括副產品。 追蹤包括從一個位置到另一個位置的所有倉庫交易。 因此，用戶可能會發現資訊量太大。 一次顯示一個法律實體的追蹤。 在公司間環境中沒有跨公司能力。 您必須為每個接收或發出品項的公司開始新的追蹤。

## <a name="what-criteria-can-i-specify-for-an-item-trace"></a>我可以為品項追蹤指定哪些標準？
物料追蹤所需的條件是物料編號、追蹤維度 (例如批號或序號) 和方向。 下表描述了您可以在品項追蹤中使用的條件。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>欄位群組</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>品項數</td>
<td>輸入您要追蹤的品項或原材料的識別碼。</td>
</tr>
<tr class="even">
<td>產品維度</td>
<td>可選：追蹤產品定義的特定方面，例如設定、尺寸、顏色或樣式。</td>
</tr>
<tr class="odd">
<td>追蹤維度</td>
<td>輸入批號、供應商批號或序號追蹤維度。 當您使用批號作為標準時，如果您已擷取該資訊，則會顯示供應商批號。</td>
</tr>
<tr class="even">
<td>儲存尺寸</td>
<td>可選：追蹤已儲存在特定位置的品項。</td>
</tr>
<tr class="odd">
<td>期間</td>
<td>可選：輸入日期以將追蹤限制在特定時期。 追蹤詳細資訊將僅顯示在這些日期之間建立的文件和交易。</td>
</tr>
<tr class="even">
<td>正向或逆向</td>
<td>選擇追蹤的方向。 您可以正向或逆向追溯：
<ul>
<li><strong>逆向</strong> – 追蹤下游以確定來源、手邊剩餘數量以及至少部分報告為已完成的任何生產訂單。</li>
<li><strong>正向</strong> – 追蹤上游以識別目的地。 您可以找到銷售訂單，以及追蹤品項或原材料已至少部分已送達的客戶。</li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="what-information-is-included-in-the-trace-details"></a>追蹤詳細資訊中包含哪些資訊？
追蹤的結果按時間順序顯示在樹狀結構上 **細節** FastTab 的 **物品追踪** 頁面。 順序會有所不同，具體取決於追蹤方向。 詳細資訊包括從供應商購買物品到將物品出售給客戶的所有交易。 追蹤結果也包括與追蹤條件中指定的品項或追蹤維度相關的臨時產品。 頂部節點根據追蹤條件中指定的儲存維度，顯示庫存單位中剩餘的品項數量。 **筆記：** 追蹤詳細資訊提供了追蹤完成時可用資訊的快照。 如果追蹤完成後資訊發生變更，則不會更新追蹤詳細資訊。

## <a name="why-dont-some-nodes-contain-any-details"></a>為什麼有些節點不包含任何細節？
為了減少追蹤詳細資訊中的資訊量，只有品項或原材料的第一個執行個體的節點包含詳細資訊。 如果所選節點不包含詳細資訊，您可以透過點擊查看包含詳細資訊的節點 **前往追蹤行**。 然後，您可以透過點擊返回您離開的節點 **返回**。

## <a name="can-i-view-only-a-particular-type-of-document-for-example-can-i-view-only-production-orders-customers-or-vendors"></a>我可以只查看特定類型的文件嗎？ 例如，我可以只查看生產訂單、客戶或供應商嗎？
是的，從追蹤詳細資訊中，您可以打開僅包含特定類型文件或交易的清單頁面。 您可以在 **物品**、**銷售量**、**購買**、**生產** 和 **質量** 群組中，從 **追踪** 動作窗格上的選單品項。 例如，若要查看追蹤詳細資訊中的供應商列表，請點擊 **追踪** &gt; **購買** &gt; **廠商**。 清單頁面匯總了追蹤詳細資訊中的文件或交易。 **待定交易**、**待定訂單** 和 **未發貨的銷售訂單** 清單頁面還顯示未包含在追蹤詳細資訊中的其他資訊。 此外，即使指定了日期範圍，也會始終顯示截至目前日期的結果。 下方資料表中描述了這些頁面可以包含的其他詳細資訊。

| 清單                    | 描述                                                                                                                                                                                                                                                                                                                   |
|--------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 不要運送銷售訂單 | 查看尚未選擇的銷售訂單行，因此不會顯示在追蹤詳細資訊中。                                                                                                                                                                                                                        |
| 待定訂單           | 查看追蹤品項的所有待處理生產訂單，無論追蹤標準中使用的追蹤維度如何。 您也可以查看待處理的生產訂單，其中追蹤的品項是一種成分，並且沒有進行註冊並且沒有交易報告為訂單已完成。 |
| 待定交易     | 查看包含指定追蹤維度或空白追蹤維度的追蹤品項的待定庫存交易。 您還可以在追蹤詳細資訊中查看品項和追蹤維度組合或空白值的待定庫存交易。                                                |

## <a name="how-many-levels-can-i-trace-up-or-down-in-a-bom-or-formula"></a>我可以在 BOM 或公式中向上或向下追蹤多少層？
您可以在物料清單 (BOM) 或公式中向上或向下追蹤一層。 例如，如果您對原材料進行追蹤，您可以看到成品和任何聯產品。 但是，如果您追蹤聯產品，則追蹤詳細資訊不包括成品。

## <a name="how-can-i-view-more-details-about-a-document-or-transaction-in-the-trace-details"></a>如何在追蹤詳細資訊中查看有關文件或交易的更多詳細資訊？
在 **細節** FastTab，有兩種方法可以在追蹤詳細資訊中查看有關所選文件或交易的更多資訊：

-   當您在 **細節** FastTab 上的追蹤詳細資訊中選擇一個節點，頁面上的其他 FastTab 會顯示節點中的文件或交易的相關資訊。
-   透過點擊 **查看詳情** 開啟所選節點中文件的詳細資訊頁面。 例如，如果您選擇描述生產訂單的節點，然後單擊 **查看詳情**，**生產訂單明細** 頁面將會出現。

某些 FastTab 能讓您存取關於所選節點的其他資訊。 例如，在 **非一致** FastTab 上，您可以點擊 **查詢**，調查是否有非一致的紀錄。 在 **批** FastTab，你可以點擊 **現有清單** 查看目前手邊實物庫存數量以及涉及該批次的任何庫存交易。

## <a name="can-i-run-more-than-one-trace-and-then-compare-the-details"></a>我可以執行多個追蹤然後比較詳細資訊嗎？
執行追蹤後，您可以在 **從節點追蹤** 按鈕在所選節點中的交易上執行新的追蹤：

-   **逆向** 或 **正向** – 為所選節點啟動新追蹤，並覆蓋當前追蹤的詳細資訊。
-   **全新逆向** 或 **全新正向** – 為所選節點啟動新追蹤，並覆蓋當前追蹤的詳細資訊。

如果你想使用 **全新逆向** 或 **全新正向** 選項，您必須使用 **在新視窗中開啟** 讓新追蹤出現在新視窗中的功能。

## <a name="can-i-save-the-trace-details"></a>我可以保存追蹤詳細資訊嗎？
您可以透過點擊動作窗格上 *<strong><em>追蹤</em></strong>* 動作下方的<strong>匯出</strong>，將<strong>詳細資訊</strong>索引標籤上的資訊保存為 XML 檔案。 除了追蹤詳細資訊之外，XML 文件也包括追蹤條件、上層節點和現有數量。 例如，如果您想將資訊附加到品質檢驗訂單或其他合規性文件中，則保存追蹤詳細資訊的功能很有用。 您可以指定文件的保存位置。 若要立即查看文件，請選擇<strong>顯示文件</strong>選項。 <strong>注意：</strong>即使您只是想查看，此檔案也會隨時被保存。 預設情況下，XML 檔案會在瀏覽器視窗中開啟。 但是，您可以右鍵點擊該文件，選擇<strong>開啟方式</strong>，然後選擇用於顯示內容的程式。

## <a name="can-i-calculate-a-balance-for-a-particular-item-or-ingredient"></a>我可以計算特定品項或成分的餘額嗎？
您可以將摘要頁面中的資訊匯出至 Microsoft Excel. 打開相關頁面，點擊 **在 Microsoft Office 中開啟** 圖示，然後選擇 **匯出至 Microsoft Excel**。 當您要從 **交易摘要** 頁面計算物料或成分的品質餘額時，此功能特別有用。 在 **交易摘要** 頁面，您可以篩選品項或成分，也可以選擇批次篩選，然後將資訊匯出至 Excel。 例如，在 Excel 中，您可以檢疫現有數量、已售數量和生產中使用的數量。

## <a name="can-i-investigate-whether-there-is-a-history-of-issues-with-items-or-raw-materials"></a>我可以調查是否存在物品或原材料問題的紀錄嗎？
追蹤詳細資訊包括關於品質檢驗訂單和不符合品項或原材料的不合格品資訊。 若要查看品質檢驗訂單和不符合品項的摘要，請在動作窗格上點擊 **品質檢驗訂單** 或 **不符合品項**。 **注意：** 破壞性品質檢驗訂單可以在追蹤詳細資訊中出現多次。 為文件 (例如採購訂單) 建立破壞性品質檢驗訂單時，會出現在該文件的各交易中。

## <a name="are-there-any-reporting-capabilities-that-are-related-to-item-tracing"></a>是否有與品項追踪相關的報告功能？
您可以生成 **運送給客戶** 報告，以識別已運送的物品或原材料的數量以及運往的客戶。 若要查詢合規性相關內容，您可以為所有客戶生成報告。 對於與客戶服務相關的查詢，您可以為所選客戶生成報告。 如果產品是用於生產成品的原材料，則成品也包括在內。 **注意：** 如果您使用刪除或封存銷售訂單的功能，報告結果也會包括已刪除或封存的所有銷售訂單。

## <a name="can-i-trace-coproducts-and-byproducts"></a>我可以追踪副產品和副產品嗎？
您可以追蹤聯產品，但不能追蹤副產品，因為追蹤維度通常不會分配給副產品。 追蹤品項時，追蹤詳細資訊包括任何相關聯產品。 包含聯產品的節點在詳細資訊中會加入單字「聯產品」。 您也可以透過在追蹤詳細資訊中選擇節點，然後點擊 **生產** FastTab。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]