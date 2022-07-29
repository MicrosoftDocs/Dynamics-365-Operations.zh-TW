---
title: 建立維度並匯入維度成員
description: 成本會計是一個獨立的模組，需要來自其他模組的主資料。
author: ShylaThompson
ms.date: 09/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CAMDimension
audience: Application User
ms.reviewer: roschlom
ms.custom: 256254
ms.assetid: e1b0a6e3-0c72-4a7d-90e1-20f870c6dbad
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 6febb8a48cf6496fb7f4c2ee9f5281d47aa1ccae1a8ecc51c908b3810302e11c
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450807"
---
# <a name="create-dimensions-and-import-dimension-members"></a>建立維度並匯入維度成員

[!include [banner](../includes/banner.md)]

成本會計是一個獨立的模組，需要來自其他模組的資料。 這些資料分為以下幾類：

-  成本元素
-  成本物件
-  統計維度

**成本元素** 對應於會計科目表中與成本相關的項目。 **成本物件** 對應於任何類型的財務維度，例如您要估計、分配成本或直接測量的產品、成本中心和項目。 **統計維度** 及其成員用於註冊非貨幣分錄。 統計維度成員可以用作成本分配和成本分攤的分攤基礎 

下圖說明了成本會計中使用的維度。

[![成本會計維度。](./media/cost-eos-dimensions.png)](./media/cost-eos-dimensions.png)

將資料匯入成本會計後，您可以使用它來構建各種視角，為組織各個級別的經理提供見解。 以下主題提供有關建立維度和匯入維度成員的資訊。 

-  [成本元素維度](cost-elements.md)
-  [建立成本元素](./tasks/create-cost-elements.md)
-  [成本物件維度](cost-objects.md)
-  [將成本元素維度成員對應到維度成員常用集合](map-cost-elements-dimension-members.md)
-  [對應成本元素維度](./tasks/map-cost-element-dimension.md)
-  [統計維度成員和統計測量提供者範本](statistical-measure-provider-template.md)








[!INCLUDE[footer-include](../../includes/footer-banner.md)]