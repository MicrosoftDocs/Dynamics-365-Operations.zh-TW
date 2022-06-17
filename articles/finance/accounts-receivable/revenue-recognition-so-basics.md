---
title: 銷售訂單的收入認列
description: 本主題介紹了確認銷售訂單和發票上的收入的基本功能。 收入認列可用於銷售訂單和從銷售訂單建立的相對應發票。
author: kweekley
ms.date: 08/24/2018
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: Customer
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: 1807e00f5f93bf9359da710af7c9a1f6de652e7ae78cf9604351af969b057b11
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8452772"
---
# <a name="revenue-recognition-on-sales-orders"></a>銷售訂單的收入認列

[!include [banner](../includes/banner.md)]

> [!NOTE]
> 收入認列功能無法透過功能管理開啟。 目前，您必須使用設定金鑰開啟該功能。

本主題介紹了確認銷售訂單和發票上的收入的基本功能。 收入認列可用於銷售訂單和從銷售訂單建立的相對應發票。 也可以透過時間和材料專案建立銷售訂單。

> [!NOTE]
> 在本主題的插圖中，為了更適當展示概念，已在格線中隱藏或新增欄。 因此，插圖中的頁面和資料可能與您在產品中所見的不同。

## <a name="enter-a-sales-order"></a>輸入銷售訂單

輸入以下銷售訂單，其中包括為收入認列設定的三個品項。

[![輸入銷售訂單。](./media/revenue-recognition-so-basic-sales-order-header.png)](./media/revenue-recognition-so-basic-sales-order-header.png)

收入認列有兩個概念：

- **確定收入價格。** 收入價格是根據已發布產品的設定計算的。 收入價格永遠不向客戶顯示，僅用於銷售訂單發票的核算。 做為銷售的一部分列印的銷售訂單明細和文件會繼續顯示單價/標價。
- **確定何時應進行收入認列。** 收益計畫表用於確定何時應確認收入。

    在本例中，第一品項 S0001 指派至 **1O** (一次性) 收益計畫表。 此明細代表里程碑型的情境，收入將在未來安裝後確認。 因此，收入將遞延至安裝完成。

    第二個品項 S0008 是設定為合約後支援 (PCS) 品項的服務項目。 在 12 個月期間內向客戶提供持續的工程服務。 因此，預設會將 **12M** 收益計畫表指派至產品。 由於此項目是 PCS 品項，因此必須定義合約開始日期和結束日期。 預設情況下，合約開始和結束日期位於品項詳細資訊 - 設定索引標籤上。在收益計畫表上，會定義 **12M** 的設定，以便自動填寫合約條款，如下圖所示。

    [![收益計畫表。](./media/revenue-recognition-so-basic-revenue-schedules.png)](./media/revenue-recognition-so-basic-revenue-schedules.png)

    第三品項，S0012，是硬體，預設不指派收益計畫表。 硬體的收入會在品項開具發票後立即確認。

## <a name="confirm-the-sales-order"></a>確認銷售訂單

要查看有關收入價格和收益計畫表的更多詳細資料，請在銷售訂單的動作窗格上使用 **管理** 索引標籤上的 **收入認列** 群組。 由於此時未確認銷售訂單，因此用於收入認列的按鈕不可用。 隨著銷售訂單經歷各個階段直至履行，這些按鈕會變為可用或不可用。

[![銷售訂單標題。](./media/revenue-recognition-so-basic-sales-order-header-02.png)](./media/revenue-recognition-so-basic-sales-order-header-02.png)

前三個按鈕為銷售訂單上針對收入認列而設定的品項提供收入價格的相關詳細資料。

- **收入價格配置** – 此按鈕在確認銷售訂單或過帳發票後可用。 銷售訂單確認和發票過帳都會計算收入以確認將在會計分錄中確認或遞延的價格。 根據設定，計算的收入價格可能與顯示給客戶的單價不同。
- **使用新訂單明細重新配置價格** – 此按鈕在確認銷售訂單或過帳發票後可用。 重新配置程序用於重新計算在將新明細新增到目前銷售訂單、開票後或新增到新銷售訂單後必須確認的收入。 在這兩種情況下，加入新品項都會導致合約更動。 因此，收入價格必須重新配置。
- **更新收入價格配置** – 此按鈕在銷售訂單確認後可用，但在銷售訂單開票後不可用。 此項更新用於重新執行收入價格配置，而無需確認銷售訂單。 銷售訂單開票後，無法重新計算收入價格。

