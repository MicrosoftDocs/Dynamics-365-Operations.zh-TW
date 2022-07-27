---
title: 從右到左語言的財務維度和主科目
description: 本主題描述了在使用從右到左的語言時需要做出的決策，並且您必須設定財務維度和主科目。
author: RyanCCarlson2
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: tfehr
ms.custom: 222564
ms.assetid: 875dcebb-1bbb-4841-a8c6-9e134da07e96
ms.search.region: global
ms.author: rcarlson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 0c88b95ba7c596f4e8c1677c475ca92deba1cb71
ms.sourcegitcommit: 9acfb9ddba9582751f53501b82a7e9e60702a613
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/10/2021
ms.locfileid: "8460339"
---
# <a name="financial-dimensions-and-main-accounts-in-right-to-left-languages"></a>從右到左語言的財務維度和主科目

[!include [banner](../includes/banner.md)]

本主題描述了在使用從右到左的語言時應考慮的一些實作決策，並且您必須設定財務維度和主科目。

財務維度和主科目是實作規劃階段的關鍵組成部分。 在系統中建立財務維度和主科目後，它們將用於 **設定科目結構**、**進階規則結構** 和 **財務維度設定以整合應用程式** 頁面。 在這些頁面上定義的順序在系統中用於資料輸入和消費。 在系統的某些地方，財務維度和主科目出現在不同的欄位中。 在其他地方，例如日記帳，財務維度和主科目顯示為單個字串。

## <a name="best-practices-for-setting-up-financial-dimensions-and-main-accounts-in-a-right-to-left-system"></a>在從右到左的系統中設定財務維度和主科目的最佳做法

- 當您為會計科目表選取分隔符號時，請選取雙分隔符號選項之一：雙連字元號 (`--`)、雙槓 (`||`)、雙句點 (`..`) 或雙下劃線 (`\\`)。
- 建立財務維度和主科目值時，僅使用數字和從右到左的語言字元。
- 避免在財務維度和主科目值中使用選定的會計科目表分隔符號。

透過遵循這些最佳做法，您可以幫助保證用戶定義順序在整個系統中的一致表示。


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]