---
title: 建立客戶發票
description: 銷售訂單的客戶發票是與銷售相關，由組織提供給客戶的單據。
author: ShivamPandey-msft
ms.date: 03/04/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustFreeInvoice
audience: Application User
ms.reviewer: twheeloc
ms.custom: 77772
ms.assetid: 00b4b40c-1576-4098-9aed-ac376fdeb8c5
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9ffb2c42748678ae265a706a00db327a160cc9f5
ms.sourcegitcommit: 411874545d7c326fc4aa877948a059371f0ccb3c
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/07/2022
ms.locfileid: "8451749"
---
# <a name="create-a-customer-invoice"></a>建立客戶發票

[!include [banner](../includes/banner.md)]

**銷售訂單的客戶發票** 是與銷售相關，由組織提供給客戶的單據。 這種類型的客戶發票是根據銷售訂單建立的，其中包括訂單行和品項編號。 在分類帳中指定並過帳品項編號。 子分類帳日記帳分錄不適用於銷售訂單的客戶發票。 如需相關資訊，請參閱[建立銷售訂單發票](tasks/create-sales-order-invoices.md)。

**普通發票** 與銷售訂單無關。 它包括含有分類帳科目、任意文字描述和您輸入的銷售額的訂單行。 您不能在此類發票上輸入品項編號。 您必須輸入適當的銷售稅資訊。 每個發票行上都會顯示銷售主科目，您可以點擊 **普通發票** 頁面上的 **分配金額** 將其分配到多個分類帳科目。 此外，客戶餘額從用於普通發票的過帳設定檔過帳到彙總帳戶。

更多資訊，請參閱：

[建立普通發票](../accounts-receivable/create-free-text-invoice-new.md)

[建立普通發票範本](../accounts-receivable/create-free-text-invoice-template-new.md)

[將普通發票範本分配給客戶](tasks/assign-free-text-invoice-template-customer.md)

[產生並過帳經常性普通發票](tasks/post-recurring-free-text-invoices.md)


**估價單** 是在張貼發票之前作為估計實際發票金額而準備的發票。 您可以為銷售訂單的客戶發票或普通發票列印估價單。

## <a name="using-sales-order-customer-invoice-data-entities"></a>使用銷售訂單客戶發票資料實體
您可以使用資料實體匯入和匯出有關銷售訂單的客戶發票的資訊。 銷售發票抬頭和銷售發票行的資訊有不同的實體。

以下實體可用於銷售發票抬頭的資訊：

- **銷售發票日記帳抬頭** 實體 (SalesInvoiceJournalHeaderEntity) 
- **銷售發票抬頭 V2** 實體 (SalesInvoiceHeaderV2Entity)

建議使用 **銷售發票日記帳抬頭** 實體，因為它為銷售表頭匯入和匯出提供了更高效能的體驗。 該實體不包含 **銷售稅金額**(INVOICEHEADERTAXAMOUNT) 欄，其表示銷售發票抬頭上的銷售稅值。 如果您的業務案例需要該資訊，請使用 **銷售發票抬頭 V2** 實體匯入和匯出銷售發票抬頭資訊。

以下實體可用於銷售發票行的資訊：

- **客戶發票行** 實體 (BusinessDocumentSalesInvoiceLineItemEntity)
- **銷售發票行 V3** 實體 (SalesInvoiceLineV3Entity)

當確定要使用哪個行實體進行匯出時，請考慮是使用完全推送還是增量推送。 此外，請考慮資料組成。 **銷售發票行 V3** 實體支援更複雜的案例 (例如，對應到庫存欄位)。 它還支援完整推送匯出案例。 對於增量推送，建議您使用 **客戶發票行** 實體。 該實體包含的資料結構比 **銷售發票行 V3** 實體簡單得多，尤其是在不需要庫存欄位整合的情況下會是更好的選擇。 由於行實體之間對應支援的差異，**客戶發票行** 實體的效能通常比 **銷售發票行 V3** 實體高。

## <a name="post-and-print-individual-customer-invoices-that-are-based-on-sales-orders"></a>過帳和列印基於銷售訂單的單個客戶發票
使用此流程建立基於銷售訂單的發票。 如果您決定在交付貨物或服務之前向客戶開具發票，您可以執行此操作。 

在過帳該發票時，每個品項的 **未開具發票數量** 都用來自所選銷售訂單的已開具發票的數量的總數更新。 如果銷售訂單上所有品項的 **未開具發票數量** 和 **剩餘交貨量** 均為 0 (零)，則銷售訂單的狀態會改為 **已開具發票**。 如果 **未開具發票數量** 不為 0 (零)，銷售訂單狀態保持不變，可以為其輸入其他的發票。

