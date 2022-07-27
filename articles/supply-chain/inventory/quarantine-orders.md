---
title: 隔離訂單
description: 本主題說明如何使用隔離訂單來封鎖庫存。
author: yufeihuang
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventLocation, InventModelGroup, InventQuarantineOrder, InventQuarantineParmEnd, InventQuarantineParmReportFinished, InventQuarantineParmStartUp, InventTrans
audience: Application User
ms.reviewer: kamaybac
ms.custom: 30021
ms.assetid: d5047727-653c-49da-b489-6fd3fe50445e
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5cf0ec8f9f4d862724cb8ab72b48771ed68eaf39
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448146"
---
# <a name="quarantine-orders"></a>隔離訂單

[!include [banner](../includes/banner.md)]

本主題說明如何使用隔離訂單來封鎖庫存。

隔離訂單可以讓您封鎖庫存。 例如，基於品質控制原因，您可能會希望隔離品項。 已隔離的庫存會轉移到隔離倉庫。

> [!NOTE]
> 如果您使用進階倉庫管理流程 (在倉庫管理中)，則隔離訂單處理僅會用於退貨銷售訂單。

## <a name="quarantine-on-hand-inventory-items"></a>隔離現有庫存品項

當您隔離品項時，您可以手動建立隔離訂單或將系統設定為在入庫處理期間自動建立隔離訂單。

若要將系統設定為自動產生隔離訂單，請按照以下步驟操作。

1. 移至 **庫存管理 \> 設定 \> 庫存 \> 項目型號群組**。
1. 在清單窗格中選擇相關的模型群組，或建立新模型群組。
1. 在 **庫存原則** FastTab，選擇 **隔離管理** 核取方塊。
1. 關閉頁面。
1. 在收貨倉庫的 **隔離倉庫** 欄位，指定預設隔離倉庫。

當在倉庫登記為收貨的品項屬於模型群組時，且已選取該群組的 **隔離管理** 核取方塊時，系統會為其產生一個隔離訂單。 隔離訂單可以指示工作人員將品項移至隔離倉庫。

當您在 **隔離訂單** 頁面中手動建立隔離訂單時，不必在相關的品項模型群組中，針對隔離管理設定品項。 對於此流程，您必須指定應隔離的現有庫存和應使用的隔離倉庫。 您可以使用隔離訂單狀態來幫助規劃流程。

## <a name="quarantine-order-statuses"></a>隔離訂單狀態

隔離訂單可以具有以下狀態：

- 已建立
- 已開始
- 報告為已完成
- 已結束

### <a name="created"></a>已建立

當手動建立隔離訂單，但該品項尚未在隔離倉庫中時，隔離訂單的狀態為 **已建立**。 產生兩個庫存交易。 其中一筆交易是問題交易，其狀態可以是 **訂購**、**預留實物** 或 **已揀貨**。 另一筆交易是收據交易，其狀態為 **已訂購** 或在隔離倉庫 **已登記**。 您可以使用常用流程預訂、揀貨和登記庫存更新。

### <a name="started"></a>已開始

當隔離訂單的狀態為 **已開始**，庫存從常規倉庫轉移到隔離倉庫，產生兩筆庫存交易。 一筆交易的狀態為 **已扣除**，而另一筆交易的狀態為 **已收到**。 同時，建立兩個庫存交易來處理退貨轉移。 這些交易沒有註明日期。 一筆交易的狀態為 **預留實物**，而另一筆交易的狀態為 **已訂購**。

### <a name="reported-as-finished"></a>報告為已完成

若要將已開始的隔離訂單報告為已完成，請開啟訂單，然後在動作窗格上選擇 **報告為完成**。 該品項已從隔離區釋放，但尚未移回常規倉庫。 可以透過品項到貨日記帳處理返回常規倉庫的移動，該日記帳可以在報告期間初始化為已完成的流程。

### <a name="ended"></a>已結束

當隔離訂單結束時，該品項會從隔離倉庫移回常規倉庫。 品項交易的狀態在隔離倉庫設定為 *已售出*，在常規倉庫設定為 *已購買*。

## <a name="quarantine-order-scrap"></a>隔離訂單報廢

在隔離訂單流程中，您可以報廢庫存。 處理報廢時，透過隔離倉庫的問題交易將庫存狀態設定為 *已售出*。

## <a name="additional-resources"></a>其他資源

- [庫存封鎖](inventory-blocking.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
