---
title: 使會計科目表分隔符號唯一碼
description: 本主題說明如何不能為科目表和維度值使用相同的分隔符號。 升級後必須更改分隔符號值。
author: panolte
ms.date: 09/17/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.custom: 265364
ms.assetid: c61391e4-c4bf-4f09-bd18-8107a1bf055e
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: 8
ms.openlocfilehash: a19dc8926df0efeac242e2e42ac37fdad91df9f8
ms.sourcegitcommit: ecd4c148287892dcd45656f273401315adb2805e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/18/2021
ms.locfileid: "8460336"
---
# <a name="make-the-chart-of-accounts-delimiter-unique"></a>使會計科目表分隔符號唯一碼

[!include [banner](../includes/banner.md)]

在 Microsoft Dynamics AX 2012 中，您可以對科目表和維度值使用相同的分隔符號。 在現行版本的 Finance and Operations 中，科目表和維度值不能使用相同的分隔符號。 如果有重複的分隔符號，您可以在升級後更改它。 

## <a name="update-delimiter"></a>更新分隔符號
如果與科目表有矛盾，可以更改科目表分隔符號和專案/子專案識別碼格式。 不能更改其他維度分隔符號。 
- 升級後可以在 **總帳參數** > **科目表和維度** > **更改分隔符號** 中更改科目表分隔符號。 
- 如果唯一的矛盾是專案/子專案識別碼格式，您可以在 **專案管理和會計參數** > **一般** > **修改子專案格式** 中更改該值。 

## <a name="how-to-determine-if-your-environment-requires-updated-delimiters"></a>如何確定您的環境是否需要更新分隔符號 
如果升級環境中的分隔符號發生矛盾，則在分段輸入控制項或維度輸入控制項中輸入值時可能會遇到不穩定。 這意味著在輸入科目和維度組合時，您將需要始終使用查詢或彈出式選單。


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
