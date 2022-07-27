---
title: 設定登記已接收品項的行動裝置功能表項目
description: 本主題重點介紹行動裝置功能表項目的設定。
author: Mirzaab
ms.date: 08/16/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WHSRFMenuItem, WHSRFMenu, WHSRFDefaultData
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 410a70294e5a417950ed5332ec5fdd7da321a31d
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8447786"
---
# <a name="set-up-a-mobile-device-menu-item-to-register-received-items"></a>設定登記已接收品項的行動裝置功能表項目

[!include [banner](../../includes/banner.md)]

本主題重點介紹行動裝置功能表項目的設定。 此功能表項目用於登記透過訂購單訂購品項的接收。 

您可以在 USMF 公司示範資料中使用本指南。 此程序供倉庫經理所用。


## <a name="create-a-mobile-device-menu-item"></a>建立行動裝置功能表項目
1. 在瀏覽窗格中，移至 **模組 > 倉庫管理 > 設定 > 行動裝置 > 行動裝置功能表項目**。
2. 選取 **新增**。
3. 在 **功能表項目名稱** 欄位中，輸入一個值。 這是此行動裝置功能表項目的唯一識別碼。 例如，您可以輸入 `My PO registration`。  
4. 在 **標題** 欄位中，輸入一個值。 這是將向行動裝置上的使用者顯示的標題。 例如，您可以輸入 `PO registration`。  
5. 在 **模式** 欄位中，選取 **工作**。 為訂購單行登記收到的現有數量將建立將品項從接收區域移動到庫存的工作。 在品項登記之前不會建立工作。 因此，將 **使用現有工作** 選項設定為 **否**。
6. 在 **一般** 區段的 **工作建立流程** 欄位，選擇 **接收訂購單品項**.
    - 訂購單行必須具有唯一識別碼，然後才能在倉庫中登記。 在這種情況下，行動裝置將登記訂購單編號和品項編號，這將可讓系統識別訂購單行。 將建立入庫工作，並且可以由另一個工作人員承擔該工作。 您選擇的工作建立方法會決定哪些欄位會出現在 **一般** FastTab 上。  
    - 如果選擇 **使用預設資料** 選項，則為啟用 **預設資料** 按鈕。 您可以在這裡選擇欄位，來顯示工作人員在日常工作中常會需要的資料，以在行動裝置上顯示這些值。  
    - **牌照分組** 參數與指派給接收品項的單位序列群組結合使用。 您可以指定是否應將少於或多於一個托盤的收貨分組到一個牌照中，或者為每個單元劃分為一個單獨的牌照。  
    - 如果選擇 **產生牌照** 選項，會根據編號順序選擇產生唯一的牌照號碼。  
    - 您可以選擇建立工作時將使用的範本。 例如，如果您為訂購單登記一個品項，則將根據工作範本產生入庫工作。 如果此處未選擇工作範本，系統將根據與範本關聯的查詢條件指派範本。  
    - 如果處置代碼顯示在行動裝置上，工作人員可以評估品項的狀態或品質，並選擇適當的代碼。 處置代碼的規則會確定品項是否可用於其他倉庫流程。 這些規則還確定哪個位置指令用於已建立的工作。   
    - 如果選取 **批次處置代碼** 選項，工作人員可以評估批次的狀態或品質，並選擇適當的處置代碼。 批次處置代碼設定的規則會確定批次是否可用於其他倉庫流程。  
    - 如果選擇 **列印標籤** 選項，收到品項時將自動列印牌照標籤。  
7. 選取 **儲存**。
8. 關閉頁面。

## <a name="add-the-menu-item-to-a-mobile-device-menu"></a>將功能表項目新增至行動裝置功能表
1. 在瀏覽窗格中，移至 **模組 > 倉庫管理 > 設定 > 行動裝置 > 行動裝置功能表**。
2. 使用 **快速篩選** 來篩選值為 `inbound` 的 **名稱** 欄位。
3. 選取 **編輯**。
4. 在可用功能表和品項樹狀結構中，選擇您先前建立的功能表項目。
5. 選取向右箭頭。
6. 選取 **儲存**。
7. 關閉頁面。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]