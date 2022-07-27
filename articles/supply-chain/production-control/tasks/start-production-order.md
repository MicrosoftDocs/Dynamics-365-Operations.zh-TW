---
title: 啟動生產訂單
description: 此程序介紹如何在工廠啟動生產訂單。
author: johanhoffmann
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: JmgRegistrationStartJob
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fa47510d84e5ee156d4f38a076ce17fad8359d147997349de023b64483d66160
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446832"
---
# <a name="start-a-production-order"></a>啟動生產訂單

[!include [banner](../../includes/banner.md)]

此程序介紹如何在工廠啟動生產訂單。 在此流程中報告時間和物料消耗。 建立此程序的示範資料公司為 USMF。 這是解釋生產訂單生命週期的第五個程序 (共七個程序)。


## <a name="start-a-production-order"></a>啟動生產訂單
1. 移至 [生產控制] > [生產訂單] > [所有生產訂單]。
    * 選取具有 [已發放] 狀態的生產訂單。  
2. 在 [動作窗格] 上按一下 [產品訂單]。
3. 點選 [啟動]。
    * 在此頁面上，您可以確認生產訂單的啟動時間。  
4. 按一下「一般」索引標籤。
5. 在 [開始工序]。 編號 欄位，輸入「10」。
6. 在「自動途程耗用量」欄位中，選擇 [永遠]。
7. 點選 [過帳塗程卡] 核取方塊。
8. 在 [自動 BOM 耗用量] 欄位中，選擇 [永遠]。
9. 點選 [過帳揀料單] 核取方塊。
10. 點選 [列印揀料單] 核取方塊。
11. 點選 [確定]。
    * 這是顯示用於生產訂單的物料的列印揀料單。  
12. 關閉頁面。

## <a name="validate-the-picking-list"></a>驗證揀料單
1. 在「動作窗格」上按一下 [檢視]。
2. 點選 [揀料單]。
3. 在清單中，尋找並選擇所需紀錄。
4. 在列表中，按一下所選行中的連結。
5. 點選 [編輯]。
6. 在 [消耗量] 欄位中，輸入一個數字。
7. 點選 [過帳]。
8. 點選 [確定]。
    * 在揀料單日記帳中，過帳生產訂單消耗的物料。 在過帳日記帳之前，如果估計數量與實際消耗數量之間存在差異，可以進行調整。  
9. 按一下 GridPanel 索引標籤。
10. 關閉頁面。

## <a name="verify-the-route-card-journal"></a>驗證途程卡日記帳
1. 在「動作窗格」上按一下 [檢視]。
2. 點選 [途程卡]。
3. 在清單中，尋找並選擇所需紀錄。
4. 在列表中，按一下所選行中的連結。
5. 點選 [編輯]。
6. 在 [時數] 欄位中輸入一個數字。
7. 點選 [過帳]。
8. 點選 [確定]。
    * 在路線卡日誌中，記錄了各個操作所花費的時間。 還可以報告好和錯誤的數量。  


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]