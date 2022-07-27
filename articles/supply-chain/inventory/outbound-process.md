---
title: 出庫作業流程概觀
description: 本主題概述了庫存管理中的出庫作業流程。
author: yufeihuang
ms.date: 07/25/2019
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: WMSOrder, WMSShipment, MCRPickingWorkbench, WMSPickingRegistration, CustomFilterGroup
audience: Application User
ms.reviewer: kamaybac
ms.custom:
- "274363"
- intro-internal
ms.assetid: 375807b2-a426-4f1b-bc1f-2fe00fd48413
ms.search.region: global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.dyn365.ops.version: AX 7.0.0
ms.search.validFrom: 2016-02-28
ms.openlocfilehash: 85012ada693a98652325a142ba4649a9a826b22b
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/15/2022
ms.locfileid: "8449640"
---
# <a name="outbound-process-overview"></a>出庫作業流程概觀

[!include [banner](../includes/banner.md)]

本主題概述了庫存管理中的出庫作業流程。

## <a name="output-orders"></a>輸出訂單

輸出訂單用於連接銷售訂單行和轉移訂單行與使用揀料單的出庫揀貨流程。

從銷售訂單或轉移訂單產生揀料單時，會自動建立輸出訂單和出貨。 揀料單與出貨具有一對一的關係。 可以從出貨處理轉移訂單出貨或銷售訂單裝箱單。 

下圖顯示出庫訂單流程的概觀。 

[![出庫訂單流程概觀。](./media/outbound-order.png)](./media/outbound-order.png)

您可以設定出庫規則來定義程式應如何處理出庫作業流程。 您可以使用這些規則來控制裝運流程。 特別是，您可以使用這些規則來控制可以在流程的哪個階段發送貨件。 以下設定說明出庫作業流程的處理方式。

## <a name="picking-route-status-for-sales-and-transfer-orders"></a>銷售和轉移訂單的揀貨路線狀態 

移至 **應收帳款**\>**設定**\>**應收帳款參數**，然後，在 **更新** 索引標籤中，選擇 **揀貨路線狀態** 欄位中的一個值。

[![銷售訂單的揀貨路線狀態欄位](./media/picking-route-status-sales-order.png)](./media/picking-route-status-sales-order.png)

如果 **揀貨路線狀態** 欄位設定為 **已完成**，則揀貨流程會自動發生，作為產生揀料單流程的一部分。 如果該欄位設定為 **已啟用**，必須手動更新揀料單行。

相同的設定適用於轉移訂單。 移至 **庫存管理**\>**設定**\>**庫存和倉庫管理參數**，然後，在 **運輸** 索引標籤中，選擇 **揀貨路線狀態** 欄位中的一個值。

[![轉移訂單的揀貨路線狀態欄位](./media/picking-route-status-transfer-order.png)](./media/picking-route-status-transfer-order.png)

## <a name="end-output-inventory-orders"></a>結束輸出庫存訂單

移至 **庫存管理**\>**設定**\>**庫存和倉庫管理參數**，然後，在 **一般** 索引標籤，設定 **結束輸出庫存訂單** 選項。

[![結束輸出庫存訂單選項](./media//end-output-inventory-order.png)](./media//end-output-inventory-order.png)

當倉庫工人減少揀料單數量時，相應的庫存訂單數量將從出貨中刪除。 當揀料單在某個時間點更新時，如果 **結束輸出庫存訂單** 選項設定為 **是**，則剩餘數量將報告回訂單。 如果 **結束輸出庫存訂單** 選項設定為 **否**，則剩餘數量保留為未完成輸出訂單數量，且需添加到新的揀料單中，作為 **未完成輸出訂單** 功能。 

[![“功能”表上的未完成輸出訂單命令。](./media/open-output-order.png)](./media/open-output-order.png)

[![未完成輸出訂單頁面上的功能表。](./media/open-output-order-function.png)](./media/open-output-order-function.png)

## <a name="reduce-quantity"></a>減少數量

您可以在產生揀料單的過程中使用的第三個參數是 **減少數量** 參數。 此參數的設定與 **保留** 設定一同使用，作為向倉庫發佈並觸發保留流程的一部分。

[![減少數量參數。](./media/reduce-quantity.png)](./media/reduce-quantity.png)

## <a name="example-of-an-outbound-process-for-a-sales-order"></a>銷售訂單的出庫作業流程示例

對於此示例，有兩個項目的銷售訂單。 在揀料單產生期間，您選擇 **減少數量** 參數。 因此，您僅為可用的現有庫存發佈和建立揀貨行。 揀貨必須通過揀料單的註冊流程進行報告（**揀貨路線狀態** = **已啟用**）。

尚未預留的庫存會在揀料單產生過程中被預留。 不可用的庫存可以從銷售訂單中移除，也可以發佈到倉庫以供之後出庫作業處理，此時庫存可用於揀貨。

[![更新揀料單。](./media/update-picking-list.png)](./media/update-picking-list.png)

一旦在 **揀料單註冊** 頁面選擇所有的揀貨行，則相關的裝運便完成。 然後可以根據揀配的庫存初始化銷售訂單裝箱單的流程。

[![更新出庫貨物。](./media/outbound-shipments.png)](./media/outbound-shipments.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]