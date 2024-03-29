---
title: 資產 KPI
description: 本主題介紹資產管理中的資產 KPI。
author: johanhoffmann
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetObjectKPI
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 8bdc60d993a784ffc123d36b5e51cbd6028316f18a2dee6f4ee134a93ffc024e
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447303"
---
# <a name="asset-kpis"></a>資產 KPI

[!include [banner](../../includes/banner.md)]

 

在資產管理中，您可以計算資產和資產類型的各種關鍵績效指標 (KPI)。 您可以使用 KPI 來了解與正常運行時間、停機時間、修復時間和平均異常間隔時間 (MTBF) 等相關的資產性能摘要。

1. 按一下 **資產管理** > **查詢** > **資產** > **資產 KPI**。

2. 在 **計算資產 KPI** 對話方塊，請選取計算中使用的 **時間尺度**，並在 **起始日期** 和 **終止日期** 欄位提供期間。 

3. 在 **要包括的記錄** 快速索引標籤，如果需要，請選取要包含在計算中的特定資產和資產類型。

4. 按一下 **確定** 以開始計算。

5. 在 **摘要** 快速索引標籤，計算結果顯示在網格檢視表中。 每個資產都顯示在單獨的明細上。

6. **摘要** 快速索引標籤上選定資產的計算，會在 **選定明細的 KPI** 快速索引標籤上看到。 KPI 值的分類如下 **時間**、**可用性**、**工單**、**維護**、**異常**、**維護停機時間** 和 **成本**。

在下表中，您可以看到 **資產 KPI** 頁面上各欄位的說明。

| 欄位                   | 描述                                                                                                                                                                                                                                                                                           |
|-------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 資產                   | 資產識別碼。                                                                                                                                                                                                                                                                                             |
| 總時間              | 已設定在行事曆中總時間，使用到計算中。 如果資產與資源相關，則會使用相關資源行事曆。 如果資產與資源無關，則使用在 **資產管理參數**‧**標準行事曆** 欄位選定的行事曆。 |
| 運作時間                  | 總時間減去停機時間。                                                                                                                                                                                                                                                                            |
| 停機時間                | 在選定時期內對資產進行維護停機登記。                                                                                                                                                                                                                              |
| 修復時間             | 維修工單使用的工時總數。                                                                                                                                                                                                                                            |
| 可用性 %          | 正常運行時間除以總時間再乘以 100。                                                                                                                                                                                                                                                   |
| 異常數量        | 在選定時期內在資產的異常症狀上登記的異常原因數。                                                                                                                                                                                                             |
| 平均無異常間隔時間                    | 平均無異常間隔時間，即總時間除以選取時間段內資產上登記的異常數量。 如果異常數為零，則將 MTBF 設定為總時間。                                                                                                                   |
| 異常率               | 1 除以 MTBF。                                                                                                                                                                                                                                                                                    |
| MRT                     | 平均修復時間時間，即修復時間除以選定時間段內資產上登記的異常數量。 如果異常數為零，則將 MRT 設定為修復時間。                                                                                                                           |
| 暫停數量         | 在資產上建立的維護停機時間登記數量。                                                                                                                                                                                                                                     |
| MTBS                    | 平均暫停間隔時間，即總時間除以維護停機登記數量。 如果在選定的時間段內維護停機時間登記數量為零，則 MTBS 值設定為總時間。                                                                                      |
| 預防成本         | 在選定期間過帳資產上，與「預防性」成本類型相關的成本。 成本類型是在工單類型上設定的。                                                                                                                                                                       |
| 修正成本         | 在選定期間過帳資產上，與「修正性」成本類型相關的成本。 成本類型是在工單類型上設定的。                                                                                                                                                                       |
| 替換值       | 用來在資產上定義替換成本的值。                                                                                                                                                                                                                                                  |
| 資產類型             | 選定在資產上的資產類型識別。                                                                                                                                                                                                                                             |
| 製造商           | 選定在資產上的製造商識別。                                                                                                                                                                                                                                                 |
| 型號                   | 選定在資產上的製造商型號識別。                                                                                                                                                                                                                                           |
| 起始日期               | KPI 計算的開始日期。 如果資產是在為計算選定的開始日期之後建立的，則資產的開始日期會顯示在此欄位中。                                                                                                                                  |
| 結束日期                 | KPI 計算的結束日期。 如果資產在為計算選定的結束日期之前即登記為停用，則該資產不再使用的日期將顯示在此欄位中。                                                                                               |
| 時間尺度              | 在計算 KPI 期間，您可以選擇要使用的時間尺度：小時、天或週。                                                                                                                                                                                                            |
| 可用性            | 正常運行時間除以總時間。                                                                                                                                                                                                                                                                         |
| 工單             | KPI 計算中包含的工單總數。                                                                                                                                                                                                                                          |
| 工單時間         | 工單使用的工時總數。                                                                                                                                                                                                                                               |
| 初級工單     | KPI 計算中包含的初級工單數量。                                                                                                                                                                                                                                        |
| 次級工單   | KPI 計算中包含的次級工單數量。                                                                                                                                                                                                                                      |
| 維護工單 | KPI 計算中包含的維護工單數量。 維護工單是沒有相關異常原因的工單。                                                                                                                                                             |
| 維護時間        | 維護工單使用的工時總數。                                                                                                                                                                                                                                       |
| 修復工單      | KPI 計算中包含的修復工單數量。 修復工單是有相關異常原因的工單。                                                                                                                                                                        |
| 可靠性 %           | 資產異常登記計算的基礎是預期指數發展，這代表隨著時間的推移，資產由於磨損而變得不那麼可靠。 此 KPI 用 MTBF 和總時間來計算。                                                            |
| MTPS                    | 平均生產暫停，即維護停機時間除以數量維護停機登記數量。 如果在選定的時間段內維護停機時間登記數量為零，則 MTPS 值設定為 0。                                                                               |
| 總成本              | 在選定期間過帳到資產的總成本。                                                                                                                                                                                                                                              |
| 投資成本         | 在選定期間過帳資產上，與「投資」成本類型相關的成本。 成本類型是在工單類型上設定的。                                                                                                                                                                       |

下圖顯示了四個資產的 KPI 計算的螢幕擷取畫面。

![四個資產的 KPI 計算的螢幕擷取畫面。](media/11-controlling-and-reporting.png)

- 您可以在 **所有資產** 選取多個資產並按一下在 **一般的** 索引標籤上地 **資產 KPI** 按鈕。然後在 **計算資產 KPI** 對話方塊按一下 **確定** 計算選定資產的 KPI。  
- KPI 計算的結果可能包括也可能不包括[維護停機登記](../work-orders/maintenance-downtime.md)，取決於維護停機時間原因代碼的設定和使用。 



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]