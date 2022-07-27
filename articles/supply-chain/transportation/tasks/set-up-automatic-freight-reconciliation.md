---
title: 設定自動貨運對帳
description: 此程序顯示如何為自動貨運對帳設定資料。
author: Henrikan
ms.date: 10/16/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TMSFreightBillType, TMSFreightBillTypeAssignment, TMSCarrierCodeLookup, DefaultDashboard, TMSAuditMaster
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: henrikan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d1dbe3c683d869f86bc7231c68839f431cc61d6b
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448758"
---
# <a name="set-up-automatic-freight-reconciliation"></a>設定自動貨運對帳

[!include [banner](../../includes/banner.md)]

此程序顯示如何為自動貨運對帳設定資料。 這通常由倉庫經理完成。 您可以在 USMF 示範公司資料中使用此程序。


## <a name="set-up-the-freight-bill-type"></a>設定貨運帳單類型
1. 移至運輸管理 > 設定 > 貨運對帳 > 貨運帳單類型。
    * 貨運帳單類型定義應如何比對貨運帳單和承運人發票。  
2. 點選 [新增]。
3. 在 [貨運帳單] 類型欄位中，輸入一個值。
4. 在 [引擎組件] 欄位中，輸入 'Microsoft.Dynamics.Ax.Tms.dll'。
    * 這是標準的運輸管理相符引擎代碼庫。  
5. 在 [引擎類別] 欄位中，輸入 'Microsoft.Dynamics.Ax.Tms.Bll.GenericNormalizer'。
    * 這是標準的運輸管理相符引擎類別。  
6. 點選 [新增]。
7. 在 [描述] 欄位中，選擇貨運帳單和承運人發票上應相符的值。  
8. 在 [比對要求] 欄位，選取 [是]。
    * 如果您將此欄位設定為 [是]，這代表在描述欄位中選擇的值需要在貨運帳單和承運人發票都相符。 如果將其設定為 [否]，則其中一個欄位可以為空白。  
9. 點選 [儲存]。

## <a name="set-up-the-freight-bill-type-assignment"></a>設定貨運帳單類型指派
1. 關閉頁面。
2. 移至運輸管理 > 設定 > 貨運對帳 > 貨運帳單類型指派。
    * 貨運帳單類型指派用於指定特定承運人使用的貨運帳單類型。   
3. 點選 [新增]。
4. 在 [模式] 欄位中輸入或選擇一個值。
5. 在 [裝運承運人] 欄位中，輸入或選擇一個值。
6. 在 [貨運帳單類型] 欄位中，選擇先前建立的貨運帳單類型。
7. 關閉頁面。

## <a name="set-up-the-audit-master"></a>設定稽核主板
1. 移至運輸管理 > 設定 > 貨運對帳 > 稽核主板。
    * 稽核主板會定義自動貨運對帳的容差界限。 它指定貨運帳單和承運人發票上的貨幣金額在相差多少以內仍允許進行對帳。 它還定義了如何處理差異。  
2. 點選 [新增]。
3. 在 [稽核主板識別碼] 欄位中，輸入一個值。
4. 在 [裝運承運人] 欄位中，選擇與之前相同的裝運承運人。
5. 在 [貨運帳單類型] 欄位中，選擇先前建立的貨運帳單類型。
6. 展開 [容差] 區段。
7. 在 [最小容差等級] 欄位中，輸入一個數字。
8. 在 [最大容差等級] 欄位中，輸入一個數字。
9. 展開 [結果] 區段。
10. 在 [超額支付原因代碼] 欄位中，輸入或選取一個值。
    * 如果貨運帳單和承運人發票上的金額不同，只要差額在容差等級內，超額支付和未足額支付原因代碼將指定應記錄的差額。  
11. 在 [未足額支付] 欄位中，輸入或選取一個值。
12. 關閉頁面。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]