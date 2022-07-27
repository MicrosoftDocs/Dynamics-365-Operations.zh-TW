---
title: 全球庫存會計支援的商業文件
description: 本主題列出了全球庫存會計支援的商業文件。 它還提供了訂購單文件的詳細範例。
author: AndersGirke
ms.date: 06/18/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2021-06-18
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 47251a7167a00346aed26b9e9535f1b12301e5a6
ms.sourcegitcommit: 8c17717b800c2649af573851ab640368af299981
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/23/2021
ms.locfileid: "8449496"
---
# <a name="business-documents-supported-by-global-inventory-accounting"></a>全球庫存會計支援的商業文件

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]
<!--KFM: Preview until 4/30/2022 -->

完全設定全球庫存會計增益集後，即可處理在 Microsoft Dynamics 365 Supply Chain Management 中輸入的庫存相關文件。

## <a name="supported-business-documents"></a>支援的商業文件

有兩種類型的商業文件：

- **有日記帳的文件**–這些文件包括產品收據、採購發票、裝箱單和銷售發票文件。
- **沒有日記帳的文件**–這些文件包括盤點、移動和庫存調整文件。

在本主題的後面部分，說明過程時將以訂購單為範例。

下表列出了當前版本支援的文件。

| 文件類型      | 文件        |
|--------------------|-----------------|
| 訂購單     | 產品收據 |
| 訂購單     | 發票         |
| 銷售訂單        | 裝箱單    |
| 銷售訂單        | 發票         |
| 庫存日記帳 | 移動        |
| 庫存日記帳 | 調整      |
| 庫存日記帳 | 盤點        |
| 庫存日記帳 | 轉移        |
| 轉移訂單     | 貨件        |
| 轉移訂單     | 接收         |

> [!IMPORTANT]
> 全球庫存會計異步處理輸入到Supply Chain Management 的文件。 對於有問題的文件，不會顯示錯誤訊息。

## <a name="example-purchase-order"></a>範例：訂購單

### <a name="product-receipt"></a>產品收據

以通常的方式過帳產品收據。 在 **所有訂購單** 頁面，選取一個訂購單，然後在「動作窗格」上的 **收到** 索引標籤，選取 **產品收據** 打開 **產品收據日記帳** 頁面。 為每個明細生成一個作業事件和一個全球庫存會計事件。 因此，選取 **明細** 索引標籤，然後選取 **庫存\>事件和測量** 打開 **事件和測量** 頁面。

全球庫存會計是一種基於事件和測量值的會計系統。 **事件和測量** 頁面的測量明細網格上顯示測量值清單。 每個測量都有一個維度清單。

對於每個作業事件，有兩種測量類型：

- **作業測量**–這些測量值以通用措辭描述業務文件。 一種測量值是使用文件中使用的測量單位的產品數量。 還有一些影響庫存價值的測量值，例如總價、折扣、折扣百分比和明細費用。
- **資源盤點測量**–這些測量值來自庫存登記的角度。 它們以庫存測量單位描述文件對庫存的影響。 如果有多個庫存登記，則有多個資源盤點測量明細。

維度按以下方式整理：

- **二元**–二元性描述了參與經濟事件的機構。 對於外部商業文件，原始維度說明輸入文件的法律實體，而二元維度描述供應商、客戶等。 對於內部業務單據 (如轉移訂單)，二元維度描述對應倉庫。
- **維度類型**–維度類型對維度進行分類。
- **維度**–維度的名稱。
- **維度值**–維度的值。

### <a name="global-inventory-accounting-event"></a>全球庫存會計事件

全球庫存會計以運營事件和測量作為輸入。 然後，它根據附加的貨幣和慣例對每個相關分類帳進行適當的會計處理。 你可以選取 **全球庫存會計事件和測量** 查看全球庫存會計事件。 全局庫存會計事件遵循與作業事件相同的方法，但它使用不同的測量。 測量類型主要分為三種：產品成本數量、產品成本和差異。

子分類帳用於進一步分類測量。 可能有多個分類帳。 這些分類帳連結到輸入文件的法律實體。 更改 **分類帳** 欄位的值，您可以查看每個分類帳的事件與測量。

### <a name="cost-element"></a>成本元素

根據附加到分類帳的成本要素原則，系統將成本要素指派給影響庫存成本的每個已核算的操作事件測量。 這些測量包括總價、折扣、折扣百分比和明細費用。

### <a name="measurement-line-details"></a>測量明細詳細資料

**概述** 索引標籤顯示附加原則的詳細資料。 成本物件維度根據成本物件原則顯示成本物件。 如果成本流程假設為 *特定 - 批次*，特定識別維度顯示批號。

### <a name="purchase-invoice"></a>採購發票

以通常的方式過帳發票。 然後，在動作窗格上，到 **發票** 索引標籤，**日記帳** 群組，選取 **發票** 打開發票日記帳。 為每個明細生成一個作業事件和一個全球庫存會計事件。 因此，選取 **明細** 索引標籤，然後選取 **庫存\>事件和測量** 打開 **事件和測量** 頁面。 **事件和測量** 頁面顯示相同的測量類型。 但是，由於頁面顯示了不同的測量角色和測量修飾詞，因此對機構 (法律實體) 的影響不同。

選取 **全球庫存會計事件和測量** 查看全球庫存會計事件。 庫存數量和成本現在從 *收貨未開票庫存* 子分類帳科目進入 *採購貨物的成本* 子分類帳科目。