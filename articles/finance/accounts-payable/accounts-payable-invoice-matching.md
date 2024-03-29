---
title: 應付帳款發票比對概觀
description: 應付帳款發票比對是比對廠商發票、訂購單和產品收貨資訊的流程。
author: sunfzam
ms.date: 07/25/2019
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: VendInvoicePostingHistory
audience: Application User
ms.reviewer: twheeloc
ms.custom:
- "27361"
- intro-internal
ms.assetid: 9f3dace7-05d8-4974-8f85-aca2e224876c
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2959df58dbde71ba516c1a230e64d38b885c23f5
ms.sourcegitcommit: 9cbff8a2cdeaf606488fb0044b3de4ab4409c9dc
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/26/2022
ms.locfileid: "8451638"
---
# <a name="accounts-payable-invoice-matching-overview"></a>應付帳款發票比對概觀

[!include [banner](../includes/banner.md)]

應付帳款發票比對是比對廠商發票、訂購單和產品收貨資訊的流程。

比對單據時，這些單據之間的差異稱為比對差異。 用指定的比對差異允差進行比較。 如果比對差異超過允差百分比或金額，廠商發票頁面和發票歷史紀錄和比對詳細資料頁面中將顯示比對差異圖示。 

例如，您輸入一個訂購單，其中包含一個單價為 1.00 的 1,000 個電池的行品項。 核准訂購單並提交給廠商。 廠商運送 1,000 個電池，且針對單價為 1.00 的這 1,000 個電池輸入產品收貨。 這些電池的庫存成本使用此價格更新。 

單價為 1.10 的 1,000 個電池的發票到達。 您的法律實體原則允許此類品項有 5% 的淨單價允差。 因此，1.05 的價格是可接受的，但 1.10 則不可以。 當您輸入發票資訊時，會識別出價格比對差異，您可以保存發票直到差異解決。

您可以使用以下類型的 **應付帳款發票比對**：

-   **發票總計比對** – 將發票上的總金額與訂購單上的總金額進行比對。 這種類型的發票比對包含最少的詳細資訊，因此您可以使用此選項來設定控制，以最大限度地減少查看發票比對資訊所需的員工時間。
-   **雙向比對** - 將發票的價格資訊與訂購單的價格資訊進行比對。
-   **三向比對** - 將發票的價格資訊與訂購單的價格資訊進行比對。 還將發票上的數量資訊與為發票選擇的產品收貨上的數量資訊進行比對。
-   **費用比對** – 將發票上的費用資訊 (金額) 與訂購單上的費用資訊 (金額) 進行比對。

> [!NOTE]
> 其他形式的發票驗證可以使用廠商發票原則來完成。 

雙向比對和三向比對一律按單價比對價格資訊。 您還可以設定這些比對原則以按總價比對價格資訊。
-   **淨單價比對** – 透過將發票上每行的淨單價與訂購單上相應的淨單價進行比較，比對雙向比對或三向比對的價格資訊。 淨單價由以下公式計算：行的淨額/行的數量
-   **總價比對** – 透過將發票上每行的淨額 (總價) 與訂購單上相應的淨額價進行比較，比對雙向比對或三向比對的價格資訊。 淨額由以下公式計算：*(單價 \* 行數量) + 行費用 - 行折扣*。 按百分比比對總價時，系統會使用交易貨幣比較值。 按金額比對總價時，系統會使用會計貨幣比較值。 當您為訂購單行部分開票時，將在該行的最後一個發票上驗證總價比對。 

通常，在編輯 **廠商發票** 頁面上的廠商發票時，將自動執行發票比對計算。 或者，可以根據需要按需求執行發票比對。 依需要值行的發票比對由 **發票驗證** 索引標籤 **應付帳款參數** 頁面上的 **自動更新發票** 標題狀態針對法律實體控制。發票比對也可以作為發票審核流程的一部分來執行。 您可以在 **廠商發票** 頁面和相關發票比對頁面上查看發票比對的結果。

## <a name="invoice-totals-matching"></a>發票總額比對
您可以使用發票總計比對，協助確保發票總額與預期金額的偏差不超過可接受的差異。 在 **發票總計比對詳細資料** 頁面中比較了六個總額，如下表所示。 如果發票總額比對的允許的允差為 20%，則總折扣金額的 100% 差異百分比將視為比對差異。

