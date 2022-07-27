---
title: 庫存封鎖
description: 本主題提供庫存封鎖的概觀，也是 Supply Chain Management 中品質檢查流程的其中一部分。 您可以使用庫存封鎖，防止項目被處理或取用。
author: yufeihuang
ms.date: 03/02/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventBlocking, InventQualityOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2094
ms.assetid: 1968e32f-eff9-4c17-8f7f-a870f0c38fbc
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 606bc23f552b57d0f4e3fdad28d1144cdf43e5d5
ms.sourcegitcommit: fcb8a3419e3597fe855cae9eb21333698518c2c7
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/09/2022
ms.locfileid: "8450012"
---
# <a name="inventory-blocking"></a>庫存封鎖

[!include [banner](../includes/banner.md)]

本主題提供庫存封鎖的概觀，也是 Supply Chain Management 中品質檢查流程的其中一部分。 您可以使用庫存封鎖，防止項目被處理或取用。

您可以使用下列方式封鎖庫存項目：

- 手動
- 建立品質檢驗訂單
- 使用產生品質檢驗訂單的程序
- 使用庫存狀態封鎖

## <a name="blocking-items-manually"></a>手動封鎖項目

您可以在 **庫存封鎖** 頁面上，透過建立交易，封鎖一定數量的項目。 手動封鎖只能封鎖現有的庫存項目。 針對手動封鎖數量，您必須決定計畫活動，包括預期的接收數量，是否為現有數量。 封鎖預期接收項目，是您希望檢查完成之後，封鎖的項目可作為現有庫存使用。 您可以維護預期的日期。 根據預設，透過品質檢驗訂單封鎖的項目，會選取 **預期接收** 選項。 您可以在 **庫存封鎖** 頁面上，透過刪除交易，取消封鎖一定數量的項目。

## <a name="blocking-items-by-creating-a-quality-order"></a>建立品質檢驗訂單封鎖項目

您可以在 **品質檢驗訂單** 頁面，建立品質檢驗訂單，指定必須經過檢查的項目。 當您建立品質檢驗訂單時，會封鎖指定的項目數量。 與品質檢驗訂單關聯的取樣計畫，只會控制必須檢查的項目數量，而非封鎖的數項。 輸入品質檢驗訂單的數量，是封鎖的數量，無論是否為取樣計畫指定送檢的數量。

> [!NOTE]
> 主計劃不支援同持使用批次到期日期和封鎖庫存狀態功能。 這可能會在主計劃期間，導致雙重排除現有庫存。 我們建議您依賴批次處置代碼封鎖過期的批次，而非庫存狀態。

## <a name="blocking-items-by-using-a-process-that-generates-a-quality-order"></a>使用產生品質檢驗訂單的程序封鎖項目

如果品質程序指定必須檢查某個項目，則會自動封鎖一定數量的項目。 因此，自動產生品質檢驗訂單時，與品質檢驗訂單關聯的取樣計畫，會控制封鎖的項目數量，及必須檢查的項目數量。 如果 **品項取樣** 頁面上選取 **完全封鎖** 選項，則會封鎖全部的數量，例如：訂購單行在檢查期間會遭到封鎖，無論項目取樣的數量是多少。

### <a name="example"></a>範例

下列範例中，當發佈訂購單的裝箱單時，產生品質檢驗訂單。 在 **品質關聯** 的頁面上，您指定發佈訂購單裝箱單的程序，會啟動品質檢驗訂單。

|設定 |使用者動作 |結果 |
|----|---|---|
| 當發佈訂購單裝箱單時，品質關聯指定必須產生品質檢驗訂單。 品質檢驗訂單的項目取樣設定，指定必須檢查訂購單行中 10% 的數量。 此外，由於項目取樣設定中，已選取 **全部封鎖** 選項，因此，無論取樣檢查的數量是多少，檢查期間必須封鎖訂購單行的全部數量。 | 已發佈裝箱單。 | 已產生品質檢驗訂單。 訂購單項目中 10% 的數量將送往檢查。 會封鎖訂購單行全部的數量。 |

## <a name="blocking-items-by-using-inventory-status-blocking"></a>使用庫存狀態封鎖來封鎖項目

您可以使用 **庫存狀態** 頁面上的 **封鎖庫存** 參數，指定哪些庫存狀態為封鎖狀態。 您不能將庫存狀態用作生產訂單、銷售訂單、轉移訂單、輸出交易或專案整合的封鎖狀態。 針對輸出工作，使用可用庫存狀態的項目。 如果您的品項狀態為 **破損**，並且在這些品項上執行主計劃，則這些品項會被認為是缺少的，並且庫存會自動補貨。

