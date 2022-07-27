---
title: 將燃料指數關聯承運業者並作為補充費用
description: 本指南展示如何建立補充分派、貨運補充費用、燃料附加費用的補充主版，以及如何將承運業燃料指數與承運業者關聯。
author: Henrikan
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TMSRatingProfile
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: henrikan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 458ee935bec970fc02e3222dcb0c176cf5ddd509
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449277"
---
# <a name="associate-a-fuel-index-with-a-carrier-as-an-accessorial-charge"></a>將燃料指數關聯承運業者並作為補充費用

[!include [banner](../../includes/banner.md)]

本指南展示如何建立補充分派、貨運補充費用、燃料附加費用的補充主版，以及如何將承運業燃料指數與承運業者關聯。 在執行本指南之前，您需要設定貨運燃料指數。 您可以使用「設定貨運燃料指數」指南來執行此操作。 這些設定工作通常由物流經理完成。 建立此流程的示範資料公司為 USMF。


## <a name="create-an-accessorial-master"></a>建立補充主版
1. 轉到運輸管理 > 設定 > 評等 > 補充主版。
2. 按一下「新增」。
3. 在「補充主版」欄位中，輸入一個值。
4. 在名稱欄位中，輸入一個值。
5. 按一下儲存。

## <a name="create-a-carrier-accessorial-charge"></a>建立貨運補充費用
1. 請移至運輸管理 > 設定 > 評等 > 貨運補充費用。
2. 按一下 「新增」。
3. 在「貨運補充識別碼」欄位中，輸入一個值。
4. 在承運業者欄位中，按一下下拉式按鈕開啟查詢。
5. 在清單中，尋找並選擇所需紀錄。
    * 在本例中，選擇卡車承運業者。  
6. 在列表中，按一下所選行中的連結。
7. 在運輸服務欄位中，按一下下拉式按鈕開啟查詢。
8. 在列表中，按一下所選行中的連結。
9. 在補充主版欄位中，按一下下拉式按鈕開啟查詢。
10. 在清單中，尋找並選擇所需紀錄。
    * 在本例中，選擇新建立的補充主版。  
11. 按一下儲存。

## <a name="create-an-accessorial-assignment"></a>建立補充指派
1. 按一下補充指派。
2. 按一下 「新增」。
3. 在名稱欄位中，輸入一個值。
4. 切換準則部分的擴充。
    * 在準則中，您可以選擇總是套用燃料附加費，或者在本範例中選擇僅套用於特定區域。  
5. 在寄出郵遞區號的欄位中，輸入一個值。
6. 在抵達郵遞區號的欄位中，輸入一個值。
7. 切換計算部分的擴充。
    * 在計算部分，您可以指定如何計算燃料附加費。 此計算取決於您選擇作為計算基礎的「補充單位」。  
8. 在補充費用類型字段中，選取「燃料附加費」。
9. 在補充單位欄位中，選擇「里程」。
10. 在區域欄位中，按一下下拉式按鈕開啟查詢。
11. 在列表中，按一下所選行中的連結。
12. 按一下「儲存」。

## <a name="update-the-carrier-rating-profile"></a>更新承運業者評級設定檔
1. 移至「運輸管理 > 設定 > 運輸 > 運輸承運業者」。
2. 在清單中，尋找並選擇所需紀錄。
3. 切換評級設定檔部分的擴充。
4. 按一下「編輯」。
5. 在運輸燃料指數欄位中，按一下下拉式按鈕開啟查詢。
6. 在列表中，按一下所選行中的連結。
7. 按一下「儲存」。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]