---
title: 驗證生產流程和版本
description: 此程序說明如何為精益製造建立新的生產流程和第一個版本。
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LeanProductionFlow
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6d87aa427c2bc3868e255c97ea11fd4e79456eef
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448629"
---
# <a name="validate-a-production-flow-and-version"></a>驗證生產流程和版本

[!include [banner](../../includes/banner.md)]

此程序說明如何為精益製造建立新的生產流程和第一個版本。 先決條件：必須定義精益製造的生產參數，及類別時間的計量單位。 您還需要定義價值流和生產群組。 請參閱有關精益製造的白皮書，以熟悉生產流程和活動的概念。 此程序在示範資料中使用的是 USMF 法律實體。 但是，假設為精益製造設定了法律實體，則可以使用其他法律實體。


## <a name="create-a-production-flow"></a>建立生產流程
1. 前往生產控制 > 設定 > 精益生產流程 > 生產流程。
2. 點選 [新增]。
3. 在名稱欄位中，輸入一個值。
4. 在 [描述] 欄位中輸入一個值。
5. 在名稱欄位中，按一下下拉式按鈕開啟查詢。
6. 在列表中，按一下所選行中的連結。
    * 價值流是營運單位，橫跨價值流的所有活動和流程。   在此階段，營運單位僅限於法律實體實體，但不具進一步的功能。  
7. 按一下 [生產群組] 欄位中的下拉式按鈕以開啟查詢。
8. 在列表中，按一下所選行中的連結。
    * 生產群組允許為生產流程定義物料、人工和 WIP 帳戶。 若要將計算環境與生產流程相關聯，必須選擇生產群組。  
9. 點選 [儲存]。

## <a name="create-a-production-flow-version"></a>建立生產流程版本
1. 選點 [新增]。
2. 在到期日欄位中，輸入日期和時間。
    * 您可以在指定時間更新該版本，甚至是有效版本的「到期日期」。 使用版本的到期日期來計劃逐步淘汰版本。  
3. 點選 [確定]。
4. 在清單中，標記所選資料列。
5. 在單位欄位中，輸入一個值。
6. 選擇 [產距時間] 單位。
7. 在 [平均產距時間] 欄位中，輸入一個數字。
    * 對於生產流程版本的產距時間控制，定義目標平均產距時間。   產距時間定義每個時間間隔的產品數量。  在提供的範例中，產距時間為每 10 件 0.2 小時。 工作時間為 8 小時，這相當於日產能為 400 件。  
8. 在 [每週期數量] 欄位中，輸入一個數字。
9. 展開或摺疊 [版本詳細資料] 區段。
10. 在 [最小產距時間] 欄位中，輸入一個數字。
    * 最小產距時間必須小於或等於平均產距時間。  
11. 在 [最大產距時間] 欄位中，輸入一個數字。
    * 最大產距時間必須大於或等於平均產距時間。  
12. 在 [期間] 中輸入實際週期的天數
    * 實際週期為從實際分鐘數向後計算實際週期時間的彙總工作天數。 可隨時變更該值，其僅用於計算實際週期。  
13. 點選 [儲存]。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]