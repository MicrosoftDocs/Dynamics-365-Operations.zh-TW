---
title: 線上財務合併
description: 本主題介紹總帳中的線上財務合併。
author: aprilolson
ms.date: 07/09/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2018-5-31
ms.dyn365.ops.version: 8.0.1
ms.openlocfilehash: 7c8a36447670458b2a8fe423f35fafd5f8cff773461f4dff47577e52573abc3a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450615"
---
# <a name="online-financial-consolidations"></a>線上財務合併

[!include [banner](../includes/banner.md)]

本主題介紹總帳中的線上財務合併。 在閱讀本主題之前，請務必閱讀[財務合併和貨幣換算概觀](financial-consolidations-currency-translation.md)主題。

完成設定後，您可以在 **合併 [線上]** 頁面輸入合併的詳細資料。 完成後，您可以點擊 **確定** 或 **批次** 處理合併。

## <a name="criteria"></a>條件
在 **合併 [線上]** 頁面的 **條件** 索引標籤，您可以定義要合併的帳戶、期間和資料類型。

![條件索引標籤。](./media/criteria-consolidate-online.png "條件索引標籤")

以下是此索引標籤上的各欄位的說明：

- **描述** – 輸入您要合併的期間的準確描述。
- **主科目** – 使用本節中的欄位來定義將要處理的主要科目。

    - **從** 和 **到** – 指定要處理的帳戶範圍。 如果您將這些欄位留空，則所有公司的所有帳戶都將移至合併公司。 因此，如果您要合併四家公司，並且每家公司都有不同的會計科目表，則所有四家公司的所有帳戶都將在合併公司中建立。
    - **使用合併科目** – 如果您將此選項設定為 **是**，則 **選擇合併科目** 欄位變為可用。 在此欄位中，選擇是否應將所有科目合併到在 **主科目** 頁面，或者您是否要從合併科目群組之一中選擇科目。
    - **合併科目群組** – 選擇要用於合併的主科目對應的群組。

- **合併期間** – 使用本節中的欄位定義合併期間。

    - **從** 和 **到** – 指定合併的日期範圍。 如果您將這些欄位留空，則將為公司分類帳日曆中定義的所有期間處理合併。 不建議將這些欄位留空。
    - **包括實際金額** – 將此選項設定為 **是**，將合併您的實際資料。
    - **包括預算金額** –將 此選項設定為 **是**，將合併預算登記中的資料。
    - **在合併期間重建餘額** – 不建議將此選項設定為 **是**。 而是以單獨批次作業的形式重建餘額。

- **預算模型** – 如果您已選擇合併預算資料，請使用此區段中的欄位來定義預算模型。

    - **從** 和 **到** – 指定要使用的模型範圍。
    - **預算匯率類型** – 選擇用於預算資料貨幣換算的預算匯率類型。

## <a name="financial-dimensions"></a>財務維度
在 **財務維度** 索引標籤，定義應包含在合併公司中的維度。 要選擇維度，請將 **規格** 欄位設定為 **維度**，然後定義合併公司中維度的順序。

![財務維度索引標籤。](./media/financial-dimensions-cons.png "財務維度索引標籤")

無論您定義的順序如何，**主科目** 將永遠是第一個區段。

## <a name="legal-entities"></a>法律實體
在 **法律實體** 索引標籤，定義應包含在合併公司中的公司。 您還可以定義這些公司的所有權百分比。 如果您指定少於 100% 的所有權，則指定的百分比將匯總到合併公司。 對於任何換算差額，**換算差額的科目類型** 欄位用於從 **自動交易帳戶** 頁面中的設定選擇主科目。

![法律實體索引標籤。](./media/legal-entities-cons.png "法律實體索引標籤")

![自動交易科目頁面。](./media/accounts-for-automatic-cons.png "自動交易科目頁面")

## <a name="elimination"></a>清除
在 **清除** 索引標籤，有三個處理清除的選項：

- 選擇清除規則，然後在 **提案選項** 欄位，選擇 **僅提案**。 此選項將在合併流程中處理清除，但不會一次性過帳所有內容。 您可以稍後過帳日記帳。
- 選擇清除規則，然後在 **提案選項** 欄位，選擇 **僅過帳**。 此選項將在合併流程中處理清除，且會一次性過帳所有內容。
- 透過使用清除日記帳，將清除提案與合併流程分開執行。

![清除索引標籤。](./media/elimination-cons-onl.png "清除索引標籤")

更多有關清除的資訊，請參閱[清除規則](./elimination-rules.md)。

## <a name="currency-translation"></a>貨幣換算
在 **貨幣換算** 索引標籤中，可以定義法律實體、帳戶和匯率類型以及匯率。 **套用匯率對象** 欄位中有三個選項可選擇：

- **合併日期** – 合併日期將用於取得匯率。 此匯率相當於即期匯率或月底匯率。 您將看到匯率預覽，但無法對其進行編輯。
- **交易日期** – 每筆交易的日期將用於選擇匯率。 此選項最常用於固定資產，通常稱為歷史匯率。 您看不到匯率的預覽，因為帳戶範圍內的各種交易會有很多匯率。
- **使用者定義的匯率** – 選擇此選項後，您可以輸入所需的匯率。 此選項可用於平均匯率，或者如果您針對固定匯率進行合併。

![貨幣換算索引標籤。](./media/currency-translation-cons-online.png "貨幣換算索引標籤")

## <a name="additional-resources"></a>其他資源

更多有關合併和貨幣換算的資訊，請參閱本主題的父主題，[財務合併和貨幣換算概觀](./financial-consolidations-currency-translation.md)。

有關可能生成合併財務報表的方案的信息，請參閱[生成合併財務報表](./generating-consolidated-financial-statements.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]