---
title: 維護要求
description: 本主題提供有關在資產管理中管理維護要求的概觀
author: johanhoffmann
ms.date: 10/01/2019
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetRequestTable, EntAssetRequestWorkspace, EntAssetRequestActivePart, EntAssetRequestWorkOrderActive, EntAssetRequestType, EntAssetRequestTableCreateWO, EntAssetRequestTableLookup, EntAssetRequestTableActivePart, EntAssetMobileRequestDetails
audience: Application User
ms.reviewer: kamaybac
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 6d247457b83036dba2fad8fd9f94e04c29a3aa5e
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/15/2022
ms.locfileid: "8449736"
---
# <a name="maintenance-requests"></a>維護要求

[!include [banner](../../includes/banner.md)]

維護要求是為了通知經理或計劃者，資產可能需要維護或維修作業而建立的附註或聲明，但不會建立工單。 如果維護要求的內容被認為有效，則可以根據維護要求建立工單。

維護要求可以為資產管理中的任何資產而建立。 根據您公司使用維護要求的方式，可以建立各種類型的維護要求。 這裡有些範例：

- 維護要求
- 附註
- 訂正或增強功能
- 投資
- 倉庫維修 (當您從另一個位置接收資產時會使用此類型，以便您進行維護或維修作業，然後在作業完成後歸還資產。)

## <a name="view-maintenance-requests"></a>檢視維護要求

如要檢視維護要求，請選擇 **資產管理** \> **通用** \> **維護要求** \> **所有維護要求**、**使用中維護要求**，或是 **我的功能位置維護要求**。 每個清單頁面都顯示了與維護要求相關的一些資訊。

![檢視維護要求。](media/01-manage-maintenance-requests.png)

> [!NOTE]
> 使用 **我的功能位置維護要求** 清單頁面來檢視維護要求清單，其中包含您作為工作者相關的機能位置，或安裝在您作為工作者相關的機能位置上的資產。 (有關如何在維護工作者上設定機能位置的資訊，請參閱[維護工作者和工作者群組](../setup-for-objects/workers-and-worker-groups.md)。)
> 
> 雖然客戶帳戶資訊可在資產服務管理 (外部維護) 中使用，但未在資產管理 (內部維護) 中提供。

如要打開記錄的詳細資訊檢視，請在 **所有維護要求** 清單頁面的網格檢視中，在 **維護要求** 欄選擇一個連結。

![檢視維護要求的詳細資料。](media/02-manage-maintenance-requests.png)

動作窗格上的按鈕排列於索引標籤上。 下列資料表簡短說明與資產管理相關的按鈕。

| 按鈕名稱                      | 描述 |
|----------------------------------|-------------|
| 編輯                             | 編輯所選維護要求。 |
| 新產品                              | 建立新的維護要求。 |
| 刪除                           | 刪除選取的維護要求。 |
| 工單集區                  | 將選定的維護要求連線到工單集區。 |
| 工單                       | 根據選取的維護要求建立工單。 |
| 資產錯誤                      | 按一下 **資產錯誤**，您可以在其中對選取的維護要求建立故障登記。 |
| 工單                      | 顯示與選取的維護要求相關的所有工單清單。 |
| 更新維護要求狀態 | 更新維護要求狀態。 |
| 生命週期狀態記錄檔              | 檢視所選維護要求的生命週期狀態記錄檔。 |
| 維護要求詳細資訊      | 列印一份顯示所選維護要求詳細資訊的報告。 |
| 寄送借出資產                  | 選擇一個借出資產，此資產應作為在選定維護要求中選取的資產臨時替代品。 |
| 歸還借出資產                | 將借出資產登記為已歸還。 |



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]