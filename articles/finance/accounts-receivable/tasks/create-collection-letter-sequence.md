---
title: 建立催款單序列
description: 使用此程序建立催款單序列。
author: JodiChristiansen
ms.date: 12/07/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CollectionLetterCourse
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: adeae6e20a799165e086df28b92a1357e8f2f0d3
ms.sourcegitcommit: f82372b1e9bf67d055fd265b68ee6d0d2f10d533
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/14/2021
ms.locfileid: "8451308"
---
# <a name="create-a-collection-letter-sequence"></a>建立催款單序列

[!include [banner](../../includes/banner.md)]

使用此程序建立催款單序列。 此工作使用 USMF 公司進行示範。

1. 在瀏覽窗格中，前往 **模組 > 信用和收款 > 設定 > 設定催款單序列**。
2. 點選 **新增**。
3. 在 **催款單序列** 欄位，輸入將代表序列的序列識別碼。 將使用該識別碼設定過帳設定檔。
4. 在 **描述** 欄位中，輸入一個值。  付款期限是選填的。 如果在此處輸入一個值，催款單費用發票將使用這些付款期限，而不是與客戶一起儲存的付款期限。  
5. 在 **催款單代碼** 欄位中，選擇您要發送的第一封催款單的代碼。 將根據發票上的到期日、您在 [天數] 欄位中輸入的寬限期值，以及您在此行輸入的其他資訊建立第一個催款單。  
6. 在 **描述** 欄位中，輸入一個值。 
7. 費用的預設貨幣是法人實體的貨幣。 此貨幣代碼可以與發票貨幣不同。   
8. 點擊 **新增**，新增將按順序發送的下一個催收信。 在大多數情況下，第一封催收信只是一個警告。 如果需要，您可以新增費用。  
9. 在 **催款單代碼** 欄位中，選擇按序列下一個發送催款單。
10. 在 **主科目** 欄位，選擇用於費用的收入科目。
11. 輸入過帳此催款單時將收取的費用。
12. 在 **品項銷售稅群組** 欄位，按一下下拉式按鈕開啟查詢。 如果必須根據費用計算銷售稅，請選擇項目銷售稅群組。  
13. 在清單中，點選已選取列的連結。
14. 在 **最低逾期餘額** 欄位，輸入在發送催款單之前所需的最低逾期餘額。
15. 在 **天數** 欄位，輸入您將允許的寬限天數。 這是在到期日之後可以產生催款單的天數。 用於計算的到期日期取決於催款單在催款單序列中的位置：
    - 催款單 1 的寬限期與發票上的到期日有關。
    - 催款單 2 和更新版本的寬限期與上一張催款單的過帳或列印日期相關，具體取決於應收帳款參數頁面中更新催款單代碼欄位中的選擇。  
16. 點擊 **新增**，新增順序中的下一個催收信。 您最多可以為催款單序列新增五個催款單代碼。  
17. 在 **催款單代碼** 欄位中，選擇按序列下一個發送催款單。
18. 在 **描述** 欄位中，輸入一個值。
19. 在 **主科目** 欄位中，指定所需值。
20. 在 **費用貨幣** 欄位中，輸入數字。
21. 在 **品項銷售稅群組** 欄位，按一下下拉式按鈕開啟查詢。
22. 在清單中，點選已選取列的連結。
23. 在 **最小逾期餘額** 欄位中，輸入一個數字。
24. 在 **天數** 欄位中，輸入數字。
25. 選擇 **鎖定** 核取方塊，以阻止客戶進行額外的交付和開具發票。 若要解除封鎖帳戶，請在 [客戶] 頁面的 [暫停開立發票與交貨] 欄位中選取 **否**。  
26. 展開 **附註** FastTab。
27. 輸入要在所選催款單代碼的催款單上顯示的文字。 您可以使用附註方塊上方的 [翻譯] 功能表，將此文字翻譯成多種語言。  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]