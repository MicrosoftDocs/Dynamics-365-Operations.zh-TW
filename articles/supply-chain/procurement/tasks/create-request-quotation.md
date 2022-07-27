---
title: 建立詢價
description: 此程序說明如何建立詢價。
author: Henrikan
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PurchRFQCaseTableListPage, PurchCreateRFQCase, InventLocationIdLookup, PurchRFQCaseTable, InventItemIdLookupSimple, EcoResCategorySingleLookup, UnitOfMeasureLookup, PurchRFQEditLines, PurchRFQEditLinesPrintOptions, VendRFQJournal, SrsReportViewerForm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b0e9e4d7c31b1e6905abeac03e462ac185f3f489
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8447807"
---
# <a name="create-a-request-for-quotation"></a>建立詢價

[!include [banner](../../includes/banner.md)]

此程序說明如何建立詢價。 這通常由採購代理人完成。 您可用示範資料公司 USMF 或自己的資料來使用此程序。 在開始之前，您需要設定徵集類型。 完成此工作並建立與傳送 RFQ 後，您可以輸入每個廠商的回覆，進行比較並授予合約。


## <a name="prepare-a-new-rfq"></a>準備新的 RFQ
1. 前往 **功能窗格 > 模組 > 採購及開源 > 詢價 > 所有詢價**。
2. 按一下 **新增**。
    可以使用以下採購類型：採購訂單 (此為預設)：確認購買產品的報價，或接受銷售產品以換取付款的報價的文件。 採購申請：如果您直接從採購申請建立 RFQ，則會自動選擇此類型。 如果您手動選擇此選項，則會收到錯誤消息。 購買合約：用於在一段時間內購買特定數量或價值之產品的合約。 如果選擇此選項，則必須選擇適用於採購合約的日期範圍。  
3. 在 **文件標題** 欄位中，輸入一個值。
4. 在 **徵集類型** 欄位中，輸入或選擇一個值。
    + 如果評分方法與徵集類型相關聯，這將是您正在建立的 RFQ 的預設評分方法。 評分方法在之後可以更改。  
    + 在 **交貨日期** 欄位中，輸入日期。  
    + 選擇您希望收到品項的最後日期。  
    + 在 **到期日與時間** 欄位中，輸入日期和時間。  
    + 指定廠商必須回應 RFQ 的日期和時間。  
5. 在 **倉庫欄位** 中，輸入或選擇一個值。 交貨地址將預設為倉庫地址。  
6. 按一下 **確定**。

## <a name="add-lines"></a>新增明細

在您指定有關您 RFQ 的基本資訊之後，您可以指定您希望廠商投標的商品或服務。 項目是預設的明細類型。

1. 在 **項目號碼** 欄位中，輸入或選擇一個值。 如果您使用 USMF，則可以選擇 T0020。  
2. 在 **數量** 欄位中，輸入一個數字。
3. 按一下 **新增明細**。
4. 在 **明細類型** 欄位中，選擇「類別」。 您可以使用類別明細類型為非庫存商品或服務建立 RFQ。 然後，您需要從採購類別的階層中選擇商品或服務的類型。  
5. 在 **採購類別** 欄位中，輸入或選擇一個值。
6. 在 **產品名稱** 欄位中，輸入一個值。
7. 在 **數量** 欄位中，輸入一個數字。
8. 在 **單位** 欄位中，輸入或選擇一個值。

## <a name="add-vendors"></a>新增廠商
1. 按一下 **標題** 以從明細檢視變更為標題檢視。 
2. 展開 **廠商** 區段。
3. 按一下 **自動新增廠商**。 您可以根據請求項目的採購類別自動將廠商新增到 RFQ。 如果沒有為明細中包含類別核准的廠商，您可以手動新增廠商。  
4. 按一下 **新增**。
5. 在 **廠商帳戶** 欄位中，輸入或選擇一個值。
6. 按一下 **新增**。
7. 在 **廠商帳戶** 欄位中，輸入或選擇一個值。 選擇廠商後，狀態將顯示已建立。 這代表廠商資訊已保存在 RFQ 中，但您尚未將 RFQ 傳送給廠商。 無論廠商狀態如何，您都可以將廠商新增到 RFQ。  

## <a name="send-the-rfq-to-vendors"></a>將 RFQ 傳送給廠商
1. 在 **動作窗格** 上，按一下 **傳送**。 在傳送詢價頁面中，檢查清單中的廠商是否是您要接收 RFQ 的廠商。  
2. 按一下 **列印**。 此對話可讓您列印 RFQ。 如果您選擇列印回覆表，則其內容會在採購和開源參數中定義。 若要選擇如何列印回覆表，請打開列印對話框後，按一下進階列印選項。 系統將為每個廠商列印一份 RFQ，其中包含狀態為已建立或已傳送的明細。 已取消的明細和已註冊回覆的明細將不會進行列印。   
3. 點選 **取消**。
4. 按一下 **確定**。
5. 關閉頁面。
6. 關閉頁面。

## <a name="view-the-rfq-journal"></a>檢視 RFQ 日誌
1. 前往 **採購和開源 > 詢價 > 詢價跟進 > 詢價日誌**。
2. 按一下 **預覽/列印**。
3. 按一下 **原始預覽**。
4. 關閉頁面。
5. 關閉頁面。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]