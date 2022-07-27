---
title: 建立寄售補貨訂單
description: 本主題說明如何建立寄售補貨訂單，可追蹤從廠商到寄售庫存的預期交貨流程。
author: yufeihuang
ms.date: 08/19/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ConsignmentReplenishmentOrder, ConsignmentReplenishmentOrderCreate, InventTrans, ConsignmentDraftReplenishmentOrderJournal, InventOnhandMovement, InventOnhandItem, InventItemIdLookupSimple, ConsignmentProductReceiptJournal, ConsignmentReplenishmentOrderLineQuantity
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9076207b73c6c76cfc44e1e02b21aad4e3f321f8
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448737"
---
# <a name="create-a-consignment-replenishment-order"></a>建立寄售補貨訂單

[!include [banner](../../includes/banner.md)]

本主題說明如何建立寄售補貨訂單，可追蹤從廠商到寄售庫存的預期交貨流程。 此主題亦說明如何記錄產品收貨，以利將寄售庫存登記為廠商的現有庫存。 此程序通常由採購專業人員完成。 您可以在 USMF 公司示範資料中使用本指南。 本道程序是針對在 Dynamics 365 for Operations 版本 1611 新增的功能。

## <a name="create-a-consignment-replenishment-order"></a>建立寄售補貨訂單
1. 在導覽窗格中，移至 **模組 > 採購和開源 > 寄售 > 寄售補貨訂單**。
2. 選擇 **新增**。
3. 在 **廠商帳戶** 欄位中，選擇廠商 **US-104** (您必須選擇 **庫存擁有者** 頁面登記的廠商)。 
4. 選擇 **確定**。
5. 選擇 **新增明細**。
6. 在 **品項編號** 欄位中，輸入 `M9211CI` (您選擇的項目必須經過設定、可用於寄售庫存)。
7. 在 **數量** 欄位中，輸入一個數字。
8. 在 **要求交貨日期** 欄位中，輸入日期。 MRP 引擎會依據要求與確認的日期來預計到貨時間。  
9. 在 **確認交貨日期** 欄位中，輸入日期。
10. 展開 **行詳細資訊** 區段。
11. 選擇 **庫存維度** 索引標籤。
12. 若要顯示 **庫存維度擁有者** 欄位內的擁有者，請重新整理頁面。 廠商 US-104 現已列為擁有者。  

## <a name="check-the-inventory-transaction-status"></a>檢查庫存交易狀態
1. 選擇 **庫存**。
2. 選擇 **交易**。
3. 注意相關列中的 **收貨** 欄位設為 **已訂購**。  
4. 關閉頁面。

## <a name="receive-items"></a>接收項目
1. 選擇 **產品收貨**。
2. 在 **外部產品收貨** 欄位，輸入一個值。
3. 在 **數量** 欄位中，輸入一個小於此處顯示的數字。 
4. 選擇 **確定**。

## <a name="check-the-on-hand-inventory"></a>檢查現有庫存
1. 選擇 **庫存**。
2. 選擇 **現有**。
3. 選擇 **概觀**。 已接收且納入該廠商寄售庫存的項目就是可用的現有項目。 **訂購總量** 欄位會顯示寄售補貨訂單的剩餘數量。  
4. 關閉頁面。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]