您可以在 **所有銷售訂單** 清單頁面上查看銷售訂單的狀態。 使用 **未結客戶發票** 清單頁面以查看您過帳的發票。

## <a name="post-and-print-individual-customer-invoices-that-are-based-on-packing-slips-and-the-date"></a>過帳和列印基於裝箱單和日期的各個客戶發票
當銷售訂單的一個或多個裝箱單已過帳時使用此流程。 客戶發票是基於這些裝箱單並反映來自這些裝箱單的數量。 發票的財務資訊基於您過帳發票時輸入的資訊。 

您可以基於至今為止已運送的裝箱單行品項建立客戶發票，即使特定銷售訂單的所有品項尚未運送。 例如，如果您的法人實體每月為每位客戶開出一張發票，以涵蓋您在該月運送的所有交貨，您可能會這樣做。 每個裝箱單代表銷售訂單品項的部分或全部交貨。 

當您張貼發票時，每個品項的 **發票餘數** 數量會使用所選裝箱單的已交貨數量總計進行更新。 如果銷售訂單上所有品項的 **未開具發票數量** 和 **剩餘交貨量** 均為 0 (零)，則銷售訂單的狀態會改為 **已開具發票**。 如果 **未開具發票數量** 不為 0 (零)，銷售訂單狀態保持不變，可以為其輸入其他的發票。 

使用發票編號更新庫存交易，銷售訂單行上的 **行狀態** 欄位會改為 **已開具發票**。 

可在 **所有銷售訂單** 清單頁面上查看銷售訂單的狀態。

## <a name="consolidate-sales-orders-or-packing-slips-for-posting"></a>合併銷售訂單或裝箱單以進行過帳
當一個或多個銷售訂單準備開具發票，且您希望將它們合併到一個發票中時，使用此流程。 

您可以在 **銷售訂單** 清單頁面選擇多張發票，然後使用 **產生發票** 來合併發票。 在 **過帳發票** 頁面上，可以變更 **匯總訂單** 設定，以按訂單編號 (單個銷售訂單有多個裝箱單) 或按發票帳戶 (單個發票帳戶有多個銷售訂單) 匯總。 使用 **排列** 按鈕可根據 **匯總訂單** 設定將銷售訂單合併到單個發票。

## <a name="post-to-revenue-account-for-sales-order-lines-that-have-no-price"></a>為沒有價格的銷售訂單行過帳到收入帳戶
對於沒有價格的銷售訂單行，可以選擇更新 **總帳** 中的 **收入** 帳戶。 若要設定或查看此資訊，請前往 **應收帳款參數** 頁面的 **分類帳和銷售稅** 索引標籤上的 **將零價銷售訂單發票行過帳到收入帳戶** 參數。 (**應收帳款 > 設定 > 應收帳款參數**)。 對於沒有價格的銷售訂單發票行，選擇 **是** 以更新 **收入** 帳戶。 收入帳戶在 **庫存過帳** 參數頁面的 **銷售訂單** 帳戶定義索引標籤上定義。如果未選擇此選項，則沒有價格資訊的行將不會過帳到 **收入** 帳戶。

