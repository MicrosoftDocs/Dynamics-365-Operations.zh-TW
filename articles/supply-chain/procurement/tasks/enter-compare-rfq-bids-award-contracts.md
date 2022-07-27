---
title: 輸入與比較 RFQ 出價並授予合約
description: 本主題說明如何輸入詢價 (RFQ) 回覆、評分和比較出價，然後授予合約給一家廠商。
author: Henrikan
ms.date: 07/09/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PurchRFQCaseTableListPage, PurchRFQCaseTable, PurchRFQReplyTable, PurchRFQCompare, PurchRFQEditLines, PurchRFQEditLinesParameters, PurchTable, PurchTablePart, PurchRFQCompareLinePrices, PurchRFQCompareRFQ
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8378a491e528c1e1166f0688e29f923a25f23eed
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449214"
---
# <a name="enter-and-compare-rfq-bids-and-award-contracts"></a>輸入與比較 RFQ 出價並授予合約

[!include [banner](../../includes/banner.md)]

本主題說明如何輸入詢價 (RFQ) 回覆、評分和比較出價，然後授予合約給一家廠商。 您能以 **USMF** 示範資料公司使用此程序。

開始此程序前，您必須有具備兩條明細且已傳送給至少兩家廠商的 RFQ。 若要建立此 RFQ，請完成[建立詢價](create-request-quotation.md)程序。 您也必須設定評分標準，才能完成此程序。

您能以廠商或採購專業人員的身分輸入出價。 如需詳細資訊，請參閱[設定與維護廠商共同合作](../set-up-maintain-vendor-collaboration.md)。

## <a name="enter-a-reply-as-a-vendor"></a>以廠商身分輸入回覆

1. 移至 **廠商共同作業 \> 工作區 \> 廠商出價**。
2. 在 **新出價邀請** 清單中，尋找剛傳送的 RFQ。 選取 RFQ 以檢視請求內容。
3. 選取 **RFQ 附件** 以檢視附件。
4. 選取 **出價**，將欄位變成可編輯。 請注意 **出價進度** 欄位現為 **廠商正在更新**。
5. 在標題和明細上，輸入出價回覆的值。
6. 如需在出價中新增附件，選取 **出價附件**。
7. 選取 **出價指導項目** FastTab 以檢視是否需要必要文件。
8. 選取 **修訂** FastTab 以檢視 RFQ 是否曾修改。
9. 選取 **問卷** FastTab。 必須回答在此出現的任何問卷。
10. 選取 **明細詳細資料** FastTab 以檢視明細的延伸資訊。
11. 只有當您必須重設已輸入原始 RFQ 的值時，再選取 **從 RFQ 重設**。
12. 您可隨時儲存出價，稍後再處理其他事宜，前提是尚未超過到期日期和時間。 在這種情況下，您可於 **廠商出價** 工作區的 **進行中出價** 清單找到這份出價。
13. 準備傳送出價時，請選取 **送出**。 若您不想出價，請選取 **拒絕**。 送出的出價會出現在 **廠商出價** 工作區的 **已送出出價** 清單中。  
14. 出價送出後，您可於到期日期和時間前隨時將其撤回。 請注意，出價撤回後，就不再是已送出狀態。 出價經採購部門接受或拒絕後，將出現在 **廠商出價** 工作區的 **得標** 或 **未得標** 清單。  

## <a name="enter-a-reply-from-a-vendor-as-a-procurement-professional"></a>以採購專業人員的身分輸入廠商回覆

1. 請確認已設定廠商出價編輯權限。 移至 **採購和開源 \> 設定 \> 採購和開源參數**。 在 **詢價** 索引標籤中，將 **購買者可編輯廠商出價** 選項設為 **是**。
2. 移至 **採購和開源 \> 詢價 \> 所有詢價**。
3. 選取狀態為 **已傳送** 的 RFQ，然後選取 **詢價案例** 欄位中的連結。
4. 選取 **管理回覆**。 出現的頁面將顯示受邀出價的廠商的 RFQ。
5. 選取尚未回覆的 RFQ。 (**回覆進度** 欄位應為 **未開始**。)
6. 選取 **編輯 \> 編輯 RFQ 回覆**。 將顯示 **RFQ 回覆** 頁面。 您現能以採購專業人員的身分，代表廠商輸入回覆。 請注意 **出價進度** 欄位現為 **購買者正在更新**。  
7. 輸入出價資料。 完成後，選取 **送出**。

