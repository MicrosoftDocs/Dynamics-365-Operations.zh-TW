---
title: 解決發票總計比對概觀期間的差異
description: 您可以使用發票總計比對，協助確保發票總額與預期金額的偏差不超過可接受的差異。
author: abruer
ms.date: 07/25/2019
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: VendTotalPriceTolerance
audience: Application User
ms.reviewer: roschlom
ms.custom:
- "63413"
- intro-internal
ms.assetid: 9ac42457-95b2-4191-ad06-c7e323704466
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4f15edb0423bba2a6fe01f4b3ef1ba1be4e463d4
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/15/2022
ms.locfileid: "8451449"
---
# <a name="resolve-discrepancies-during-invoice-totals-matching-overview"></a>解決發票總計比對概觀期間的差異

[!include [banner](../includes/banner.md)]

一種類型的發票比對驗證是發票總計比對。 若要指定系統執行發票總計比對，在 **應付帳款參數** 頁面中，在 **發票驗證** 索引標籤將 **比對發票總計** 選項設定為 **是**。 

您可以使用發票總計比對，協助確保發票總額與預期金額的偏差不超過可接受的差異。 在 **發票總計比對詳細資料** 頁面中比較六個總額。 如果任何一個總計偏離預期相對應訂購單的總計，則會標記對比差異。 

要查看有總計比對差異的發票，在 **廠商發票項目** 工作區，按一下 **待處理發票** 圖格。 然後，在「動作窗格」上，在 **檢閱** 索引標籤按一下 **比對詳細資料**。 如果偵測到比對差異，發票金額旁邊會出現警告圖示。 您可以透過檢視發票總計比對詳細資料來檢視更多關於總計的詳細資料。 

確定差異後，如果您認為發票上的資料不正確，您可能需要連絡廠商。 根據與廠商協定的合約，您可以採取以下其中一項措施：

-   接受差價，並過帳具有比對差異的發票。 如果存在比對差異，您的系統可能被設定為需要核准才能過帳。 在這種情況下，您必須核准比對差異，並且可以選擇性地輸入核准註解。 然後您可以選取過帳發票。
-   將發票金額修改為預期金額，然後過帳發票。
-   要求廠商提供完整的貸記和新的更正發票。

如需詳細資料，請參閱[研究/解決例外狀況](tasks/research-resolve-exceptions.md)。




[!INCLUDE[footer-include](../../includes/footer-banner.md)]