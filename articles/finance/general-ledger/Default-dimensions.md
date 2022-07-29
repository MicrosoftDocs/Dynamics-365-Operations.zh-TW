---
title: 財務維度和過帳
description: 計劃和設定會計科目表時，必須考慮過帳單據或日記帳時，各種元件如何協同工作。 這些元件包括科目結構、進階規則以及平衡和固定維度。 本主題介紹各個元件的定義及其協同工作方式。
author: aprilolson
ms.date: 08/04/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerChartofAccounts,DimensionDetails
audience: Application User
ms.reviewer: roschlom
ms.custom: 14091
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 9e7416c1ed69fa9783694e2adee7ada4e25e14054daeb1761428855690eb522f
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450858"
---
# <a name="financial-dimensions-and-posting"></a>財務維度和過帳 

[!include [banner](../includes/banner.md)]

計劃和設定會計科目表時，必須考慮過帳單據或日記帳時，各種元件如何協同工作。 這些元件包括科目結構、進階規則以及平衡和固定維度。 本主題介紹各個元件的定義及其協同工作方式。

## <a name="chart-of-accounts-and-financial-dimension-components"></a>會計科目表和財務維度元件

基於規則的豐富系統用於定義主科目和財務維度值的有效組合。 本節簡要概述了個個元件的功能及其位置。

### <a name="account-structures"></a>科目結構

設定分類帳時需要科目結構。 必須定義並啟用至少一種科目結構，並且必須將其指派給分類帳。 科目結構中必須包含主科目。 您可以定義最適合業務的客戶細分順序。 定義主科目後，系統可以確定使用的科目結構。 透過將主科目放在結構的首位或靠前位置，可幫助限制值，還可以幫助系統將最後一個已知的有效值用作預設值。 科目結構中最多還可以有 10 個財務維度。 科目結構定義了哪些維度值與其他值組合有效。 它還定義是否必須輸入維度值。

### <a name="advanced-rules"></a>進階規則

設定會計科目表時，進階規則是可選元件。 您可以根據需要向科目結構新增任意數量的進階規則。 進階規則通常用於處理在滿足特定條件時必須追蹤其他財務維度的情況。 例如，如果您使用差旅費用帳戶，可能會需要追蹤其他資訊，例如員工出差參加的活動。 如果有多個進階規則，它們將根據規則名稱按字母順序套用。 規則新增的客戶細分只能在科目結構的客戶細分之後套用。

### <a name="balancing-dimension"></a>平衡維度

可以選擇定義平衡財務維度。 在 **分類帳** 頁面，您可以定義應平衡的財務維度。 然後，每當交易過帳到該財務維度時，系統都會自動建立並過帳分錄以使財務維度平衡。

### <a name="defaultfixed-financial-dimensions-on-the-main-account"></a>主科目的預設/固定財務維度

預設維度來自各種位置，例如主記錄 (如客戶或廠商記錄)、單據標題和主科目。 本主題重點介紹法人主科目的預設維度。 可以為分類帳的所有科目結構中使用的各財務維度定義主科目具有 **非固定** 還是 **固定** 值。 如果財務維度 **非固定**，則使用預設值，但可以覆寫該值。 此行為適用於系統中的所有預設值，甚至是來自主記錄的預設值。 如果財務維度設定為 **固定** 值，則一律套用該值，無論該值與預設值來自同一位置還是使用者輸入的。

## <a name="order-in-which-default-dimensions-are-applied-during-posting"></a>過帳期間套用預設維度的順序

人們經常好奇各種元件的執行順序。 了解套用預設維度的順序非常重要，因為此行為會影響您設定的方法。

> [!NOTE]
> 此資訊僅適用於應用程式中預設維度的套用。 如果使用 Microsoft Excel 或資料管理框架匯入資料，則行為不同。

### <a name="example-1"></a>範例 1

**科目結構**

| 主科目            | 事業單位           | 部門              | 成本中心             |
|-------------------------|-------------------------|-------------------------|-------------------------|
| 允許所有值。 | 允許所有值。 | 允許所有值。 | 允許所有值。 |

**主科目**

| 主科目 | 姓名          | 法律實體 | 部門                                 |
|--------------|---------------|--------------|--------------------------------------------|
| 401100       | 產品銷售 | USMF         | 固定 - 022 銷售和行銷部 |

