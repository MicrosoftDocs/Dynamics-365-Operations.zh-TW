---
title: 生產中的物料替換
description: 本主題介紹如何在生產流程中替換物料。
author: johanhoffmann
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ProdBOM
audience: Application User
ms.reviewer: kamaybac
ms.custom: 70171
ms.assetid: ce3b11ef-550e-49b7-8942-2607c2ec3c5c
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f24ed91c7a99eba6129d18c385cea9c9312aebefc325c7e0914b1c0b32231e32
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447171"
---
# <a name="material-substitution-in-manufacturing"></a>生產中的物料替換

[!include [banner](../includes/banner.md)]

本主題介紹如何在生產流程中替換物料。 

在生產流程中替換物料的方法有以下三種：

-   按日期，即某物料在特定日期之後替換為另一種物料時
-   在主計劃期間，即因為物料缺貨，將其替換為不同物料時
-   在生產期間，即物料意外缺貨並被另一種物料替換時

## <a name="substituting-material-by-date"></a>按日期替換物料
考慮以下案例：公司製造的機器包含一個組件，該組件將在兩個月後從廠商的目錄中過期。 從到期日起，廠商將提供可以替換舊組件的新組件。 可以在物料清單 (BOM) 行上設定起止日期。 對於此範例，您透過在 **結束日期** 欄位中輸入到期日期將舊組件設定為到期。 然後在 BOM 上，設定新的替換組件，使其從舊組件到期後的第二天開始生效。 為此，請在 **開始日期** 欄位中輸入開始日期。

## <a name="substituting-material-by-planning"></a>按計劃替換物料
只有在使用配方而不是在使用 BOM 時，才能在計劃期間替換物料。 考慮以下案例：一家食品製造公司正在使用含有 20 種成分的配方製作醬汁。 配方中的一種成分可以用另外兩種成分中的一種代替。 但是，由於這兩種成分比首選成分更昂貴，因此只有在首選成分缺貨時才使用替換品。 可以替換的物料稱為 A，而可以替換它的兩種物料稱為 B 和 C。按計劃的物料替換是由配方行上的 **計劃群組** 和 **優先順序** 欄位控制的。 對於此範例，您為三種物料建立配方行，並將配方行與同一計劃群組相關聯。 在設定中，物料 A 的配方行優先順序最高 (編號最小)，物料 C 的配方行優先順序最低，物料 B 的配方行的優先順序介於其他兩行的優先順序之間。 如果您對成品有需求，主計劃會先確定是否可以滿足物料 A 的需求。 如果無法滿足需求，則總體規劃會按優先順序順序查看物料 B 和 C。 如果物料 B 是現有庫存物料，它將在確定配方的計劃批次訂單後使用。 如果這些物料都不是現有庫存物料，主計劃會為物料 A 建立計劃訂單。**請注意：** 當您在計劃群組中設定配方行時，應僅在具有最高優先順序的物料上指定數量。 此數量將用於計算計劃中所有物料的需求，即使是優先順序較低的物料。 您不能在計劃群組中的低優先順序品項上指定不同的數量。

## <a name="substituting-material-during-production"></a>在生產期間替換物料
考慮以下案例：焊接作業需要一塊金屬板。 在作業過程中，一名倉庫工人通知機器操作員金屬板缺貨。 但是，金屬板可以用稍厚的金屬板代替。 這樣，就可以完成作業了。 可以將物料新增到未結生產訂單的 BOM 中。 如果生產訂單的狀態為 **已開始**，當使用者將新品項新增到生產 BOM 時，會要求使用者重新估算訂單。 新增物料後，可以為新品項建立新的揀料單。 您不必將新物料新增到生產 BOM。 相反，您可以將其直接新增到生產揀料單中。 然後，當揀料單過帳時，系統會將物料新增到生產 BOM。





[!INCLUDE[footer-include](../../includes/footer-banner.md)]