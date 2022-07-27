---
title: 建立生產流程版本
description: 此程序著重於創建新的生產流程版本。
author: johanhoffmann
ms.date: 11/03/2017
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
ms.openlocfilehash: 5b72d6162edd0ae6ccbfdcfe3e63ecff30528454
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448197"
---
# <a name="create-a-production-flow-version"></a>建立生產流程版本

[!include [banner](../../includes/banner.md)]

此程序著重於創建新的生產流程版本。 對於此程序，必須定義精益製造的生產參數，及類別時間的計量單位。 您還需要定義價值流和生產群組。 若要深入瞭解精益製造中的生產流程和活動，請參閱 Microsoft Dynamics AX 精益製造上的白皮書。 建立此程序的示範資料公司為 USMF。


## <a name="create-a-production-flow"></a>建立生產流程
1. 前往生產控制 > 設定 > 精益生產流程 > 生產流程。
2. 按一下新增。
3. 在名稱欄位中，輸入一個值。
4. 在 [描述] 欄位中輸入一個值。
5. 在名稱欄位中，按一下下拉式按鈕開啟查詢。
6. 在列表中，按一下所選行中的連結。
    * 選擇價值流類型的營運單位。 價值流是營運單位，橫跨價值流的所有活動和流程。 在此階段，營運單位僅限於法律實體實體，但不具進一步的功能。  
7. 按一下 [生產群組] 欄位中的下拉式按鈕以開啟查詢。
8. 在列表中，按一下所選行中的連結。
    * 為生產流程選擇一個生產群組。 生產群組允許為生產流程定義物料、人工和 WIP 帳戶。 若要將計算環境與生產流程相關聯，必須選擇生產群組。  
9. 按一下儲存。

## <a name="create-a-production-flow-version"></a>建立生產流程版本
1. 按一下新增。
2. 在到期日欄位中，輸入日期和時間。
    * 如果需要，請定義版本的到期日。 您可以隨時更新，即使是作業中的版本。 您可以用來計畫逐步淘汰版本。  
3. 按一下確定。
4. 在清單中，標記所選資料列。
5. 在單位欄位中，輸入一個值。
6. 解決差距單位變更。
7. 在 [平均產距時間] 欄位中，輸入一個數字。
    * 定義版本的平均差距時間。 對於生產流程版本的產距時間控制，定義目標平均產距時間。 差距定義每個時間段的數量。 在示例中，差距時間為每 10 件 0.2 小時。 工作時間為 8 小時，這相當於日產能為 400 件。  
8. 在 [每週期數量] 欄位中，輸入一個數字。
    * 定義與平均差距時間相關的每個週期數量。  
9. 按一下切換，展開版本詳細資訊部分。
10. 在 [最小產距時間] 欄位中，輸入一個數字。
    * 定義最短的差距時間。 最小產距時間必須小於或等於平均產距時間。  
11. 在 [最大產距時間] 欄位中，輸入一個數字。
    * 最大產距時間必須大於或等於平均產距時間。  
12. 在實際週期時間 (天) 欄位中，輸入一個數字。
    * 在實際週期時間 (天) 欄位中，輸入天數。 實際週期為從實際分鐘數向後計算實際週期時間的彙總工作天數。 可隨時變更該值，其僅用於計算實際週期。  
13. 按一下儲存。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]