| 總額欄位    | 實際發票總額 | 預計發票總額 | 差異百分比 | 比對狀態 |
|----------------|----------------------|------------------------|---------------------|--------------|
| 餘額        | 495.00               | 495.00                 | 0%                  | 通過       |
| 總折扣 | 0.00                 | 9.90                   | 100%                | 未通過       |
| 費用        | 64.90                | 64.90                  | 0%                  | 通過       |
| 銷售稅      | 139.98               | 137.50                 | 2%                  | 通過       |
| 四捨五入      | 0.00                 | 0.00                   | 0%                  | 通過       |
| 發票金額 | 699.88               | 687.50                 | 2%                  | 通過       |

發票總額比對由 **應付帳款參數** 頁面上的 **比對發票總額** 切換針對法律實體控制。 對預期發票總額和實際發票總額執行比對。 預期發票總額是根據訂購單中的價格、費用和銷售稅資訊以及發票中的數量計算得出的。

## <a name="two-way-price-totals-matching"></a>雙向，總價比對
使用雙向比對有助於確保訂購單和發票上的價格資訊之間的差異在可接受的允差範圍內。 可以將發票上每個明細的淨額價格資料以及所有待處理的和之前已過帳發票明細的淨額價格資料，與相應的訂購單明細淨額進行比較。 這稱為總價比對。 

可以根據百分比、金額或百分比和金額進行總價比對。 

如果指定了採購價格總允差百分比，則比較五個欄位，如下表所示。 由於採購價格總允差百分比為 10%，50% 的總價差異百分比表示比對差異。

| 比對狀態 | 發票淨額 | 預期淨額 | 不相符的採購價格總額 (差異金額) | 不相符的採購價格總百分比 (差異百分比) | 採購價格總允差百分比 |
|--------------|--------------------|---------------------|--------------------------------------------------|--------------------------------|---------------------------|
| 通過       | 105.00             | 100.00              | 5.00                                             | 5%                             | 10%                 |
| 未通過       | 150.00             | 100.00              | 50.00                                            | 50%                            | 10%                     |

如果指定了採購價格總允差金額，則比較五個欄位，如下表所示。 由於採購價格總允差金額為 100.00%，所以價格總差異金額 105.00 表示比對差異。

| 比對狀態 | 發票淨額 | 預期淨額 | 不相符的採購價格總額 (差異金額) | 不相符的採購總價，以會計貨幣表示 (差異金額) | 採購價格總允差 |
|--------------|--------------------|---------------------|-----------------------------------------------|-------------------------------|--------------------------------|
| 通過       | 150.00             | 100.00              | 50.00                                            | 50.00                    | 100.00                         |
| 未通過       | 205.00             | 100.00              | 105.00                                           | 105.00                  | 100.00                         |

如果使用百分比允差和允差金額 (有時稱為不超過金額) 設定總價比對，則在評估行是否具有比對差異時會考慮這兩個允差。 如果百分比或金額超過允差，如下表中的 150.00 和 205.00 行所示，則該行存在比對差異。

| 比對狀態 | 發票淨額 | 預期淨額 | 不相符的採購價格總百分比 (差異百分比) | 採購價格總允差百分比 | 不相符的採購總價，以會計貨幣表示 (差異金額) | 採購價格總允差 |
|--------------|--------------------|---------------------|-----------------------------|------------------|----------------------------------|--------------------------------|
| 通過       | 105.00             | 100.00              | 5%                     | 10%                         | 5.00           | 100.00                         |
| 未通過       | 150.00             | 100.00              | 50%                   | 10%                     | 50.00            | 100.00                         |
| 未通過       | 205.00             | 100.00              | 105%                 | 10%                      | 105.00                                  | 100.00                         |

雙向比對由 **應付帳款參數** 頁面上的 **行比對原則** 欄位針對法律實體控制。 根據 **允許比對原則覆寫** 欄位中的選擇，您可以在 **比對原則** 頁上為特定廠商、品項或品項和廠商組合選擇雙向比對，在 **採購訂單** 頁上為特定訂購單選擇雙向比對。

總價比對由 **應付帳款參數** 頁面上的 **比對總價** 欄位針對法律實體控制。 採購價格總允差百分比和允差金額 (不超過金額) 也在該頁面上指定。

