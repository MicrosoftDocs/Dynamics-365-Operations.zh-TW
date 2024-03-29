---
title: 銷售退貨
description: 本主題提供有關退貨單流程的資訊。 其中包括有關客戶退貨及其對成本計算和現有庫存數量影響的資訊。
author: Mirzaab
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReturnTableListPage, ReturnTable, ReturnTableListPagePreviewPane, ReturnTableReferences, SalesReturnExpiredOrdersPart, SalesReturnFindOrderFormPart
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.assetid: 98a4b517-e606-4036-b55f-1ab248898bdf
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5cfcfd165b5f7b97d1ee88175b3f6c9d418c30c2
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8447801"
---
# <a name="sales-returns"></a>銷售退貨

[!include [banner](../includes/banner.md)]

本主題提供有關退貨單流程的資訊。 其中包括有關客戶退貨及其對成本計算和現有庫存數量影響的資訊。

客戶可能出於各種原因退貨。 例如，某物品可能有瑕疵，或者可能不符合客戶的期望。 當客戶發出退貨要求時，退貨流程就開始了。 收到客戶的要求後，將建立退貨單。

## <a name="return-order-process"></a>退貨單流程
下圖提供退貨單流程的概觀。  

[![退貨單流程。](./media/salesreturns01.jpg)](./media/salesreturns01.jpg)  

退貨單流程有兩種類型：實際退貨和僅貸記。

-   **實際退貨** – 退貨單授權對實際退回產品。
-   **僅貸記** – 退貨單為客戶貸記授權，但不要求客戶實際退回產品。

### <a name="physical-return-order-process"></a>實際退貨單流程

1.  **建立退貨單。** 正式記錄授權，供客戶退回任何有瑕疵或不想要的產品。 退貨單不要求公司接受退回的產品或為客戶提供貸記。 如果接受退貨，您可以授權在有瑕疵的品項退回之前發送更換品項。
2.  **到達倉庫進行檢查。** 根據退貨單文件完成初步檢查和驗證。 退貨單還支援對退回的品項進行隔離，以進行額外的檢驗和品質控制。
3.  **確定處置。** 完成檢查流程，並決定應如何處理退回的產品。 作為此步驟的一部分，決定您是向客戶授與貸記、拒絕產品退貨，還是接受產品退貨、報廢產品，然後將更換產品發送給客戶。
4.  **產生裝箱單。** 產生裝箱單，並認可您在步驟 3 中做出的處置決定。 完成物流流程。
5.  **產生發票。** 關閉退貨單。

### <a name="credit-only-process"></a>僅貸記流程

1.  **建立退貨單。** 正式記錄授權，供客戶在不退回任何有瑕疵品或不想要產品的情況下接收貸記。 **僅貸記** 處置代碼授權決定為沒有實際退貨的客戶授與貸記。
2.  **產生發票。** 產生貸方通知單，然後關閉退貨單。

## <a name="return-material-authorization"></a>退料授權
退料授權 (RMA) 處理以銷售訂單功能為基礎。 RMA 登記為退貨單，該退貨訂單建立為銷售訂單，且可能有其他與之關聯的銷售訂單，其稱為更換單。 兩個銷售訂單都連結到原始 RMA 編號。

-   **退貨單** – 若要登記 RMA，請建立退貨單，這是指派類型為 **退貨單** 的銷售訂單。 對 RMA 資訊所做的任何變更都會在銷售訂單中自動更新。 在退貨單的狀態為 **開放** 前，其不會顯示在銷售訂單清單中。 使用 RMA 來處理退回品項的到達和接收，以及授權僅貸記處置動作 (請參閱 **處置代碼和處置動作** 一節)。 所有其他後續流程都必須在銷售訂單中處理。
-   **更換單** – 當必須將更換單運送給客戶時，RMA 可以包括第二個關聯的銷售訂單。 您可以手動為 RMA 建立更換單，以支援立即裝運。 或者，可以在為具有指示換貨之處置代碼的 RMA 行項完成到達、檢驗和收貨後自動建立更換單。 更換單具有與銷售訂單相同的功能。 例如，您可以使用它來將自訂產品配置為更換品項、建立生產訂單以修復退回的品項、建立直接交貨定購單以從廠商處發送更換品項，或支援其他用途。

