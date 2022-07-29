---
title: 記錄外幣租賃
description: 本主題解釋如何以非會計或報表貨幣記錄租賃。
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeaseDetail
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 91bf3f91614f0dd4835c253456128c9ced046749c0e13383590e01dfd436c921
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450690"
---
# <a name="record-leases-in-foreign-currencies"></a>記錄外幣租賃

[!include [banner](../includes/banner.md)]

資產租賃說明以非會計貨幣或報表貨幣計入的租賃在 **分類帳設定** 頁設立。 所有租賃皆應以其交易貨幣輸入。 換句話說，它們應以租賃契約指定的貨幣輸入。 本主題解釋如何以非會計或報表貨幣記錄租賃。

如果您以外幣輸入租賃，則使用權 (ROU) 資產會同時以會計貨幣和報表貨幣折舊。 這些貨幣皆在 **分類帳設定** 頁配置。 此行為也用在固定資產。 當您建立外幣租賃時，選取 **貨幣** 欄位的交易貨幣。

會計貨幣的匯率是 **會計貨幣匯率** 欄位的預設值。 報表貨幣的匯率是 **報表貨幣匯率** 欄位的預設值。 這些匯率在租賃開始日當天起生效。 **會計貨幣匯率** 和 **報表貨幣匯率** 欄位在 **租賃細節** 頁上的 **Finance 和報表交流資訊** FastTab 上。

1. 選取 **固定利率** 勾選方塊以取代自動輸入的匯率，接著輸入新匯率。
2. 在其他欄位輸入租賃必要的資訊，然後選取 **建立期程表**。
3. 在新 **租賃細節** 頁面選取 **帳冊**。
4. 在 **租賃帳冊** 頁的 **Financial 和報表交流資訊** 索引標籤上，驗 **會計貨幣初始使用權資產** 和 **報表貨幣初始使用權資產** 欄位。 這裡的每一個欄位都以對應貨幣顯示轉換後的 ROU 資產餘額。 每當您更改任何財務資訊時，這些欄位都會更新。 確認付款日程表之前選取 **建立日程表**。

    初始認列日記帳分錄會記錄使用租賃列明貨幣匯率的使用權資產。 日記帳分錄也包括 **會記貨幣初始使用權資產** 和 **報表貨幣初始使用權資產** 欄位。

## <a name="subsequent-measurement-for-foreign-currency-leases"></a>外幣租賃的後續計量

折舊日程表顯示以報表貨幣、會計貨幣和交易貨幣預期的折舊支出金額。

若要檢視報表貨幣或記帳貨幣計入的使用權資產餘額和折舊金額，請打開 **資產折舊日程表** 頁面，並選取 **顯示會計貨幣金額** 或 **顯示報表貨幣金額** 勾選方塊。

當您按照外幣計價的租賃建立折舊支出日記帳分錄時，分錄會使用租賃上列出的匯率。 日記帳分錄也使用 **會記貨幣初始使用權資產** 和 **報表貨幣初始使用權資產** 欄位值。

最終折舊支出金額可使用稍微不同的匯率計算，藉此讓使用權資產以會計貨幣和報表貨幣完全折舊。

如果租賃已被重新分類為 **遞延租金**，系統會自動清除會計和報表貨幣的匯率 (如果它們已經定義)。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
