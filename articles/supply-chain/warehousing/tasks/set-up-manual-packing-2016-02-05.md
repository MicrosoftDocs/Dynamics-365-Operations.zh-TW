---
title: 設定手動包裝 (2016 年 2 月和 2016 年 5 月)
description: 包裝流程可讓您驗證產品並將其包裝到集裝箱中。
author: Mirzaab
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLocationProfile, WHSParameters, WHSContainerType, WHSPackProfile, WHSCloseContainerProfile, InventLocationIdLookup, UnitOfMeasureLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bbcd9653f2f3752f067828918ee61d96f9307c6d
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448869"
---
# <a name="set-up-manual-packing-february-2016--may-2016"></a>設定手動包裝 (2016 年 2 月和 2016 年 5 月)

[!include [banner](../../includes/banner.md)]

包裝流程可讓您驗證產品並將其包裝到集裝箱中。 在這個流程中，倉庫工作人員從儲存位置挑選產品並將它們移動到包裝站，他們會在包裝站檢查品項的數量和類型，並將其指派到適當的集裝箱中。 當集裝箱裝滿後，他們可以將其關閉並將其移動到出庫碼頭，產品就可以裝運了。 此程序使用的是 USMF 示範公司。 此程序僅適用於 Dynamics 365 for Operations 的 2016 年 2 月和 2016 年 5 月的版本。


## <a name="set-up-location-profiles"></a>設定位置設定檔
1. 移至倉庫管理 > 設定 > 倉庫 > 位置設定檔。
2. 點選 [新增]。
    * 位置設定檔用於包裝站，並包含位置的資訊和規則。  
3. 在 [位置設定檔識別碼] 欄位中，輸入一個值。
4. 在名稱欄位中，輸入一個值。
5. 在 [位置格式] 欄位中，輸入或選取一個值。
6. 在 [位置類型] 欄位中，輸入或選取一個值。
7. 在 [允許混合品項] 欄位選取 [是]。
8. 在 [允許庫存狀態] 欄位選取 [是] 。
9. 在 [覆寫批次天數的規則] 欄位選取 [是]。
10. 關閉頁面。

## <a name="set-up-warehouse-management-parameters"></a>設定倉庫管理參數 
1. 移至倉庫管理 > 設定 >倉庫管理參數。
2. 按一下 [包裝] 索引標籤。
3. 在 [包裝位置的設定檔識別碼] 欄位，輸入或選取一個值。
    * 選取要用於包裝的位置設定檔。  
4. 關閉頁面。

## <a name="set-up-container-types"></a>設定集裝箱類型
1. 移至倉庫管理 > 設定 > 集裝箱 > 集裝箱類型。
2. 點選 [新增]。
    * 您可以定義要使用的集裝箱類型。 您可以指定集裝箱的實際尺寸，包括皮重、最大重量、最大體積、長度、寬度和重量。  屬性是允許您在集裝箱類型上新增額外尺寸的自訂欄位。     
3. 在 [集裝箱類型代碼] 欄位中，輸入一個值。
4. 在 [描述] 欄位中輸入一個值。
5. 在 [皮重] 欄位中，輸入一個數字。
6. 在 [最大重量] 欄位中輸入一個數字。
7. 在 [體積] 欄位中輸入一個數字。
8. 在 [長度] 欄位中輸入一個數字。
9. 在 [重量] 欄位中輸入一個數字。
10. 在 [高度] 欄位中輸入一個數字。
11. 點選 [儲存]。
12. 關閉頁面。

## <a name="set-up-packing-profiles"></a>設定包裝設定檔
1. 移至倉庫管理 > 設定 > 包裝 > 包裝設定檔。
2. 點選 [新增]。
3. 在 [包裝設定檔識別碼] 欄位中，輸入一個值。
4. 在 [描述] 欄位中輸入一個值。
5. 在 [集裝箱關閉設定檔設定檔] 欄位，輸入或選取一個值。
    * 集裝箱關閉設定檔識別碼是可選的，是此包裝設定檔的預設關閉集裝箱設定檔。  
6. 在 [集裝箱識別碼模式] 欄位中，選擇一個選項。
    * 此選項決定在建立集裝箱時是自動產生集裝箱識別碼，還是手動建立集裝箱識別碼。  
7. 在 [集裝箱類型] 欄位中，輸入或選取一個值。
    * 建立新集裝箱時預設會使用集裝箱類型。  
8. 選取 [集裝箱關閉時自動建立集裝箱] 核取方塊。
9. 點選 [儲存]。
10. 關閉頁面。

## <a name="set-up-container-closing-profiles"></a>設定集裝箱關閉設定檔
1. 移至倉庫管理 > 設定 > 集裝箱 > 集裝箱關閉設定檔。
    * 集裝箱關閉設定檔定義集裝箱關閉時發生的情況。 您可以設定多個關閉集裝箱設定檔。       
2. 點選 [新增]。
3. 在 [集裝箱關閉設定檔設定檔] 欄位，輸入一個值。
4. 在 [描述] 欄位中輸入一個值。
5. 在 [資訊清單] 欄位中，選擇一個選項。
    * 指定是否在關閉集裝箱或確認裝運時顯示。 請注意，顯示要求運輸管理。 必須在運輸引擎中實施清單才能使其運作。  
6. 在倉庫欄位中，輸入或選擇一個值。
7. 在 [最終裝運的預設位置] 欄位中，輸入或選取一個值。
    * 這將是關閉集裝箱後產品將移動到的位置。 此位置必須具有在倉庫參數上定義的位置設定檔。  
8. 在 [重量單位] 欄位中，輸入或選取一個值。
9. 點選 [儲存]。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]