## <a name="create-a-return-order"></a>建立退貨單
當客戶連絡您的組織以退回有瑕疵或不想要的產品和/或要為其貸記時，退貨單流程就開始了。 在您的組織接受退貨後，將透過退貨單記錄退貨。 該退貨單成為退貨產品內部處理的重點。 下圖顯示了建立退貨單的過程。  

[![建立退貨單的過程。](./media/salesreturn02.png)](./media/salesreturn02.png)

### <a name="create-a-return-order-header"></a>建立退貨單標題

建立退貨單時，必須包含下表中的資訊。

| 欄位              | 描述                                              | 附註                                                                                                                                                                                                                                                                                                                                        |
|--------------------|----------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 客戶帳戶   | 對客戶表的參考                       | 必須提供現有的客戶帳戶。                                                                                                                                                                                                                                                                                                  |
| 交貨地址   | 品項退回的地址                 | 預設為使用組織的地址。 如果在標題中選擇了特定倉庫，則交貨地址改為倉庫的交貨地址。 您可以在 **退貨單詳細資料** 頁面上變更此地址。                                                                                                  |
| 站點/倉庫     | 接收退回產品的站點或倉庫 | 退貨單的收貨地址根據站點或倉庫的收貨地址決定。                                                                                                                                                                                                                                 |
| RMA 編號         | 指派給退貨單的識別碼              | RMA 編號在整個退貨單流程中當作替用索引鍵使用。 指派的 RMA 編號是以 **應收帳款參數** 頁面上設定的 RMA 編號序列為基礎。                                                                                                                              |
| 最後期限           | 可以退回商品的最後日期               | 預設值的計算方法是目前日期加上有效期限。 例如，如果退貨僅在退貨單建立之日起 90 天內有效，且退貨單是在 5 月 1 日建立的，則該欄位中的值為 **7 月 30 日**. 有效期限在 **應收帳款參數** 頁面上設定。 |
| 退貨原因代碼 | 客戶退貨的原因          | 在使用者定義的原因代碼清單中選擇原因代碼。 您隨時可以更新此欄位。                                                                                                                                                                                                                                    |

### <a name="create-return-order-lines"></a>建立退貨單行

完成退貨標題後，您可以使用以下其中一種方法建立退貨行：

-   手動輸入每個退貨行的品項詳細資料、數量和其他資訊。
-   使用 **尋找銷售訂單** 功能。 建議在建立退貨單時使用此功能。 **尋找銷售訂單** 功能建立從退貨行到已開立發票銷售訂單行的參考，並從銷售行擷取行詳細資料，例如品項編號、數量、價格、折扣和成本值。 該參考有助於保證當產品退回公司時，其價值與銷售時的單位成本相同。 該參考還會驗證沒有以超過發票上銷售數量的數量建立退貨單。

>[附註！] 參考銷售訂單的退貨行將作為銷售的更正或撤銷處理。 有關詳細資訊，請參閱本主題後面的「過帳到分類帳」一節。

### <a name="charges"></a>費用

費用和收費可以透過以下一種或多種方新增到退貨單中：

-   您可以手動將費用新增到退貨單標題、退貨單行或兩者。
-   費用可以作為退貨原因代碼的函數，自動新增到退貨單標題中。
-   可以根據行的處置代碼將費用自動新增到退貨單行。