最後兩個按鈕提供有關銷售訂單上具有收益計畫表的該些品項的收益計畫表詳細資料。

- **預期收入認列表** – 此按鈕在銷售訂單確認後可用，但在銷售訂單開票後不可用。 它會打開一個顯示預期收益計畫表的頁面。 最終附表可能會變動，因為預期附表使用要求的出貨日期，而最終附表使用實際出貨日期。
- **收入認列表** – 此按鈕在銷售訂單開票後可用。 進行確認或建立裝箱單時，不會建立最終收入認列表。 它只會在銷售訂單開票時建立。

在下例中，收入價格配置發生在確認銷售訂單時。 請注意，即使收入價格的配置方式不同，**確認收入** 欄位中的總金額仍必須等於向客戶開具發票的銷售訂單明細的總和。 例如，銷售訂單明細的總和 (不含稅) 為 $,1499。 因此，**確認收入** 值的總和也必須是 $,1499。

[![收入價格配置。](./media/revenue-recognition-so-basic-revenue-price-allocation.png)](./media/revenue-recognition-so-basic-revenue-price-allocation.png)

另外會建立預期的收入認列表。 收益計畫表使用 **確認收入** 值做為遞延的金額。 品項 S0001 遞延 $321.21 而不是 $300，品項 S0008 遞延 $160.61 而不是 $100。 品項 S0012 未顯示在預期附表中，因為收入未遞延。 發生過帳時，品項 S0012 將 $1,017.18 直接過帳到收入分類帳科目。

[![預期收入認列表。](./media/revenue-recognition-so-basic-expected-rev-rec-schedule.png)](./media/revenue-recognition-so-basic-expected-rev-rec-schedule.png)

## <a name="create-the-packing-slip"></a>建立裝箱單

接下來，可以為銷售訂單建立裝箱單。 將裝箱單過帳時不會確認收入。 如果未確認銷售訂單，則將裝箱單過帳不會觸發收入價格計算。 它也不會觸發預期或最終收入認列表的建立。 如果品項模型群組設定為遞延裝箱單上的收入，它將使用目前的過帳設定檔分類帳科目繼續過帳，而不是在發票過帳上使用的新遞延收入科目。

## <a name="create-the-invoice"></a>建立發票

最後一步是為銷售訂單開具發票。 如果查看發票的憑單，您會注意到品項 S0001 和 S0008 的收入被遞延 ($321.21 + 160.61 = 481.82)，而品項 S0012 的剩餘金額已過帳到收入 (1,017.18)。 這些值加起來就是 $1,499，這與銷售訂單明細的總和相符。

[![憑單交易。](./media/revenue-recognition-so-voucher-transactions.png)](./media/revenue-recognition-so-voucher-transactions.png)

建立發票後，用於收入認列的 **收入價格配置**、**使用新訂單明細重新配置價格** 和 **收入認列表** 按鈕變得可用，但 **更新收入價格配置** 和 **預期收入認列表** 按鈕不可用。

[![可用的收入認列按鈕可用性。](./media/revenue-recognition-so-basic-after-invoice-buttons.png)](./media/revenue-recognition-so-basic-after-invoice-buttons.png)

**收入價格配置** 按鈕仍然可用，以便您查看收入價格計算。 如果確認後銷售訂單沒有發生任何變更，過帳發票不會更改 **確認收入** 欄位中的計算金額。

預期的收入認列表會移除並以最終收入認列表取代。 每個銷售訂單明細都保有收益計畫表詳細資料，並在履行合約義務時用於將遞延收入釋放為實際收入。

[![最終收入認列表。](./media/revenue-recognition-so-revenue-recognition-schedule.png)](./media/revenue-recognition-so-revenue-recognition-schedule.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]