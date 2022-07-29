---
title: 處理分類帳配比日記帳
description: 本主題說明如何在 Dynamics 365 Finance 處理配比要求。
author: aprilolson
ms.date: 07/26/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerAllocationRequest, LedgerJournalTable, LedgerJournalTransAllocation
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7d37b1a9869cc130786d0e8fde68184e04c881bad1f64c86943174213025db82
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450678"
---
# <a name="process-ledger-allocation-journal"></a>處理分類帳配比日記帳

[!include [banner](../../includes/banner.md)]

本主題說明如何處理配比要求。 使用 Process 配比要求頁建立過帳到總帳，或直接過帳到總帳前，可以審核與核准的配比日記帳。 在您可以建立配比日記帳之前，必須至少有一個有效的分類帳配比規則。 此工作使用 USMF 公司進行示範。

1. 在導覽窗格中，前往 **模組 > 總帳 > 配比 > 處理配比要求**。
2. 在 **規則** 欄位的下拉式選單中選取想要的記錄。
3. 在 **截止日** 欄位，輸入日期。

    - **截止日** 在分類帳為規則的資料來源時非常重要。 此日期控制預計納入配比的分類帳餘額。  
    - 在 **零來源** 欄位選取 **停止**。 這將停止配比過程並顯示訊息，寫明已選取零來源金額。  

4. 在 **提案選項** 欄位，選取 **僅限提案**。 選取 **僅限提案** 在配比過帳到總帳前，審核及選擇性地核准配比日記帳中的結果。  
5. 在 GL 過帳日欄位，輸入日期。
6. 選取 **確定**。
7. 在導覽窗格中，前往 **模組 > 總帳 > 配比 > 配比日記帳**。
8. 選取 **明細**。
9. 選取 **過帳**。
10. 選取 **過帳**。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]