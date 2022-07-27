---
title: 資產異常成本控制
description: 本主題說明資產管理中的資產異常成本控制。
author: johanhoffmann
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetCostControlFault
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 3c36fc791fac6cce0433935adb88eb8cdc23003368204a87efc12cf5a419ec9d
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447012"
---
# <a name="asset-fault-cost-control"></a>資產異常成本控制

[!include [banner](../../includes/banner.md)]

 

在資產管理中，您可以計算資產異常登記的成本，獲得實際成本摘要並且與預算成本進行比較。 實際成本是以已過帳的交易記錄為基礎。 此日期是記錄異常徵兆的異常日期。

1. 請按一下 **資產管理** > **查詢** > **資產異常** > **資產異常成本分析**。

2. 在 **資產異常成本控制** 對話方塊中，選取要包含在計算中的財務維度集 (如果需要)。

4. 如果您不想顯示成本為零的結果，在 **跳過零** 切換按鈕上選取「是」。

5. 您可使用 **程度** 欄位，指定成本控制明細相關功能位置的詳細程度。 

    例如，如果在欄位中插入數字「1」，並且您有一個多級功能位置結構，則一個功能位置的所有資產異常明細將顯示在上級，因此一個明細上的時數可能從位於較低層級的功能位置累加。 
    
    如果將數字「0」插入 **程度** 欄位，您將看到一個詳細的結果，其中顯示了與它們相關的所有功能位置程度上的所有資產異常成本控制。

6. 如果要限制搜尋，可以 **要包括的記錄** 快速索引標籤上選取具體資產、異常日期、異常原因。

7. 按一下 **確定** 以開始計算。

8. 按一下 **分組依據** 按鈕以顯示需要的計算詳細程度。 選定的 **分組依據** 按鈕將反白顯示。 按一下按鈕以啟用或停用。

## <a name="example"></a>範例

此範例顯示了資產異常成本控制計算。

- **原始預算** 欄位中，顯示來自工單預測的預算成本。 
- **實際成本** 欄位，顯示工作訂單上的已過帳成本。 
- **承諾成本** 欄位，顯示與工單相關的公司既定總成本。

    ![圖 1。](media/05-controlling-and-reporting.png)

更多關於如何設定異常的資訊，請參閱[異常管理](../setup-for-work-orders/fault-management.md)主題。


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]