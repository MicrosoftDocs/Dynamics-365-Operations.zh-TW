---
title: 使用安全庫存日記帳更新最小涵蓋範圍
description: 此程序介紹如何根據歷史交易計算最小涵蓋範圍提案，然後使用這些提案來更新品項的品項涵蓋範圍。
author: johanhoffmann
ms.date: 08/09/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ReqItemJournalName, ReqItemJournalSafetyStock, EcoResProductInformationDialog, EcoResProductDetailsExtended, ReqItemTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5ae2209fc2412a4a67b46d6eb82ecb70aafc0159
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448632"
---
# <a name="use-the-safety-stock-journal-to-update-minimum-coverage"></a>使用安全庫存日記帳更新最小涵蓋範圍

[!include [banner](../../includes/banner.md)]

此程序介紹如何根據歷史交易計算最小涵蓋範圍提案，然後使用這些提案來更新品項的品項涵蓋範圍。 方法是使用安全庫存日記帳。 用於創建此工作的示範資料公司是 USMF。 此工作適用於生產計劃員，以幫助維持最小涵蓋範圍。


## <a name="create-a-new-safety-stock-journal-name"></a>建立新的安全庫存日記帳名稱
1. 在 **瀏覽窗格** 中，移至 **主規劃 > 設定 > 安全庫存日記帳名稱**。
2. 點選 **新增**。
3. 在 **名稱** 欄位，輸入「物料」。
4. 請在 **說明** 欄位中，輸入「物料」。
5. 關閉頁面。

## <a name="create-a-safety-stock-journal"></a>建立安全庫存日記帳
1. 在 **瀏覽窗格** 中，移至 **主計劃 > 主計劃 > 執行 > 安全庫存計算**。
2. 點選 **新增**。
3. 在 **名稱** 欄位中，輸入或選擇一個值。 選擇您建立的安全庫存日記帳名稱，例如「物料」。  
4. 點選 **建立行**。
5. 請在 **開始日期** 欄位中輸入日期。  
6. 請在 **截止日期** 欄位中輸入日期。
7. 點選 **確定**。 這會為具有庫存交易的維度建立行。  

## <a name="calculate-proposal"></a>計算提案
1. 點選 **計算提案**。
2. 選擇 **使用提前期的平均發貨量** 選項。
3. 將 **倍增因數** 設定為「10」。 倍增因數用於調整提案。 由於示範資料只有少量交易，因此您需要設定因數才能獲得可行的提案。  
4. 點選 **確定**。 向下滾動找到 M0002 和 M0003。 查看 **計算的最小值** 數量資料行。   

## <a name="update-minimum-quantity"></a>更新最小數量
1. 在 **新增最小數量** 欄位，輸入數字。 更新 [新增最小數量] 以符合 [計算的最小數量] 中的值。 如果計算出的最小值為零，您可以輸入所需的未來值。 例如，您可以在此欄位中為擁有倉庫 12 的 M0002 輸入計算的最小數量。  
2. 在清單中，尋找並選擇所需紀錄。 例如，您可以選擇擁有倉庫 12 的 M0002。  
3. 在 **新增最小數量** 欄位，輸入數字。 更新 [新增最小數量] 以符合 [計算的最小數量] 中的值。 如果計算出的最小值為零，您可以輸入所需的未來值。  

## <a name="post-the-new-minimum-quantity-and-validate-the-result"></a>過帳新的最小數量並驗證結果
1. 點選 **過帳**。
2. 點選 **確定**。
3. 點選項目，以打開 **品項編號** 欄位中的連結。
4. 點選項目，以打開 **品項編號** 欄位中的連結。
5. 在 **動作窗格** 上，按一下「計劃」。
6. 點選 **品項涵蓋範圍**。 請注意，已使用安全庫存日記帳中的新最小數量更新了 **最小數量**。  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]