將退貨原因代碼或處置代碼指派給該行後會自動新增費用。 如果稍後變更了原因代碼，不會刪除現有的費用項目，但可能會根據新的原因代碼新增新的費用項目。 當您將費用新增到退貨單行時，當行或行訂單為負數時，計算為行或訂單值百分比的費用將變為負數，除非百分比也是負數。 具有負值的費用代表對客戶的貸項。

### <a name="return-reason-codes"></a>退貨原因代碼

透過將原因代碼套用於退貨，您可以幫助簡化退貨模式的分析。 原因代碼提供客戶想退貨原因的資訊。 部分組織有許多原因代碼。 這些組織可能會將原因代碼分組為原因代碼群組，以獲得更好的概觀和累積報告。

### <a name="disposition-codes-and-disposition-actions"></a>處置代碼和處置動作

退貨單流程中的一個重要步驟是將處置代碼指派給退貨單行，作為到達登記的一部分。 處置代碼決定以下資訊：

-   **財務影響** – 是否應將退回品項的記入客戶貸記，是否應將任何費用新增到退貨單行？
-   **退回品項的處置** – 該品項是否可以重新新增到庫存中，是否應該報廢，或者應該退回給客戶？
-   **退回品項的物流** – 是否應該發送更換品項給客戶？

除了決定退回貨物的處置方式外，處置代碼還可能導致將費用套用於退貨行。 它們還可用於分組收益，以進行統計分析。 處置代碼會做為退貨單設定的一部分進行定義。 但是，每個處置代碼都必須參考其中一個內鍵處置動作。 下表列出了內建處置代碼及其動作。 **重要：** 如果不應退回品項，但仍應為客戶記入貸記，則為退貨行指派 **僅貸記** 處置代碼。

<table>
<thead>
<tr class="header">
<th>處置代碼</th>
<th>財務影響</th>
<th>對物流的影響</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>僅貸記</td>
<td><ul>
<li>客戶的貸記是銷售價格減去任何費用或收費。</li>
<li>報廢品項的損失過帳到分類帳。</li>
</ul></td>
<td>該品項不應退回。 此處置動作用於以下情況：
<ul>
<li>當事人之間有足夠的信任。</li>
<li>退回瑕疵品項的成本過高。</li>
<li>不允許將品項&#39;退回庫存。 由於其他條件，不需要&#39;實際退回。</li>
</ul></td>
</tr>
<tr class="even">
<td>貸記</td>
<td><ul>
<li>客戶的貸記是銷售價格減去任何費用或收費。</li>
<li>退貨商品的成本會增加庫存價值。</li>
</ul></td>
<td>該品項被退回並新增回庫存中。</td>
</tr>
<tr class="odd">
<td>更換並貸記</td>
<td><ul>
<li>客戶的貸記是銷售價格減去任何費用或收費。</li>
<li>退貨品項的成本會增加庫存價值。</li>
<li>為更換建立單獨的銷售訂單並單獨處理。</li>
</ul></td>
<td>該品項被退回並新增回庫存中。</td>
</tr>
<tr class="even">
<td>更換並報廢</td>
<td><ul>
<li>客戶的貸記是銷售價格減去任何費用或收費。</li>
<li>報廢品項的損失過帳到分類帳。</li>
<li>為更換建立單獨的銷售訂單並單獨處理。</li>
</ul></td>
<td>該品項被退回並報廢。</td>
</tr>
<tr class="odd">
<td>退回給客戶</td>
<td>無，除任何費用或收費。</td>
<td>該品項被退回，但在檢查後寄還給客戶。 如果品項已故意毀損或保固已失效，則可能會使用此處置動作。</td>
</tr>
<tr class="even">
<td>報廢</td>
<td><ul>
<li>客戶的貸記是銷售價格減去任何費用或收費。</li>
<li>報廢品項的損失過帳到分類帳。</li>
</ul></td>
<td>退回或報廢品項。</td>
</tr>
</tbody>
</table>

