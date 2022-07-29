---
title: 計算各法律實體的固定資產折舊
description: 固定資產折舊可以在一個步驟中跨法律實體進行。
author: saraschi2
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: AssetParameters, AssetProposalDepreciation, DefaultDashboard, LedgerJournalTable
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 769e271ec9bb202ca695e5430c79e66f7320838fdfd232bab7c72ce5816a7b05
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450477"
---
# <a name="calculate-fixed-asset-depreciation-across-legal-entities"></a>計算各法律實體的固定資產折舊

[!include [banner](../../includes/banner.md)]

固定資產折舊可以在一個步驟中跨法律實體進行。 此程序將說明如何為多個法律實體設定和執行流程。 它使用 USMF 法律實體的會計角色和示範資料。


## <a name="set-up-cross-company-depreciation-run-journals"></a>設定跨公司折舊執行日記帳
1. 前往 [固定資產] > [設定] > [固定資產參數]。
2. 展開 [固定資產方案] 區段。
3. 選點 [新增]。
4. 在 [過帳層] 欄位中，輸入或選取一值。
5. 在 [日記帳名稱] 欄位，輸入或選取一值。
    * 在每個法律實體的固定資產參數頁面上重複日記帳設定。  

## <a name="depreciation-run"></a>折舊執行
1. 前往 [固定資產] > [日記帳分錄] > [建立折舊方案]。
2. 在 [過帳層] 欄位中，輸入或選取一值。
    * 日記帳名稱將預設來自固定資產參數。 可以在此處變更目前法律實體。  
3. 請在截止日期欄位中輸入日期。
    * 選擇要包括在折舊執行中的法律實體。  
    * 只有在固定資產參數頁面上為固定資產方案設定的日記帳的法律實體才會顯示在清單中。  
4. 在過帳日記帳欄位中選擇 [是]。
    * 篩選欄位包括為此折舊執行選擇的法律實體的所有固定資產、群組和帳簿。  
    * 批次處理選項預設為啟用。 啟用此選項後，折舊日記帳的建立和過帳將在後台執行。  
5. 點選 [建立日記帳]。
6. 前往 [固定資產] > [日記帳分錄] > [固定資產日記帳]。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]