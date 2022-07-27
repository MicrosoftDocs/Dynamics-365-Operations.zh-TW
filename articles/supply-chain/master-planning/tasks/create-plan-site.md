---
title: 為地點創建計畫
description: 生產計劃員為特定的項目，計算生產的物料和產能需求。
author: ChristianRytt
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, ReqCreatePlanWorkspace, ReqTransPlanCard, ReqTransPOUrgentFormPart, SysQueryForm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3f7da319d4c28af311d79dc01bb93a9fe2f76480
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448125"
---
# <a name="create-a-plan-for-a-site"></a>為地點創建計畫

[!include [banner](../../includes/banner.md)]

生產計劃員為特定的項目，計算生產的物料和產能需求。 創建採購建議後，他們會在計畫的地點上找到訂單，並確認訂單，從緊急的訂單開始。 最緊急的訂單，是需要在當前日期確定的訂單。 使用示範數據公司 USMF 來執行以下任務。


## <a name="create-a-materials-and-capacity-plan-for-an-item"></a>為項目創建物料和產能計劃
1. 按一下主計畫。
    * 您需要前往預設儀表板。  
2. 按一下執行。
3. 展開記錄以包含區段。
4. 按一下篩選。
5. 在清單中，標記所選資料列。
6. 在 [條件] 欄位中，輸入一個值。
    * 例如：D0001  
7. 按一下確定。
8. 按一下確定。
    * 這可能需要幾分鐘的時間。  
9. 重新整理頁面。

## <a name="identify-the-urgent-planned-orders-for-the-item"></a>確定項目的緊急計劃訂單
1. 打開項目編號列的篩選條件。
2. 使用「以…開始」篩選條件操作，將篩選條件套用到「項目編號」欄位，設定值為「D0001」。
3. 打開訂單日期列篩選條件。
4. 使用「完全正確」篩選條件操作，將篩選條件套用到「訂單日期」，設定值為當前日期。

## <a name="firm-all-the-urgent-orders-for-the-item"></a>確定項目的所有緊急訂單
1. 在清單中，標記或取消標記所有列。
2. 按一下確認。
3. 按一下確定。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]