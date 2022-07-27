---
title: 計算看板數量建議
description: 此流程著重在使用看板數量計算為指定看板原則最佳化看板大小和數量。
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
ms.openlocfilehash: 18d2a8dd2a8c132873744ba890ca6b1eb1fd34b6
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448278"
---
# <a name="calculate-kanban-quantity-suggestions"></a>計算看板數量建議

[!include [banner](../../includes/banner.md)]

此流程著重在使用看板數量計算為指定看板原則最佳化看板大小和數量。 建立此程序的示範資料公司為 USMF。 此流程供價值流經理使用。 先決條件是您已完成將新看板數量計算原則新增到看板規則的過程。


## <a name="create-a-kanban-quantity-calculation"></a>建立看板數量計算
1. 請前往生產控制 > 定期工作 > 看板數量計算 > 計算看板數量。
2. 點選「新增」。
3. 在名稱欄位，輸入'Speaker2016'。
4. 在名稱欄位中，按一下下拉式按鈕開啟查詢。
    * 選取看板原則，該看板原則為新增新看板數量計算原則到看板規則過程中建立的。 例如，Speaker2016。  
5. 在列表中，按一下所選行中的連結。
6. 在規則啟用日期欄位中，將日期和時間設定為 '2012-12-17T08:00:00'。
    * 該日期用來決定哪些固定看板規則包含在看板數量計算中。  
7. 在滿足需求期間開始日期欄位中，將日期和時間設定為 '2012-11-17T09:00:00'。
    * 日期指出計算看板數量的過去需求交易從何時開始納入。  
8. 在滿足需求期間結束日期欄位中，將日期和時間設定為 '2012-12-17T07:59:59'。
    * 日期指出計算看板數量的過去需求交易從何時停止納入。  
9. 在需求期間開始日期欄位中，將日期和時間設定為 '2012-12-17T08:00:00'。
    * 日期指出計算看板數量的目前需求交易從何時開始納入。  
10. 在需求期間結束日期欄位中，將日期和時間設定為 '2013-01-16T07:59:59'。
    * 日期指出計算看板數量的目前需求交易從何時停止納入。  

## <a name="generate-kanban-quantity-proposal"></a>生成看板數量建議
1. 按一下「儲存」。
2. 按一下「生成」。
    * 將會為看板規則 000020 生成看板數量建議明細。  

## <a name="run-kanban-quantity-calculation"></a>執行看板數量計算
1. 按一下「計算」。
    * 這將計算看板數量建議。  
2. 按一下「確定」。
3. 在清單中，標記所選資料列。
    * 請注意，建議的看板數量為 2。  

## <a name="change-product-quantity-and-calculate-again"></a>更改產品數量並重新計算
1. 將產品數量設為 '5'。
2. 按一下「計算」。
3. 按一下「確定」。
    * 請注意，在看板數量為 5 時，建議看板數量更改為 4。  
    * 這是因為在產品數量較少的情況下，我們需要更多的看板來滿足需求。  

## <a name="update-kanban-rule"></a>更新看板規則
1. 在規則生效日期欄位中，輸入日期和時間。
    * 將「規則啟用的日期」設定為將來的某個日期。 例如，今天 + 一年。  
2. 按一下「更新」。
3. 按一下「確定」。
4. 關閉頁面。

## <a name="validate-change-on-kanban-rule"></a>驗證看板規則的更改
1. 前往產品資訊管理 > 精益製造 > 看板規則。
2. 在列表中，按一下所選行中的連結。
    * 選取在上一個子任務中建立的看板規則。 應該是按數字排序的清單中的第一個看板規則。  
3. 切換詳細資料區段的展開項目。
    * 請注意生效日期，這表示著此規則在此日期之前不會啟用。  
4. 切換數量部分的擴充。
    * 請注意，這是您在看板數量計算中輸入的預設數量。  
    * 請注意，這是看板數量計算中的固定看板數量 4。  
5. 按一下 ListPanel 索引標籤。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]