## <a name="additional-settings-that-change-the-posting-behavior"></a>變更過帳行為的其他設定
以下欄位會變更過帳流程的行為。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>欄位</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>數量</td>
<td>選擇單據過帳所依據的數量。 可用的選項會有所不同，具體取決於您過帳的單據類型，例如裝箱單或發票。
<ul>
<li><strong>目前交貨量</strong> – 選擇在<strong>目前交貨量</strong>欄位中輸入的所有數量。 使用此選項確認或交付部分訂單。</li>
<li><strong>已揀料</strong>–選擇所有已揀料的數量。</li>
<li><strong>全部</strong> – 選擇尚未按目前文件類型進行更新的全部銷售訂單的數量。</li>
<li><strong>裝箱單</strong> – 選擇所有已透過裝箱單更新的數量。</li>
<li><strong>揀料數量和未庫存產品</strong> – 選擇所有已揀料的數量和所有未庫存產品的全部數量。</li>
</ul></td>
</tr>
<tr class="even">
<td>過帳</td>
<td><ul>
<li>選擇此選項以記錄銷售訂單。</li>
<li>清除此選項以列印格式銷售訂單。 <strong>請注意：</strong>如果您為付款計劃簽訂了協定，則付款計劃不會顯示在預估銷售訂單上。 付款計劃僅顯示在實際銷售訂單上。</li>
</ul></td>
</tr>
<tr class="odd">
<td>後期選項</td>
<td>選擇此選項以稍後套用選定的查詢。 此選項用於批次作業。 執行批次作業時執行查詢。</td>
</tr>
<tr class="even">
<td>減少數量</td>
<td>選擇此選項可在單據過帳時自動減少交貨數量，使交貨數量等於可用庫存。</td>
</tr>
<tr class="odd">
<td>列印</td>
<td>選擇何時列印單據：
<ul>
<li><strong>目前</strong> – 在每張發票更新後列印單據。</li>
<li><strong>之後</strong> – 更新所有發票後列印單據。</li>
</ul>
<strong>請注意：</strong>僅當您選擇<strong>列印發票</strong>、<strong>列印確認</strong>、<strong>列印揀料單</strong>或<strong>列印裝箱單</strong>選項時，<strong>列印</strong>欄位才可用。 例如，在<strong>表單排</strong>序頁面中，您已將系統設定為按發票科目對資訊進行排序。 然後您可以選擇<strong>之後</strong>以按發票帳戶排序的批次列印單據。 否則，將在處理完成之前打印文檔，並且不會按照<strong>表單排序</strong>頁面中指定的順序對文檔進行排序。</td>
</tr>
<tr class="even">
<td>列印發票</td>
<td>選擇此選項以列印發票。 如果關閉此選項，您可以在不列印的情況下過帳發票。</td>
</tr>
<tr class="odd">
<td>發送電子郵件</td>
<td>選擇此選項可在發票過帳後將銷售訂單的發票作為電子郵件附件發送給客戶。 附件以 PDF 和 XML 檔案格式發送。 此選項僅當您在<strong>電子發票參數</strong>頁面上選擇<strong>啟用 CFD (電子發票)</strong>選項時，此選項才可用。 <strong>請注意：</strong>(MEX) 此控制僅適用於主要地址在墨西哥的法人實體。</td>
</tr>
<tr class="even">
<td>使用列印管理目的地</td>
<td>選擇此選項可以使用在<strong>列印管理設定</strong>頁面上為交易、單據或模組指定的列印設定。</td>
</tr>
<tr class="odd">
<td>檢查信用額度</td>
<td>選擇在執行信用額度檢查時應分析的資訊。
<ul>
<li><strong>無</strong> – 無需進行信用額度檢查。</li>
<li><strong>餘額</strong> – 依據客戶餘額檢查信用額度。</li>
<li><strong>餘額 + 裝箱單或產品收據</strong> – 根據客戶餘額和交貨檢查信用額度。</li>
<li><strong>餘額 + 全部</strong> – 根據客戶餘額、交貨及未結訂單檢查信用額度。</li>
</ul></td>
</tr>
<tr class="even">
<td>貸項更正</td>
<td>選擇此選項可在憑證交易記錄中將貸項通知單顯示為借項。</td>
</tr>
<tr class="odd">
<td>貸方剩餘數量</td>
<td>如果要過帳貸方通知單，請選擇此選項以保留訂單的剩餘數量。 如果清除此選項，則剩餘數量設定為 0 (零)。</td>
</tr>
<tr class="even">
<td>匯總更新</td>
<td>選擇如何匯總多個銷售訂單：
<ul>
<li><strong>無</strong> - 不匯總銷售訂單。 例如，將為每個銷售訂單建立單獨的發票。</li>
<li><strong>發票帳戶</strong> – 根據在<strong>匯總更新參數</strong>頁面上設定的條件、匯總所有選定的訂單。</li>
<li><strong>訂單</strong> – 將選定範圍的訂單匯總到您指定的一個訂單中。 將根據在<strong>匯總更新參數</strong>頁面上設定的條件，對所選訂單進行匯總。 如果選擇此選項，則必須在<strong>銷售訂單</strong>欄位中選擇此值。</li>
<li><strong>自動匯總</strong> – 如果已在<strong>匯總更新</strong>頁面上指定了匯總更新，則根據在<strong>匯總更新參數</strong>頁面上設定的條件對所有選定的訂單進行匯總。 如果未指定匯總更新，訂單將單獨過帳訂單。</li>
<li><strong>裝箱單</strong> – 對於每張裝箱單，將所選範圍內的訂單匯總到一張發票中。 僅當在<strong>數量</strong>欄位中選擇<strong>裝箱單</strong>後，此選項才可用。</li>
</ul></td>
</tr>
</tbody>
</table>







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
