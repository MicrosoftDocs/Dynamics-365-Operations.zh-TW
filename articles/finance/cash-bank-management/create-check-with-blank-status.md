---
title: 建立具有空白狀態的支票
description: 本主題說明如何在支票頁面上為銀行帳戶建立空白支票。
author: abruer
ms.date: 10/26/2017
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: BankChequeTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 21941
ms.assetid: d7e22bd8-fd0d-47e1-843f-45ab0193ff8d
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2019-09-17
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 3c431ed975aecf116fbf626018038b112a0a8cca063e1462e31e206480643e11
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8452718"
---
# <a name="create-checks-that-have-blank-status"></a>建立具有空白狀態的支票

[!include [banner](../includes/banner.md)]

本主題說明如何建立空白支票。 例如，您可以建立一張空白支票來記錄已損毀且無法用於付款的支票。

您在 **支票** 頁面上執行支票的維護工作。 例如，您可以建立新的支票號碼及刪除支票。 您還可以建立狀態為 **空白** 的支票。 空白支票建立後，便不能在系統中刪除或重複使用。

> [!NOTE]
> 僅當您 **功能管理** 頁面上開啟 **建立狀態為空白的支票** 功能，才可在 **支票** 頁面上使用此功能。 如果該功能未開啟，則僅能在應付帳款中付款產生過程中從 **支票付款** 對話方塊建立具有 **空白** 狀態的支票。

要打開 **支票** 頁面，前往 **現金和銀行管理 \> 銀行帳戶 \> 銀行賬戶**，然後在動作窗格中的 **管理付款** 索引標籤上，選擇 **相關資訊** 群組中的 **支票**。 或者，移至 **現金和銀行管理 \> 查詢和報告 \> 支票**。

然後，要建立具有 **空白** 狀態的支票，在動作窗格上選擇 **建立空白支票**。 在系統建立空白支票時，相關的銀行帳戶會暫時停用。 此行為可降低在建立空白支票的同時產生付款的風險。 處理完成後，相關聯的銀行帳戶將重新啟動。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]