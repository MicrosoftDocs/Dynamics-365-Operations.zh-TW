---
title: 取消倉庫工作進行例外狀況處理
description: 本主題說明取消工作功能，可讓倉庫主管處理已中斷工作。
author: Mirzaab
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSTroubIeshootingSeIfService, WHSTroubleshootingSelfService
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2019-10-1
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: af0c147eefbfe22cb6b6d531f514e6f293d66689
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448518"
---
# <a name="cancel-warehouse-work-for-exception-handling"></a>取消倉庫工作進行例外狀況處理

[!include [banner](../includes/banner.md)]

Microsoft Dynamics 365 Supply Chain Management 中的取消工作功能，允許系統管理員使用者取消當前正在進行但被系統中斷或由於例外情況無法完成的特定倉庫工作。 此功能是一種具吸引力且安全的 SQL 更正腳本的替代方案，可修復資料不一致。 但是，儘管這些腳本通常是由 IT 專業人員請求的，但公司中具有系統管理員權限的使用者可以使用取消工作功能。

您可以在以下位置存取取消工作功能：**倉庫管理**\>**定期任務**\>**清理\>取消工作**。 在 **取消工作** 對話方塊，指定取消工作的工作識別碼，然後選取 **確定**。

## <a name="warehouse-work-that-can-be-canceled"></a>可以取消的倉庫工作

在倉庫揀選作業期間，工作人員可能會遇到這樣的情況：他們已從儲存位置將數量登記揀選到其使用者位置，但隨後他們無法登記放置作業。 不一致的倉庫資料通常 (但並非總是) 是工作中斷的原因。

不像使用工作標題上的 **取消** 按鈕的常態取消功能，取消工作功能不需要最後完成的工作明細是是 **放置** 類型。 換言之，取消工作功能，即使工作明細上的品項數量位於使用者位置，也可以執行取消邏輯。

> [!NOTE]
> 對於因作業因素必須取消的工作，倉庫使用者必須繼續使用工作頁面上的常規取消功能。

只有 **銷售**、**轉移出貨**、**原物料揀料**，或 **補貨** 類型的工作，可以使用取消工作功能。 對於凍結的原物料揀料工作或可以使用常規取消功能取消的工作 (請參閱前面的備註)，取消邏輯不會執行。

要解除中斷工作，系統會取消所有剩餘的工作明細並修復與指定的工作識別碼關聯的倉庫資料。 然後涉及受影響品項數量的任何常規倉庫處理作業可以繼續。

若要在工作取消後將受影響的物品放在特定位置，使用者必須在移行動裝置上使用庫存移動或數量調整作業。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]