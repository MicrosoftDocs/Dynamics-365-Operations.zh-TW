---
title: 銷售稅分配和覆寫
description: 此程序示範如何為商業管道分配銷售稅群組。
author: Henrikan
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: RetailStoreTable, RetailTaxOverrideCode, RetailTaxOverrideGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f72c9ffde760c1bc151ee15fe050f3704e43d83e
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448980"
---
# <a name="sales-tax-assignment-and-overrides"></a>銷售稅分配和覆寫

[!include [banner](../../includes/banner.md)]

此程序示範如何為商業管道分配銷售稅群組。 也會逐步說明建立新的銷售稅覆寫並將其分配給現有銷售稅覆寫群組的程序。 在 USRT 示範公司資料中可以使用此流程。

1. 移至零售與商務 > 管道 > 商店 > 所有商店。
2. 在清單中點選 [休士頓] 的管道識別碼連結。
3. 按一下 [編輯]。
    * [銷售稅群組] 欄位包含目前公司的銷售稅群組清單。 目前分配的群組是一般的 [德州] 銷售稅群組。 [華盛頓] 和 [華盛頓金縣] 也有銷售稅群組。 銷售稅群組可以包括多個城市的適用稅制。  
    * 可以在 [銷售稅覆寫] 欄位將銷售稅覆寫群組對應到管道。 銷售稅覆寫群組可用於將適用於多個商店的銷售稅覆寫組合在一起。 可以建立群組並將其直接分配給管道以節省時間，而不用手動分配銷售稅覆寫。  
4. 按一下 [儲存]。
5. 關閉頁面。
6. 移至零售與商務 > 管道設定 > 銷售稅 > 銷售稅覆寫。
7. 按一下 [新增]。
8. 在 [銷售稅覆寫] 欄位中，為新覆寫命名。
9. 在 [描述] 欄位中，提供覆寫的描述。
10. 將狀態設為 [啟用]。
11. 展開或摺疊 [覆寫] 區段。
12. 在 [類型] 欄位中，選取一個選項。
    * 品項銷售稅群組可用於覆寫屬於該群組特定品項的稅。 例如，食品品項的納稅方式通常與耐久財不同，所以可能有自己的銷售稅群組。 銷售稅群組是適用於特定管道的稅務群組。 例如，如果某個管道同時開展零售和批發業務，則可以使用不同的品項銷售稅群組。 所有適用的稅都將對應到銷售稅群組。  
    * 現在可以選擇 [來源] 和 [目標] 稅，或 [來源稅群組] 和 [目標稅群組] 來建立銷售稅覆寫。 [來源] 欄位表示要覆寫的稅或稅群組。 透過銷售稅群組覆寫提供的選項比透過銷售稅群組覆寫提供的選擇多。 可以將銷售稅覆寫設定為覆寫整個交易記錄中的稅，或覆寫交易記錄的特定行中的稅。  
13. 按一下 [儲存]。
14. 關閉頁面。
15. 移至零售與商務 > 管道設定 > 銷售稅 > 銷售稅覆寫群組。
    * 在此步驟中，您會將新建立的銷售稅覆寫分配給為休士頓管道分配的銷售稅覆寫群組。  
16. 按一下 [編輯]。
17. 展開或摺疊 [設定] 區段。
18. 按一下 [新增]。
19. 在 [銷售稅覆寫] 欄位中，按一下下拉式按鈕開啟查詢。
20. 從清單中選擇先前建立的銷售稅覆寫。
21. 在列表中，按一下所選行中的連結。
22. 按一下 [儲存]。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]