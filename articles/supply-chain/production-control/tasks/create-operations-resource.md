---
title: 創建營運資源
description: 營運資源執行專案或生產過程的活動。
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WrkCtrTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 90535d3a6cf58fc10309cf035bc74143a96c2add
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448950"
---
# <a name="create-an-operations-resource"></a>創建營運資源

[!include [banner](../../includes/banner.md)]

營運資源執行專案或生產過程的活動。 此程序展示如何定義營運資源。 您能以示範資料公司 USMF 或自己的資料走完這段程序。

1. 前往資源。
2. 按一下新增。
3. 在資源欄位中，輸入一個值。
4. 在 [描述] 欄位中輸入一個值。

## <a name="define-capacity-and-consumption-parameters"></a>定義產能和使用參數
1. 展開營運區段。
2. 在報廢百分比欄位中，輸入一個數字。
3. 在設定類別欄位中，輸入或選擇一個值。
    * 指定成本類別，該類別定義成本設定的占比。  
4. 在執行時間類別欄位中，輸入或選擇一個值。
    * 指定成本類別，該類別定義成本執行時間的占比。  
5. 在數量欄位中，輸入或選擇一個值。
    * 指定成本類別，該類別定義根據輸出數量的資源成本佔比。  
6. 在產能單位欄位中，選擇一個選項。
    * 指定單位，以表示營運資源產能的單位。  
7. 在產能欄位中，輸入一個數字。
8. 在效率百分比欄位中，輸入一個數字。
    * 效率百分比，是指定您期望從營運資源中獲得的效率。 效率百分比調整營運資源的輸送量並影響為資源保留的時間。  
9. 在營運排程百分比欄位中，輸入一個數字。
    * 指定您在營運排程中，營運資源使用的最大百分比容量。  
10. 在有限產能欄位中選擇是。
    * 如果營運資源，於排程中是根據實際可用產能，且須考慮現有的產能預留，則將此選項設定為是。 如果將此選項設定為否，則營運資源會假設為有無限產能，導致資源可能被超額預訂。  
11. 在瓶頸資源中選擇是。

## <a name="define-working-times"></a>定義工作時間
1. 展開行事曆區段。
2. 按一下新增。
3. 在行事曆欄位中，輸入或選擇一個值。
    * 指定工作時間日曆，以定義資源的產能 (以小時為單位)。  
4. 在清單中，尋找並選擇所需紀錄。
5. 在列表中，按一下所選行中的連結。

## <a name="define-resource-capabilities"></a>定義資源能力
1. 展開能力部分。
2. 按一下新增。
    * 功能是指營運資源執行特定活動的能力。 排程引擎會將每個活動的資源需求，與可用營運資源的能力配對，以配置所有資源。  
3. 在產能欄位中，輸入或選擇一個值。
4. 在等級欄位中輸入一個數字。
    * 指定資源處理能力的熟練程度。  
5. 在優先順序欄位中輸入一個數字。
    * 相對於能力，指定營運資源的優先順序。 當以優先順序排程時，優先順序級別最高的 (數值最小) 的營運資源，會優先選擇。  

## <a name="assign-resource-to-resource-group"></a>將資源指派到資源群組
1. 展開資源群組部分。
2. 按一下新增。
    * 資源群組為營運支援定義地點、生產單位和倉庫內容。 營運資源只能在指派給資源群組時進行排程，而且只能指派到資源群組所在的地點。  
3. 在資源群組欄位中，輸入或選擇一個值。
4. 在輸入位置欄位中，輸入或選擇一個值。
    * 指定運營資源使用物料的倉庫位置。  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]