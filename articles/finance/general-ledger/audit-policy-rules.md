---
title: 稽核原則規則
description: 您可以使用稽核原則來評估費用報告、廠商發票和訂購單，以確保它們符合您建立的原則規則。 根據您指定的排程，所有與稽核原則關聯的規則都以批次模式執行。  每個原則規則都是原則規則類型的執行個體。 對於每種原則規則類型，一次只能啟用一個原則規則。
author: panolte
ms.date: 08/01/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AuditPolicyAdditionalOption, AuditPolicyRule
audience: Application User
ms.reviewer: roschlom
ms.custom: 12991
ms.assetid: 8d787017-71dc-418f-b8c2-4ea9763d9978
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bbf93f5b8b2f8d95102a52178b096d7e334894483c0ac0bacc62653aea845022
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450474"
---
# <a name="audit-policy-rules"></a>稽核原則規則

[!include [banner](../includes/banner.md)]

您可以使用稽核原則來評估費用報告、廠商發票和訂購單，以確保它們符合您建立的原則規則。 根據您指定的排程，所有與稽核原則關聯的規則都以批次模式執行。  每個原則規則都是原則規則類型的執行個體。 對於每種原則規則類型，一次只能啟用一個原則規則。 

## <a name="queries-and-query-types"></a>查詢和查詢類型

建立稽核原則規則時，先選擇原則規則類型。 原則規則類型會指定應用程式物件樹 (AOT) 查詢，以作為建立原則規則的起點。 它還指定用於原則規則的查詢類型。 該查詢會確定原則規則評估的來源文件。 它還指定來源文件中選擇文件供稽核時使用的標識法律實體和日期的欄位。 查詢類型控制查詢頁面和稽核原則規則頁面中的預設欄位。 下表顯示了可用於稽核原則規則的查詢類型。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>查詢類型</th>
<th>用途</th>
<th>更多資訊</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>條件</td>
<td>根據指定值評估來源文件屬性。</td>
<td></td>
</tr>
<tr class="even">
<td>彙總</td>
<td>透過彙總數值，根據原則規則評估多個來源文件或來源文件行。</td>
<td></td>
</tr>
<tr class="odd">
<td>取樣</td>
<td>隨機選擇來源文件的指定百分比來評估是否違反原則。</td>
<td>選擇此選項時，請使用稽核原則規則頁面指定要隨機選擇進行稽核文件的百分比。</td>
</tr>
<tr class="even">
<td>複製</td>
<td>評估來源文件以確定它們是否在指定欄位中包含重複分錄。</td>
<td>選擇此選項時，使用稽核原則規則頁面指定針對重複分錄對文件進行評估時要新增到文件選擇日期範圍的天數。</td>
</tr>
<tr class="odd">
<td>清單搜尋</td>
<td>評估特定實體的來源文件。</td>
<td>查詢的根文件定義了要進行稽核的文件。 查詢必須是包含 Dirpartytable 資料表參考的清單查詢。 此選項只能與以下 AOT 查詢一起使用：
<ul>
<li><span class="ui">AuditPolicyExpenseList</span> (費用報表監視的員工)</li>
<li><span class="ui">AuditPolicyPurchList</span> (訂購單監視的廠商)</li>
<li><span class="ui">AuditPolicyVendInvoiceList</span> (廠商發票監視的廠商)</li>
</ul>
選擇此選項時，請在稽核原則規則頁面中指定要監視的實體。</td>
</tr>
<tr class="even">
<td>關鍵字搜尋</td>
<td>評估來源文件以確定它們是否包含某些特定字詞。</td>
<td>選擇此選項時，請在稽核原則規則頁面中輸入要尋找的字詞。 稽核原則規則頁面還包括可讓您指定資料表和欄位，以評估所輸入單詞的選項。</td>
</tr>
</tbody>
</table>

## <a name="common-parameters"></a>共同參數
特定稽核原則的所有原則規則共用相同的批次參數和相同的文件選擇日期範圍。 這些參數是在 [其他選項] 頁面中為原則指定的。



## <a name="additional-resources"></a>其他資源

[稽核原則違規記錄和案例](audit-policy-violations-cases.md)
[定義來源文件的稽核原則](tasks/define-audit-policies-source-documents.md)




[!INCLUDE[footer-include](../../includes/footer-banner.md)]