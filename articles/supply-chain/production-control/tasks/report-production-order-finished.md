---
title: 將生產訂單報告為完成
description: 此程序說明如何將生產訂單報告為完成。
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ProdTableListPage, ProdParmReportFinished, ProdJournalTransProd, ProdSetupReportFinished
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: aa27691942b27886e85c52b7b3a736a62db7b7bd
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449328"
---
# <a name="report-a-production-order-as-finished"></a>將生產訂單報告為完成

[!include [banner](../../includes/banner.md)]

此程序說明如何將生產訂單報告為完成。 建立此程序的示範資料公司為 USMF。 這是解釋生產訂單生命週期的第六個程序 (共七個程序)。


## <a name="report-a-production-order-as-finished"></a>將生產訂單報告為完成
1. 移至 [生產控制] > [生產訂單] > [所有生產訂單]。
    * 選取具有「已開始」狀態的生產訂單。  
2. 在 [動作窗格] 上按一下 [產品訂單]。
3. 按一下「報告為完成」。
    * 在此頁面上，您可以確認報告為完成的成品數量。  
4. 按一下「一般」索引標籤。
5. 將「良品數量」設為 '18'。
6. 將「不良品數量」設為 '2'。
7. 在「不良品原因」欄位中選取「物料」。
8. 選取或清除「結束作業」核取方塊。
9. 選取或清除「接受不良品」核取方塊。
10. 按一下 [確定]。

## <a name="verify-the-report-as-finished-journal"></a>驗證「報告為完成的日記帳」
1. 在「動作窗格」上按一下 [檢視]。
2. 按一下「報告為完成」。
3. 在清單中，標記所選資料列。
4. 在列表中，按一下所選行中的連結。
    * 已過帳「報告為完成的日記帳」。 如果您想對日記帳進行調整，您可以手動建立新的日記帳以在其中進行變更。  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]