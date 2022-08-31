---
title: 建立 Excel 活頁簿以編輯零售交易
description: 本文章描述如何建立 Excel 活頁簿，以便在 Microsoft Dynamics 365 Commerce 中編輯零售交易。
author: josaw1
ms.date: 11/04/2020
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: global
ms.author: josaw
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.industry: Retail
ms.openlocfilehash: 93e0053c38c9595cab59947e4b65b0b4aa966380
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/12/2022
ms.locfileid: "9270200"
---
# <a name="create-an-excel-workbook-to-edit-retail-transactions"></a>建立 Excel 活頁簿以編輯零售交易

[!include [banner](../includes/banner.md)]

本文章描述如何建立 Excel 活頁簿，以便在 Microsoft Dynamics 365 Commerce 中編輯零售交易。

## <a name="overview"></a>概觀

客戶可從系統的不同部分存取一個預定義的 Excel 範本並用於編輯和稽核零售交易。 然而，客戶也可以為此目的建立自訂 Excel 活頁簿。

## <a name="create-and-configure-an-excel-workbook"></a>建立和設定 Excel 活頁簿

要建立和設定 Excel 活頁簿，以便編輯零售交易，請依照這些步驟操作。

1. 打開 Excel，然後建立一個空白活頁簿。
1. 在 **插入** 索引標籤上，選擇 **我的增益集**。
1. 在右側窗格中，選擇 **新增伺服器資訊** 連結。
1. 輸入伺服器 URL，然後選擇 **確定**。
1. 如果您收到「找不到小程式註冊」錯誤消息，請按照以下步驟解決問題：

    1. 在 Commerce 中，移至 **系統管理 \> 設定 \> Office 應用程式參數**。
    1. 在 **應用程式參數** FastTab 上，選擇 **初始化應用程式參數**。
    1. 在確認訊息方塊中，選擇 **確定**。
    1. 在 **已註冊的小程式** FastTab 上，選擇 **初始化小程式註冊**。
    1. 根據需要重複前三個步驟。

1. 選擇 **設計**，然後選擇 **新增資料表**。
1. 根據需要修改的資料，選擇必須添加到 Excel 活頁簿中進行編輯的實體。 使用下表做為參考。

    | 交易類型 | 要使用的資料實體 |
    |------------------|----------------------|
    | 現金自運交易、線上訂單、非同步客戶訂單、非同步客戶報價 | 交易 (可查帳)、銷售交易 (可查帳)、付款交易 (可查帳)、稅務交易 (可查帳)、折扣交易 (可查帳)、費用交易 (可查帳) |
    | 銀行投放 | 交易 (可查帳)、銀行招標交易 (可查帳) |
    | 保險櫃投放 | 交易 (可查帳)、保險櫃招標交易 (可查帳) |
    | 招標公告 | 交易 (可查帳)、招標公告交易 (可查帳) |
    | 收入、費用 | 交易 (可查帳)、收入/支出交易 (可查帳)、付款交易 (可查帳) |
    | 申報起始金額、取消招標、浮動輸入、更改招標、發票付款、客戶押金 | 交易 (可查帳)、付款交易 (可查帳) |

    > [!NOTE]
    > 每個 Excel 活頁簿只能添加一個資料實體，這點很重要。 此外，必須將由金鑰符號所標記的所有欄位添加到相關活頁簿中。

1. 設定活頁簿後，套用所需的篩選條件。 請務必對檔案中的所有工作表套用相同的篩選條件。 避免將大量資料載入到 Excel 檔案中。 否則，效能可能會受到影響，並且 Excel 和您的系統可能會變慢。 我們建議您始終使用「公司」和「對帳單編號」或「交易編號」做為檔案的篩選條件。
1. 篩選條件設定好後，選擇 **重新整理** 以載入資料。
1. 編輯所需資料，然後進行發佈。 如果 **發佈** 按鈕不可用，某些金鑰欄位可能未添加到 Excel 活頁簿中。

## <a name="additional-resources"></a>其他資源

[編輯和稽核現金自運及現金管理交易](edit-cash-trans.md)

[編輯和稽核線上訂單以及非同步客戶訂單交易](edit-order-trans.md)

[編輯零售交易的財務維度](edit-financial-dim.md)

[將欄位新增至 Excel 活頁簿以編輯零售交易](add-fields-excel.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
