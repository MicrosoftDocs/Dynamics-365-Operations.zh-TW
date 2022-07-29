---
title: 定義財務維度
description: 此程序顯示如何新增實體支援的財務維度和自訂財務維度。
author: aprilolson
ms.date: 06/25/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DimensionDetails,  DimensionAttributeTableExtensionActivate, DimensionValueDetails
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ed6dad64032c03e638c2090471af825dd18560a1
ms.sourcegitcommit: 03f53980a4bc67b73ac2be76a3b3e7331d0db705
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/18/2021
ms.locfileid: "8450912"
---
# <a name="define-financial-dimensions"></a>定義財務維度

[!include [banner](../../includes/banner.md)]

此程序顯示如何新增實體支援的財務維度和自訂財務維度。  本指南使用 USMF 示範公司。


## <a name="create-an-entity-backed-financial-dimension"></a>建立實體支援的財務維度
1. 前往 **瀏覽窗格 > 模組 > 總帳 > 會計科目表 > 維度 > 財務維度**。
2. 點選 **新增**。
3. 在 **使用者值表單** 欄位，選擇系統中定義的實體作為財務維度的基礎。 
4. 在 **維度名稱** 欄位，鍵入描述財務維度的值。 該名稱可與系統定義的實體名稱不同，但不能包含空格或特殊字元。
5. 點選 **啟用**。 啟用財務維度會使用財務維度名稱更新資料表並移除已刪除的維度。 您可以在啟用財務維度之前輸入維度值，但在啟用財務維度之前無法使用它。  
6. 在啟用訊息上點選 **關閉**。
7. 點選 **啟用**。 維度啟用可以安排在特定日期和時間按批次執行。  
8. 在 **動作窗格** 上，點選 **維度值**。 某些維度值是公司特定的。 您可以透過驗證公司名稱是否在維度值清單中來驗證是否是特定於公司的維度值。  

## <a name="create-a-custom-financial-dimension"></a>建立自訂財務維度
1. 關閉頁面。
2. 點選 **新增**。
3. 在 **使用以下來源中的值** 欄位，選擇 **自訂維度**。
4. 在 **維度名稱** 欄位，鍵入描述財務維度的值。
    - 名稱不能包含空格或特殊字元。  
    - 您還可以指定帳戶遮罩來限制可以為維度值輸入的金額和資訊類型。   
    - 您可以為每個維度值輸入相同的字元，例如字母或連字號。 您還可以輸入數字符號 (#) 和與符號 (&) 作為每次要變更的字母和數字的預留位置建立維度值。 使用數字標誌 (#) 作為編號預留位置，使用符號 (&) 作為字母的預留位置。  範例：若要限制維度值為字母 CC 和三個數字，您要輸入 CC-### 作為格式遮罩。  
5. 點選 **啟用**。 啟用財務維度會使用財務維度名稱更新資料表並移除已刪除的維度。 您可以在啟用財務維度之前輸入維度值，但在啟用財務維度之前無法使用它。     
6. 點選 **啟用**。 維度啟用可以安排在特定日期和時間按批次執行。      
7. 在 **動作窗格** 上，點選 **維度值**。
8. 點選 **新增**。
9. 在 **維度值** 欄位，鍵入描述財務維度值的名稱。
10. 在 **描述** 欄位，鍵入描述您的財務維度值的描述。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
