---
title: 創建產品設定模型
description: 此程序說明如何創建產品設定模型，並輸入基本資訊，例如：屬性和子元件。
author: t-benebo
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCCreateProductConfigurationModel, PCProductConfigurationModelDetails, PCBOMLineDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ca99c0346a3f982164076167c3429587aac18be6
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448113"
---
# <a name="create-a-product-configuration-model"></a>創建產品設定模型

[!include [banner](../../includes/banner.md)]

此程序說明如何創建產品設定模型，並輸入基本資訊，例如：屬性和子元件。 建立此程序的示範資料公司為 USMF。


## <a name="create-a-product-model"></a>創建產品模型

1. 移至 **產品資訊管理\>產品\>產品設定模型**。
1. 選擇 **新增**。
1. 在 **名稱** 欄位中，輸入一個值。
1. 在 **描述** 欄位中，輸入一個值。
1. 在 **求解策略** 欄位中，選擇一個選項。
    * 求解器策略決定如何處理產品設定模型中的限制式。 選擇會對產品配置模型的性能產生影響。  
1. 在 **名稱** 欄位中，輸入一個值。
    * 根組件代表產品設定模型，但也可以用於其他產品模型。  
1. 選擇 **確定**。
1. 在 **重複使用設定** 欄位，選擇一個選項。
    * 如果重複使用設定參數設定為是，則系統將在每次設定會話後，檢查相同的配置，如果找到完全匹配則重新使用。  

## <a name="add-attributes"></a>新增屬性

1. 展開 **屬性** 部分。
2. 選擇 **新增**。
3. 在清單中，標記所選資料列。
4. 在 **名稱** 欄位中，輸入一個值。
5. 在 **求解名稱** 欄位中，輸入一個值。
    * 求解名稱用於產品設定的求解限制式。 不能包含空格或除了 _ (下底線) 以外的特殊字符。  
6. 在 **描述** 欄位中，輸入一個值。
    * 描述文字會顯示給設定使用者，因此可以有助於選擇正確的屬性值。  
7. 在 **屬性類型** 欄位中，輸入或選擇一個值。
    * 屬性類型決定屬性可使用哪些值。  
8. 選擇 **包含在重複使用中** 核取方塊。
    * 此選項僅在選擇重用配置選項時可用。 在重複使用核取方塊中的屬性，代表系統尋找精確匹配時，會考慮該屬性。  

## <a name="add-subcomponents"></a>新增子元件

1. 展開 **子元件** 區段。
2. 選擇 **新增**。
3. 在清單中，標記所選資料列。
4. 在 **名稱** 欄位中，輸入一個值。
5. 在 **求解名稱** 欄位中，輸入一個值。
6. 在 **描述** 欄位中，輸入一個值。
7. 在 **組件** 欄位中，輸入或選擇一個值。
    * 每個子組件必須引用一個組件定義。 這種設計支持可重複使用的組件，並確保一旦定義了組件，它就可以在許多產品模型中使用。  
8. 選擇 **儲存**。
9. 選擇 **BOM 行詳細資訊**。
    * BOM 行詳細信息表單，使用戶能夠為子組件選擇所需的屬性。 每個屬性都可以被賦予一個固定值，或映射到一個屬性。 映射到屬性將導致 BOM 行屬性根據配置選擇獲得不同的值。  
10. 在 **項目號碼** 欄位中，輸入或選擇一個值。
    * 每個子組件代表一個具有基於約束的配置技術的可配置基準產品。 通過項目編號進行引用。  
11. 選擇 **設定** 核取方塊。
12. 選擇 **計算** 欄位中的 **是**。
    * 設置計算選項，確保在為產品運行成本計算時包含該產品。  
13. 選擇 **設定** 索引標籤。
14. 選擇 **設定** 核取方塊。
15. 在 **數量** 欄位中，輸入一個數字。
    * 數量欄位決定設定的產品中將使用多少該產品。  
16. 選擇 **設定** 核取方塊。
17. 在 **每個系列** 欄位中，輸入一個數字。
18. 選擇 **確定**。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]