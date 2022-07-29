---
title: 在期間結束時關閉總帳
description: 本主題介紹為總帳執行定期結算時要完成的工作。
author: aprilolson
ms.date: 08/01/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerPeriodCloseWorkspace
audience: Application User
ms.reviewer: roschlom
ms.custom: 14111
ms.assetid: cec9e039-c1a2-482c-bea6-e11d896eea9d
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f83ea7a870c52884030125736809ead02b264aef1dcd654f6ff94dab0fbb2004
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450411"
---
# <a name="close-the-general-ledger-at-period-end"></a>在期間結束時關閉總帳

[!include [banner](../includes/banner.md)]

本主題介紹為總帳執行定期結算時要完成的工作。 

在總帳中，您會完成某個期間或年度的關帳流程。 關帳流程使系統為新期間做好準備。 要為新年度準備系統，您必須執行年終結算流程。 每個組織在一個期間結束時會執行不同的流程和步驟。 以下是期末的一些可選步驟：

-   完成所有其他模組的所有工作，例如應收帳款、應付帳款和庫存。
-   確認所有日記帳都已過帳。
-   執行外幣重估以產生任何未實現的損益金額。
-   結算每個會計科目的交易。
-   處理任何所需的分配。
-   手動過帳期末調整。
-   記錄交易，並審查 **分類帳日記帳** 報表。
-   使用合併公司或財務報表執行合併。
-   使用財務報表產生期末財務報表。
-   將分類帳期間設定為 **暫停**，因此不會發生進一步的過帳。 您還可以在期末活動發生時將時間期間限制為特定使用者群組，以便更好地控制。 將週期設定為 **永久關閉** 不是一個好主意，因為您將無法重新打開已關閉的期間。

[財務期間結帳] 工作區可用於組織和追蹤各種期末流程所需的工作。 


有關詳細資訊，請參閱下列主題：
- [財務期間結帳工作區](financial-period-close-workspace.md) 
- [年終結算](Year-end-close.md)  
- [大量財務期間結帳](tasks/mass-financial-period-close.md)






[!INCLUDE[footer-include](../../includes/footer-banner.md)]