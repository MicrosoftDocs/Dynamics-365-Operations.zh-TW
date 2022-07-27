---
title: 結束生產訂單
description: 此程序說明如何結束生產訂單。
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
ms.openlocfilehash: bb87a8df77ecced213b4bd61c40fa372b092ab765528e1cd96274cf79537d521
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447159"
---
# <a name="end-a-production-order"></a>結束生產訂單

[!include [banner](../../includes/banner.md)]

此程序說明如何結束生產訂單。 建立此程序的示範資料公司為 USMF。 這是解釋生產訂單生命週期的七個程序中的最後一個。


## <a name="end-a-production-order"></a>結束生產訂單
1. 移至 [生產控制] > [生產訂單] > [所有生產訂單]。
    * 選取具有「回報完成」狀態的生產訂單。  
2. 在 [動作窗格] 上按一下 [產品訂單]。
3. 按一下結束。
    * 在此頁面上，您可以確認要結束的生產訂單。  
4. 按一下「一般」索引標籤。
5. 在日期欄位中輸入日期。
6. 在報廢方法欄位中選擇「分配」。
    * 您選擇分配方法時，報廢材料的成本將新增到成品中。  
7. 按一下確定。

## <a name="validate-calculation-results"></a>驗證計算結果
1. 在動作窗格上，按一下「管理成本」。
2. 按一下查看成本比較。
    * 結束生產訂單後，您可以將估計成本價與實際成本價進行比較，以獲得生產差異的概覽。  


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]