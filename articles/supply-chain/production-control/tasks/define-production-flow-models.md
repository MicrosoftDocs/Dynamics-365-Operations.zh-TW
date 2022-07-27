---
title: 定義生產流程模型
description: 生產流程模型可描述精益製造工作單元如何計算並維持產能。
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LeanProductionFlowModel
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6fb12be6f744cee8af3a845d6b278d1f1462ec5d
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449181"
---
# <a name="define-production-flow-models"></a>定義生產流程模型

[!include [banner](../../includes/banner.md)]

生產流程模型可描述精益製造工作單元如何計算並維持產能。 因此，生產流程模型的定義是工作單元定義的先決條件。 建立此程序的示範資料公司為 USMF。


## <a name="define-a-production-flow-model"></a>定義生產流程模型。 
1. 移至生產控制 > 設定 > 精益生產流程 > 生產流程模型。
2. 按一下新增。
3. 在生產流程模型欄位中，輸入生產流程模型的識別碼。
4. 在模型類型欄位中，選擇一個選項。
    * 有兩種模型類型：輸送量類型和時數類型。 以輸送量類型而言，使用此生產流程模型的工作單元產能將以產品數量表示並計算。 以時數類型而言，使用此生產流程模型的工作單元產能將以時數表示並計算。 請注意，現有生產流程模型無法變更此屬性。 工作單元有產能預留後，就無法變更生產流程模型。  
5. 輸入 EPE 週期內的天數。
    * 間隔是指生產流程或工作單元生產的每個零件至少生產一次的期間。 EPE 週期越短，生產流程就越有彈性。 若 EPE 週期 = 0，則所有需求都可在同一天生產。 EPE 週期會用於排程精益處理作業。 排程工作單元的作業時，若 EPE 週期 = 5，則排程流程會尋找工作單元在到期日 - EPE 週期 (到期日前 5 天) 該時間的產能，以確保產品能在該週期生產。 產品庫存前置時間通常會等於或大於相關生產流程的 EPE 週期。  
6. 在計劃期間類型欄位中，選擇一個選項。
    * 工作單元有產能預留後，就無法變更計劃期間類型。 在此特定工作單元中，您只能選擇期間類型相同的生產流程模型。  
7. 在計劃時間柵欄欄位中，輸入一個數字。
    * 計劃時間柵欄是指相關工作單元可預留產能的天數。 在計劃時間柵欄中，輸入天數。   自動規劃不會計劃此期間以外的看板處理作業。 計劃時間柵欄通常是生產流程或工作單元生產之產品平均庫存前置時間的兩倍。 EPE 週期不應大於計劃時間柵欄的一半。     
8. 在產能不足反應欄位中，選擇一個選項。
    * 選項包括：延後 - 將排程事件的所有需求延後至下一個輸送量足夠的可用生產日。 取消 - 結束排程事件的自動規劃，使相關作業保持在未規劃狀態。   新增至要求日 - 在要求的期間規劃所要求的作業。 這會使當天的單元超載，因此規劃者必須進行檢閱並手動調整。   分配到可用期間 - 將排程事件的不同作業分配到所有可用的生產日，從第一天可用的生產日開始分配。 最低分配數量為看板作業數量。 分配動作會將最低規劃數量 (看板數量) 分配至輸送量足夠的每一天。  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]