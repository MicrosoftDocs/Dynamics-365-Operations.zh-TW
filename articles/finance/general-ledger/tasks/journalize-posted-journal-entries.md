---
title: 分錄已過帳日記帳分錄
description: 此項程序顯示如何分錄已過帳的日記帳分錄。
author: aprilolson
ms.date: 03/09/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerParameters, SysQueryForm
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8d8fca167563b14c825ebe29874c6488ddfb4d9a
ms.sourcegitcommit: 06acdfbccd7bd213a2397ea7b85d104f01914437
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/10/2022
ms.locfileid: "8451752"
---
# <a name="journalize-posted-journal-entries"></a>分錄已過帳日記帳分錄

[!include [banner](../../includes/banner.md)]

總帳的分錄流程提供對總帳已過帳的憑據條目分組和申報的方式。 根據您提供的標準，處理過程會產生使用唯一編號順序且總帳的 **日記帳編號** 值作為參考的憑據清單。

按照下列步驟分錄已過帳的日記帳分錄。 這段程序使用 **USMF** 示範資料公司。

1. 前往 **總帳**\>**分類帳設定**\>**總分類帳參數**。
2. 在 **擴充總帳日記帳** 欄位，選取一值。 如果您選取 **是**，報表輸出將有差異。
3. 如果尚未執行分錄流程，選取是否可以關閉期間。 如果您選取 **是**，該期間必須待分錄流程完成後才能關閉。
4. 關閉頁面。
5. 前往 **總帳**\>**定期任務**\>**分錄**，並選取 **篩選條件**。
6. 選取您希望定義篩選條件的列。
7. 在 **標準** 欄位，輸入或選取過濾標準。
8. 選取 **確定** 關閉頁面。
9. 選取 **確定** 開始分錄流程。 報表將在流程完成後產生。

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
