---
title: 改善預測模型
description: 本主題說明您可以用來改善預測模型效能的功能。
author: ShivamPandey-msft
ms.date: 07/16/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-05-28
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: 804c18c1b165fff99390db1fda22da0137249373
ms.sourcegitcommit: e40a9fac5bac9f57a6dcfe73a1f21856eab9b6a9
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/02/2021
ms.locfileid: "8451011"
---
# <a name="improve-the-prediction-model"></a>改善預測模型

[!include [banner](../includes/banner.md)]

本主題說明您可以用來改善預測模型效能的功能。 您開始在 Microsoft Dynamics 365 Finance 中的 **Customer 付款預測** 工作區改善您的模型。 接著在 AI Builder 完成改善步驟。

## <a name="select-historical-outcomes"></a>選取歷史結果

您先選取三個可能發票結果中的一個或多個：**準時**、**遲** 和 **非常遲**。 所有三個結果皆應選取。 如果您清除任何選取的結果，發票將從訓練流程中篩除，預測的精確度將會降低。

[![確認結果。](./media/confirm-3-outcomes.png)](./media/confirm-3-outcomes.png)

如果貴組織只要求兩個結果，請更改 **遲** 和 **非常遲** 的門檻值為 0 (零) 天。 您可以藉由這個方式有效地將預測收合到 **準時** 或 **遲** 的二元狀態。

## <a name="select-fields"></a>選取欄位

當您選取預計納入模型的欄位時，請注意清單包括 Microsoft Dataverse 資料表中所有開放使用的欄位，此資料表對應 Azure 資料湖的資料。 其中一些欄位 **不** 應該選取。 不應該選取的欄位屬於下列三類中其中一類：

- 此欄位是 Dataverse 資料表的必備欄位，但資料湖沒有支援資料。
- 此欄位是識別碼，因此對機器學習功能沒有意義。
- 此欄位代表預測期間將不開放使用的資訊。

下列各章節顯示用在發票和客戶實體的欄位，並且列出 **不** 應該選取進行訓練的欄位。 專為各個欄位指明的類別係指上述清單的類別。
 
### <a name="invoice-dataverse-table"></a>發票 Dataverse 資料表

下圖顯示開放發票資料表使用的欄位。

[![開放發票資料表使用的欄位。](./media/available-fields.png)](./media/available-fields.png)

不應該選取進行訓練的欄位如下：

- **發票帳戶** (第 2 類)
- **已結案** (第 3 類) – 本欄位用來篩選訓練用發票 (已結案) 和預測發票 (未結案)。
- **名稱** (第 1 類)
- **來源識別碼** (第 2 類)
- **來源記錄** (第 2 類)
- **來源資料表** (第 2 類)

### <a name="customer-dataverse-table"></a>客戶 Dataverse 資料表

下圖顯示開放客戶資料表使用的欄位。

[![開放客戶資料表使用的欄位。](./media/related-entities.png)](./media/related-entities.png)

不應該選取進行訓練的欄位如下：

- **列項唯一鍵** (第 2 類)

## <a name="filters"></a>篩選器

您可以藉由設定發票欄位或客戶資料表欄位的篩選標準，篩選用於訓練的發票。 例如，您可以設定門檻值，只包括總數等於或超過特定金額的發票。 或者，您可以排除與特定客戶群組的客戶相關聯的發票。

更多篩選您的資料的資訊，請參閱[建立預測模型](/ai-builder/prediction-create-model#filter-your-data)。

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
