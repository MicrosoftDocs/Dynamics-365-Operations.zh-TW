---
title: 運輸管理雜費
description: 本主題說明運輸產生的費用必須如何與費用代碼相關聯。
author: Henrikan
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2020-10-16
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 776c73b1a29666e393bed7c40059a578fe86cb0d
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448878"
---
# <a name="transportation-management-miscellaneous-charges"></a>運輸管理雜費

[!include [banner](../includes/banner.md)]

與所有雜項費用一樣，運輸產生的費用必須與費用代碼相關聯。 否則，它們將不會作為雜項費用加回訂單中。 此 **收費代碼** 能決定費用如何與新增代碼的訂單和訂單行相關聯。

前往 **運輸管理 > 設定 > 評分 > 雜項費用** 定義資格標準，決定何時特定 **收費代碼** 能適用於收費。

對於每個相關的 **收費模組** 設定 (*客戶* 和 *廠商*)，您應該至少有一個設定，其中 **雜費類型** 會設定為 *無*。 如果缺少此項，雜項費用將 *不會* 加入訂單中。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]