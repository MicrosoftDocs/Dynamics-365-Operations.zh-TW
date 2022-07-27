---
title: 維護排程成本
description: 本主題說明資產管理中的維護排程成本。
author: johanhoffmann
ms.date: 08/27/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 267452bf5ec8cafebb5927045e8708a41603ec16f48626b7fd351d13fdb2fab7
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446946"
---
# <a name="maintenance-schedule-cost"></a>維護排程成本

[!include [banner](../../includes/banner.md)]

 

在資產管理中，您可以計算維護排程明細的預算成本。 如果您想要瞭解預期成本的概觀，例如與下一年計劃的預防性維護作業相關成本，這將非常實用。 該計算是根據「維護計劃」、「維護回合」與「維護要求」類型的現有維護排程明細而來。

1. 按一下 **資產管理** > **查詢** > **資產** > **維護排程成本**。

2. 在 **維護排程成本** 對話方塊中，如果您想查看按財務維度分組的成本，您可以選擇一個 **財務維度集**。

>[!NOTE]
>您可在 **總帳** > **會計科目表** > **維度** > **財務維度集** 中設定財務維度集。

3. 您可使用 **等級** 欄位，指定維護排程明細相關機能位置的詳細程度。 例如，如果在欄位中插入數字「1」，並且您有一個多等級機能位置結構，則一個機能位置的所有維護排程明細，將顯示在最高等級，因此一個明細上的時數可能從位於較低等級的機能位置累加。 如果將數字「0」插入 **等級** 欄位，您將看到一個詳細的結果，其中顯示了與它們相關的所有機能位置等級上的所有維護排程明細。

4. 如果要對特定資產進行計算，請在 **要包括的記錄** FastTab 上按一下 **篩選**，並選擇相關資產。 如果需要，您還可以為成本計算指定一個 **預期開始** 的日期，或選擇不同 **狀態**

5. 按一下 **確定** 以開始成本計算。

6. 在 **維護排程成本** 索引標籤 > **分組依據...** 動作窗格群組中，按一下相關按鈕以顯示成本計算所需的詳細等級。 選定的動作窗格群組按鈕將反白顯示。 按一下按鈕以啟用或停用。

7. 如果您想進行新的成本計算，請按一下 **計算成本** 按鈕。

下圖顯示了維護排程成本計算的結果。

![圖 1。](media/17-preventive-maintenance.png)



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]