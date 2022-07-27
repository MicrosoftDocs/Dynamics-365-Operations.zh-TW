---
title: 警示概述 (包含影片)
description: 本主題提供有關警示的一般資訊。 您可以使用警示來隨時了解您想要在工作日追蹤的事件。
author: RichdiMSFT
ms.date: 09/04/2019
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: EventCreateRule
audience: Application user
ms.reviewer: sericks
ms.search.region: Global
ms.author: richdi
ms.search.validFrom: 2018-3-30
ms.dyn365.ops.version: Platform update 15
ms.openlocfilehash: c3332bdf7f2edb693c95a4d5a6f95906e14c0a42
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/15/2022
ms.locfileid: "8460245"
---
# <a name="alerts-overview"></a>警示概述

[!include [banner](../includes/banner.md)]

## <a name="about-alerts"></a>關於警示
警示形成系統中危急事件的通知系統。 您可以使用警示來隨時了解您想要在工作日追蹤的事件。 您可以輕鬆地建立自己的警示規則集，以便收到有關逾期交貨、已刪除訂單、更改價格或其他您必須回應的事件的警示。

在企業資源規劃 (ERP) 中，有幾種典型的場景可以使用警示函數。 這裡有些範例。

### <a name="scenario-1-create-an-alert-rule-for-new-sales-orders"></a>場景 1：為新的銷售訂單建立警示規則

1. 打開 **所有銷售訂單** 頁面。
2. 在動作窗格上，在 **選項** 索引標籤上，在 **分享** 組中，選取 **建立自訂警示**。
3. 在 **建立警示規則** 對話方塊中，在 **提醒我時間** FastTab 上，在 **事件** 欄位中，選 **記錄已建立**。

### <a name="scenario-2-create-an-alert-rule-for-postponement-of-a-delivery-date"></a>場景 2：為延遲交貨日期建立警示規則

1. 打開 **所有訂購單** 頁面。
2. 選取訂購單 ID 以存取訂購單詳情。
3. 展開 **訂購單標題** FastTab。
4. 在動作窗格上，在 **選項** 索引標籤上，在 **分享** 組中，選取 **建立自訂警示**。
5. 在 **建立警示規則** 對話方塊中，在 **提醒我時間** FastTab 上，在 **欄位** 欄位中，選取 **交貨日期**。
6. 在 **事件** 欄位中，選取 **已被推遲**。
    
在您關閉 **建立警示規則** 對話方塊後，您的規則出現在 **管理警示規則** 頁面。 您可以使用 **管理警示規則** 頁面以更新您現有的警示規則。 例如，您可以修改事件觸發器、更新事件通知和更新到期日。 若要打開 **管理警示規則** 頁面，使用動作窗格 **選項** 索引標籤上的 **提醒我** 按鈕。

## <a name="what-occurs-when-an-alert-rule-is-created"></a>建立警示規則時會發生什麼？

建立警示規則時，您可以將預定義事件與特定欄位聯繫在一起。 例如，欄位中指定的日期已到達，或欄位內容發生變化。 或者，您可以將事件與特定頁面上的記錄聯繫在一起。 例如，建立一條記錄，或刪除一條記錄。

當欄位或頁面上的記錄發生所選事件時，會向您發送警示。 例如，您建立一個規則，其中將特定訂購單明細上的 **交貨日期** 欄位與 **在這段時間之前到期** 事件聯繫在一起。 您將時間範圍設定為五天。 在這種情況下，會在該訂購單明細的交貨日期後五天發送警示。

此外，您可以透過設定條件來改善警示規則。 例如，您可以收到有關為特定廠商帳戶建立的新訂購單的警示。

## <a name="preparing-for-an-alert"></a>準備警示

在設定警示規則之前，請確定您希望何時或在什麼情況下接收警示。 當您知道要通知哪個事件時，找到導致該事件出現的資料的頁面。 該事件可以是到達的日期或發生的特定更改。 因此，您必須找到指定日期的頁面，或者出現更改的欄位或建立的新記錄的頁面。 在獲得此資訊後，您可以建立警示規則。

## <a name="components-of-an-alert-rule"></a>警示規則的組成部分

警示規則有五個組成部分：

- **事件** – 觸發警示規則的事件可以是到達的日期或發生的特定更改。 您在 **建立警示規則** 對話方塊的 **寄送有關工作狀態更改的電子郵件警示** FastTab 定義事件。
- **條件** – 在 **建立警示規則** 對話方塊的 **提醒我** FastTab 上，您可以選取條件的範圍，以控制何時收到有關事件的警示。 您可以僅將規則套用於現行的記錄，也可以套用於頁面上的所有可見記錄。 如果規則適用於法律實體，您可以將 **組織範圍** 選項設定為 **是**。
- **規則到期** – 在 **建立警示規則** 對話方塊的 **提醒我直到** FastTab 上，您可以指定警示規則應該啟用多長時間。
- **內容** – 在 **建立警示規則** 對話方塊的 **提醒我的方式** FastTab 上，您可以指定警示訊息應使用的主題文字和訊息文字。
- **使用者** – 在 **建立警示規則** 對話方塊的 **提醒誰** FastTab 上，您可以指定應該接收警示訊息的使用者。 在預設情況下，您的使用者 ID 已選取。

    > [!NOTE]
    > 此選項僅限於組織管理員。

## <a name="videos"></a>影片

### <a name="how-to-use-alerts-to-monitor-filtered-data"></a>如何使用警示來監控篩選的資料

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3DWZ3]

[如何使用警示來監控篩選的資料](https://youtu.be/ZYKMcv6kl9s)影片 (如上所示) 包含在 YouTube 上的[財務和營運播放清單](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW)。

### <a name="alert-rule-options"></a>警示規則選項

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3E4PV]

[警示規則選項](https://youtu.be/cpzimwOjicM)影片 (如上所示) 包含在 YouTube 上的[財務和營運播放清單](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW)中。




[!INCLUDE[footer-include](../../../includes/footer-banner.md)]