## <a name="arrival-at-the-warehouse-for-inspection"></a>到達倉庫進行檢查
這些物品必須先進行到貨登記和選用檢驗，才能藉由過帳裝箱單實際接收退回的品項並入庫。 下圖提供到貨流程的概觀。 以下小節說明圖中所示的每個步驟。  

[![到貨流程。](./media/salesreturn03.png)](./media/salesreturn03.png)  

該流程有其他幾個本主題未涵蓋的變體。 以下是這些驗證中的一部分：

-   不要使用 **到貨概觀** 清單來建立到貨日記帳。 請改為手動建立到貨日記帳。 退貨單會有 **銷售訂單** 作為參考。
-   如果您使用的是 Warehouse Management，則會產生托盤運輸。 在托盤運輸過程中，退貨行的狀態為 **已到貨**。
-   透過使用 **登記** 功能，直接從退貨單行登記退回品項的到貨。

在到貨流程中，退貨會與倉庫到貨的一般流程整合。 到達流程還支援為必須經過單獨檢驗的退回品項建立隔離單。

### <a name="identify-products-in-the-arrival-overview-list"></a>在到貨概觀清單中識別產品

**到貨概觀** 頁面會列出所有計劃的傳入到貨。 
>[附註！] 退貨訂單的到貨必須與其他類型的到貨交易分開處理。 在 **到貨概觀** 頁面 (例如，透過使用隨附的 RMA 文件)，在動作窗格上點選 **開始到貨** 以建立和初始化與到貨相符的到貨日記帳。

### <a name="edit-the-arrival-journal"></a>編輯到貨日記帳

透過將 **隔離管理** 選項設為 **是**，您可以為退貨行建立隔離單。 如果行已發送隔離進行檢驗，則不能指定處置代碼。 
 
如果在品項的庫存模型群組中將 **隔離管理** 選項設為 **是**，**日記帳行** 頁面上的 **隔離管理** 選項將標記為到貨日記帳行且不能進行變更。 如果將行發送隔離，則必須指定適當的隔離倉庫。 

如果到貨行未送檢驗，倉庫到達文員必須直接在到貨日記帳行上指定處置代碼，然後過帳到貨日記帳。 如果不應為退貨行的全部數量指派相同的處置代碼，或者如果尚未收到該行的全部數量，則必須分割該行。 分割到貨日記帳行時，也會分割退貨行 (**SalesLine**) 並建立新的批次識別碼。 您可以透過減少到貨日記帳行的數量來分割行。 過帳日記帳時，將為剩餘數量建立狀態為 **已預期** 的新退貨行。 也可以透過點選 **功能** &gt; **分割** 來分割行。

### <a name="process-the-quarantine-order"></a>處理隔離單

如果退回的產品在隔離倉庫進行檢驗，任何附加處理都將在隔離單中完成。 為每個發送隔離的到貨行建立隔離單。 處置代碼表示檢驗流程的結果。 

您可以分割隔離單，就像分割到貨日記帳一樣。 如果分割隔離單，則會導致相應的退貨行分割。 輸入處置代碼後，使用 **結束** 功能或 **報告為完成** 功能完成隔離單。 如果您選擇 **報告為完成**，將在指定倉庫中建立新到貨。 然後，您可以使用 **到貨概觀** 頁面。 

如果到貨來自隔離單，則不能變更在檢驗期間指派的處置代碼。 如果您使用 **結束** 功能完成隔離單，則將自動登記批次。 有時，物品可能會從隔離退回到運送和接收部門。 例如，隔離檢查員可能不知道該物品在庫存中的儲存位置。 在這種情況下，必須更新相應的裝箱單以正確登記和處理因隔離而指定的處置代碼。 

登記退貨行時，可以將收貨確認發送給客戶。 **退貨確認** 報告類似於退貨單文件。 **退貨確認** 報告不記入日記帳，也不會登記在系統中，因為它不是退貨單流程的必要步驟。

## <a name="replace-a-product"></a>更換產品
有兩種管理產品更換的方法：