## <a name="two-way-net-unit-price-matching"></a>雙向，淨單價比對
使用雙向比對有助於確保訂購單和發票上的價格資訊之間的差異在可接受的允差範圍內。 您可以比較發票上每個品項的淨單價的價格資訊。 這稱為淨單價比對。 

在 **發票總計比對詳細資料** 頁面中比較了九行總額，如下表所示。 如果淨單價比對的允許價格允差為 10%，則淨單價的 22.61% 差異將視為比對差異。

| 行欄位                    | 發票面額 | 訂購單面額 | 差異百分比 | 比對狀態 |
|-------------------------------|---------------|----------------------|---------------------|--------------|
| 單價                    | 55.40         | 55.38                | 0%                  | 通過       |
| 計價單位                    | 1.00          | 1.00                 | 0%                  | 通過       |
| 採購費用          | 50.00         | 0.00                 | 100%                | 未通過       |
| 折扣                      | 0.00          | 0.00                 | 0%                  | 通過       |
| 折扣率              | 0.00          | 0.00                 | 0%                  | 通過       |
| 多行折扣            | 0.00          | 0.00                 | 0%                  | 通過       |
| 多行折扣百分比 | 0.00          | 0.00                 | 0%                  | 通過       |
| 淨額                    | 271.60        | 221.52               | 22.61%              | 未通過       |
| 淨單價                | 67.9000       | 55.3800              | 22.61%              | 未通過       |

雙向比對由 **應付帳款參數** 頁面上的 **行比對原則** 欄位針對法律實體控制。 根據 **允許比對原則覆寫** 欄位中的選擇，您可以在 **比對原則** 頁上為特定廠商、品項或品項和廠商組合選擇雙向比對，在 **採購訂單** 頁上為特定訂購單選擇雙向比對。 

淨單價比對由 **應付帳款參數** 頁面上的 **啟用發票比對驗證** 欄位針對法律實體控制。 透過使用 **價格允差** 頁面，淨單價允差百分比可用於設定品項、品項群組、廠商群組、廠商、品項和廠商群組或法律實體。

## <a name="two-way-price-totals-matching-and-net-unit-price-matching"></a>雙向，總價比對和淨單價比對
您可以同時使用總價比對和淨單價比對。 此範例假設以下設定：

-   USB 隨身碟品項的淨單價允差為 10%。
-   法律實體的總價比對允差為 15% 或 500.00。

訂購單包括以下行。

| 品項編號 | 數量 | 單價 | 淨額 |
|-------------|----------|------------|------------|
| USB 隨身碟   | 1,000    | 10.00      | 10,000.00  |

輸入三張發票，如下表所示。 發票 3 存在發票比對差異，因為 1,880.00 的差異超過了採購價格總允差金額 500.00。 對於總價比對，發票淨額除了您目前正在使用的發票外，還包括所有以前過帳的發票。

| 品項編號          | 數量 | 單價 | 淨額 | 價格比對 | 總價比對 |
|----------------------|----------|------------|------------|-------------|-------------------|
| 發票 1：USB 隨身碟 | 800      | 10.80      | 8,640.00   | 通過      | 通過            |
| 發票 2：USB 隨身碟 | 100      | 10.80      | 1,080.00   | 通過      | 通過            |
| 發票 3：USB 隨身碟 | 200      | 10.80      | 2,160.00   | 通過      | 未通過            |
| 總計                |          |            | 11,880.00  |             |                   |

## <a name="three-way-matching"></a>三向比對

使用三向比對有助於確保訂購單和發票上的價格資訊之間的差異在可接受的允差範圍內，並確保發票上的數量與相應產品收貨上的數量相比對。

在「發票比對詳細資料」頁面上對同一行金額進行了比較，和雙向比對相同。 此外，發票上的數量與已收到的產品收貨數量相比對。 如果發票數量與比對的產品收貨數量不同，則存在數量比對錯誤。

