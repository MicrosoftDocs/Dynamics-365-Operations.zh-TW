---
title: 廠商發票和發票審核日記帳的預設沖銷帳戶
description: 本主題將幫助您決定應為發票日記帳指派的預設科目。
author: abruer
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 62093
ms.assetid: 553933ca-928d-4031-bb8c-f9cff458320b
ms.search.region: global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e1b0184850602191da5448df25779437f70e5c3182e1b7b70d92d4c406e08599
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450519"
---
# <a name="default-offset-accounts-for-vendor-invoice-and-invoice-approval-journals"></a>廠商發票和發票審核日記帳的預設沖銷帳戶

[!include [banner](../includes/banner.md)]

預設沖銷科目用於以下廠商發票日記帳頁面：

-   發票日記帳
-   發票審核日記帳

使用下表幫助您決定應為發票日記帳分配的預設科目。

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th>在此處設定預設帳戶</th>
<th>提供預設帳戶的位置</th>
<th>此選項如何影響處理</th>
<th>何時應使用此選項</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>廠商群組</strong> – 在<strong>預設帳戶設定</strong>頁面上為廠商群組設定預設的沖銷帳戶，可以從<strong>廠商群組</strong>頁面打開此頁。</td>
<td><ul>
<li>廠商帳戶</li>
<li>如果沒有為廠商帳戶指定預設帳戶，則為廠商群組中廠商帳戶的日記帳分錄</li>
</ul></td>
<td>廠商群組的預設沖銷帳戶在<strong>預設帳戶設定</strong>頁面上顯示為廠商的預設沖銷帳戶。 您可以從<strong>所有廠商</strong>清單頁面中開啟此頁面。</td>
<td>如果隨著時間推移，您常為同一廠商群組的同類物品付款，則使用此選項。</td>
</tr>
<tr class="even">
<td><strong>廠商帳戶</strong> – 在<strong>預設帳戶設定</strong>頁面上為廠商帳戶設定預設的沖銷帳戶，可以從<strong>廠商</strong>頁面打開此頁。</td>
<td>廠商帳戶的日記帳分錄</td>
<td>廠商帳戶的預設沖銷帳戶顯示為廠商帳戶的日記帳分錄的預設沖銷帳戶。</td>
<td>如果隨著時間推移，您常為同一廠商的同類物品付款，則使用此選項。</td>
</tr>
<tr class="odd">
<td><strong>日記帳名稱</strong> – 在<strong>日記帳名稱</strong>頁面上為日記帳設定預設沖銷帳戶。 選擇<strong>固定沖銷帳戶</strong>選項。 請注意，如果日記帳名稱的日記帳類型為<strong>發票登記</strong>或<strong>審核</strong>，則不能在日記帳名稱指定預設沖銷科目。</td>
<td><ul>
<li>使用日記帳名稱的日記帳標題</li>
<li>使用日記帳名稱的日記帳中的日記帳分錄</li>
</ul></td>
<td>如果選擇<strong>日記帳名稱</strong>頁面中的<strong>固定沖銷帳戶</strong>選項，則日記帳名稱的沖銷科目會覆寫廠商或廠商群組的預設沖銷科目。</td>
<td>使用此選項可為記入特定帳戶的特定成本和費用設定日記帳，而不管廠商屬於哪個廠商或廠商群組。</td>
</tr>
<tr class="even">
<td><strong>日記帳名稱</strong> – 在<strong>日記帳名稱</strong>頁面上為日記帳設定預設沖銷帳戶。 清除<strong>固定沖銷帳戶</strong>選項。 請注意，如果日記帳名稱的日記帳類型為<strong>發票登記</strong>或<strong>審核</strong>，則不能在日記帳名稱指定預設沖銷科目。</td>
<td><ul>
<li>日記帳標題</li>
<li>使用日記帳名稱的日記帳中的日記帳分錄</li>
</ul></td>
<td>這些預設分錄用於日記帳標題頁面，而日記帳標題頁面上的沖銷科目用作日記帳憑單頁面上的預設分錄。 只要預設科目不是為廠商帳戶設定的，就使用<strong>日記帳名稱</strong>頁面中的預設科目。</td>
<td>當未分配預設廠商沖銷帳戶時，使用此選項設定預設帳戶。</td>
</tr>
<tr class="odd">
<td><strong>日記帳標題</strong> – 在日記帳憑單頁面上為日記帳設定預設沖銷帳戶作為預設分錄。 請注意，如果日記帳標題的日記帳類型為<strong>發票登記</strong>或<strong>審核</strong>，則不能在日記帳名稱指定預設沖銷科目。</td>
<td>日記帳中的日記分錄</td>
<td>為日記帳的預設對方科目在日記帳憑單頁面中作為預設分錄。</td>
<td>如果日記帳中的大多數分錄具有相同的沖銷科目，則使用此選項有助於加快資料輸入。</td>
</tr>
</tbody>
</table>







[!INCLUDE[footer-include](../../includes/footer-banner.md)]