-   **預先更換** – 在收到客戶退回的產品之前更換產品。
-   **依處置代碼更換** – 自動建立新的更換單行。

### <a name="up-front-replacement"></a>預先更換

在預先更換中，更換物品可以在物品退回之前交付給客戶。 如果品項是要有備用零件來更換才能取下的機器零件，或者如果您希望客戶盡快收到更換產品，則此方法會非常實用。 預先更換單是獨立的銷售訂單。 標題資訊源自客戶，行資訊源自退貨單。 您可以獨立於退貨單編輯、處理和刪除更換單。 當您刪除更換單時，會收到一則訊息，指出該訂單已建立為更換單。 下圖顯示預先更換的流程。  

![預先更換流程。](./media/SalesReturn04.png)

退貨單包括對更換單的參考。 如果在退回有瑕疵的品項之前為退貨單建立了預先更換單，則在退回有瑕疵的品項後，您無法選擇更換處置代碼。

### <a name="replacement-by-disposition-code"></a>依處置代碼更換

如果將更換物品發送給客戶，且在退貨單上使用 **更換並報廢** 或 **更換並貸記** 處置動作，請使用下圖中顯示的流程。  

![使用處置代碼時的更換流程。](./media/SalesReturn05.png)

更換品項將使用獨立的銷售訂單 (即更換銷售訂單) 進行交付。 此銷售訂單是在產生退貨單的裝箱單時建立的。 訂單標題使用退貨單標題上參考的客戶資訊。 行資訊是從 **更換品項** 頁面中輸入的資訊中收集的。 必須為具有以「更換」字詞開頭的處置動作的行，填寫 **更換品項** 頁面。 但是，更換品項的數量和身分都沒有經過驗證或受到限制。 此行為允許以下情況：客戶需要配置或尺寸不同的相同品項，以及客戶需要完全不同的品項。 根據預設，**更換品項** 頁面會輸入相同品項。 但如果已設定此功能，則可選擇其他品項。 

>[附註！] 更換銷售訂單在建立後可以進行編輯和刪除。

## <a name="generate-a-packing-slip"></a>產生裝箱單
必須先更新該品項所屬訂單的裝箱單，退回的品項才可以入庫。 正如發票更新流程是對財務交易記錄進行更新一樣，裝箱單更新流程是對庫存記錄的實體更新。 換句話說，此流程會對庫存進行變更。 在退貨的情況下，在裝箱單更新期間會實作指派給處置動作的步驟。 產生裝箱單時，會發生以下事件：

-   在倉庫中，使用標準流程執行實際收貨。 如果庫存模型組 (**過帳實際庫存**) 和應收帳款參數 (**在分類帳中過帳裝箱單**) 設置得當，將產生分類帳過帳。
-   已使用包含「報廢」一詞的處置動作標記的品項將被報廢，並將庫存損失過帳到分類帳。
-   將接收使用 **退還給客戶** 處置動作標記的品項並交付給客戶。 這些品項對庫存沒有實際影響。
-   已建立更換銷售訂單。 此銷售訂單會根據 **更換品項** 頁面的資訊為基礎。

只能為退貨狀態為 **已登記** 的行產生裝箱單，並且只能為退貨行中的完整數量產生。 如果退貨單上有幾行具有 **已登記** 狀態，則可透過從 **過帳裝箱單** 頁面刪除其他行，為一小組行產生裝箱單。 

部分退貨是根據退貨單行 (而非退貨單裝運) 定義。 因此，如果您收到一個退貨單行上指示的完整數量，但未收到退貨單其他行中的任何數量，則該交貨不是部分交貨。 但是，如果退貨單行要求退回 10 單位的品項，但您只收到 4 單位，則該交貨為部分交貨。 如果不是所有預期的退貨品項都已到貨，則可擱置裝運，等待剩餘的退貨數量到貨。 或者，您可以登記並過帳部分數量。 作為過帳裝箱單流程的一部分，您可以將客戶裝運文件中的裝箱單參考號與訂單行相關聯。 此關聯是選擇性的，僅供參考。 它不會建立任何交易記錄更新。 

