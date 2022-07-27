---
title: 預估生產訂單
description: 您可使用 USMF 示範資料公司或自己的資料集來執行此程序。
author: johanhoffmann
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0450186382b6c306910fc6653f67ce313b7cfc2c69a134a9a806d1a232dc0fd2
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447147"
---
# <a name="estimate-a-production-order"></a>預估生產訂單

[!include [banner](../../includes/banner.md)]

您可使用 USMF 示範資料公司或自己的資料集來執行此程序。 在這兩種情況下，您都需要有「已建立」狀態的未結生產訂單。 這是解釋生產訂單生命週期的第二個程序 (共七個程序)。


## <a name="estimate-a-production-order"></a>預估生產訂單
1. 移至 [生產控制] > [生產訂單] > [所有生產訂單]。
2. 在方格中選擇狀態為「已建立」的訂單。
3. 在 [動作窗格] 上按一下 [產品訂單]。
4. 按一下預估。
    * 在此步驟中，會計算單張生產訂單的估計成本。   
5. 按一下確定。

## <a name="view-the-calculation-details"></a>查看計算詳細資訊
1. 在動作窗格上，按一下「管理成本」。
2. 按一下查看計算詳細資訊。
    * 此頁面會顯示成本明細。 例如，您可以在第一列查看成品的每單位總成本。 隨後的列包含根據物料清單、生產路線和間接成本所計算的成本。  


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]