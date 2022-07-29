---
title: 會計來源總管
description: 本文提供有關會計來源總管的資訊，您可以使用這些資訊詳細分析總帳會計分錄背後的來源資訊。
author: rcarlson
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AccountingSourceExplorer
audience: Application User
ms.reviewer: roschlom
ms.custom: 15391
ms.assetid: 57b95899-7298-43c0-8034-45b5d993cbf2
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ab098aa36d6fa6c34beaaa31ecfbb1eb47840e343d7dee3d9cd3034d6ff8f9c8
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450525"
---
# <a name="accounting-source-explorer"></a>會計來源總管

[!include [banner](../includes/banner.md)]

本文提供有關會計來源總管的資訊，您可以使用這些資訊詳細分析總帳會計分錄背後的來源資訊。

會計來源總管是顯示來源資訊的新頁面。 您可以將會計來源總管當作獨立工具或分析總帳會計分錄背後的詳細資料。 例如，您可以使用會計來源總管取得記錄餘額中餘額或憑證交易的最詳細來源資訊。 然後，您可以使用「匯出到 MS Excel」功能進一步劃分和切割 Microsoft Excel 中的資訊 (例如，在樞紐分析表中或在樞紐分析表報表上) 。

會計來源總管永遠顯示與總帳顯示的每個分類帳科目相同的總金額 (例如，在試算表中)。 和試算表一樣，您可以在單獨的資料行中顯示區段。 只需選擇適合的財務維度集。 

您可以使用參數來定義分析的日期間隔。 此功能也類似於試算表中的功能。

對於使用原始憑證框架的所有單據，會計來源總管會根據會計分配顯示附加資訊，如果適用，還會顯示專案會計分配。 此資訊包括金額類型、專案、活動、類別和行屬性。 以下是您可以執行的一些分析範例：

-   訂購單和廠商發票之間的差異，因為每個差異都由金額類型表示，例如費用差異
-   每個專案、業務單位和主科目的計費與非計費工時和支出

對於使用原始憑證參考識別概念的原始憑證，會計來源總管會顯示更多詳細資料，例如客戶、廠商、工作人員、產品、數量、單位文字和描述。 以下是您可以執行的一些分析範例：

-   每個業務單位的飯店支出和會計期間飯店品牌，根據支出報表
-   每個廠商、產品、部門的折扣

對於這些單據，您還可以從會計來源總管瀏覽到實際的原始憑證。

> [!NOTE]
> 從版本 10.0.20 開始，**更新** 按鈕提供了兩個附加範圍來限制為在頁面上輸入資料而執行的初始查詢。 這些附加範圍也在版本 10.0.19 中作為服務更新提供。 以新增以下欄位：
>
> - 來源憑證、目標憑證
> - 來源主科目、目標主科目

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
