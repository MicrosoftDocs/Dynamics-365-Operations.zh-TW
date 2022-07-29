---
title: 資產異常分析
description: 本主題說明資產管理中的資產異常分析。
author: johanhoffmann
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetObjectFaultCalculate
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 880ed35a9780185836218a5c2a7addb2a47eabd737d6bec99794ecb7a0959791
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447306"
---
# <a name="asset-fault-analysis"></a>資產異常分析

[!include [banner](../../includes/banner.md)]

 

在資產管理中，您可以分析資產異常登記，以了解特定時期內登記的異常總數。 可以從不同的角度分析異常登記，例如專注在資產、資產類型、功能位置、異常徵兆或異常類型。

1. 請按一下 **資產管理** > **查詢** > **資產異常** > **資產異常分析**。

2. 在 **資產異常分析計算** 對話方塊，您可以使用 **層級** 欄位以指示您希望資產異常明細在功能位置上的詳細程度。 

    例如，如果在欄位中插入數字「1」，並且您有一個多級功能位置結構，則一個功能位置的所有資產錯誤明細將顯示在上級，因此一個明細上的時數可能從位於較低層級的功能位置累加。 
        
    如果將數字「0」插入 **層級** 欄位，您將看到一個詳細的結果，其中顯示了與它們相關的所有功能位置層級上的所有資產異常明細。

3. 如果要限制搜尋，可以在 **要包括的記錄** 快速索引標籤上選取具體資產、異常日期、異常原因和異常補救措施。

4. 按一下 **確定** 以開始計算。

5. 在 **資產異常分析** 索引標籤，按一下一個以上的 **以…分組** 按鈕，來顯示您想要查看的詳細程度。 使用中的按鈕被醒目提示。 以按一下按鈕來啟用或停用按鈕。

6. 請按一下 **更新計算** 在螢幕上顯示您的選擇。 

>[!NOTE]
>每次啟用或停用 **以…分組** 按鈕，記得按一下 **更新計算** 按鈕。 這是必須的，因為在重新計算異常機率時會處理大量資料。

## <a name="examples"></a>範例

有很多方法可以分析異常登記。 本節有五個範例，說明在分析資產異常登記時，不同的資料選擇如何提供更多見解和詳細資料。

### <a name="group-by-symptoms"></a>以異常徵兆分組

在下面的螢幕擷取畫面中，只有 **異常徵兆** 按鈕被選取。

- 已對三種異常徵兆進行異常登記：「漏氣」、「保險絲熔斷」和「設備卡住」。  
- 在 **機率%** 欄，所有百分比加起來為 100%。 機率是以在此異常分析中的所有 **異常徵兆** 登記進行計算。

![圖 1。](media/06-controlling-and-reporting.png)

### <a name="group-by-symptoms-and-time-period"></a>按異常徵兆和時間段分組

在下面的螢幕擷取畫面中，新增 **年** 和 **月** 以顯示如何在選定時間段內查看異常記錄。

- 異常徵兆現在顯示為每年/每月的登記。  
- 在 **機率 %** 欄，如果您將每個月的所有百分比相加，則它們加起來為 100%。 機率是以在此異常分析中的 **異常徵兆** 登記進行計算。 如果您的資產上有大量明細，但一個明細有特別高的比例，則表示有異常徵兆需要更仔細地檢查，才找到限制該異常徵兆的登記數量的方法。

![圖 2。](media/07-controlling-and-reporting.png)

### <a name="group-by-multiple-symptoms-and-assets"></a>以多個異常徵兆和資產分組

在以下三個螢幕擷取畫面中，資產和資產類型的組合被用來作為計算基礎，這將增加詳細程度。  

一般情況下，在 **以日期分組**、**以資產分組**、**以功能位置分組** 動作窗群組中的按鈕，以及 **異常** 按鈕 (異常識別碼)，包含期間或資產關係。 **異常徵兆**、**區域**、**類型**、**原因**，和 **解決方式** 按鈕是異常管理中用於分析資產異常登記和查明問題區域的分類。  

**以異常徵兆、資產和資產類型分組**

在下面的螢幕擷取畫面中，新增 **資產** 和 **資產類型** 提供有關異常登記的的更多詳細資料。

- 異常徵兆現在分為 **資產** / **資產類型** / **異常徵兆** 組合。  
- 在 **機率 %** 欄，如果您分別將 **資產** / **資產類型** / **異常徵兆** 的所有百分比相加，則它們各自加起來為 100%。 機率是以在此異常分析中的 **異常徵兆** 登記進行計算。 如果您的資產上有大量明細，但一個明細有特別高的比例，則表示有異常徵兆需要更仔細地檢查，才找到限制該異常徵兆的登記數量的方法。

![圖 3。](media/08-controlling-and-reporting.png)

**以兩種異常徵兆、資產和資產類型分組**

在下面的螢幕擷取畫面中，新增 **區域** 到 **異常徵兆**、**資產** 及 **資產類型**，提供有關異常登記的的更多詳細資料。

- 在 **機率 %** 欄，如果您在一個資產上將 **資產** / **資產類型** / **異常徵兆** 的所有百分比相加，則它們各自加起來為 100%。 機率是以在此異常分析中的 **異常徵兆** 和 **區域** 組合進行計算。 如果您的資產上有大量明細，但一個明細有特別高的比例，則表示有異常區域需要更仔細地檢查，才找到限制該異常區域的登記數量的方法。  

![圖 4。](media/09-controlling-and-reporting.png)

**以三種異常徵兆、資產和資產類型分組**

在下面的螢幕擷取畫面中，新增了 **類型**，並顯示了此範例中最詳細的計算。
 
- 在 **機率 %** 欄，如果您在一個資產上將 **資產** / **資產類型** / **異常徵兆** 的所有百分比相加，則它們各自加起來為 100%。 機率是以在此異常分析中的 **異常徵兆**、**區域** 和 **類型** 組合進行計算。 如果您的資產上有大量明細，但一個明細有特別高的比例，則表示有異常類型需要更仔細地檢查，才找到限制該異常類型的登記數量的方法。

![圖 5。](media/10-controlling-and-reporting.png)


>[!NOTE]
>對於建立在工作訂單和維護要求上的所有異常登記，若需要摘要，請按一下 **資產管理** > **查詢** > **資產異常** > **資產異常**。 在 **資產異常** 頁面，選取資產異常登記並展開 **相關資訊** 窗格，查看有關相關工作訂單或維護要求的資訊。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]