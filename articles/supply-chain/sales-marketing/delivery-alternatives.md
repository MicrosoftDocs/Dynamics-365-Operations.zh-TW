---
title: 交貨備選方案
description: 銷售訂單接受者可以使用交貨備選方案頁面探索替代訂單履行選項。
author: Henrikan
ms.date: 04/10/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SalesLineDeliveryDetails
audience: Application User
ms.reviewer: kamaybac
ms.custom: 271623
ms.assetid: 527f6084-44fe-41bb-924f-4386e926358a
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: henrikan
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: f58f7923d82f3aa371ba916352211195870f9a75
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448542"
---
# <a name="delivery-alternatives"></a>交貨備選方案

[!include [banner](../includes/banner.md)]

銷售訂單接受者可以使用 **交貨備選方案** 頁面以探索替代訂單履行選項。

**交貨備選方案** 頁面佈局提供了所有替代選項的概觀。 它還讓訂單接受者越過目前公司以尋找履行機會。 他們現在可以查看公司間的機會和來自外部供應商的機會。 銷售訂單接受者可以依據交貨日期將選項排序，以查看交貨備選方案的智慧型清單。 此外，參數可以協助他們更妥當地管理建議的交貨。 由於運輸時間會影響交貨日期，因此銷售訂單接受者可以探索承運人提供的各種運輸選擇。 由於每個建議都顯示了詳細資訊，因此訂單接受者可以直接從 **交貨備選方案** 頁面做出明智的決定。

## <a name="open-the-delivery-alternatives-page"></a>開啟交貨備選方案頁面

你可以從銷售訂單列開啟 **交貨備選方案** 頁面。

1. 選擇 **產品和供應 \> 交貨備選方案**。
1. 選擇 **線路詳情 \> 交貨 \> 交貨備選方案。**

你還可以使用以下方式開啟 **交貨備選方案** 頁面：開啟 **銷售訂單處理和查詢** 工作區，然後選擇 **訂單和我的最愛 \> 延遲訂單列 \> 交貨備選方案** **附註：** 你只有在滿足以下兩個條件時才能開啟 **交貨備選方案** 頁面：

- 填寫所有必填的銷售列資訊。
- **交貨日期控制** 欄位被設定為 **沒有** 以外的值。

## <a name="delivery-date-control-methods"></a>交貨日期控制方法

交貨日期控制方法決定系統如何確定交貨日期、如何計算交貨備選方案以及顯示什麼資訊。 請注意，交貨日期控制會考慮日曆。 因此，以下日曆會影響建議的收貨日期：倉庫日曆、運輸日曆、供應商日曆和客戶日曆。 下表描述了每一種交貨日期控制的方法。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><strong>方法</strong></td>
<td><strong>描述</strong></td>
</tr>
<tr class="even">
<td><strong>無</strong></td>
<td><ul>
<li>不支援銷售列的交貨備選方案。 此選項會關閉交貨日期控制。</li>
</ul></td>
</tr>
<tr class="odd">
<td><strong>銷售提前期</strong></td>
<td><ul>
<li>交貨備選方案是根據預定義的銷售提前期計算的。 運輸天數會依據交貨方式計算。</li>
<li>交貨備選方案包括擁有現有庫存的倉庫和供需訂單。</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>ATP</strong></td>
<td><ul>
<li>交貨備選方案是根據可承諾 (ATP) 邏輯計算的。 目前的可用性和預期的未來可用性會列入考慮。 運輸天數會依據交貨方式計算。</li>
<li>交貨備選方案包括擁有現有庫存的倉庫和供需訂單。</li>
</ul></td>
</tr>
<tr class="odd">
<td><strong>ATP + 發行保證金</strong></td>
<td><ul>
<li>交付備選方案的計算與 ATP 方法相同，但在計算中會包含發行保證金。</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>CTP</strong></td>
<td><ul>
<li>交貨備選方案是根據承諾能力 (CTP) 邏輯計算的。 MRP 爆炸用於確定可用性。 請注意，CTP 至少會將交貨日期與銷售提前期相抵消。 運輸天數會依據交貨方式計算。</li>
<li>交貨備選方案包括對以下倉庫的建議：
<ul>
<li>目前倉庫</li>
<li>預設倉庫</li>
<li>所有擁有現有庫存的倉庫</li>
<li>所有擁有供應訂單的倉庫</li>
<li>擁有有效物料清單 (BOM) 版本的所有倉庫</li>
</ul></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="view-information-about-delivery-alternatives"></a>查看有關交貨備選方案的資訊

