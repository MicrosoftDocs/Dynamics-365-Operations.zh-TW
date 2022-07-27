---
title: 財務績效 PowerBI.com 解決方案
description: 本主題介紹財務績效 PowerBI.com 解決方案。
author: kweekley
ms.date: 05/09/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 106233
ms.assetid: 517e6a88-e7a1-4398-9971-b22fa83306ba
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1ca8338473b2efd91b6570e140ee1def3fa93df14dcf57273f601efb7f548d08
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460220"
---
# <a name="financial-performance-powerbicom-solution"></a>財務績效 PowerBI.com 解決方案

[!include [banner](../includes/banner.md)]

> [!NOTE]
> 此 PowerBI.com 解決方案已被棄用，如[已刪除或棄用的財務和營運應用程式功能](../migration-upgrade/deprecated-features.md#power-bi-content-packs-available-on-appsource)中所述。

本主題介紹 **財務績效** PowerBI.com 解決方案。 它描述了包含的儀表板和報表，並提供了有關用於構建解決方案的資料模型和實體的資訊。

## <a name="main-account-setup"></a>主科目設定
因為組織希望負債和收入金額在報表中顯示為正數，所以主賬戶的設定很重要。 若要使這些主科目顯示為正數金額，主科目類型必須設定為 **負債** 或 **收入**。 使用這些帳戶類型時，透過 Power BI 報表將反轉符號並將金額顯示為正數。

## <a name="dashboard-and-reports-that-are-included-in-the-powerbicom-solution"></a>PowerBI.com 解決方案中包含的儀表板和報表
儀表板包含基於基礎報表的匯總資料圖格。 每個圖格都包含組織中所有公司當年的匯總資訊。 以下是一些圖格：

- 現金
- 今年總收入
- 今年總費用
- 今年淨收入
- 速動比率
- 今年按帳戶類別的總費用
- 流動比率
- 債務佔總資產比例
- 實際收入與預測收入
- 今年的帳單收入
- 今年營運費用率
- 今年的利潤率
- 實際與預算費用 - 所有公司

每個圖格都有一份支援報表。 這些報表包含提供更多資訊的圖表和表格。 下表描述了這些報表。

| 報告                      | 報表包含的資訊 |
|-----------------------------|--------------------------------------|
| 現金分析               | 法律實體現金、季度現金、現金總額和帳戶現金<blockquote>[!NOTE] 按季度劃分的現金資訊不包括第一季度總額中的期初餘額。 它顯示每個季度發佈的新交易總數。</blockquote> |
| 流動比率分析      | 按法律實體劃分的流動比率、按季度劃分的流動比率以及流動資產和流動負債的餘額 |
| 速動比率分析        | 法律實體速動比率、季度速動比率以及現金、應收賬款和流動負債餘額 |
| 銷貨成本科目 | 法律實體的銷貨成本 (COGS)、今年和去年各季度的銷售成本、法律實體的銷貨成本佔銷售額、總銷貨成本和銷貨成本佔銷售額的百分比 |
| 營運資金分析    | 按法律實體劃分的營運資金、按季度劃分的營運資金、流動資產、流動負債和總營運資金 |
| 資產和債務分析     | 按法律實體劃分的總資產和債務對總資產的回報率、債務對總資產的回報率和季度至今的總資產回報率、資產和負債 |
| 利潤率分析      | 按法律實體的實際和預算利潤率、按季度的利潤標記、利潤率百分比和利潤率 |
| 淨收入分析         | 按法律實體劃分的實際和預算淨收入、今年和去年的淨收入以及費用占淨收入的百分比 |
| 盈餘分析           | 法律實體的息稅前實際和預算收益 (EBIT)、今年和去年的息稅前利潤、費用佔收入的百分比以及實際和預算費用佔收入的比例 |
| 收入分析            | 總收入、法律實體實際和預算總收入、今年和去年總收入、法律實體收入預算差異、本期和上期總收入 |
| 費用分析            | 總費用、法律實體的實際與預算總費用、季度的實際和預算總費用、賬戶類別的總費用和營運費用比率 |
| 帳單收入分析     | 應收帳款總額、法律實體應收帳款總額、季度應收帳款總額、應收帳款餘額<blockquote>[!NOTE] 該資訊不包括應收帳款分類帳的期初餘額。 它顯示過帳到應收帳款的新交易總數。</blockquote> |

所有這些報表上的圖表和圖格都可以篩選並固定到儀表板上。 如需如何在 Power BI 中篩選和釘選的相關資訊，請參閱[建立和設定儀表板](https://powerbi.microsoft.com/guided-learning/powerbi-learning-4-2-create-configure-dashboards)。

## <a name="understanding-the-data-model-and-entities"></a>了解資料模型和實體
以下實體被用作 **財務績效** PowerBI.com 解決方案的基礎：

**彙總資料實體**

- **GeneralLedgerActivities** – 該實體按帳戶類別彙總總帳餘額。
- **BudgetActivities** – 該實體按帳戶類別彙總預算餘額。

**資料實體**

- FiscalCalendars
- MainAccounts
- LegalEntities
- 分類帳
- ChartofAccounts

這些實體用於在資料模型中建立計算測量。 計算的測量用於計算內容中使用的關鍵績效指標 (KPI) 和報表。 預設情況下，內容會引入過去三年和未來一年的資料。 若要在您的報表和儀表板上包含其他計算，您可以修改[Microsoft Excel 活頁簿](/dynamics/s-e/)。 此活頁簿是用於建立內容的預設資料模型。


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]