## <a name="take-care-when-blocking-items-that-use-both-inventory-status-blocking-and-quality-order-blocking"></a>同時使用庫存狀態和品質檢驗訂單封鎖項目時要特別小心

您可以建立與庫存關聯的品質檢驗訂單，其庫存狀態已啟用 **庫存封鎖** 參數。 在這種案例中，品質檢驗訂單會在庫存狀態建立的記錄之外，產生額外的庫存封鎖紀錄。 由於品質檢驗訂單封鎖，會啟用 **預期接收** 參數，這會產生額外的 *訂購的庫存* 交易。 住種組合會導致難以理解產生的庫存交易，因為，封鎖的總數量看起來超過現有的總數量。 讓我們用範例檢查交易，範例中，要接收 10 件 A0001 項目，已建立品質檢驗訂單，要對其中 1 件項目進行樣本檢查。 行為還取決於，是否啟用 **庫存和倉庫管理參數** 頁面上的 **保留訂購品項** 選項。

>[!NOTE]
>如果您同時使用庫存狀態鎖定和品質檢驗訂單，我們強烈建議您啟用 **保留訂購品項** 選項。

### <a name="example-with-reserve-ordered-items-enabled"></a>範例中，已啟用「保留訂購品項」

啟用 **保留訂購品項** 時，所有庫存封鎖的交易，狀態會是 *實際預留* 或是 *訂購保留*。

| 庫存交易參考 | 收貨 | 簽發 | 數量 | 網站 | 倉庫 | 庫存狀態 | 位置 | 牌照 | 註解 |
|---|---|---|---|---|---|---|---|---|---|
| 訂購單 | 已購買 | | 10 件 | 2 | 24 | 封鎖 | RECV | receiptLp1 | | 
| 庫存封鎖 | | 實際保留 | -9 件 | 2 | 24 | 封鎖 | | | 庫存狀態封鎖產生的交易 |
| 庫存封鎖 | | 實際保留 | -1 件 | 2 | 24 | 封鎖 | RECV | receiptLp1 | 品質檢驗訂單取樣封鎖產生的交易 |
| 庫存封鎖 | 已訂購 | | 1 件 | 2 | 24 | 封鎖 | RECV | receiptLp1 | 品質檢驗訂單取樣封鎖的預期接收 |
| 庫存封鎖 | | 訂購保留 | 1 件 | 2 | 24 | 封鎖 | | | 庫存狀態封鎖產生的交易

### <a name="example-with-reserve-ordered-items-disabled"></a>範例中，停用「保留訂購品項」

當 **保留訂購品項** 停用時，於法保留預期的接收，因為處於 *已訂購* 狀態，所以部分封鎖的項目，仍會是 *訂購* 狀態。

| 庫存交易參考 | 收貨 | 簽發 | 數量 | 網站 | 倉庫 | 庫存狀態 | 位置 | 牌照 | 註解 |
|---|---|---|---|---|---|---|---|---|---|
| 訂購單 | 已購買 | | 10 件 | 2 | 24 | 封鎖 | RECV | receiptLp1 | |
| 庫存封鎖 | | 實際保留 | -9 件 | 2 | 24 | 封鎖 | | | 庫存狀態封鎖產生的交易 |
| 庫存封鎖 | | 實際保留 | -1 件 | 2 | 24 | 封鎖 | RECV | receiptLp1 | 品質檢驗訂單取樣封鎖產生的交易 |
| 庫存封鎖 | 已訂購 | | 1 件 | 2 | 24 | 封鎖 | RECV | receiptLp1 | 品質檢驗訂單取樣封鎖的預期接收 |
| 庫存封鎖 | | 訂購 | 1 件 | 2 | 24 | 封鎖 | RECV | receiptLp1 | 庫存狀態封鎖產生的交易

請注意兩種案例中，交易狀態和維度的差異。 因此，我們建議啟用 **保留訂購品項** 選項。

### <a name="disable-expected-receipts-from-quality-orders-that-sample-blocked-inventory-feature"></a>停用品質檢驗訂單中樣本庫存封鎖的預期接收功能

為了簡化品質檢驗訂單的庫存交易，系統提供一項功能，可以停用這類品質檢驗訂單的預期接收。 由於預期接收立即由庫存狀態封鎖，因此，此變更不會減少現有庫存。

此功能預設為關閉。 管理員可以透過在 [功能管理](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)工作區中搜尋 *停用品質檢驗訂單中樣本庫存封鎖的預期接收* 以開啟或關閉此功能。

## <a name="additional-resources"></a>其他資源

[建立和維護封鎖庫存](tasks/create-maintain-inventory-blocking.md)

[品質管理流程](quality-management-processes.md)

[檢查商品品質](tasks/inspect-quality-goods.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]