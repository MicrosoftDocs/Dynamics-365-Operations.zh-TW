---
title: 固定資產推延報表
description: 本主題說明如何使用固定資產推延報表。
author: moaamer
ms.date: 01/08/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 23021
ms.assetid: d7e86f72-95db-4423-9b04-761e9536a959
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2017-12-20
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: b0c0c8b1a33041e266ce266dc79b29c8a7dbfa14
ms.sourcegitcommit: 62ca651c94e61aaa69cfa59e861f263f89d01c4a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/03/2021
ms.locfileid: "8451248"
---
# <a name="fixed-assets-roll-forward-report"></a>固定資產推延報表

[!include [banner](../includes/banner.md)]

**固定資產推延** 報表以易於閱讀的 Microsoft Excel 格式、期末結算、財務報表和稅務報表所需的詳細固定資產資料提供。 這份報表包括固定資產的期初和期末餘額，連同期間的估價變動、期間發生的任何新資產收購和處置。 資料以個別固定資產編入報表，另外也彙總固定資產群組和法人實體的數值。

**固定資產推延** 報表使用電子報表 (ER) 框架。 在您可以執行報表之前，固定資產模型和固定資產推延配置必須從 Microsoft Dynamics Lifecycle Services (LCS) 匯入。 有關說明，請參閱[從 Lifecycle Services 下載電子報表配置](/dynamics365/unified-operations/dev-itpro/analytics/download-electronic-reporting-configuration-lcs)。

這份報表可在 Microsoft Dynamics 365 for Finance and Operations、Enterprise edition 7.3，或 Microsoft Dynamics 365 for Finance and Operations Hotfix Enterprise edition (2017 年七月) 使用。 必須將三個 Hotfix 套用在 2017 年七月發行版本的環境：

- **KB 4041754:** 套用平台更新包後，因為不適用當前版本，因此無法從 LCS 下載電子報表 (ER) 配置
- **KB 4056107:** 電子報表 (GER) 累積性更新 5
- **KB 4056353:** 固定資產報表和附註報表不符合 GAAP 和 IFRS 的要求

下表說明報表可用的欄位。


|                    欄位                    |                                                                                                                                描述                                                                                                                                |
|---------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|              餘額：期初              |                                                                                           自報表指定的 “開始” 日期起的固定資產帳面淨值。                                                                                           |
|              餘額：期末              |                                                                                            截至報表指定的 “到” 日期為止的固定資產帳面淨值。                                                                                            |
|         收購：期初價值         |                                                 直到報表指明的 "自" 日期止，所有屬於<strong>收購</strong>和<strong>收購調整</strong>類型的交易金額總和。                                                  |
|      收購：期間收購      |                                                 報表日期範圍期間已經過帳，所有屬於<strong>收購</strong>和<strong>收購調整</strong>類型的交易金額總和。                                                  |
|       收購：期間處置        |                                                                        報表日期範圍期間處置交易已經過帳的所有反向收購金額總和。                                                                        |
|         收購：期末價值         |                                                  直到報表指明的 "到" 日期止，所有屬於<strong>收購</strong>和<strong>收購調整</strong>類型的交易金額總和。                                                   |
|        折舊：期初值         | 直到報表指明的 "自" 日期止，所有屬於<strong>折舊</strong>、<strong>折舊調整</strong>、<strong>特別折舊扣減額</strong>和<strong>異常折舊</strong>類型的交易金額總和。 |
|     折舊：期間折舊     |                         報表日期範圍期間已經過帳，所有屬於<strong>折舊</strong>、<strong>折舊調整</strong>和<strong>異常折舊</strong>類型的交易金額總和。                          |
| 折舊：期間異常折舊 |                                                              報表日期範圍期間已經過帳，所有屬於<strong>特別折舊扣減額</strong>類型的交易金額總和。                                                               |
|       折舊：期間處置       |                                                                       報表日期範圍期間處置交易已經過帳的所有反向折舊金額總和。                                                                        |
|        折舊：期末值         |  直到報表指明的 "到" 日期止，所有屬於<strong>折舊</strong>、<strong>折舊調整</strong>、<strong>特別折舊扣減額</strong>和<strong>異常折舊</strong>類型的交易金額總和。  |
|    增記/減記：期初值     |                              直到報表指明的 "自" 日期止，所有屬於<strong>增記調整</strong>、<strong>減記調整</strong>和<strong>重估</strong> 類型的交易金額總和。                               |
|   增記/減記：期間增記   |                                                                    報表日期範圍期間已經過帳，所有屬於<strong>增記調整</strong>類型的交易金額總和。                                                                    |
|  增記/減記：期間減記  |                                                                   報表日期範圍期間已經過帳，所有屬於<strong>減記調整</strong>類型的交易金額總和。                                                                   |
| 增記/減記：期間重估  |                                                                        報表日期範圍期間已經過帳，所有屬於<strong>重估</strong>類型的交易金額總和。                                                                        |
|   增記/減記：期間處置   |                                                           報表日期範圍期間處置交易已經過帳的所有增記、減記和重估反向金額總和。                                                           |
|    增記/減記：期末值     |                               直到報表指明的 "到" 日期止，所有屬於<strong>增記調整</strong>、<strong>減記調整</strong>和<strong>重估</strong> 類型的交易金額總和。                                |
|          處置：處置日期           |                                                                                                                固定資產帳冊的處置日期。                                                                                                                |
|    處置：處置時的帳面淨值    |                                                                                                    處置時固定資產的帳面淨值。                                                                                                    |
|            處置：銷售值            |                                                                                               固定資產處置帳冊的銷售值 - 銷售交易。                                                                                                |
|           處置：廢料值            |                                                                                               固定資產處置帳冊的廢料值 - 廢料交易。                                                                                               |
|           處置：損/益            |                                                                                 以固定資產帳冊處置交易部分計算的損益值。                                                                                 |



[!INCLUDE[footer-include](../../includes/footer-banner.md)]