下圖顯示主科目 401100 中設定的預設固定維度。

[![預設財務維度。](./media/default-dimensions.png)](./media/default-dimensions.png)

在這個非常基本的範例中，我們將輸入一個普通日記帳，其中部門維度設定為使用預設值 **023** (作業)。 我們將輸入並過帳一個分類帳。 下圖顯示了總帳標題中的預設財務維度。

[![普通日記帳。](./media/general-journal.png)](./media/general-journal.png)

日記帳標題上的預設維度將導致在銷售科目行預設套用部門 023。 下圖顯示了普通日記帳行，其中 **023** 套用標題中的預設維度值。

[![日記帳憑單。](./media/journal-voucher.png)](./media/journal-voucher.png)

但是，過帳行時，會套用固定維度，並將行過帳到部門 022。 下圖顯示了已過帳憑單，其中銷售帳戶套用固定維度。

[![套用固定維度的憑單交易。](./media/voucher-transactions.png)](./media/voucher-transactions.png)

### <a name="example-2"></a>範例 2

此範例使用與第一個範例相同的設定。 但是，我們將新增第二個元件並使用部門維度作為平衡維度。 在下圖中，**部門** 設定為 USMF 分類帳的平衡財務維度。

[![圖例顯示部門作為平衡財務維度。](./media/ledger.png)](./media/ledger.png)

當使用相同的日記帳標題設定並過帳相同的交易時，首先套用固定維度。 然後套用平衡邏輯來幫助保證每個部門都有一個平衡的分錄。 下圖顯示在套用固定維度後包含平衡分錄的憑單交易。

[![套用平衡分錄後的憑單交易。](./media/voucher-transactions2.png)](./media/voucher-transactions2.png)

### <a name="example-3"></a>範例 3

在本例中，我們將新增一個進階規則。 進階規則指定如果使用銷售帳戶 401100 和部門 022 (銷售和行銷)，系統應追蹤名為 [客戶] 的附加客戶細分。

由於順序，這個範例很重要。 科目結構是在輸入主科目後確定的。 如果您參考科目結構設定，系統可以確定主科目、事業單位、部門和成本中心是相關的。 此時尚未觸發進階規則，因為在過帳期間為日記帳憑單套用預設維度之前，不會套用固定維度。 在下圖中，客戶細分不存在，因為尚未滿足進階規則的條件。

[![分類帳科目。](./media/drop-down.png)](./media/drop-down.png)

過帳將失敗，因為在流程結束時套用了固定維度。 如果主科目為 401100，部門為 022，維度驗證確定需要客戶段。 由於驗證錯誤，無法過帳。 下圖顯示了在維度驗證確定 [客戶] 是必需的客戶細分之後顯示的訊息。

[![訊息詳細資料。](./media/message.png)](./media/message.png)

在此範例中，您必須覆寫預設值，以便觸發進階規則並且您可以輸入客戶細分。 但是，這種解決方案並非總是可行的，有些使用者甚至不會注意到過帳規則。 因此，在設定會計科目表時了解預設維度的套用順序非常重要。

若要實現此範例中的目標，可透過多種方式變更設定。 例如，您可以為銷售帳戶建立一個新的科目結構並在結構中包含客戶細分。 您還可以在現有科目結構中新增更多行，並指定主科目和有效部門值。 然後，在額外的客戶結構中，可以發現包含 [客戶] 客戶細分單獨銷售科目的科目結構非常有用。

## <a name="additional-resources"></a>其他資源 

以下部分資源涉及我們軟體的早期版本。 但是，許多關於預設維度的套用資訊和很多概念在早期版本中是相同的，這些參考資料仍然有效。

[單位間會計的平衡日記帳](example-balanced-journals-interunit-accounting.md)

[計劃您的會計科目表](plan-chart-of-accounts.md) 

[「在 AX 2012 中計劃會計科目表」部落格](/archive/blogs/axsa/planning-your-chart-of-accounts-in-ax-2012-part-1-of-7) – 此連結將前往七個部分系列中的第 1 部分。

[會計分配中的維度預設值](/archive/blogs/ax_gfm_framework_team_blog/dimension-defaulting-in-accounting-distributions-part-1-introduction)

[維度框架中的維度預設值](/archive/blogs/ax_gfm_framework_team_blog/dimension-defaulting-part-1-financial-dimensions-discovery)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
