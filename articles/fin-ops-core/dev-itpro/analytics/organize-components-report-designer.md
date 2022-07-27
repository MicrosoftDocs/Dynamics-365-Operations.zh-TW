---
title: 在 Report Designer 中組織報表組件
description: 本主題說明如何在 Report Designer 中組織現有報表、建構元素和物件。
author: ShylaThompson
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: kfend
ms.custom: 59161
ms.assetid: 32e728c5-3b06-4049-8070-ade01e951d49
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 6b30e7e480edb50bb9509e270806224755f98e38111cda0c1cae86a0f56eb193
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460381"
---
# <a name="organize-report-components-in-report-designer"></a>在 Report Designer 中組織報表組件

[!include [banner](../includes/banner.md)]

在您設計了建構元素並產生了報表之後，組織這些對像以便使用者更容易找到它們會很有幫助。 本文章說明如何在 Report Designer 中組織現有報表、建構元素和物件。

您可以在 Report Designer 中重新命名資料夾、報表、建構元素和其他物件，以幫助組織您的檔案。 根據您重新命名的對像類型，您可能必須更新與該物件的關聯。

## <a name="rename-a-folder-or-building-block-in-report-designer"></a>在 Report Designer 中重新命名資料夾或建構元素
在 Report Designer 中，您可以重新命名資料夾、報表定義、列定義、欄定義和報表樹狀結構定義。

### <a name="rename-a-folder-or-building-block-in-report-designer"></a>在 Report Designer 中重新命名資料夾或建構元素

1. 在 Report Designer 中，使用瀏覽窗格找到要重新命名的資料夾或物件。
2. 按右鍵點選資料夾或物件，然後點選 **重新命名**。 瀏覽窗格中的 **名稱** 欄位變為可用。
3. 輸入新名稱，然後按 Enter。
4. 如果建構元素是列定義、欄定義或報表樹狀結構定義，則必須更新與其關聯的其他建構元素。 按右鍵點選您在步驟 3 中重新命名的建構元素，選取 **關聯**，然後在清單中選取一個項目來更新它。
5. 重複步驟 4，直到所有關聯項目都更新完畢。

## <a name="create-and-manage-report-groups"></a>建立和管理報表群組
您可以將報表定義分組以同時產生多個報表。 若要建立、修改、刪除和產生報表群組，您必須具有設計者或管理員角色。 具有產生者角色的使用者可以產生報表群組，也可以修改報表群組的使用者報表定義設定。

### <a name="create-a-report-group"></a>建立報表群組

1. 在 Report Designer 中的瀏覽窗格，點選 **報表群組**。
2. 在 **檔案** 選單上，點選 **新建**&gt;**報表群組定義** 以在檢視器視窗中打開一個新的報表群組。 或者，點選 **報表群組按鈕**![報表群組。](media/report-group.gif "報表群組") 在工具列上。
3. 點選 **報表群組** 索引標籤。若要覆寫有關產生此報表的各個報表定義的資訊，請選取 **覆寫各個報表定義中的公司、詳情和日期設定** 核取方塊。 公司名稱、詳細程度、暫時設定和日期資訊會自動輸入，但您可以進行更新。
4. 若要產生顯示報表幣種的多個報表，請選取 **包括所有報表貨幣** 核取方塊。 然後，您可以在查看報表時透過點選網路檢視器中的 **貨幣** 按鈕來存取多個檢視表。
5. 在 **分組報表** 欄位，點選 **新增** 選取要包含在報表群組中的報表。 若要在 **新增** 對話方塊中選取多個報表，請在選取報表時按住 Ctrl 鍵。 選取完報表後，點選 **確定**。
6. 點選 **檔案**&gt;**儲存** 以儲存新報表群組。

### <a name="modify-a-report-group"></a>修改報表群組

