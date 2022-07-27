---
title: 整合的分類帳
description: 本主題介紹使用 Dataverse 在財務和營運與其他 Dynamics 365 應用程式之間整合分類帳資料。
author: tonyafehr
ms.date: 09/06/2019
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: tfehr
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 0deb4198acb59b90bf06e4050889d028df2223e3
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8460234"
---
# <a name="integrated-ledger"></a>整合的分類帳

[!include [banner](../../includes/banner.md)]



在商業應用程式中，分類帳資料定義了公司開展業務的核心設定。 例如，分類帳資料描述了公司遵循的會計年度、交易貨幣以及使用的帳戶。 本主題介紹此核心財務資料的整合。

## <a name="templates"></a>範本

分類帳資料包括一組在資料交流過程中協同工作的核心財務表對應，如下表所示。

財務和營運應用程式 | Customer Engagement 應用程式     | 描述
---------------------------------|----------------------------------|------------
[CDS 匯率](mapping-reference.md#123) | msdyn_currencyexchangerates |
[會計科目表](mapping-reference.md#121) | msdyn_chartofaccountses |
[貨幣](mapping-reference.md#218) | transactioncurrencies |
[匯率貨幣對](mapping-reference.md#122) | msdyn_currencyexchangeratepairs |
[匯率類型](mapping-reference.md#129) | msdyn_exchangeratetypes |
[財務維度格式](mapping-reference.md#130) | msdyn_financialdimensionformats |
[財務維度](mapping-reference.md#128) | msdyn_dimensionattributes |
[會計行事曆整合實體](mapping-reference.md#132) | msdyn_fiscalcalendars |
[會計行事曆期間](mapping-reference.md#131) | msdyn_fiscalcalendarperiods |
[會計行事曆年度整合實體](mapping-reference.md#133) | msdyn_fiscalcalendaryears |
[分類帳](mapping-reference.md#148) | msdyn_ledgers |
[主科目](mapping-reference.md#152) | msdyn_mainaccounts |
[主科目類別](mapping-reference.md#151) | msdyn_mainaccountcategories |

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
