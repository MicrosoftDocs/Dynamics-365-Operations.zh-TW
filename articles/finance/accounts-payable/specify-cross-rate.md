---
title: 指定交叉匯率
description: 本主題提供與 Microsoft Dynamics 365 Finance 中交叉匯率相關的資訊。
author: abruer
ms.date: 05/16/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c46ac3324a985810ede61072190014538d0b7ed36f7eedfc387468619cc88cb2
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450363"
---
# <a name="specify-the-cross-rate"></a>指定交叉匯率

[!include [banner](../includes/banner.md)]

本主題說明交叉匯率的用途，以及在使用發票結算付款時如何指定交叉匯率。 當滿足以下所有條件時使用交叉匯率:  
-   您正在使用發票結算付款。 
-   付款明細行和發票明細行使用不同的貨幣。 
-   兩種貨幣都不是會計貨幣。 

交叉匯率不用於將付款交易貨幣換算為付款會計貨幣的計算。 相反地，會從匯率表中擷取匯率，以計算付款交易貨幣金額與付款會計貨幣金額的值。 

例如，會計貨幣為 USD，發票貨幣為 CAD，付款貨幣為 EUR。 交叉匯率讓您可以輸入匯率以直接在 CAD 和 EUR 之間進行換算，而不必透過 USD 換算。 當您選擇發票和主要付款時，您可以輸入發票明細行的交叉匯率。 交叉匯率是截至結算日止這些交易的貨幣之間的匯率。

1.  移至以下其中一個頁面: 
- **應收帳款 > 一般 > 客戶 > 所有客戶** 
- **應付帳款 > 一般 > 廠商 > 所有廠商** 
- **採購和委外 > 一般 > 廠商 > 所有廠商**
2.  選取您正在結算其未結交易的客戶或廠商。 
3.  對於客戶，在 **所有客戶** 清單頁面上，前往 **催收 > 結算未結交易**。 對於廠商，在 **所有廠商** 清單頁面上，前往 **發票 > 結算未結交易**。 
4.  選取為主要付款的交易，然後按一下 **標示付款**。 **標示** 欄中的核取方塊已選取，且在 **主要付款** 欄中顯示資訊圖示。 
5.  在 **交叉匯率** 欄位中，輸入截至結算日止發票貨幣與付款貨幣之間的匯率。 


[!INCLUDE[footer-include](../../includes/footer-banner.md)]