一般情況下，您可以跳過裝箱單流程，直接開立發票。 在這種情況下，您本應在產生裝箱單期間執行的步驟將在開立發票期間完成。

## <a name="generate-an-invoice"></a>產生發票
雖然 **退貨單** 頁面中包含處理退貨單物流特殊事項所需資訊和動作，您還是必須使用 **銷售訂單** 頁面以完成開立發票流程。 然後，您的組織可以同時為退貨單和銷售訂單開立發票，且同一個人可以根據需要完成開立發票流程。 若要從 **銷售訂單** 頁面查看退貨單，請點選銷售訂單編號的連結以打開關聯的銷售訂單。 您也可以在 **所有銷售訂單** 頁面上找到退貨單。 退貨單是訂單類型為 **退貨單** 的銷售訂單。

### <a name="credit-correction"></a>貸項更正

在開立發票流程中，請驗證所有雜項費用是否皆正確。 若要讓分類帳過帳變為更正 (Storno)，請在過帳發票/貸方通知單時，考慮使用 **過帳發票** 頁面中 **其他** 索引標籤上的 **貸項更正**。 
>[附註！] 根據預設，如果已啟用 **應收帳款參數** 頁面上的 **用於更正的貸方通知單** 選項，則已啟用 **貸項更正** 選項。 但是，建議不要使用 Storno 過帳退貨。

## <a name="create-intercompany-return-orders"></a>建立公司間退貨單
退貨單可以在您組織內的兩家公司之間完成。 支援以下方案：

-   涉及公司間關係的兩家公司之間的簡單公司間退貨
-   在賣方公司建立客戶退貨單時建立的公司間鏈
-   在買方公司建立廠商退貨單時建立的公司間鏈
-   外部客戶涉及公司間關係的兩家公司之間的直接交貨裝運退貨

### <a name="setup"></a>設定

下圖顯示兩家公司建立公司間關係，並利用公司間貿易需要滿足的最低設定。  

![最低設定。](./media/SalesReturn06.png)

在以下案例中，CompBuy 是買方公司，而 CompSell 是賣方公司。 通常，銷售公司將貨物運送給買方公司，或者在直接發貨的情況下，會直接運送給最終客戶。 在 CompBuy 中，廠商 IC\_CompSell 定義為與公司 CompSell 關聯的公司間端點。 同時，在 CompSell 中，客戶 IC\_CompBuy 定義為與公司 CompBuy 關聯的公司間端點。 必須在兩家公司中定義適當的動作原則詳細資料和值對應。 在直接交貨裝運案例中，在銷售公司中建立一個公司間退貨單，其也是一個公司間銷售訂單。 公司間退貨單的 RMA 編號可以從 CompSell 中的 RMA 編號序列中選取，也可以從 CompBuy 中指派給原始退貨單的 RMA 編號複製。 CompBuy 中 **PurchaseRequisition** 動作原則上的 RMA 編號設定決定了這些動作。 如果 RMA 編號是同步的，如果兩家公司使用相同的編號規則，您應該計劃降低編號衝突的風險。

### <a name="simple-intercompany-returns"></a>簡單公司間退貨

此方案涉及同一組織中的兩家公司，如下圖所示。  

![簡單公司間退貨。](./media/SalesReturn07.png)

在買方公司建立廠商退貨單或在賣方公司建立客戶退貨單時，可以建立訂單鏈。 在其他公司中建立相應的訂單，並確保廠商退貨單上的標題和行資訊反映客戶退貨單上的設定。 建立的退貨單可以包括或排除對現有客戶發票的參考 (**尋找銷售訂單**)。 兩個訂單的裝箱單和發票可以單獨處理。 例如，您不必在為客戶退貨單產生裝箱單之前為廠商退貨單產生裝箱單。