## <a name="score-the-bids"></a>評分出價

1. 在 **所有詢價** 頁面中，選取您想為回覆評分的 RFQ 案例。
2. 選取 **管理回覆**。
3. 選取要評分的回覆。
4. 選取 **標題** 以檢視出價的評分。
5. 在 **出價評分** FastTab 中，於一項評分標準的 **分數** 欄位輸入一個數字。 若您將滑鼠懸停在評分標準上，工具提示會顯示規定的分數範圍。 在此示範中，您可針對任何評分標準輸入 1 到 5 之間的數字。  
6. 對另一項評分標準重複步驟 5。
7. 若該 RFQ 案例的問卷已傳送給廠商，您可於 **問卷** FastTab 輸入廠商回應。
8. 關閉頁面。
9. 為所有其他出價重複步驟 1 到 8。

## <a name="compare-the-replies"></a>比較回覆

1. 在動作窗格上，於 **一般** 索引標籤選取 **比較回覆**。
2. 在 **排名** 欄位中，輸入一個數字。  
    - 此頁面顯示的出價包含標題和明細資訊，並於標題層級列出總分。 您可排序明細方格，並列可互相比較的明細，方便您比較。 此外也有下列資訊：
    - **數量** – 廠商報價的數量。 此數量不一定等於 RFQ 指定的數量。
    - **淨額** – 廠商針對明細內項目提供的價格，減去折扣。
    - **偏差** – 出價標題或明細的交貨日期與 RFQ 標題或明細要求的交貨日期的差距天數。 您可為每個出價輸入排名。  
3. 選取您想排名的其他出價標題明細。
4. 在 **排名** 欄位中，輸入一個數字。
5. 選取 **儲存**。

## <a name="reject-a-bid"></a>拒絕出價

1. 選取您想拒絕的出價標題明細。 您一次只能接受、拒絕或退回一份出價或一份出價內的多條明細。
2. 選取 **標記** 核取方塊。  
    - 若您於出價的標題選取 **標記** 核取方塊，則會同時標記所有明細。 若要拒絕或接受出價內的部分明細，只要標記那些明細即可。 此外，您可針對 RFQ 的部分明細接受一家廠商的出價，並將其他 RFQ 明細授予不同廠商。 然而，一次只能對一份出價執行操作。  
    - 若有備用明細，您可接受原始出價明細或其備用明細之一，不得兩者都接受。  
3. 選取 **拒絕**。
4. 選取 **參數**，然後在 **拒絕原因** 欄位中輸入或選取拒絕此出價的原因。 原因會儲存於回覆中。  
5. 選取 **確定**。
6. 選取 **確定**。

## <a name="accept-a-bid"></a>接受出價

1. 選取要接受的出價，然後選取 **詢價** 欄位內的連結。 若您位於 **比較詢價回覆** 頁面上，將突顯系統在接受動作時會考慮的出價。 您一次只能接受一份出價的明細。  
2. 在動作窗格上，選取 **回覆**。
3. 選取 **接受**。 若您僅標記特定明細，則接受動作只會納入這些明細。 若您想接受出價內的所有明細，則無須標記明細。  
4. 選取 **參數**，然後在 **接受原因** 欄位中輸入或選取接受此出價的原因。 原因會儲存於出價中。  
5. 選取 **確定**。
6. 選取 **確定**。 選取 **確定** 後，產生的訂購單內容會依據 RFQ 接受的明細。 若有其他尚未處理 (接受、拒絕或退回) 的出價，系統會提示您拒絕這些出價。  

## <a name="view-the-purchase-order-that-is-generated"></a>檢視產生的訂購單

在動作窗格上，於 **一般** 索引標籤選取 **訂購單**。 出現的頁面會顯示您接受出價時產生的訂購單。


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]