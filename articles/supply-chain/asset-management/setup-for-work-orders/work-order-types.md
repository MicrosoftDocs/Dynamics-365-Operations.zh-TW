---
title: 工單類型
description: 本主題說明在資產管理中的工單類型。
author: johanhoffmann
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetWorkOrderType
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: d77effbfe329a449318d6942918245917f22cdc23defadcb5e85f02c6c786f6d
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447054"
---
# <a name="work-order-types"></a>工單類型

[!include [banner](../../includes/banner.md)]

 

工單類型用於對工單進行分類。 例如，您可能有與預防性維護和矯正性維護相關的工單。

工單類型定義與工單生命週期模型的從屬關係。 工單生命週期模型定義可在工單上設定的工單生命週期狀態。 (工單生命週期狀態的範例包括 **已建立**、**進行中** 和 **已完成**。)

如需有關工單生命週期狀態和專案階段的資訊，請參閱[工單生命週期狀態](work-order-lifecycle-states.md)。

1. 選取 **資產管理** \> **設定** \> **工單** \> **工單類型**。
2. 選取 **新增** 建立工單類型。
3. 在 **工單類型** 欄位，輸入工單類型的識別碼。
4. 在 **名稱** 欄位中，輸入名稱。
5. 在 **工單生命週期模型** 欄位，選擇生命週期模型。
5. 如果應該將與此類工單相關的所有工單作業都應安排給同一維護工作人員，請將 **一位維修工作人員** 選項設定為 **是**。
6. 根據需要在 **成本類型** 欄位，選擇 **糾正**、**預防性** 或 **投資**。 一個工單上的所有工單作業必須具有相同的成本類型。
7. 在 **強制** 區段，將相關選項設定為 **是**，以指定將哪些與故障相關或與維護停機時間相關的資訊新增到此類工單中。

    > [!NOTE]
    > **強制** 區段中的選項與 **工單生命週期狀態** 頁面 (**資產管理** \> **設定** \> **工單** \> **生命週期狀態**) 的 **驗證** 快速索引標籤上的選項有關。

8. 選擇 **儲存**。

![工單類型。](media/16-setup-for-work-orders.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]