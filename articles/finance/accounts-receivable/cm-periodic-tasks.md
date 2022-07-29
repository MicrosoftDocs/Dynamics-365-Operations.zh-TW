---
title: 定期信用管理工作
description: 本主題介紹管理客戶信用額度流程中進行的定期工作。
author: JodiChristiansen
ms.date: 09/04/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: roschloma
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 398fcd9d45ce0ddfb1f7189e0712f9dac2db012f
ms.sourcegitcommit: 408786b164b44bee4e16ae7c3d956034d54c3f80
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/05/2021
ms.locfileid: "8451146"
---
# <a name="periodic-credit-management-tasks"></a>定期信用管理工作

[!include [banner](../includes/banner.md)]

本主題介紹管理客戶信用額度流程中進行的定期工作。

## <a name="update-risk-scores"></a>更新風險評分

隨著業務的發展和環境的變化，特定客戶的信用風險也會發生變化。 為了幫助為您的客戶維持適當的信用額度，您必須定期查看每個風險評分的標準並更新每個客戶的評分。 您可以使用 **更新風險評分** 頁面 (**信用和收帳 \> 定期工作 \> 信用管理 \> 更新風險評分**) 更新以下分數。 所有使用者定義的計算也會進行處理。

- **平均付款天數** – 此分數是客戶支付發票所需的平均天數。
- **自以下時間以來的客戶** – 此分數是客戶成為您組織客戶的年數。
- **業務開始年分** – 該分數是客戶經營業務的年數。 它使用 **客戶** 頁面上的 **業務開始時間** 欄位的值。
- **未結銷售款天數** – 此分數是根據應收帳款餘額、銷售收入和前 12 個月的天數計算。
- **平均餘額** – 該分數是根據前 12 個月期間的應收帳款餘額計算。
- **信用管理群組**、**帳戶狀態**，和 **國家/地區** – 這些分數使用來自客戶的資訊。

## <a name="update-customer-balance-statistics"></a>更新客戶餘額統計資料

您可以執行 **更新客戶餘額統計資料** 流程，以更新顯示在 **餘額統計查詢** 頁面上的餘額統計資料計算結果。 此資訊用於計算風險評分和 **客戶** 頁面上信用統計 FactBox 中顯示的值。

執行該流程時，它會更新單一客戶的客戶餘額統計資料。 要設定批次作業來為多個客戶執行流程，您可以使用 **計算餘額統計資料** 頁面 (**信用管理 \> 定期工作 \> 計算餘額統計資料**)。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
