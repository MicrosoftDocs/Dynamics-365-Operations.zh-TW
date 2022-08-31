---
title: 收入認列重新配置 - 案例 1
description: 此文章會介紹重新配置案例，其中輸入了兩筆銷售訂單，但訂單僅經過確認。 如果兩個以上的銷售訂單處於確認狀態，相同的情境將產生類似的結果。
author: bking
ms.date: 12/21/2020
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: Customer
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: bking
ms.search.validFrom: 2020-12-21
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 92af49d9446fd9ed3310d8d0d50af902e7a7e693
ms.sourcegitcommit: 1909d18a74cef85aad020a6a7473281e451f58c7
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/24/2022
ms.locfileid: "9348309"
---
# <a name="revenue-recognition-reallocation--scenario-1"></a>收入認列重新配置 - 案例 1

[!include [banner](../includes/banner.md)]

此文章會介紹重新配置案例，其中輸入了兩筆銷售訂單，但訂單僅經過確認。 如果兩個以上的銷售訂單處於確認狀態，相同的情境將產生類似的結果。

針對此案例，在 **總帳參數** 頁面上的 **收入認列** 索引標籤中，**將發票更正過帳到應收帳款** 選項設定為 **否** (**收入認列 \> 設定 \> 總帳參數**)。

[![將發票更正過帳到應收帳款的選項設定為否。](./media/06_rev-rec-scenarios.png)](./media/06_rev-rec-scenarios.png)

為客戶 US\_SI\_0003 建立了一筆銷售訂單。 客戶要購買筆記型電腦 (項目編號 S0012) 及針對該筆記型電腦的支援方案 (項目編號 S0008，「持續的工程服務」)。 該筆記型電腦的收入會立即進行確認 (尚未排定收入認列的時間)。 支援方案的收入會依合約中指定的日期範圍遞延，並在 12 個月中確認。

[![筆記型電腦及支援方案的銷售訂單明細。](./media/07_rev-rec-scenarios.png)](./media/07_rev-rec-scenarios.png)

銷售訂單已確認。 由於這兩個項目都針對收入價格配置設定，收入價格會在銷售訂單確認時進行計算。 您可以在 **收入價格配置** 頁面 (在 **銷售訂單** 頁面的動作窗格 **管理** 索引標籤，在 **收入認列** 群組中選取 **收入價格配置**)，檢視會確認的收入。 筆記型電腦的收入將會過帳到收入帳戶，金額為美金 1,008.01 元。 支援方案的收入將會過帳到遞延收入帳戶，金額為美金 190.99 元。 收入價格的總和必須等於設定用來擷取收入價格配置的明細總和 (美金 1,199.00 元)。

[![收入價格配置頁面。](./media/08_rev-rec-scenarios.png)](./media/08_rev-rec-scenarios.png)

在銷售當下，客戶選擇不購買安裝服務 (項目編號 S0001)，但之後改變了主意。 因此，針對同一位客戶輸入了第二筆銷售訂單。

[![安裝服務的銷售訂單明細。](./media/09_rev-rec-scenarios.png)](./media/09_rev-rec-scenarios.png)

已確認第二筆銷售訂單。 由於此筆銷售訂單僅包含一項明細，因此在確認銷售訂單時，並不會進行收入價格配置。 只有在有兩個以上的不重複項目，且該項目已針對收入價格配置進行設定時，才會進行收入價格配置。

若此筆新銷售訂單是該客戶合約的唯一變更，現在即可執行重新配置流程。 在兩筆銷售訂單之一中，選取 **使用新訂單明細重新配置價格**，以開啟 **使用新訂單明細重新配置價格** 頁面。 或者，依序前往 **收入認列 \> 定期任務 \> 使用新訂單明細重新配置價格**。 選取該兩筆銷售訂單以及對應的銷售訂單明細，然後選取 **更新重新配置**。 **重新配置的金額** 欄位會顯示每項銷售訂單明細的新收入價格。

[![使用新訂單明細重新配置價格頁面上的新收入價格。](./media/10_rev-rec-scenarios.png)](./media/10_rev-rec-scenarios.png)

若您選取 **預期憑單**，則不會顯示任何內容，因為尚未對任何發票進行過帳。

要完成重新配置，請選取 **處理**。 即使未過帳任何內容，您也會收到過帳日期的提示。 在重新配置完成之後，每筆銷售訂單的 **收入價格配置** 頁面都會顯示兩筆銷售訂單中所有項目的價格配置情況。 換句話說，每筆銷售訂單的 **收入價格配置** 頁面都會包含不存在於該筆銷售訂單內的項目，因為該項目雖然在不同的銷售訂單內，但都隸屬於相同的合約。

> [!TIP]
> 若要提供關於額外項目顯示原因的背景，您可以為格線新增其他欄位，例如 **重新配置識別碼** 及 **銷售訂單**。
> 
> [![收入價格配置頁面上的其他欄位。](./media/11_rev-rec-scenarios.png)](./media/11_rev-rec-scenarios.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
