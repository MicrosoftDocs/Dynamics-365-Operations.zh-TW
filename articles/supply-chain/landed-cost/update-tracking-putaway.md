---
title: 更新入庫追蹤
description: 本主題介紹如何設定和執行更新定期入庫工作的追蹤。
author: sherry-zheng
ms.date: 08/02/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: d8e2a42d8e12a5a9cf18e876b6f9e45ecb877881
ms.sourcegitcommit: ecd4c148287892dcd45656f273401315adb2805e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/18/2021
ms.locfileid: "8447702"
---
# <a name="update-tracking-for-put-away"></a>更新入庫追蹤

[!include [banner](../includes/banner.md)]

*更新入庫追蹤* 定期工作設計為夜間定期批次處理執行。 它會標識哪些航程已收到所有庫存交易，哪些航程沒有實際結束日期的值。 然後根據需要將實際結束日期設定為目前日期。

系統為每個 *裝運集裝箱* 的每個旅程 *支線* 建立了 *集裝箱活動*。 這些值由建立航程時選擇的旅程範本定義。 對於每個集裝箱活動記錄，可以為 **開始日期**、**預計結束日期** 和 **實際結束日期** 欄位設定值。 收到一段旅程已開始或已完成的確認後，可以更新這些欄位。

通常，與確認日期相關的資訊由協力廠商 (例如貨運業者) 提供，因為這些動作是在 Microsoft Dynamics 365 Supply Chain Management 外部進行維護。 但是，若要追蹤貨物從旅程支線到達倉庫這一過程 (以貨物入庫為標誌)，則不需要來自協力廠商的資訊。 因此，可以根據 Dynamics 365 Supply Chain Management 中的資訊確定追蹤。

若要設定和執行 *更新入庫追蹤* 定期工作，請按照以下步驟作業：

1. 移至 **到岸成本 \> 定期工作 \> 更新入庫追蹤**。
1. 在 **更新入庫追蹤** 對話方塊中，在 **參數** 區段設定以下欄位：

    - **支線** – 選擇您要更新追蹤之旅程部分的唯一識別名稱/編號。 選擇的值必須代表到達倉庫的航程。
    - **活動** – 選擇在所選航程中進行的活動。 這些值是在追蹤控制中心中為每個旅程範本行分配的。

1. 若要限制應包含在更新中的記錄集，請在 **要包括的記錄** FastTab 上選擇 **篩選** 按鈕。 將出現一個標準查詢對話方塊，您可以在其中定義選擇條件、排序條件和聯結。 這些欄位的運作方式就如同它們為 Supply Chain Management 中其他查詢類型運作時一樣。 此處欄位是唯讀的，並顯示與您的查詢相關的值。
1. 在 **於背景執行** FastTab 根據需求設定批次和排程選項，就像您在 Supply Chain Management 中處理其他工作類型的方式一樣。
1. 選擇 **確定** 以套用您的設定，並執行或排程更新。
