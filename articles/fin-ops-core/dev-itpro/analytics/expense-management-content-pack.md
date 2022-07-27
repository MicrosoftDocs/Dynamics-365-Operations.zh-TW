---
title: 費用管理 Power BI 內容
description: 本主題介紹費用管理 Power BI 內容中包含的內容。
author: panolte
ms.date: 03/18/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TrvExpenseWorkspace, ExpenseWorkspace
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kfend
ms.search.validFrom: 2018-10-31
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: 178a65c44abd0c9c068d4da1f2684a60062da595247560de4cb81d97ab7b6521
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460218"
---
# <a name="expense-management-power-bi-content"></a>費用管理 Power BI 內容

[!include [banner](../includes/banner.md)]

本主題介紹費用管理 Power BI 內容中包含的內容。 

## <a name="overview"></a>概觀
兩個 Power BI 內容包可用於 8.1 及更高版本中的費用管理。 
- 有一個為送出費用報表的員工設計的個人儀表板。 

  儀表板經過客製化，可向個人提供有關未送出和已送出金額的關鍵資訊，以及對費用交易歷史的歷史和見解。 個人儀表板是一個包含使用者最重要資訊的頁面。

- 有一個為應付帳款記帳員和經理設計的管理儀表板。 儀表板專為追蹤和報表員工的整體開支而量身訂製。 它提供關鍵費用指標，例如未送出的費用、里程和平均費用報表金額。 它使用交易資料並提供所有公司費用管理的彙總檢視表。 它還提供每位員工的明細，並可選取新增財務維度資料。 管理費用分析內容包含： 
  - 概述頁面，其中包含有關費用金額的關鍵指標以及對草稿、處理中和已完成費用報表的見解。 
  - 員工統計頁面，用於按時間、成本類型和統計組查看員工的個人詳情。 
  - 員工比較頁面，用於隨時間比較多名員工。 

所有金額均以公司貨幣顯示。 顯示所有公司的資料，但如果需要，您可以新增公司篩選器。 

## <a name="accessing-the-power-bi-content"></a>存取 Power BI 內容
您可以在 Microsoft Dynamics Lifecycle Services (LCS) 的共用資產庫中找到 Expense Admin Dashboard.pbix 和 Expense Personal Dashboard.pbix Power BI 內容。 如需如何下載內容並在您的組織中實作的相關資訊，請參閱[來自 Microsoft 和您的合作夥伴的 LCS 中的 Power BI 內容](/archive/blogs/dynamicsaxbi/power-bi-content-from-microsoft-and-your-partners)。
該內容可作為嵌入式 Power Bi 內容從費用管理工作區獲得。 任何費用所有者都可以存取自己的個人費用，而只有應付帳款記帳員和經理可以存取管理內容以查看所有使用者的費用資料。

## <a name="refreshing-the-power-bi-content"></a>重新整理 Power BI 內容
費用管理 Power BI 內容需要從實體儲存重新整理 TrvBiExpenseMeasurement 測量和 BudgetActivityMeasure。 

## <a name="metrics-that-are-included-in-the-power-bi-content"></a>Power BI 內容中包含的計量
內容包括一組報表頁面。 每一頁由一組可視覺化為圖表、圖格和表格的指標組成。 下表概述了 Power BI 內容中的視覺效果。

**個人費用分析**

| 報表頁 | 視覺化                             |
|-------------|-------------------------------------------|
| 我的費用 | 里程金額                         |
|             | 處理中的費用報表                |
|             | 否。 未送出的費用               |
|             | 需支付的個人費用              |
|             | 未送出的金額                        |
|             | 已送出的金額                          |
|             | 待償還金額             |
|             | 帶有金額和狀態的費用報表   |
|             | 已送出但未經核准的費用報表  |
|             | 按成本類型劃分的費用                     |
|             | 商家費用                      |
|             | 按已處理費用分列的費用            |
|             | 專案費用                       |
|             | 一段時間內的總交易金額        |

**管理費用分析**

| 報表頁         | 視覺化                           |           
|---------------------|-----------------------------------------|
| 費用概述    | 草稿費用金額                   |
|                     | 草稿費用明細數           |
|                     | 草稿費用明細                     |
|                     | 費用報表原則違規        |
|                     | 未付金額                      |
|                     | 已送出但未經核准的費用       |
|                     | 已核准費用                       |
|                     | 總費用金額                    |
|                     | 費用報表總計                |
|                     | 按成本類型劃分的費用                   |
|                     | 商家費用                    |
|                     | 員工費用                   |
|                     | 費用與專案                     |
| 員工比較 | 費用金額                         |
|                     | 員工隨時間推移的費用金額   |
| 員工統計 | 按成本類型的費用報表            |
|                     | 個人費用                       |
|                     | 按統計組的費用報表     |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]