1. 在 Report Designer 中的瀏覽窗格，點選 **報表群組**。
2. 按兩下點選要修改的報表群組。
3. 在 **報表群組** 索引標籤，進行所需的更改。
4. 在 **檔案** 選單，點選 **儲存** 要儲存修改後的報表群組，或者，點選 **儲存** 按鈕![儲存。](media/save.gif "儲存") 在工具列上。

> [注意] 如果您已安排報表以按設定的時間間隔產生，您可以覆寫這些設定並立即產生報表。

### <a name="generate-a-report-group-report"></a>產生報表群組報表

1. 在 Report Designer 中的瀏覽窗格，點選 **報表群組**。
2. 開啟要產生的報表群組。
3. 點選 **產生報表** 按鈕![產生報表。](media/generate-report.gif "產生報表") 產生報表。

### <a name="delete-a-report-group"></a>刪除報表群組

1. 在 Report Designer 中的瀏覽窗格，點選 **報表群組**。
2. 按右鍵點選要刪除的報表群組，然後選取 **刪除**。
3. 出現確認訊息時，點選 **是**。

## <a name="report-group-tab-controls"></a>報表群組索引標籤控制項
下表描述了 **報表群組** 索引標籤上的控制項。

<table>
<thead>
<tr>
<th>控制項</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr>
<td>覆寫個別報表定義中的公司、詳細資料與日期設定</td>
<td>選中此核取方塊可覆寫此報表群組中報表的各個報表定義，僅用於產生這些報表。</td>
</tr>
<tr>
<td>公司名稱</td>
<td>選取要用於報表的公司。</td>
</tr>
<tr>
<td>詳細程度</td>
<td>指定報表包含的詳細程度。
<ul>
<li><strong>財務</strong>− 高級摘要報表。 除了透過報表樹狀結構新增的帳戶和維度外，您無法深入了解帳戶和維度。</li>
<li><strong>財務&amp;帳戶</strong>− 包含高級摘要和帳戶詳情的報表。</li>
<li><strong>財務、帳戶&amp;交易</strong>− 包含高級摘要和交易詳情的報表。</li>
</ul></td>
</tr>
<tr>
<td>暫付</td>
<td>指定報表包含的活動類型。
<ul>
<li><strong>僅限過帳活動</strong>− 僅包括在您的財務資料中過帳的交易和餘額。</li>
<li><strong>過帳和未過帳活動</strong> − 包括在您的財務資料中輸入和過帳的所有交易和餘額。</li>
<li><strong>僅限未過帳活動</strong>− 在您的財務資料中僅包括已輸入但尚未過帳的交易。</li>
</ul></td>
</tr>
<tr>
<td>包括所有報表貨幣</td>
<td>在您的 Microsoft Dynamics ERP 系統中設定的任何其他報表貨幣都在此處列出。 選中此核取方塊以使用指定的貨幣產生其他報表。 若要在網路檢視器中查看這些報表，請點選<strong>貨幣</strong>按鈕，然後選取一種貨幣。</td>
</tr>
<tr>
<td>日期資訊不會隨報表定義一起儲存</td>
<td><ul>
<li>基準週期</li>
<li>基準年度</li>
<li>涵蓋期間</li>
</ul>
只有預設的基準週期設定與報表定義一起儲存。</td>
</tr>
<tr>
<td>日期資訊會隨報表定義一起儲存</td>
<td><ul>
<li>報表日期</li>
<li>預設基準週期</li>
</ul></td>
</tr>
<tr>
<td>群組中的報表</td>
<td>在報表群組中新增、刪除和重新排序報表。
<ul>
<li>若要將報表定義新增到報表群組，請按兩下點選報表群組將其打開，然後點選<strong>新增</strong>。 選取要包含在報表群組中的報表，然後點選<strong>確定</strong>。</li>
<li>若要從報表群組中移除報表，請選取它，然後點選<strong>移除</strong>。</li>
<li>若要修改產生報表的順序，請在清單中選取一個報表，然後點選<strong>上移</strong>或<strong>下移</strong>。</li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="additional-resources"></a>其他資源

[財務報表](financial-reporting-intro.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]