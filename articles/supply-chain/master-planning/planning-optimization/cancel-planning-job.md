---
title: 取消計劃作業
description: 本主題說明如何取消計劃最佳化功能的現行計劃作業。
author: ChristianRytt
ms.date: 02/18/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 85dffae7e5484d34d0cfa4bf44649fcdd69fc36804802ad9f02c122adf5d9785
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447231"
---
# <a name="cancel-a-planning-job"></a>取消計劃作業

[!include [banner](../../includes/banner.md)]

在 Microsoft Dynamics 365 Supply Chain Management 您可以取消使用計劃最佳化功能的現行計劃作業。 在直接從使用者介面 (不是在後台) 觸發計劃最佳化作業時，選取 **取消** 對話方塊，不會取消計劃最佳化作業。 即使您收到如「作業已取消」之類的警告，您仍需要使用以下步驟來取消計劃最佳化的計劃作業。


若要取消現行的計劃作業，請執行以下步驟。 

> [!NOTE]
> 只能取消現行作業。

1. 前往 **主計劃 \> 設定 \> 計劃**。
2. 為計劃執行選取適當的計劃。
3. 選取 **歷程**。
4. 選擇要取消的計劃作業。
5. 選取 **取消**。

直到計劃最佳化服務確認作業已被取消，作業狀態將是 **取消中**。 狀態會接著變更為 **已取消** 狀態。

> [!NOTE]
> 要查看狀態更改，您必須選取 **重新整理** 按鈕來重新整理頁面。

## <a name="additional-resources"></a>其他資源

[規劃最佳化概觀](planning-optimization-overview.md)

[開始使用規劃最佳化](get-started.md)

[規劃最佳化適合度分析](planning-optimization-fit-analysis.md)

[檢視計劃歷程與規劃日誌](plan-history-logs.md)

[將篩選條件套用至計劃](plan-filters.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]