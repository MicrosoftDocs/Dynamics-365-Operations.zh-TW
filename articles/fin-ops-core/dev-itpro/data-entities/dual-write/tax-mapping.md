---
title: 整合稅務
description: 本主題介紹財務和營運與 Dataverse 之間的稅務資料整合。
author: tonyafehr
ms.date: 09/06/2019
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: tfehr
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 532e6603b74ad0293d65684d2d6858ef31fbc496
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8460449"
---
# <a name="integrated-tax"></a>整合稅務

[!include [banner](../../includes/banner.md)]



稅收設定資料定義了間接稅 (增值稅、商品及服務稅、銷售稅) 和扣繳稅款的設定。 介紹了計稅規則、稅率、稅務核算、結算等概念。

## <a name="templates"></a>範本

稅務資料包括在資料互動期間協同工作的一組表對應，如下表所示。

| 財務和營運應用程式 | 客戶業務開發應用程式 | 描述 |
|-----------------------------|-----------------------------------|-------------|
[品項銷售稅群組](mapping-reference.md#196) | msdyn_taxitemgroups | |
[銷售稅主管機構](mapping-reference.md#193) | msdyn_taxauthorities | |
[銷售稅免稅代碼實體 CDS](mapping-reference.md#194) | msdyn_taxexemptcodes | |
[銷售稅群組](mapping-reference.md#195) | msdyn_taxgroups | |
[銷售稅分類帳過帳群組 V2](mapping-reference.md#197) | msdyn_taxpostinggroups | |
[扣繳稅款代碼](mapping-reference.md#210) | msdyn_withholdingtaxcodes | |
[扣繳稅款群組](mapping-reference.md#211) | msdyn_withholdingtaxgroups | |

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
