---
title: 大量建立銷售報價
description: 此步驟說明如何有效建立一系列產品或服務的報價，並發送給多個客戶。
author: Henrikan
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SalesQuotationTemplateGroup, SalesQuotationListPage, SalesCreateQuotation, SalesQuotationTable, SysQueryForm, SalesQuickQuote
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: acb2b49c7cb2024aec1140d04150bd1ab9d75c14
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448611"
---
# <a name="mass-create-sales-quotations"></a>大量建立銷售報價

[!include [banner](../../includes/banner.md)]

此步驟說明如何有效建立一系列產品或服務的報價，並發送給多個客戶。 大量報價是根據報價範本建立。 您可使用自己的資料或 USMF 示範資料公司來執行此程序。


## <a name="create-a-quotation-template"></a>建立報價範本
1. 前往銷售和行銷 > 設定 > 報價單 > 範本群組。
2. 按一下新增。
3. 在群組識別碼欄位中，輸入您想要的識別碼。
4. 在 [描述] 欄位中輸入一個值。
5. 按一下儲存。
6. 關閉頁面。
7. 前往銷售和行銷 > 銷售報價 > 所有報價。
8. 按一下新增。
9. 在帳戶類型欄位中，選取「客戶」。
10. 在客戶帳戶欄位中，輸入或選擇一個值。
11. 按一下確定。
    * 如果要將報價變為範本，您必須在報價標題上設定此步驟。 必須於新增報價行之前完成此步驟。   
12. 在動作窗格上按一下選項。
13. 按一下變更檢視。
14. 按一下標題檢視。
15. 展開設定部分。
16. 在群組識別碼欄位中，輸入或選擇一個值。
17. 在範本名稱欄位中，輸入一個值。
18. 在使用欄位中選擇「是」。
    * 只有使用中的範本，可以應用於新的銷售報價。  
19. 在動作窗格上按一下選項。
20. 按一下變更檢視。
21. 按一下行檢視。
22. 在項目欄位中，輸入或選擇一個值。
23. 在項目欄位中輸入值。
24. 關閉頁面。
25. 在折扣比例欄位中，輸入數字。
26. 按一下新增明細。
27. 在項目欄位中，輸入或選擇一個值。
28. 在項目欄位中輸入值。
29. 關閉頁面。
30. 在單價欄位中，輸入新價格或變更目前價格。
31. 按一下新增明細。
32. 在項目欄位中，輸入或選擇一個值。
33. 在項目欄位中輸入值。
34. 關閉頁面。
35. 在數量欄位中，輸入一個數字。
36. 在折扣欄位中，輸入數字。
37. 按一下儲存。

## <a name="apply-the-template-to-create-a-single-quotation"></a>將範本應用至建立單一報價
1. 前往銷售和行銷 > 銷售報價 > 所有報價。
    * 請注意，您剛剛建立的報價單已標記為範本。  
2. 按一下新增。
3. 在帳戶類型欄位中，選取「客戶」。
4. 在客戶帳戶欄位中，輸入或選擇一個值。
5. 展開範本部分。
6. 在群組識別碼欄位中，輸入或選擇一個值。
7. 在範本名稱欄位，輸入或選擇一個值。
8. 在計算方法欄位中，選擇「根據範本值」。
9. 按一下確定。
    * 新的報價已根據範本資料和條款建立。  
10. 關閉頁面。
11. 關閉頁面。

## <a name="apply-the-template-to-mass-create-quotations"></a>將範本應用至建立大量報價
1. 前往銷售和行銷 > 銷售報價 > 報價更新 > 大量建立報價。
2. 在帳戶類型欄位中，選取「客戶」。
3. 在群組識別碼欄位中，輸入或選擇一個值。
4. 在範本名稱欄位，輸入或選擇一個值。
5. 在計算方法欄位中，選擇「根據範本值」。
6. 展開記錄以包含區段。
7. 按一下篩選。
8. 在條件欄位中，設定篩選條件，以覆蓋您希望在此大量報價中包括地客戶。 使用以下格式「客戶 1..客戶 N」。
    * 例如，您可以將過篩選條件設定為：US-001..US-004  
9. 按一下確定。
10. 按一下確定。
11. 前往銷售和行銷 > 銷售報價 > 所有報價。
    * 驗證是否根據所選的範本，為大量更新步驟中指定的所有客戶建立報價。  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]