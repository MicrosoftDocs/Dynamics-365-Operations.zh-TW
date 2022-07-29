---
title: 將固定資產與租賃相關聯
description: 本主題說明如何將現有固定資產與新租賃相關聯。
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeaseDetail
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: bd55d433b0961b8b210b9c28d7340ff880635a85
ms.sourcegitcommit: 3af457fc216bd0020843291ca57fd379acb53c96
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/17/2021
ms.locfileid: "8450906"
---
# <a name="associate-fixed-assets-with-leases"></a>將固定資產與租賃相關聯

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

本主題說明如何將現有固定資產與新租賃相關聯。 將固定資產與租賃相關聯時，初始認列時的使用權 (ROU) 資產價值將是固定資產的購置成本。

在將固定資產與租賃關聯之前，您必須在固定資產中為固定資產建立記錄。 然後，在 **租賃摘要** 頁面，您必須建立租賃並將資產連結到該租賃。

1. 按照[新增或複製租賃](add-lease.md)中的步驟新增租賃。 在 **新增租賃** 頁面的 **固定資產編號** 欄位，選擇尚未購置的資產。
2. 選擇 **帳簿**，並確認付款時間表。
3. 選擇 **初始認列**。
4. 選擇 **資產租賃日記帳**。

    租賃的初始認列日記帳分錄借記固定資產的金額，該金額通常借記到使用權資產科目。

    您現在可以查看固定資產的交易類型和帳簿。

5. 選擇 **日記帳詳細資料**。
6. 選擇 **行** 以查看日記帳分錄的各個行。
7. 選擇包含資產的日記帳行，然後選擇 **固定資產** 索引標籤。

    **固定資產** 索引標籤會顯示交易類型和帳簿。 根據預設，**交易類型** 欄位設為 **購置**，**帳簿** 欄位設為固定資產的目前帳簿。

在過帳初始認列日記帳分錄後，交易會顯示為固定資產的購置交易。 要查看交易表，請前往 **固定資產\>固定資產\>固定資產**，選擇適當的資產，然後選擇 **估價**。 您應該會看到初認列日記帳分錄已經為指定的固定資產建立了一筆購置交易。

現在可以使用固定資產中的標準折舊功能對固定資產進行折舊。 有關折舊的詳細資訊，請參閱[折舊方法和慣例](../fixed-assets/depreciation-methods-conventions.md)。

當租賃與固定資產相關聯時，固定資產帳簿上的 **使用年限** 欄位將更新，以與以下標準中的最小值保持一致： 

 - 資產的使用年限
 - 關聯租賃帳簿中的租賃期

如果租賃帳簿的 **所有權轉移** 欄位設為 **是**，則 **使用年限** 欄位中的值將一律是資產的使用年限。 
 
每次調整租賃時都會更新使用年限，以確保使用權資產在租賃期內折舊，如同在資產租賃中折舊一樣。

> [!NOTE]
> 如果您將固定資產與租賃相關聯，則將停用資產租賃中的 **資產折舊** 和 **租賃減值** 按鈕。 您可以從固定資產查看資產折舊和租賃減值交易。 也將停用 **資產交易**，該按鈕用於打開查詢表單。 您也可以在固定資產中打開 **資產交易** 查詢表單。  

**固定資產** 和 **固定資產帳簿** 頁面將顯示與固定資產關聯的租賃識別碼。 如果固定資產與租賃相關聯，則租賃識別碼和租賃描述將顯示在 **固定資產** 頁面的 **租賃資訊** FastTab 上。 對於與租賃帳簿關聯的固定資產帳簿，**租賃識別碼**、**租賃描述** 和 **帳簿類型** 欄位將顯示 **租賃資訊** FastTab 上所選固定資產帳簿的資訊，以表示它與租賃帳簿相關聯。

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
