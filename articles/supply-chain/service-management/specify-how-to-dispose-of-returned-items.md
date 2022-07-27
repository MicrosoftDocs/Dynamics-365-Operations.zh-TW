---
title: 指定如何處置退回的品項
description: 指定如何處置退回的品項。
author: kamaybac
ms.date: 05/07/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventQuarantineOrder
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e609c1c285b34a5416a2058809b2fc4fafb73fca
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448404"
---
# <a name="specify-how-to-dispose-of-returned-items"></a>指定如何處置退回的品項

[!include [banner](../includes/banner.md)]

處理退貨單時，必須指定退貨原因代碼來識別產品被退回的原因。 您還必須指定處置代碼和處置動作，以確定應如何處理退回的產品。

建立退貨單、登記品項到達或對物料到達執行裝箱單更新，以及結束檢疫單時，可以套用處置代碼。

您可以定義支援業務流程所需的任何處置代碼。 下表提供了一組常用代碼來指派退回品項處置。

<table>
<colgroup>
<col />
<col />
<col />
</colgroup>
<thead>
<tr class="header">
<th><p>處置類型</p></th>
<th><p>常用代碼</p></th>
<th><p>描述</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>處置</p></td>
<td><p>SC</p></td>
<td><p>報廢/銷毀</p></td>
</tr>
<tr class="even">
<td><p>處置</p></td>
<td><p>DC</p></td>
<td><p>捐贈給慈善機構</p></td>
</tr>
<tr class="odd">
<td><p>處置</p></td>
<td><p>TD</p></td>
<td><p>第三方處置</p></td>
</tr>
<tr class="even">
<td><p>處置</p></td>
<td><p>SL</p></td>
<td><p>回收</p></td>
</tr>
<tr class="odd">
<td><p>處置</p></td>
<td><p>TS</p></td>
<td><p>第三方銷售 (二級市場)</p></td>
</tr>
<tr class="even">
<td><p>修復/修改</p></td>
<td><p>RW</p></td>
<td><p>重新作業</p></td>
</tr>
<tr class="odd">
<td><p>修復/修改</p></td>
<td><p>RF</p></td>
<td><p>再製造/翻新</p></td>
</tr>
<tr class="even">
<td><p>修復/修改</p></td>
<td><p>MD</p></td>
<td><p>修改</p></td>
</tr>
<tr class="odd">
<td><p>修復/修改</p></td>
<td><p>RP</p></td>
<td><p>修復</p></td>
</tr>
<tr class="even">
<td><p>修復/修改</p></td>
<td><p>RV</p></td>
<td><p>退回給廠商</p></td>
</tr>
<tr class="odd">
<td><p>其他</p></td>
<td><p>AI</p></td>
<td><p>按原樣使用</p></td>
</tr>
<tr class="even">
<td><p>其他</p></td>
<td><p>RS</p></td>
<td><p>轉售</p></td>
</tr>
<tr class="odd">
<td><p>其他</p></td>
<td><p>EX</p></td>
<td><p>交換</p></td>
</tr>
<tr class="even">
<td><p>其他</p></td>
<td><p>MS</p></td>
<td><p>雜項</p></td>
</tr>
</tbody>
</table>


對於您定義的每個處置代碼，您必須選擇一個處置動作。 處置動作確定處置代碼的實際和財務影響。 例如，處置動作確定退回品項的實際處理方式、退回品項所產生的財務影響，以及是否必須將更換品項發送給客戶。 您可以根據業務需要定義不限數量的處置代碼，但您只能選擇六個預先定義的處置動作。 下表介紹的是處置動作及其定義。

<table>
<colgroup>
<col />
<col />
</colgroup>
<thead>
<tr class="header">
<th><p>處置動作</p></th>
<th><p>描述</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>貸記</strong></p></td>
<td><p>將物品返回庫存並貸記客戶。</p></td>
</tr>
<tr class="even">
<td><p><strong>僅限貸記</strong></p></td>
<td><p>貸記客戶，不要求或期待客戶退回物品。</p></td>
</tr>
<tr class="odd">
<td><p><strong>報廢</strong></p></td>
<td><p>報廢品項並貸記客戶。</p></td>
</tr>
<tr class="even">
<td><p><strong>更換和貸記</strong></p></td>
<td><p>報廢品項，建立更換訂單並貸記客戶。</p></td>
</tr>
<tr class="odd">
<td><p><strong>更換和報廢</strong></p></td>
<td><p>報廢品項，建立更換訂單並貸記客戶。</p></td>
</tr>
<tr class="even">
<td><p><strong>退回給客戶</strong></p></td>
<td><p>拒絕所退回的品項，並將其退給客戶。</p></td>
</tr>
</tbody>
</table>

## <a name="select-a-disposition-code-for-a-quarantine-order"></a>選擇檢疫單的處置代碼

1. 移至 **庫存管理** \> **定期** \> **品質管理** \> **檢疫單**。
1. 對於現有的檢疫單，請從 **概觀** 索引標籤上的 **處置代碼** 欄位中選擇動作。

## <a name="see-also"></a>另請參閱

[檢疫單 (表單)](/dynamicsax-2012//quarantine-order-form)

[處置代碼 (表單)](https://technet.microsoft.com/library/hh597113\(v=ax.60\))

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