### <a name="direct-delivery-shipment-returns-among-three-parties"></a>三方間直接交貨裝運退貨

如果之前 **直接交貨** 類型的銷售已完成，且與客戶互動的公司中有針對該客戶的發票，則可以建立此方案。 在下圖中，CompBuy 公司曾向客戶 Extern 銷售產品並為其開立發票。 產品透過公司間訂單鏈直接從 CompSell 公司運送給客戶。  

![三方間直接交貨裝運退貨。](./media/SalesReturn08.png)

如果客戶 Extern 想要退回產品，則在 CompBuy 公司中為客戶建立退貨單 (RMA02)。 若要建立公司間鏈，必須將退貨單標記為直接交貨。 使用 **尋找銷售訂單** 功能為要退貨的客戶發票揀貨時，將建立有以下文件組成的公司間訂單鏈：

-   **原退貨單單：** RMA02 (CompBuy 公司)
-   **訂購單：** PO02 (CompBuy 公司)
-   **公司間退貨單：** RMA\_00032 (CompSell 公司)

建立直接交貨公司間鏈之後，必須在公司間退貨單 (CompSell 公司中的 RMA\_00032) 環境中實際處理退貨。 CompBuy 公司無法接收產品。 將處置代碼指派給公司間退貨單後，其會與原始退貨單同步，以便為原始訂單開立正確的發票。

## <a name="post-to-the-ledger"></a>過帳到分類帳
為退貨單開立發票時產生的分類帳過帳受一些重要設定和參數的影響：

-   **退貨成本價** – 對於 **標準成本** 以外的其他庫存模型，**退貨成本價** 參數決定接受品項回庫存或報廢時的成本。 若要計算正確的庫存估價，請務必正確設定 **退貨成本價**。 如果使用 **尋找銷售訂單** 功能建立參考客戶發票的退貨單行，則 **退貨成本價** 值等於所售品項的成本價。 否則，成本價的值來自品項設定或可以手動輸入。
-   **貸項更正/Storno** - **過帳發票** 頁面上的 **貸項更正** 參數決定應記錄為正 (DR/CR) 項目，還是負更正項目。

在以下範例中，退貨成本價表示為 **發票成本價**。

### <a name="example-1-the-return-order-doesnt-reference-a-customer-invoice"></a>範例 1：退貨單未參考客戶發票

退貨單不參考客戶發票。 退回的品項已記入貸方。 產生退貨單發票或貸方通知單時不選擇 **貸記更正** 參數。  

![退貨單不參考客戶發票。](./media/SalesReturn09.png)  

>[附註！] 品項主價格用作 **退貨成本價** 參數的預設值。 預設價格與出庫時的成本價不同。 因此，這代表已經產生了 3 的損失。 此外，退貨單不包括在銷售訂單上給予客戶的折扣。 因此，將出現透支。

### <a name="example-2-credit-correction-is-selected-for-the-return-order"></a>範例 2：為退貨單選擇貸項更正

範例 2 與範例 1 相同，除了產生退貨單發票時選擇了 **貸項更正** 參數。  

![選擇貸項更正的退貨單。](./media/SalesReturn10.png)  

>[附註！] 分類帳過帳做為負更正輸入。

### <a name="example-3-the-return-order-line-is-created-by-using-the-find-sales-order-function"></a>範例 3：使用「尋找銷售訂單」功能建立退貨單行

在此範例中，使用 **尋找銷售訂單** 功能建立退貨單行 建立發票時不選擇 **貸項更正** 參數。  

![使用「尋找銷售訂單」建立的退貨單行。](./media/SalesReturn11.png)  

>[附註！]**折扣** 和 **退貨成本價** 設定正確。 因此，客戶發票會精確撤銷。





[!INCLUDE[footer-include](../../includes/footer-banner.md)]