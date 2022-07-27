---
title: 建立生產訂單
description: 此程序說明如何建立生產訂單。
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ProdTableListPage, ProdTableCreate, ProdTable, ProdBOM, ProdRoute, ProdJournalCreate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: cb7eb237758acb6f27c636050fa5a74d1fd758f1
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449340"
---
# <a name="create-a-production-order"></a>建立生產訂單

[!include [banner](../../includes/banner.md)]

此程序說明如何建立生產訂單。 建立此程序的示範資料公司為 USMF。 這是解釋生產訂單生命週期的第一個程序 (共七個程序)。


## <a name="create-a-production-order"></a>建立生產訂單
1. 移至 [生產控制] > [生產訂單] > [所有生產訂單]。
2. 按一下新增生產訂單。
3. 在項目編號欄位中輸入「D0001」。
4. 在交貨欄位中，輸入日期。
    * 交貨日期，指生產訂單應結束，以按時交貨的時間。 此日期可用於安排流程。 例如，您可以自交貨日期起，向後安排訂單。  
5. 將數量設為「20」。
    * 注意：BOM 編號欄位自動顯示當前項目任何使用中的 BOM 編號，但您可以從批准的 BOM 版本列表中，選擇使用中的 BOM 來變更生產訂單的 BOM。    注意：路徑編號欄位自動顯示當前項目任何使用中的路徑編號，但您可以從批准的路徑版本列表中，選擇使用中的路徑來變更生產訂單的路徑。  
6. 按一下建立。

## <a name="validate-the-production-order"></a>驗證生產訂單
1. 在列表中，按一下所選行中的連結。
    * 按一下您剛剛建立的生產訂單連結。 這會打開訂單的詳細資訊頁面。  
2. 按一下編輯。
3. 在交貨欄位中，輸入日期。
    * 例如，您可以變更生產訂單的交貨日期。  
4. 按一下儲存。
5. 關閉頁面。

## <a name="update-the-bom"></a>更新 BOM
1. 在 [動作窗格] 上按一下 [產品訂單]。
2. 按一下 BOM。
    * 打開 BOM 頁面，驗證生產訂單建立時，從預設資料複製的 BOM 資料。 在此程序中，您需要更新 BOM 的數量。  
3. 按一下編輯。
4. 在數量欄位中，輸入一個數字。
    * 變更 BOM 明細上的數量，會影響生產訂單的物料使用成本估算。  
5. 按一下儲存。
6. 關閉頁面。

## <a name="update-the-production-route"></a>更新生產路徑
1. 在 [動作窗格] 上按一下 [產品訂單]。
2. 按一下路徑。
    * 打開路徑頁面，驗證訂單建立時，從預設資料複製的生產路徑資料。 在此程序中，您需要更新生產路徑中作業的數量。  
3. 在清單中，尋找並選擇所需紀錄。
4. 按一下編輯。
5. 在處理數量欄位中，輸入一個數字。
    * 變更流程時間，會影響估計的路徑成本和生產訂單的成本。  
6. 按一下儲存。
7. 關閉頁面。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]