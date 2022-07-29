---
title: 配置期間
description: 本主題提供有關在主科目上使用配置期間的資訊。
author: rachel-profitt
ms.date: 06/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AccountingDistribution, LedgerAllocationRule, MainAccount, AllocationTerms
audience: Application User
ms.reviewer: roschlom
ms.custom: 17361
ms.assetid: 04c8548a-0af9-492b-954b-946b4f8ca023
ms.search.region: Global
ms.author: raprofit
ms.search.validFrom: 2020-06-15
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 957baba1364fbbd4a51c6f51b0fad5bf8db46680fa97b9d3d0474dc015064609
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450831"
---
# <a name="allocation-terms"></a>配置期間

[!include [banner](../includes/banner.md)]

本主題提供有關在主科目上使用配置期間的資訊。 配置期間用來在多種分類帳科目組合間配置金額。 它們有助於確保將費用或營收計入正確的會計對象。

您在主科目上建立的每個配置條款定義預計從單一來源主科目和財務維度組合配置憑單的佔比。 此外，您定義將配置金額的目的地主科目和財務維度。 

當您為配置定義來源財務維度時，您可以選取每個維度是特定或非特定。 具體指出來源交易的財務維度必須與選取維度比對。 當您選取不特定時，它會指出任何財務維度值都會促成比對。

當您為配置期間定義目的地分類帳科目時，您必須指明配置金額的主科目。 您可以使用已過帳來源交易的相同主科目或不同的主科目。 如果使用相同主科目，儲存記錄時會顯示警告。 除了指明主科目以外，您也必須指明目的地維度。 以各維度而言，您可以指明是否保存或更改來源財務維度值。 如果選取否，您必須為財務維度選取新值。 如果選取是，則不指明額外資訊，過帳時系統將維持原本的財務維度。

您可以新增到主科目的配置期間數量並未設限；不過，在配置期間所配置的總佔比不能超過 100。 如果原始憑單金額的一部分應在來源財務維度保持不變，您可以建立低於 100% 的配置量。 配置期間可以新增到主科目作為法人實體佣金。 如果您使用共用的會計科目表，您必須為每個法人實體定義配置期間。 為了存取 **配置期間** 按鈕，您必須先在法人實體佣金上選取 **配置** 勾選方塊。

## <a name="allocation-term-example"></a>配置期間範例
您已經為貴組織定義名為 CORPORATE 的成本中心，編號 000。 過帳公用事業費用發票時，它們會編碼到此 CORPORATE 成本中心。 貴公司已定義一條規則，所有公用事業費用應按佔比配置給個別成本中心。 部門和業務單位的其他財務維度將保持不變。

本範例中，會針對公用事業費用主科目建立新配置期間。 預計按佔比配置的各成本中心會建立一行。 各行來源財經維度 **選取標準** 會針對 **成本中心** 特 **定** 指明，數值會設定為 000：CORPORATE。 以部門和業務單位而言，**選取標準** 會是 **非特定**。

在 **目的地分類帳** FastTab 上，主科目將是相同的公用事業費用科目，而 **業務單位** 和 **部門** 的 **保存來源財務維度** 將設定為 **是**。 **成本中心** 的 **保存來源財務維度** 將設定為 **否**，而選取值將是您配置的各間成本中心。 如果預計配置三間成本中心，則會建立三筆配置期間記錄。 各配置期間的唯一差異是目的地分類帳戶指明的成本中心。

## <a name="create-an-allocation-term-on-a-main-account"></a>在主科目建立配置期間

1. 在 **瀏覽窗格** 中，前往 **模組 > 總帳 > 會計科目表 > 科目 > 主科目**。
2. 在清單中，尋找並選取所需的記錄。
3. 在 **法人實體佣金** FastTab 上選取 **新增**。
4. 選取 **公司** 和 **新增**。
5. 選取 **配置** 勾選方塊。
6. 選取 **配置期間**。
7. 選取 **編輯** 修改預設記錄，或選取 **新增** 新增記錄。
8. 在 **佔比** 欄位，輸入您希望配置憑單交易的佔比。
9. 在 **來源財務維度** FastTab的各財務維持 **選取標準**，選取一個選項。
    - 如果您選擇 **特定**，則在右側下拉式方塊選取財務維度值。
    - 如果您選取 **非特定**，則財務維度不需要額外資訊。
10. 在 **記帳** 欄位的 **目的地分類帳** 帳戶 FastTab 上，選取您希望配置憑單交易佔比的主科目。
11. 在每個財務維度的 **保留來源財務維度** 中，選取一個選項。
    - 如果您選取 **否**，則在右側下拉式方塊選取您希望配置憑單交易的財務維度值。
    - 如果您選取 **是**，則不需要額外資訊。 過帳配置數額時，系統將保留原始憑單上的值。
12. 對每個額外配置數額重複步驟 7-11。 所有配置總數額在 **總佔比** 欄位指出。 此金額不能超過 100。
13. 關閉所有頁面。

>[!NOTE] 
> 您可以選擇性使用 **複製** 按鈕重複選取的配置數額。

為主科目建立配置期間時，系統將在符合配置期間的來源財務維持憑單過帳時，自動過帳新憑單。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]