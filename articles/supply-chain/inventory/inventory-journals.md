---
title: 庫存日記帳
description: 本主題說明如何使用庫存日記帳，針對各種類型的實物庫存交易進行過帳。
author: yufeihuang
ms.date: 04/05/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventJournalBOM, InventJournalCount, InventJournalCountTag, InventJournalLossProfit, InventJournalMovement, InventJournalTransfer, WMSJournalTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 51631
ms.assetid: 3fedeaaf-502f-483c-93d2-ab266828189e
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f9370e495bf16ed638646843faaf0ff599fe1abc
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448677"
---
# <a name="inventory-journals"></a>庫存日記帳

[!include [banner](../includes/banner.md)]

本主題說明如何使用庫存日記帳，針對各種類型的實物庫存交易進行過帳。

Supply Chain Management 的庫存日記帳，可針對各種類型的實物庫存交易進行過帳，例如過帳發貨和收貨、庫存變動、建立物料清單 (BOM) 以及實物庫存的對帳。 所有庫存日記帳的使用方式相當類似，但分成不同類型。

## <a name="types-of-inventory-journals"></a>庫存日記帳的類型
庫存日記帳具備以下類型：

-   變動
-   庫存調整
-   轉移
-   BOM
-   品項到貨
-   生產輸入
-   盤點
-   標籤盤點

### <a name="movement"></a>變動

使用庫存變動日記帳時，即可在新增庫存時增加項目成本，但必須在建立日記帳的時候指定總帳沖銷帳戶，將增加的成本手動配置到特定總帳科目。 若您希望覆寫預設過帳科目，即可使用此庫存日記帳類型。

### <a name="inventory-adjustment"></a>庫存調整

使用庫存調整日記帳，即可在新增庫存時增加項目成本。 增加的成本會依據項目群組過帳設定檔的設定，自動過帳至特定總帳科目。 若項目應維持預設總帳沖銷帳戶，則可使用此庫存日記帳類型來更新庫存數量的增減。 過帳庫存調整日記帳時，將過帳庫存收貨或發貨、改變庫存價值，並建立分類帳交易。

### <a name="transfer"></a>轉移

轉移日記帳可轉移項目的庫存地點、批次或產品變體，不會產生成本影響。 例如，您可將項目在相同公司內的不同倉庫間轉移。 使用轉移日記帳時，您必須同時指定「來源」與「目的」庫存維度 (如站點和倉庫)。 所定義之庫存維度的現有庫存會隨之改變。 庫存轉移會反映物料即時變動情形。 不會追蹤在途庫存。 若必須追蹤在途庫存，您應使用轉移訂單。 過帳轉移日記帳時，每條日記帳明細各會建立兩個庫存交易：

-   「來源」位置的庫存發貨。
-   「目的」位置的庫存收貨。

### <a name="bom"></a>BOM

報告 BOM 完成時，您可建立 BOM 日記帳。 使用 BOM 日記帳，即可直接過帳 BOM。 此過帳會產生該產品的庫存收貨，以及相關 BOM 和其中產品的庫存發貨。 無須途程的簡單或大量生產情境中，此庫存日記帳類型相當實用。

### <a name="item-arrival"></a>品項到貨

您可使用品項到貨日記帳，登記品項 (如來自訂購單) 收貨。 **到貨摘要** 頁面的到貨管理可建立品項到貨日記帳，或者您可於 **品項到貨** 頁面手動建立日記帳分錄。 若啟用品項到貨日記帳名稱來檢查揀料位置，則 Supply Chain Management 會尋找接收品項的位置，如有空間就會產生入庫品項位置目的地。

### <a name="production-input"></a>生產輸入

生產輸入日記帳的運作與品項到貨日記帳類似，不過是用於生產訂單。

### <a name="counting"></a>盤點

盤點日記帳可讓您更正項目或項目群組目群的現有庫存，然後過帳實際實物盤點，以利您針對差異的對帳進行調整。 盤點群組有助於將具備各種特性的項目分組，且可將之與盤點原則建立關聯，以將這些項目都納入盤點日記帳。 例如，您可設定盤點群組來盤點具特定頻率的項目，或在庫存下降到特定水準時盤點項目。 如需如何定義盤點群組的資訊，請參閱[定義庫存盤點流程](tasks/define-inventory-counting-processes.md)。

### <a name="tag-counting"></a>標籤盤點

標籤盤點日記帳可將編號標籤指派給盤點批次。 標籤應包含標籤編號、品項編號和項目數量。 為了確保每個標籤只使用一次，並確實使用所有標籤，每個品項編號都應有其獨特的一組標籤，且有自己的數字序列。 每個標籤可設定這三種狀態值：

-   **已使用** – 此標籤已盤點此品項編號。
-   **已作廢** – 此標籤的這個品項編號已作廢。
-   **缺少** – 此標籤缺少這個品項編號。

過帳標籤盤點日記帳時，將依據標籤盤點日記帳的明細，建立新的盤點日記帳。 如需標籤盤點的詳細資訊，請參閱[庫存標籤盤點](inventory-tag-counting.md)。

## <a name="working-with-journals"></a>使用日記帳
一個日記帳同時只能由一位使用者存取。 若多個使用者必須同時存取許多日記帳來建立日記帳明細，則這些使用者必須選取目前未使用的日記帳，以避免資訊被覆寫。 若多個部門使用相同日記帳類型，建議建立多個日記帳名稱 (如每個部門一個日記帳)。 分割日記帳可能也有幫助，讓例行過帳程序皆輸入進其專屬的庫存日記帳。 針對與庫存交易相關的例行過帳，請為定期庫存調整和庫存盤點各自建立一個日記帳。

## <a name="posting-journal-lines"></a>過帳日記帳明細
您可隨時過帳您建立的日記帳明細，直到您鎖定額外交易的項目。 您輸入日記帳的資料仍會保留在該日記帳，即使您關閉日記帳且未過帳明細也沒關係。

## <a name="data-entity-support-for-inventory-journals"></a>庫存日記帳的資料實體支援

資料實體支援下列整合類型的情境：
-    同步服務 (OData)
-  非同步整合

如需詳細資訊，請參閱[資料實體](../../fin-ops-core/dev-itpro/data-entities/data-entities.md)。

> [!NOTE]
> 並非所有庫存日記帳皆支援 OData，因此您無法使用 Excel 資料收集工具來取得已發佈、已更新及已匯回 Supply Chain Management 的資料。 

日記帳資料實體的另一差異在於使用內含標題與明細資料的複合式實體的能力。 目前，複合式實體適用於：
-   庫存調整日記帳
-   庫存變動日記帳

這兩個庫存日記帳僅支援資料管理匯入專案的 *初始化倉庫* 情境：
-  如未指定日記帳標題編號，但指定日記帳類型的數字序列，則匯入工作會自動針對每 1000 個明細建立日記帳標題。 例如，匯入 2020 個明細將產生下列三個日記帳標題：
    -  標題 1：包含 1000 個明細
    -  標題 2：包含 1000 個明細
    -  標題 3：包含 20 個明細
-  系統會假設每個庫存維度 (如產品、儲存和追蹤維度) 存在獨特的明細資訊。 因此，相同匯入專案中，無法匯入僅日期欄位有差異的日記帳明細。

## <a name="additional-resources"></a>其他資源

[資料實體](../../fin-ops-core/dev-itpro/data-entities/data-entities.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]