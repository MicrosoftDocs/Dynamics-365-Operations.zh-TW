---
title: 銀行管理工作區
description: 本主題提供有關銀行管理工作區的資訊。 此工作區顯示與公司銀行帳戶相關的資訊。
author: roschlom
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BankTreasurerWorkspace
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: f12f907e6135af60e092a2c20ebfd4d196b2d861
ms.sourcegitcommit: 62ca651c94e61aaa69cfa59e861f263f89d01c4a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/03/2021
ms.locfileid: "8451215"
---
# <a name="bank-management-workspace"></a>銀行管理工作區

[!include [banner](../includes/banner.md)]

**銀行管理** 工作區顯示與公司銀行帳戶相關的資訊。 此工作區包括 **摘要** 檢視表和 **分析** 頁面。 **摘要** 檢視表顯示摘要圖標、銀行帳戶資訊、餘額圖表和相關資訊。 **分析** 頁面使用 Microsoft Power BI 功能顯示與銀行帳戶餘額相關的視覺效果。

## <a name="summary-view"></a>摘要檢視表表

### <a name="summary"></a>摘要

**摘要** 區段中的圖標概述了您的銀行帳戶，並提供您最常用頁面的快速存取。 銀行對帳資訊特定於進階銀行對帳功能。 包含的資訊僅適用於在 **銀行帳戶** 頁面上的 **進階銀行對帳** 選項設定為 **是** 的銀行帳戶。 從 **摘要** 區段，您可以為所有法律實體的銀行帳戶匯入電子銀行文件。

### <a name="bank-accounts"></a>銀行帳戶

法律實體中的每個銀行帳戶都由 **銀行帳戶** 區段的一張卡表示。 顯示目前餘額，您可以深入了解構成該摘要餘額金額的交易。 **過渡交易** 金額還可讓您深入了解構成該摘要金額的交易。 過渡交易是使用過渡功能過帳但尚未清除的任何待定交易。 **待定餘額** 金額是目前餘額減去過渡或待定交易。

該卡還顯示上次對帳銀行帳戶的時間。 僅當為銀行帳戶啟用進階銀行對帳時才會顯示此資訊。

### <a name="balance"></a>餘額

**餘額** 圖表顯示了在 **銀行帳戶** 區段或法律實體中所有銀行帳戶的歷史餘額資訊摘要。 此資訊可用於不同時期：本週、本月、本年度、過去五年和所有時期 (銀行帳戶的完整歷史記錄)。 

如果您正在查看單個銀行帳戶的 **餘額** 圖表，則以銀行帳戶貨幣顯示歷史餘額。 如果您正在查看法律實體中的所有銀行帳戶的圖表，則以會計貨幣顯示歷史餘額。

資料上次更新時間的資訊匯顯示在圖表頂端。 您可以依需要變更資料。

### <a name="related-information"></a>相關資訊

從 **相關資訊** 區段可以打開 **普通日記帳** 頁面以完成銀行轉帳。 您也可以快速打開 **銀行交易** 和 **過渡交易** 頁面。

## <a name="analytics-view"></a>分析檢視表

**分析** 頁面提供有關目前公司銀行帳戶的重要指標。 頁面上提供了以下視覺化項目：

-   以系統貨幣計的銀行總餘額
-   依法律實體分類的餘額
-   銀行帳戶貨幣的今日實際餘額與預測餘額比較
-   依銀行帳戶分類的餘額
-   原幣餘額

您可以從 **現金概觀 – 所有公司** 工作區查看跨所有公司的銀行分析。 如需更多資訊，請參閱[現金概觀 Power BI 內容](Cash-Overview-Power-BI-content.md)。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
