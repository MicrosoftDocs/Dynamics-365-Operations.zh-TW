---
title: 財務 Report Designer 中的報表定義
description: 本文提供有關報表定義的資訊。
author: ShylaThompson
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: kfend
ms.custom: 59131
ms.assetid: 966a3f1d-c59c-4a84-acd4-5bb7e65144c8
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: fed19d541af1ef6a55f09127f08d73b1301eefb6369f6d76314463e18fb273c8
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460402"
---
# <a name="report-definitions-in-financial-report-designer"></a>財務 Report Designer 中的報表定義

[!include [banner](../includes/banner.md)]

本文提供有關報表定義的資訊。 報表定義是一個報表組件 (或建構元素)，它使用列定義、欄定義和可選的報表樹狀結構定義來建立報表。 報表定義還提供用於自訂報表的選項和設定。 

報表定義是一個報表組件 (或建構元素)，它使用列定義、欄定義和可選的報表樹狀結構定義來建立報表。 報表定義還提供可用於自訂報表的選項和設定。 定義列定義和欄定義後，必須將它們組合到報表定義中。 此時，您還可以定義定義的其他方面，例如詳細程度和報表日期。 然後，您可以儲存並產生報表。 財務報表提供以下詳細程度：

- 財務
- 財務與科目
- 財務、科目與交易

但是，根據資料在 Microsoft Dynamics ERP 系統中的儲存方式，報表中可能不提供交易詳情。

## <a name="create-a-report-definition"></a>建立報表定義
1. 在 Report Designer 中，在 **檔案** 選單，點選 **新建**，然後選取 **報表定義**。
2. 在 **報表**、**輸出和分發**、**頁首和頁尾** 以及 **設定** 索引標籤上指定適當的信息。

## <a name="contents-of-a-report-definition"></a>報表定義的內容
下表描述了報表定義中的索引標籤以及信息的使用方式。

<table>
<thead>
<tr>
<th>索引標籤</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr>
<td>報告</td>
<td>建立報表、設定報表或修改現有報表。</td>
</tr>
<tr>
<td>輸出和指派</td>
<td>更改報表的輸出類型和目的地。</td>
</tr>
<tr>
<td>頁首與頁尾</td>
<td>定義和格式化報表的頁首與頁尾。 例如，您可以將文字或影像新增到頁首與頁尾。 財務報表支援影像的 .bmp、.jpg 和 .png 檔案。 您還可以新增自動文字代碼以插入其他信息，例如公司名稱、報表名稱或頁碼。</td>
</tr>
<tr>
<td>設定</td>
<td>指定報表定義設定，例如以下設定：
<ul>
<li>格式化和進位金額</li>
<li>格式化詳細報表</li>
<li>格式化報表樹狀結構</li>
<li>產生例外報表</li>
<li>指定貨幣轉換</li>
<li>小計和篩選帳戶詳情</li>
</ul>
</td>
</tr>
</tbody>
</table>

## <a name="additional-resources"></a>其他資源

[財務報表編製](financial-reporting-intro.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]