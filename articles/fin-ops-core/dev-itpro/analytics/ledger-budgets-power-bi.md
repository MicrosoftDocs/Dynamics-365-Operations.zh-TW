---
title: 實際與預算 Power BI 內容
description: 本主題說明實際與預算 Power BI 內容。 它解釋瞭如何存取報表並提供有關資料模型的資訊。
author: panolte
ms.date: 12/18/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BudgetTrackingWorkspace
audience: Application user, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 7a5628dc67c721bf616803d6a31047cee09d8a434d43c0175dd8639815b7c9a6
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460207"
---
# <a name="actual-vs-budget-power-bi-content"></a>實際與預算 Power BI 內容

[!include [banner](../includes/banner.md)]

本主題說明 **實際與預算** Microsoft Power BI 內容。 它解釋了如何存取 Power BI 報表，並提供有關用於構建內容的資料模型和實體的資訊。

## <a name="overview"></a>概觀

**實際與預算** Power BI 內容是為負責監控其組織中實際與預算績效的個人建立的。 **實際與預算** Power BI 內容可讓您了解您的預算差異。 您可以按科目類別、預算代碼、主科目、主科目說明或會計期間分析本年度的預算，以更好地了解任何差異的原因。

## <a name="accessing-the-power-bi-content"></a>存取 Power BI 內容
來自 **實際與預算** Power BI 內容的報表顯示在 **分類帳預算和預測** 以及 **CFO** 工作區中。

## <a name="reports-that-are-included-in-the-power-bi-content"></a>Power BI 內容中包含的報表
下表提供了有關在 **實際與預算** Power BI 內容中的每個報表頁面上找到的指標的詳情。

| 報告                      | 指標                                                                             |
|-----------------------------|-------------------------------------------------------------------------------------|
| 費用 - 實際與預算 | <ul><li>今年總費用</li><li>今年預算總支出</li></ul>  |
| 收入 - 實際與預算  | <ul><li>今年總收入</li><li>今年預算總收入</li><ul>     |
| 費用                     | <ul><li>今年總費用</li><li>以預算為基礎的費用目標</li><ul> |
| 收入                     | <ul><li>今年總收入</li><li>以預算為基礎的收入目標</li><ul>   |
| 淨收入                  | <ul><li>今年淨收入</li><li>以預算為基礎的淨收入目標</li><ul>   |

## <a name="understanding-the-data-model-and-entities"></a>了解資料模型和實體

| 實體                    | 內容                                                                         |
|---------------------------|----------------------------------------------------------------------------------|
| 總帳活動 | 總帳的交易金額                                       |
| 預算活動         | 預算登記的交易金額                                      |
| 主科目             | 篩選報表的主科目                                               |
| 會計行事曆          | 用於篩選報表的會計行事曆                                            |
| 分類帳                   | 可用於將報表篩選到目前分類帳的分類帳              |
| 預算代碼              | 用於篩選報表的預算代碼                                                |
| 法律實體            | 可用於將報表篩選到目前法律實體的法律實體 |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]