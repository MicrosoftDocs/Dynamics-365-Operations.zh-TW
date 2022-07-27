---
title: 維護要求生命週期狀態
description: 本主題介紹如何在「資產管理」中設定維護要求生命週期狀態。
author: johanhoffmann
ms.date: 04/20/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetRequestLifecycleState, EntAssetRequestLifecycleModel
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3ece0fc1121211706350d804fec59e72ef08282fcba4e65f557a510834738b11
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446928"
---
# <a name="maintenance-request-lifecycle-states"></a>維護要求生命週期狀態

[!include [banner](../../includes/banner.md)]

 


維護要求生命週期狀態定義要求可以經歷的階段。 範例包括 **已建立**、**使用中** 和 **已結束**。 將維護要求轉換為工單時，維護要求生命週期狀態應更新為 **已結束** 或 **已關閉**，以表示維護要求不再處於活動狀態。 在 **所有維護要求** 清單頁面上，可以查看所有維護要求，無論其生命週期狀態如何。

## <a name="set-up-maintenance-request-lifecycle-states"></a>設定維護要求生命週期狀態

1. 選取 **資產管理** \> **設定** \> **維護要求** \> **生命週期狀態**。
2. 選取 **新增** 建立維護要求生命週期狀態。
3. 在 **生命週期狀態** 欄位中，輸入生命週期狀態識別碼。
4. 在 **名稱** 欄位中，輸入名稱。

    在 **詳細資料** FastTab 上，**生命週期模型** 欄位會顯示使用此生命週期狀態的維護要求生命週期模型數目。

5. 如果維護要求在此生命週期狀態期間應處於使用中狀態，請在 **一般** FastTab 上，將 **使用中** 選項設為 **是**。
6. 如果應為處於此生命週期狀態的維護要求自動輸入實際結束日期和時間，請將 **設定實際結束時間** 選項設為 **是**。
7. 如果可以從處於此生命週期狀態的維護要求建立工單，請將 **建立工單** 選項設為 **是**。
8. 如果可以刪除處於此生命週期狀態的維護要求，請將 **刪除** 選項設為 **是**。
9. 如果您使用倉庫修復，則在 **更新** FastTab 上，**資產** 區段中 **輸入** 和 **輸出** 選項是相關的。 如果當維護要求的維護要求生命週期狀態設為 **輸入** 或 **輸出** 時，該維護要求中選擇之資產的資產生命週期狀態應自動更新為 **輸入** 或 **輸出**，則將適當的選項設為 **是**。

下圖顯示 **維護要求生命週期狀態** 頁面的範例。

![維護要求生命週期狀態頁面。](media/02-setup-for-requests.png)

> [!NOTE]
> 維護請求生命週期狀態、生命週期狀態群組和類型與工單生命週期狀態、生命週期狀態群組和類型相關，並以相同的方式使用。 

## <a name="set-up-maintenance-request-lifecycle-models"></a>設定維護要求生命週模型

建立維護要求所需的生命週期狀態後，可將其劃分為生命週期狀態群組或生命週期模型。 維護要求生命週期模型用於建立可用於不同類型維護要求的流程。 至少應建立一個標準的維護要求生命週期模型。

1. 選取 **資產管理** \> **設定** \> **維護要求** \> **生命週期模型**。
2. 選取 **新增** 建立維護要求生命週期模型。
3. 在 **生命週期模型** 欄位中，輸入生命週期模型識別碼。
4. 在 **名稱** 欄位中，輸入名稱。

    在 **詳細資料** FastTab 上，**生命週期狀態** 欄位會顯示在生命週期模型中所選的生命週期狀態數目。 **維護要求類型類型** 欄位會顯示使用生命週期模型的維護要求類型類型數目。

5. 在 **生命週期狀態** 快速索引標籤上，選取應在生命週期模型中包含的生命週期狀態：

    - 若要在生命週期模型中包含生命週期狀態，請在 **剩餘的生命週期狀態** 區段中選取該狀態，然後選取向右箭號按鈕![向右箭號。](media/03-setup-for-requests.png) 將其移至 **選取的生命週期狀態** 區段。
    - 若要在生命週期模型中包含所有可用生命週期狀態，請選取 **選取所有可用狀態** 按鈕![選取所有可用狀態。](media/04-setup-for-requests.png)。 所有生命週期狀態都移到 **已選取生命週期狀態** 區段。
    - 若要將生命週期狀態從生命週期模型中移除，請在 **已選取生命週期狀態** 區段中選取該狀態，然後選取向左箭號按鈕![向左箭號。](media/05-setup-for-requests.png) 將其移至 **剩餘的生命週期狀態** 區段。

6. 如果使用倉庫修復，則 **一般** FastTab 上 **更新** 區段中的欄位相關。

    - 在 **已接收資產的生命週期** 欄位中，選取在接收維護要求中選取要進行倉庫修復的資產時，應將該資產自動更新為的資產生命週期狀態。
    - 在 **已交付資產的生命週期** 欄位中，選取在維護要求中選取的資產在修復後退回時，應將該資產自動更新為的資產生命週期狀態。

下圖顯示 **維護要求生命週期模型** 頁面的範例。

![維護要求生命週模型頁面。](media/06-setup-for-requests.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]