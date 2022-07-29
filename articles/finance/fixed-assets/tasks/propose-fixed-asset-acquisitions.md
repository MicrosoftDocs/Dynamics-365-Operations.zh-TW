---
title: 提議取得固定資產
description: 本主題說明如何使用固定資產日記帳的取得提議取得固定資產。
author: moaamer
ms.date: 03/17/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: AssetTable, AssetBook, LedgerJournalTable, LedgerJournalTransAsset, SysQueryForm
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 70347009ede494760cd7f51b46db04b434b9fbcc
ms.sourcegitcommit: 62ca651c94e61aaa69cfa59e861f263f89d01c4a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/03/2021
ms.locfileid: "8451269"
---
# <a name="propose-fixed-asset-acquisitions"></a>提議取得固定資產

[!include [banner](../../includes/banner.md)]

本主題說明如何使用固定資產日記帳的取得提議取得固定資產。 它使用 USMF 法律實體的會計角色和示範資料。 若要透過固定資產提議日記帳取得固定資產，您必須先建立固定資產記錄，接著在資產帳冊定義取得價格。

## <a name="create-an-asset-acquisition-proposal"></a>建立資產取得提議

完成下列步驟建立資產取得提議。 

1. 在導覽窗格中，前往 **模組 > 固定資產 > 日記帳分錄 > 固定資產日記帳**。
2. 選取 **新增**。
3. 在 **名稱** 欄位，輸入或選取一值。
4. 在動作窗格中，選取 **明細**。
5. 選取 **提議**。
6. 選取 **取得提議**。
7. 選取 **篩選**。 選取 **重設** 清除先前數值。
8. 選取 **固定資產編號** 排。
9. 在 **條件** 欄位中，輸入或選取一個值。 針對您希望以此提議取得的固定資產設定其餘標準。  
10. 選取兩次 **確定** 離開窗格。
- 驗證交易明細是否已經建立。  
- 唯有取得日期和價格在帳冊上設定的固定資產才會納入取得提議。  
11. 在頁面上，選取 **帳冊** 索引標籤。
12. 選取 **過帳**。

## <a name="include-default-financial-dimensions-in-an-acquisition-proposal"></a>將預設財務維度納入取得提議

取得交易可藉由前往 **固定資產 > 日記帳分錄 > 固定資產日記帳**，使用 Excel 增益集建立。 在頁面上建立新日記帳並移到 **明細** 專區和選取 Excel 圖示，接著選取固定資產日記帳明細。 系統將建立並打開代表日記帳明細的 Excel 範本。 您可以針對要新增到範本的日記帳明細新增資料，接著將該項資訊發佈到系統。 

如果選取的資產帳冊和 Excel 範本輸入的對應固定資產已經設定預設維度，則當從 Excel 發佈日記賬到系統時，將從資產帳冊主資料調用預設財務維度。 若要在從 Excel 增益集發佈固定資產日記帳時，自動將財務維度納入資產帳冊，必須提前設定預設維度。  


[!INCLUDE [footer-include](../../../includes/footer-banner.md)]
