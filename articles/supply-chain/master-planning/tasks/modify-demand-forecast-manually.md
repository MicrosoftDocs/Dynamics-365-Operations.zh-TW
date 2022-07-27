---
title: 指南：手動修改需求預測
description: 本主題將說明如何修改品項的預測
author: ChristianRytt
ms.date: 08/12/2019
ms.topic: business-process
ms.search.form: EcoResProductDetailsExtended, ForecastSales
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6f48e1689d21fd0085ec38aab8f5171997fbf432
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8447993"
---
# <a name="guide-modify-a-demand-forecast-manually"></a>指南：手動修改需求預測

[!include [banner](../../includes/banner.md)]

本程序將說明如何修改品項的預測。 此程序適用於生產規劃員。

## <a name="modify-the-forecast-for-a-selected-item"></a>修改所選品項的預測

若要修改所選品項的預測：

1. 請前往 **模組 \> 產品資訊管理 \> 產品 \> 已發布產品**。
1. 在清單中，尋找並選擇所需紀錄。 選取您希望修改預測的品項。
1. 在動作窗格上，開啟 **計劃** 索引標籤，並選擇 **需求預測**。
1. 在清單中，選取列。 如果沒有預測明細，請選取動作窗格上的 **新增** 來建立新明細。  
1. 在 **銷售數量** 欄位，輸入正數。 此數字代表品項的預測數量。 如果輸入負數，將顯示錯誤。
1. 視需要填寫其他欄位。
1. 在動作窗格上，選擇 **儲存**。

## <a name="modify-the-forecast-for-one-or-more-items-with-microsoft-excel"></a>使用 Microsoft Excel 修改一或多個品項的預測

若要使用 Microsoft Excel 修改一或多個品項的預測：

1. 執行以下動作之一：
    - 開啟任何品項 (無論哪個品項都無妨) 的 **需求預測** 頁面，如上一節所述。
    - 前往 **總體規劃 \> 預測 \> 手動預測實體 \> 需求預測明細**。
1. 在動作窗格上，選擇 **在 Microsoft Office 中開啟 \> 需求預測實體**。
1. 選取下載位置並儲存，然後在 Excel 中開啟下載的檔案。
1. 如果您看到警告，請選擇 **啟用編輯**。
1. 在 Excel 中，使用 Microsoft Dynamics 工作窗格登入 Supply Chain Management。 請在啟用 **讓我保持登入** 選項的狀態下登入，且必須信任資料連接應用程式。
1. Excel 試算表會顯示貴公司的所有目前需求預測明細。  視需要新增、刪除及編輯需求預測明細。
1. 選擇 Microsoft Dynamics 工作窗格上的 **發佈**，將您的變更上傳回 Supply Chain Management。


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
