---
title: 成本核算表
description: 設定成本核算表涉及兩個目標。 第一個目標是定義格式，用於顯示有關製造品項或生產訂單的銷貨成本資訊。 這個格式化顯示稱為成本核算表。 第二個目標，定義計算間接成本的基礎。 成本核算表的設定，基於用來顯示資訊和間接成本計算公式的成本群組功能。 本文介紹成本核算表設定的兩個目標。
author: AndersGirke
ms.date: 11/18/2021
ms.topic: article
ms.search.form: CostSheetDesigner, CostSheetCalculationFactor
audience: Application User
ms.reviewer: kamaybac
ms.custom: 53201
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 64b8a9b8b29193f25e706e52424de2af3454aec8
ms.sourcegitcommit: f11ad8d7ee8a4d2ee1a1bb601622b50e14955c4a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/18/2021
ms.locfileid: "8449487"
---
# <a name="costing-sheets"></a>成本核算表

[!include [banner](../includes/banner.md)]

設定成本核算表涉及兩個目標。 第一個目標是定義格式，用於顯示有關製造品項或生產訂單的銷貨成本資訊。 這個格式化顯示稱為成本核算表。 第二個目標，定義計算間接成本的基礎。 成本核算表的設定，基於用來顯示資訊和間接成本計算公式的成本群組功能。 本文介紹成本核算表設定的兩個目標。 

下表列出可以存取成本核算表的現成資訊安全角色，包括預設設定授予每個角色的存取層級。

| 角色 | 存取
|---|---|
| 會計經理 | 編輯 |
| 庫存會計員 | 檢視 |
| 庫存會計 | 檢視 |

成本核算表格式化顯示製造品項或生產訂單之銷貨成本的相關資訊。 設定成本核算表時，您可以定義資訊格式並定義計算間接成本的基礎。 成本核算表的設定，基於用來顯示資訊和間接成本計算公式的成本群組功能。 以下是更多有關成本核算表設定之兩個目標的資訊：

- **定義成本核算表的格式。** 成本核算表的使用者定義格式識別了包含製造品項之銷貨成本的成本細分。 例如，可以根據成本群組將有關品項銷售成本的資訊細分為材料、人工和間接費用。 這些成本群組指派至品項、路線規劃作業的成本類別和間接成本計算公式。 定義多個成本群組時，成本核算表的格式通常需要小計。 例如，可以彙總與材料相關的多個成本群組。 成本核算表格式的定義為選用，但如果要計算間接成本，必須定義成本核算表格式。
- **定義計算間接成本的基礎。** 間接成本反映與製造品項生產相關的製造費用。 間接成本計算公式可以表示為附加費或費率。 附加費表示價值的百分比，而費率表示路線規劃作業每小時的金額。 成本群組定義計算公式的基礎，例如人工成本群組的 100% 附加費或機器成本群組的 50.00 美元小時費率。 如果要定義計算公式及其成本群組基礎，成本核算表設定要求您識別代表間接費用的成本群組，並選擇使用附加費或費率方法。

每個計算公式都必須作為成本記錄輸入。 成本記錄由指定的成本核算版本、附加費百分比或費率金額、成本群組基礎、狀態和生效日期組成。 首次輸入項目成本記錄時，它具有 **待處理** 狀態和生效日期。 當您啟用項目成本記錄時，狀態將更新以讓記錄成為目前使用中記錄，且生效日期會更新為啟用日期。 成本記錄也可以為特定於站點的計算公式指定站點。 或者，您可以將 **站點** 欄位留空，代表計算公式為全公司的公式。 計算公式標示為按項目公式時，成本記錄可以選擇包含指定的項目或項目群組。 

間接成本計算公式的目前使用中成本記錄用於估算生產訂單成本。 它們也用於計算與實際時間和材料耗用相關的實際成本。 待定成本記錄用於未來日期的物料清單 (BOM) 計算。 

成本計算版本的兩個鎖定政策會判斷是否可以維護待處理成本，以及該待處理成本是否可以開始使用。 使用鎖定政策允許資料維護，然後防止成本計算版本中成本記錄的資料維護。 

為間接成本定義成本核算表格式和計算後，您必須執行另外的步驟來驗證和保存資訊。 成本核算表代表全公司的格式，用於一致顯示有關銷貨成本的資訊。 

成本核算表顯示於 **計算品項成本** 頁面。 成本核算表可以在 **品項價格** 頁面顯示製造品項的計算成本記錄，或在 **BOM 計算結果** 頁面顯示為特定清單的計算記錄。 它也可以顯示於生產訂單的 **價格計算** 頁面。

[!INCLUDE[footer-include](../../includes/footer-banner.md)]