| 行欄位                    | 發票面額 | 訂購單面額 | 差異百分比 | 比對狀態 |
|-------------------------------|---------------|----------------------|---------------------|--------------|
| 單價                    | 55.40         | 55.38                | 0%                  | 通過       |
| 計價單位                    | 1.00          | 1.00                 | 0%                  | 通過       |
| 採購費用          | 50.00         | 0.00                 | 100%                | 未通過       |
| 折扣                      | 0.00          | 0.00                 | 0%                  | 通過       |
| 折扣率              | 0.00          | 0.00                 | 0%                  | 通過       |
| 多行折扣            | 0.00          | 0.00                 | 0%                  | 通過       |
| 多行折扣百分比 | 0.00          | 0.00                 | 0%                  | 通過       |
| 淨額                    | 271.60        | 221.52               | 22.61%              | 未通過       |
| 淨單價                | 67.9000       | 55.3800              | 22.61%              | 未通過       |

| 行欄位                     | 發票面額 | 比對狀態 |
|--------------------------------|---------------|--------------|
| 發票數量               | 4.00          |              |
| 產品收貨總數符合 | 0.00          | 未通過       |

三向比對由 **應付帳款參數** 頁面上的 **行比對原則** 欄位針對法律實體控制。 根據 **允許比對原則覆寫** 欄位中的選擇，您可以在 **比對原則** 頁上為特定廠商、品項或品項和廠商組合選擇三向比對，在 **採購訂單** 頁上為特定訂購單選擇三向比對。

## <a name="charges-matching"></a>費用比對
您可以使用費用比對，協助確保費用總額與預期金額的偏差不超過可接受的差異百分比。 適用於發票和訂購單的每個費用代碼的總金額，且訂購單是在 **比較費用面額 - 發票：** 頁面中進行比較，如下表所示。 如果費用代碼允許的允差為 25%，則 **授權費用代碼** 的 99,999,999,999.99% 差異百分比將視為比對差異。

> [!NOTE] 
> 99,999,999,999.99% 的差異百分比表示訂購單的預期金額為零，且發票上的實際金額為正值。 

| 費用比對狀態 | 發票費用代碼 | 實際總計算值 | 預期總計算值 | 差異金額 | 差異百分比 | 允差百分比 |
|----------------------|----------------------|-------------------------------|---------------------------------|-----------------|---------------------|----------------------|
| 未通過               | 授權              | 25                            | 0                               | 25              | 99,999,999,999.99%  | 25%                  |
| 通過               | 運費              | 200                           | 200                             | 0               | 0%                  | 25%                  |
| 未通過               | 急件             | 4                             | 2                               | 2               | 100%                | 25%                  |

費用總額比對由 **應付帳款參數** 頁面上的 **比對費用** 切換針對法律實體控制。 您可以在 **費用允差** 頁面上設定費用的差異允差百分比。

> [!NOTE]
> 費用比對僅對在 **費用代碼** 頁上選擇了 **比較訂購單和發票面額** 切換的費用代碼執行。

## <a name="related-functionality"></a>相關功能
廠商發票通常是根據代表實際發貨的產品收貨，而不是根據訂購單。 有時開票金額與訂購單金額不相符，有時發貨數量與開票數量不相符。 您可以透過以下方式管理此資訊：
-   根據產品收貨建立廠商發票。 發票會自動建議產品收貨，您可以選擇要使用的產品收貨。 如果需要，您還可以從多個訂購單中選擇特定的產品收貨行品項。
-   查看並核准發票上的已開票數量與產品收貨上的已接收數量之間的數量差異。 如果有差異，您可以儲存該發票並之後將其與不同的產品收貨比對，或變更開票數量以比對接收的數量。
-   輸入原始訂購單中未包含的發票金額，以便發票資訊與您從廠商處收到的發票相比對。 您可以將訂購單的費用與發票的費用進行比較。 如有必要，您可以將費用新增到發票並將其分配到發票行。
-   查看並核准發票淨單價和訂購單淨單價之間的價格比對差異。 您可以為法律實體、廠商和品項設定價格允差百分比。 如果廠商發票行價格不在可接受的價格允差範圍內，您可以儲存發票直到它被核准過帳，或者直到您收到廠商的更正。

有關詳細資訊，請參閱[三向比對原則](three-way-matching-policies.md)和[設定應付帳款發票比對驗證](tasks/set-up-accounts-payable-invoice-matching-validation.md)。 






[!INCLUDE[footer-include](../../includes/footer-banner.md)]
