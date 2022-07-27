---
title: 創建訂購單時應用購買合約
description: 此程序說明如何在您創建訂購單時使用購買合約。
author: Henrikan
ms.date: 08/09/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 130524dc8e0c8724e35bf13c6b250ab721383711
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448305"
---
# <a name="apply-a-purchase-agreement-when-creating-a-purchase-order"></a>創建訂購單時應用購買合約

[!include [banner](../../includes/banner.md)]

此程序說明如何在您創建訂購單時使用購買合約。 創建訂購單時，必須應用購買合約，因為合約的一般條款應複製到訂購單標題。 此工作通常由採購代理人執行。 作為本指南的先決條件，您必須擁有有效的購買合約，其中包含廠商和項目的產品數量承諾用量。 如果您的購買合約包含其他類型的承諾用量，則可以使用相同的程序。

## <a name="create-a-purchase-order"></a>建立採購訂單

1. 前往 **生產和採購\>工作區\>採購訂單準備**。
1. 在動作窗格上，選擇 **新建訂購單**。
1. **創建訂購單** 對話框開啟。 選擇一個 **廠商帳戶**。 根據需要檢查和調整其他地址欄位。
1. 展開 **一般** FastTab。
1. 在 **購買合約** 欄位，找到並選擇您要使用的有效合約。 此列出廠商所有可用的合約。  
1. 選擇 **是**。
1. 選擇 **確定**。

## <a name="add-a-line"></a>新增明細

1. 在 **項目編號** 欄位中，輸入一個值。 如果承諾用量中有指定的庫存或位置維度，則您必須在訂購單明細中輸入相同的值才能使用合約。
1. 在 **地點** 欄位中，打開下拉式按鈕以開啟查詢。 地點可能已經使用訂單預設值，或是廠商預設值填入。 如果是這種情況，請跳過此步驟。  
1. 在清單中，尋找並選擇所需紀錄。
1. 在列表中，選擇所選行中的連結。
1. 在 **數量** 欄位中，輸入一個數字。 驗證價格是從承諾用量中複製的價格。  

## <a name="look-up-the-commitment"></a>查看承諾用量

1. 選擇 **更新明細**。
1. 選擇 **附件**。 在這裡，您可以獲得訂購單的詳細資訊。 例如，您可以查看價格，以及價格和折扣是否固定，這意味著如果您將訂購單上的價格或折扣變更為與承諾用量不同的值，系統將刪除連結，因此訂購單明細將無法滿足承諾用量。 您還可以查看是否已選擇強制最大值選項，這意味著，不能以加總所有購買的數量，以超過履行的承諾用量。  
1. 關閉頁面。

## <a name="look-up-the-purchase-agreement"></a>查看購買合約

1. 在 **動作窗格** 上，選取 **一般**。
1. 選擇 **購買合約**。
1. 關閉頁面。
1. 關閉頁面。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]