本節介紹有關交貨備選方案的資訊，這些資訊可在 **交貨備選方案** 頁面的每一張 FastTab 上取得。

### <a name="the-product-fasttab"></a>產品 FastTab

此 FastTab 顯示產品摘要和目前銷售線的詳細資訊。

### <a name="the-delivery-alternatives-fasttab"></a>交貨備選方案 FastTab

此 FastTab 顯示按收貨日期排序的交貨備選方案清單。 在清單上方，您可以選擇建議依據的選項。 您還可以選擇交貨方式，此方式會決定運輸天數。 可以使用以下選項：

- **包括其他產品變體** - 此選項適用於具有產品變體的產品。 它將包括產品其他變體的交貨備選方案。 此選項不適用於 CTP。
- **包括部分數量** - 預設情況下，僅包含滿足銷售列全部數量的建議。 選擇此選項以包含僅部分履行訂單列的建議。 當客戶要求交貨日期更早並接受部分交貨時，此選項很有用。
- **包括以後的日期** - 預設情況下，僅顯示比銷售行當前日期更好 (更早) 的建議。 選擇此選項以包括較晚的日期。 此選項在日期以外的參數具有優先權的情況下很有用。 例如，可能偏好特定的供應商或倉庫。
- **交貨方式** - 選擇偏好的交付方式以優化運輸時間和成本。 您將立即看到對建議的交貨備選方案的影響。 因此，很容易比較備選方案。
- **包括採購** - 選擇採購時，建議的交貨備選方案包括從外部供應商和企業中的其他公司 (公司間) 採購的選項。 這 **包括採購** ATP 和 ATP + Issue 保證金交割日期控制支持選項。 包括來自產品的預設採購供應商和所有批准的產品供應商的採購選項。
- 對於外部供應商，計算會基於採購提前期。
- 對於公司內部，計算會根據採購公司的交貨日期控制考慮採購公司的可用資源。
- **交貨類型** (採購相關)
  - **庫存** - 產品從採購倉庫運送到銷售線上的站點/倉庫。 然後將它們從該倉庫運送給客戶。
  - **直接發貨** - 產品直接從採購倉庫運送給客戶。

### <a name="the-availability-information-fasttab"></a>可用性資訊 FastTab

此 FastTab 上的資訊與所選的交貨備選方案列相關。 顯示以下資訊，具體取決於銷售列的交貨日期控制：

- **銷售提前期**
  - **今天可用** - 顯示目前現有實物、預留實物和可用實物庫存。
  - **參數** - 顯示庫存單位和銷售提前期。

- **ATP 和 ATP + 發行保證金**
  - **今天可用** - 顯示目前現有實物、預留實物和可用實物庫存。
  - **參數** - 顯示庫存單位和銷售提前期。
  - **未來可用性** - 顯示所選站點和倉庫的目前和未來可用性的圖形表示 **送貨備選方案**。 您可以選擇圖表欄以查看有關產品未來可用性的更多詳細資訊。 滑桿顯示 ATP 時間範圍內的相關需求和供應訂單清單。

- **CTP**
  - **今天可用** - 顯示目前現有實物、預留實物和可用實物庫存。
  - **參數** - 顯示庫存單位和銷售提前期。
  - **爆炸** - 顯示所選交貨備選方案的供應爆炸。 您可以使用 **設置** 更改展開中顯示的字段和庫存維度。

### <a name="the-impact-of-selected-alternative-fasttab"></a>所選備選方案 FastTab 的影響

此 FastTab 強調了所選交貨備選方案的影響。 如果您選擇 **確定**，銷售列將使用 SELECTED 欄中反白顯示的值進行更新。 請注意，如果所選交貨備選方案上的數量小於銷售列上的數量，則會建立交貨排程，並將訂單行拆分為兩列：一列用於選定數量，另一列用於剩餘數量。 您還可以更新商業列，使其與計劃列匹配並影響定價。

## <a name="additional-resources"></a>其他資源

[訂單承諾](delivery-dates-available-promise-calculations.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]