---
title: 為採購類別階層設定原則
description: 使用此程序來設定某個類別中訂購產品的規則。
author: Henrikan
ms.date: 07/22/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SysPolicyListPage, SysPolicy, ProcCategoryAccessPolicyRule, ProcCategoryPolicyRule, EcoResCategorySingleLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ee056d7c2a8bdc9bcd2f5a0f4b96a7bf69c8c862
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448971"
---
# <a name="set-up-policies-for-procurement-category-hierarchies"></a>為採購類別階層設定原則

[!include [banner](../../includes/banner.md)]

使用此程序來設定某個類別中訂購產品的規則。 這些規則是為特定的採購原則定義的。 類別存取規則可控制員工在建立申請時可以存取哪些採購類別。 建立申請時，應採用的採購原則和類別存取規則由法人實體和員工所屬的營運單位確定。 您可以在 USMF 示範公司資料中使用此程序。 此任務通常由採購經理執行。


## <a name="find-the-procurement-policy"></a>尋找採購原則
1. 在瀏覽窗格中，前往 **模組 > 採購和委外 > 設定 > 原則 > 採購原則**。
2. 點選 [採購原則 USMF] 雲則上的連結。 這是您將新增規則的原則。 其必須是使用中原則。  

## <a name="create-a-category-access-rule"></a>建立類別存取規則
1. 展開 **原則規則** FastTab。
2. 在 **原則規則類型** 清單中，選擇 **類別存取原則規則**. 如果 **建立原則規則** 按鈕變暗，這是因為已經有用於類別存取的使用中原則規則。 檢查 **有效** 和 **到期** 欄位以確定是哪個，選去後點選 **淘汰原則規則**。 如果 **建立原則規則** 按鈕可用，則無需執行任何操作。  
3. 點選 **建立原則規則**。
4. 在 **生效日期** 欄位中，輸入日期和時間。 該時間不得與另一個已經處於使用中狀態的規則重疊。  
5. 選擇將套用規則的類別。 記下這是哪個類別 - 稍後您將需要它。 當您選擇一個類別時，其上層類別或多個類別也將新增到所選類別清單中。 如果您希望規則套用於所選類別的所有子類別，請選與包括 **子類別** 核取方塊。
6. 點選向右箭號以新增到 **所選類別** 清單。  
4. 點選 **確定**。 如果將 **包括上層規則** 選項設為 [是]，且尚未為子類別定義任何原則規則，還將把為上層類別定義的原則規指派給其下層類別。

## <a name="create-a-category-policy-rule"></a>建立類別原則規則
1. 在 **原則規則類型** 清單中，選擇 **類別原則規則**. 如果 **建立原則規則** 按鈕變暗，請選擇活動原則規則，然後點選 **淘汰原則規則**。  
2. 點選 **建立原則規則**。
3. 在 **生效日期** 欄位中，輸入日期和時間。
4. 選點 **新增**。
5. 在 **類別** 欄位，選擇用於 **類別存取規則** 的同一類別。
6. 在 **廠商選取** 欄位中，選擇一個選項。 選擇原則以控制在建立申請時可以為類別選擇哪種廠商。  
7. 點選 **關閉**。 您定義的原則規則適用於 [耗用] 類型的申請。 如果要為「補貨」類型的申請定義原則，請為該原則規則類型建立名為「補貨類別存取原則規則」的規則。  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]