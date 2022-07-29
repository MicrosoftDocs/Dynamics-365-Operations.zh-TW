---
title: 檢視廠商發票自動化結果（預覽）
description: 本主題說明如何檢視處於自動送出到工作流程中的廠商發票的狀態。
author: abruer
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.assetid: ''
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-09-08
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: e7ec69177cdb4f6304b75016963f4111bbfde6ed975d66ffa702426a68dce640
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450300"
---
# <a name="view-vendor-invoice-automation-results"></a>檢視廠商發票自動化結果

[!include [banner](../includes/banner.md)]

本主題說明如何檢視處於自動送出到工作流程中的廠商發票的狀態。 為每個匯入的廠商發票維護自動化歷程記錄的詳情。 根據您自動化的業務流程，**待處理的廠商發票** 頁面顯示 **自動化收據比對狀態** 和 **自動送出到工作流程狀態** 的值。 您可以檢視詳情並制定計劃，重點關注未能通過自動化步驟的發票。 然後，在修正問題後，您可以繼續匯入發票的自動化流程。

在您可以編輯已送出的發票之前，您必須暫停自動處理作業。 如果必須暫停自動送出到工作流程中的發票，請在 **廠商發票** 頁面將 **包括在自動化處理** 欄位設定到 **不是**。 然後自動化將不會執行，直到將 **包括在自動化處理** 設定為 **是的**。 如果發票尚未在工作流程系統中並且未被自動化流程使用，則可以暫停進一步自動化。

如果匯入的發票需要送出到工作流程，您可以檢視其 **廠商發票** 面頁上的 **自動化狀態** 值。 追蹤以下狀態：

- **包括** – 在 **應付帳款參數** 頁面上定義的自動化流程可正常執行，但尚未完成。
- **暫停** – 在 **應付帳款參數** 頁面上定義的自動化流程已開始執行，但流程中的至少有一個步驟失敗。 如果將 **包括在自動化處理** 欄位設定為 **不是** ，**暫停** 狀態也適用。 您可以透過選取 **檢視最新結果** 檢視失敗。
- **在工作流程中** – 透過自動或手動送出到工作流程來匯入的發票送出到工作流程系統。
- **工作流程完成** – 已完成匯入發票的工作流程。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]