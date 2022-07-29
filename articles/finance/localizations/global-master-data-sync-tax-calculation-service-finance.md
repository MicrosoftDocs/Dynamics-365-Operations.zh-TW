---
title: 將稅金計算服務的稅金設定同步到 Dynamics 365 Finance
description: 本主題說明如何將稅金計算服務的稅金設定主資料同步到 Microsoft Dynamics 365 Finance。
author: wangchen
ms.date: 01/05/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TaxIntegration, TaxServiceParameters
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: intro-internal
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: d5d994934014a146f825431cb53dfbef8fe20bc8
ms.sourcegitcommit: 27475081f3d2d96cf655b6afdc97be9fb719c04d
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2022
ms.locfileid: "8451338"
---
# <a name="sync-the-tax-setup-from-the-tax-calculation-service-to-dynamics-365-finance"></a>將稅金計算服務的稅金設定同步到 Dynamics 365 Finance

[!include [banner](../includes/banner.md)]

本主題說明如何將稅金計算服務的稅金設定主資料同步到 Microsoft Dynamics 365 Finance。

待您完成[開始計算稅金](global-get-started-with-tax-calculation-service.md)的必要設定步驟後，下列稅金設定資料會自動從稅金計算服務同步到財務。

## <a name="sales-tax-code"></a>銷售稅籍代碼

| 稅金計算服務           | Finance                             |
| --------------------------------- | ----------------------------------- |
| 稅籍代碼                          | 銷售稅籍代碼                      |
| 描述                       | 姓名                                |
| 用戶輸入                        | 結算期                   |
| 用戶輸入                        | 總帳過帳群組                |
| 用戶輸入                        | 營業稅金幣別                  |
| 已配置負稅率 | 允許負銷售稅百分比 |

## <a name="tax-value"></a>稅金值

| 稅金計算服務 | Finance                   |
| ----------------------- | ------------------------- |
| 自交易日期起   | 開始日期                 |
| 到交易日期止     | 結束日期                   |
| 最低金額          | 最低限額             |
| 最高金額          | 最高限額             |
| 稅率                | 值                     |
| 不得扣抵率     | 不得扣抵百分比 |

## <a name="tax-limits"></a>稅金限制

| 稅金計算服務 | Finance           |
| ----------------------- | ----------------- |
| 自交易日期起   | 開始日期         |
| 到交易日期止     | 結束日期           |
| 最低稅金金額      | 最低銷售稅 |
| 最高稅金金額      | 最高銷售稅 |

## <a name="sales-tax-group"></a>銷售稅群組

| 稅金計算服務                         | Finance                                    |
| ----------------------------------------------- | ------------------------------------------ |
| 稅務組                                       | 銷售稅群組                            |
| 此稅務組下的稅籍代碼                  | 此銷售稅群組下的銷售稅代碼 |
| 稅籍代碼標記為 **免稅**         | 責任制                                     |
| 稅籍代碼標記為 **免稅**         | 免稅代碼                                |
| 稅籍代碼標記為 **反向收費** | 反向收費                             |
| 稅籍代碼標記為 **使用稅**        | 使用稅                                    |

## <a name="item-sales-tax-group"></a>品項銷售稅群組

| 稅金計算服務             | Finance                                         |
| ----------------------------------- | ----------------------------------------------- |
| 細項稅務組                      | 品項銷售稅群組                            |
| 此細項稅務組下的稅籍代碼 | 此細項銷售稅群組下的銷售稅代碼 |

同步完成後，繼續維護 Finance 的其餘參數以達到過帳和編製報表目的。

> [!NOTE]
> 不支援將稅金設定從 Finance 同步到 稅金計算服務。 關於現有的財務環境，請先在稅金計算服務中建立稅務組。 然後將設定資料同步回到財務環境。
