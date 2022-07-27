---
title: 使用負載規劃工作台規劃負載和裝運
description: 本主題說明如何使用負載規劃工作台為銷售訂單建立負載。
author: Mirzaab
ms.date: 07/08/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WHSHistory, WHSLoadTable, WHSLoadPlanningListPage, WHSLoadPlanningWorkbench
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d641ece709d36d8f3ee29cde47918154835a5bb9
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448572"
---
# <a name="plan-loads-and-shipments-using-the-load-planning-workbench"></a>使用負載規劃工作台規劃負載和裝運

[!include [banner](../../includes/banner.md)]

本主題說明如何使用負載規劃工作台為銷售訂單建立負載。 作為先決條件，我們將先建立銷售訂單。 此程序是運輸協調員日常工作的一部分。 建立此程序的示範資料公司為 USMF。


## <a name="create-a-sales-order"></a>建立銷售訂單
1. 移至 **瀏覽窗格 > 模組 > 應收帳款 > 訂單 > 所有銷售訂單**。
2. 選取 **新增**。
3. 在 **客戶帳戶** 欄位中，選擇下拉式按鈕開啟查詢。
4. 選擇帳戶 **US-004**。
5. 選取 **確定**。
6. 在 **項目編號** 欄位中，選擇下拉式按鈕開啟查詢。
7. 選則品項 **A0001**。 **A0001** 可供運輸管理使用。  
8. 在 **站點** 欄位中，選取下拉式按鈕開啟查詢，然後選取品項。
9. 在 **數量** 欄位中，輸入一個數字。
10. 在 **倉庫** 欄位，為此範例輸入「24」。 該倉庫可用於運輸管理和進階倉庫管理。  
11. 選擇 **儲存**。
12. 關閉頁面。

## <a name="create-a-new-load"></a>建立新負載
1. 移至 **瀏覽窗格 > 模組 > 運輸管理 > 規劃 > 負載規劃工作台**。
2. 選擇 **銷售行** 索引標籤。現在，您將為剛剛建立的銷售訂單建置負載。 可以根據採購訂單、轉移訂單和銷售訂單的供需情況建置負載。  
3. 在動作窗格上，選擇 **供應和需求**。
4. 選擇 **至新負載**。
5. 在 **負載範本識別碼** 欄位中，選擇下拉式按鈕開啟查詢。 負載範本定義了整個負載的重量和體積的最大測量值。 例如，負載範本可能代表集裝箱或卡車的大小。 選取品項。
6. 選取 **確定**。

## <a name="rate-and-route-the-load"></a>對負載進行評等和路線選擇
1. 選擇 **評等和路線選擇**。
2. 選擇 **費率路線工作台**。
3. 選擇 **費率工廠**。
4. 在清單中，尋找並選擇所需紀錄。
5. 選擇 **指派**。
6. 關閉頁面。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]