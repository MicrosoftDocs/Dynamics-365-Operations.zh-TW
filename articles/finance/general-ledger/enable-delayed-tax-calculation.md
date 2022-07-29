---
title: 在日記帳上啟用延遲計稅
description: 本主題說明如何在日記帳行數非常多時打開延遲稅款計算功能以幫助提高稅款計算的效能。
author: ericwang
ms.date: 09/18/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2019-09-18
ms.dyn365.ops.version: 10.0.7
ms.openlocfilehash: 8394c83245865fd7fa02ddf80ada0532d1d4368e10e0a3248d0f8163f8e2224d
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450438"
---
# <a name="enable-delayed-tax-calculation-on-journals"></a>在日記帳上啟用延遲計稅
[!include [banner](../includes/banner.md)]


本主題說明如何延遲日記帳的銷售稅計算。 當有許多日記帳行時，此功能有助於提高稅收計算的效能。

默認情況下，每當更新與稅務相關的字段時，都會計算日記帳行上的銷售稅金額。 這些字段包括銷售稅組和物料銷售稅組的字段。 對日記帳行的任何更新都會導致重新計算所有日記帳行的稅額。 儘管此行為有助於用戶查看實時計算的稅額，但如果日記帳行數非常多，它也會影響效能。

延遲稅款計算功能可讓您延遲日記帳的稅款計算，因此有助於解決績效問題。 開啟此功能後，僅當用戶選擇 **銷售稅** 或發布日記。

您可以在三個級別延遲計算銷售稅：

- 法律實體
- 日記帳名稱
- 日記帳標題

系統優先考慮日記帳抬頭的設置。 默認情況下，此設置取自期刊名稱。 默認情況下，期刊名稱的設置取自 **總賬參數** 創建期刊名稱時的頁面。 以下部分說明如何為法人、日記帳名稱和日記帳標題打開延遲稅款計算。

## <a name="turn-on-delayed-tax-calculation-at-the-legal-entity-level"></a>在法人級別啟用延遲稅款計算

1. 前往 **總帳\>分類帳設定\>總分類帳參數**。
2. 在 **一般** FastTab 上的 **銷售稅務** 索引標籤，將 **延遲稅務計算** 選項設定為 **是的**。

![總帳參數影像。](media/delayed-tax-calculation-gl.png)

## <a name="turn-on-delayed-tax-calculation-at-the-journal-name-level"></a>在日記帳名稱等級啟用延遲稅款計算

1. 前往 **總賬\>日記帳設定\>日記帳名稱**。
2. 在 **一般** FastTab 上的 **銷售稅務** 部分，將 **延遲稅務計算** 選項設定為 **是的**。

![日記帳名稱影像。](media/delayed-tax-calculation-journal-name.png)

## <a name="turn-on-delayed-tax-calculation-at-the-journal-header-level"></a>在日記帳標題等級啟用延遲稅款計算

1. 前往 **總帳 \> 日記帳分錄 \> 普通日記帳**。
2. 選取 **新增**。
3. 選取日記帳名稱。
4. 在 **設置** 索引標籤，設置 **延遲稅款計算** 選項 **是的**.

![一般日記帳頁面影像。](media/delayed-tax-calculation-journal-header.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]