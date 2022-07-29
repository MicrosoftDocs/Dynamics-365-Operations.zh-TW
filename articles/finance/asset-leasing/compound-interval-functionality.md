---
title: 複利間隔功能
description: 本主題提供的資訊將幫助您在每月、每季度、每半年和每年的複利間隔中進行選擇。
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
ms.openlocfilehash: 9d0f01748d370dfa5351ceb007a630564ca5d3a76c142830f32ce11951db9088
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450162"
---
# <a name="compounding-interval-functionality"></a>複利間隔功能

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

本主題提供的資訊將幫助您在每月、每季度、每半年和每年的複利間隔中進行選擇。 複利間隔功能用於確定租賃付款計劃中每年的複利期數。 本主題中的四個範例均顯示了在不同間隔內租賃的付款計劃。

您不能選擇低於租賃付款頻率的複利間隔。 例如，季度複利間隔不能與每月付款頻率一起使用，年複利間隔不能與半年付款頻率一起使用。 如果嘗試選擇低於租賃付款頻率的複利間隔，將收到錯誤訊息。

> [!NOTE]
> 在本主題的全部四個範例中，複利間隔與付款頻率相符。

## <a name="examples"></a>範例

### <a name="setup-for-all-four-leases"></a>設定全部四個租賃

下表顯示在 **一般** 和 **付款計劃行** 索引標籤上，針對範例中的四個租賃設定的值。

**一般索引標籤**

| 欄位                      | 值                        |
|----------------------------|------------------------------|
| 增量借款利率 | **5%**                       |
| 年金類型               | **普通年金**         |
| 複利區間       | 請參閱各個範例。 |
| 付款頻率          | **每月**                  |
| 開始日期          | **1/1/2020**                 |

**付款排程明細索引標籤**

| 欄位             | 值                        |
|-------------------|------------------------------|
| 開始日期        | **1/1/2020**                 |
| 期間           | **120**                      |
| 期間區間   | **月**                   |
| 結束日期          | **12/31/2029**               |
| 付款頻率 | 請參閱各個範例。 |
| 付款金額    | **50,000**                   |

### <a name="lease-1-monthly-compounding-interval-and-monthly-payment-frequency"></a>租賃 1：每月複利間隔和每月付款頻率

下表列出了付款計劃的前 12 個月。 請注意以下詳情：

- 「期間」欄中的值每個月都會增加 1，因為每個月都是一個新的複利區間。
- 在「現值」欄的公式中利率會除以 12，因為每年有 12 個複利期間。 指數 (即上標數字) 等於「期間」欄中的值。

| 期間 | 月 | 日期       | 付款金額 | 現值                                       |
|--------|-------|------------|----------------|-----------------------------------------------------|
| 1      | 1     | 1/31/2020  | 50,000.00      | 50,000 ÷ (1 + \[5% ÷ 12\])<sup>1</sup> = 49,792.53  |
| 2      | 2     | 2/29/2020  | 50,000.00      | 50,000 ÷ (1 + \[5% ÷ 12\])<sup>2</sup> = 49,585.92  |
| 3      | 3     | 3/31/2020  | 50,000.00      | 50,000 ÷ (1 + \[5% ÷ 12\])<sup>3</sup> = 49,380.17  |
| 4      | 4     | 4/30/2020  | 50,000.00      | 50,000 ÷ (1 + \[5% ÷ 12\])<sup>4</sup> = 49,175.28  |
| 5      | 5     | 5/31/2020  | 50,000.00      | 50,000 ÷ (1 + \[5% ÷ 12\])<sup>5</sup> = 48,971.23  |
| 6      | 6     | 6/30/2020  | 50,000.00      | 50,000 ÷ (1 + \[5% ÷ 12\])<sup>6</sup> = 48,768.03  |
| 7      | 7     | 7/31/2020  | 50,000.00      | 50,000 ÷ (1 + \[5% ÷ 12\])<sup>7</sup> = 48,565.67  |
| 8      | 8     | 8/31/2020  | 50,000.00      | 50,000 ÷ (1 + \[5% ÷ 12\])<sup>8</sup> = 48,364.15  |
| 9      | 9     | 9/30/2020  | 50,000.00      | 50,000 ÷ (1 + \[5% ÷ 12\])<sup>9</sup> = 48,163.47  |
| 10     | 10    | 10/31/2020 | 50,000.00      | 50,000 ÷ (1 + \[5% ÷ 12\])<sup>10</sup> = 47,963.62 |
| 11     | 11    | 11/30/2020 | 50,000.00      | 50,000 ÷ (1 + \[5% ÷ 12\])<sup>11</sup> = 47,764.61 |
| 12     | 12    | 12/31/2020 | 50,000.00      | 50,000 ÷ (1 + \[5% ÷ 12\])<sup>12</sup> = 47,566.41 |

### <a name="lease-2-quarterly-compounding-interval-and-quarterly-payment-frequency"></a>租賃 2：每季複利間隔和每季付款頻率

下表列出了付款計劃的前 12 個月。 請注意以下詳情：

- 「期間」欄中的值每三個月 (即每季) 都會增加 1，因為每一季都是一個新的複利區間。
- 在「現值」欄的公式中利率會除以 4，因為每年有四個複利期間。 指數等於「期間」欄中的值。

| 期間 | 月 | 日期       | 付款金額 | 現值                                     |
|--------|-------|------------|----------------|---------------------------------------------------|
| 1      | 1     | 1/31/2020  | 0.00           | 0.00 ÷ (1 + \[5% ÷ 4\])<sup>1</sup> = 0           |
| 1      | 2     | 2/29/2020  | 0.00           | 0.00 ÷ (1 + \[5% ÷ 4\])<sup>1</sup> = 0           |
| 1      | 3     | 3/31/2020  | 50,000.00      | 50,000 ÷ (1 + \[5% ÷ 4\])<sup>1</sup> = 49,382.72 |
| 2      | 4     | 4/30/2020  | 0.00           | 0.00 ÷ (1 + \[5% ÷ 4\])<sup>2</sup> = 0           |
| 2      | 5     | 5/31/2020  | 0.00           | 0.00 ÷ (1 + \[5% ÷ 4\])<sup>2</sup> = 0           |
| 2      | 6     | 6/30/2020  | 50,000.00      | 50,000 ÷ (1 + \[5% ÷ 4\])<sup>2</sup> = 48,773.05 |
| 3      | 7     | 7/31/2020  | 0.00           | 0.00 ÷ (1 + \[5% ÷ 4\])<sup>3</sup> = 0           |
| 3      | 8     | 8/31/2020  | 0.00           | 0.00 ÷ (1 + \[5% ÷ 4\])<sup>3</sup> = 0           |
| 3      | 9     | 9/30/2020  | 50,000.00      | 50,000 ÷ (1 + \[5% ÷ 4\])<sup>3</sup> = 48,170.92 |
| 4      | 10    | 10/31/2020 | 0.00           | 0.00 ÷ (1 + \[5% ÷ 4\])<sup>4</sup> = 0           |
| 4      | 11    | 11/30/2020 | 0.00           | 0.00 ÷ (1 + \[5% ÷ 4\])<sup>4</sup> = 0           |
| 4      | 12    | 12/31/2020 | 50,000.00      | 50,000 ÷ (1 + \[5% ÷ 4\])<sup>4</sup> = 47,576.21 |

> [!NOTE]
> 如果年金類型變更為 **年金到期**，付款將在季度初而不是季度末進行。

### <a name="lease-3-semiannual-compounding-interval-and-semiannual-payment-frequency"></a>租賃 3：半年複利間隔和半年付款頻率

下表列出了付款計劃的前 12 個月。 請注意以下詳情：

- 「期間」欄中的值每六個月 (即每半年) 都會增加 1，因為每半年都是一個新的複利區間。
- 在「現值」欄的公式中利率會除以 2，因為每年有兩個複利期間。 指數等於「期間」欄中的值。

| 期間 | 月 | 日期       | 付款金額 | 現值                                     |
|--------|-------|------------|----------------|---------------------------------------------------|
| 1      | 1     | 1/31/2020  | 0.00           | 0.00 ÷ (1 + \[5% ÷ 2\])<sup>1</sup> = 0           |
| 1      | 2     | 2/29/2020  | 0.00           | 0.00 ÷ (1 + \[5% ÷ 2\])<sup>1</sup> = 0           |
| 1      | 3     | 3/31/2020  | 0.00           | 0.00 ÷ (1 + \[5% ÷ 2\])<sup>1</sup> = 0           |
| 1      | 4     | 4/30/2020  | 0.00           | 0.00 ÷ (1 + \[5% ÷ 2\])<sup>1</sup> = 0           |
| 1      | 5     | 5/31/2020  | 0.00           | 0.00 ÷ (1 + \[5% ÷ 2\])<sup>1</sup> = 0           |
| 1      | 6     | 6/30/2020  | 50,000.00      | 50,000 ÷ (1 + \[5% ÷ 2\])<sup>1</sup> = 48,780.49 |
| 2      | 7     | 7/31/2020  | 0.00           | 0.00 ÷ (1 + \[5% ÷ 2\])<sup>2</sup> = 0           |
| 2      | 8     | 8/31/2020  | 0.00           | 0.00 ÷ (1 + \[5% ÷ 2\])<sup>2</sup> = 0           |
| 2      | 9     | 9/30/2020  | 0.00           | 0.00 ÷ (1 + \[5% ÷ 2\])<sup>2</sup> = 0           |
| 2      | 10    | 10/31/2020 | 0.00           | 0.00 ÷ (1 + \[5% ÷ 2\])<sup>2</sup> = 0           |
| 2      | 11    | 11/30/2020 | 0.00           | 0.00 ÷ (1 + \[5% ÷ 2\])<sup>2</sup> = 0           |
| 2      | 12    | 12/31/2020 | 50,000.00      | 50,000 ÷ (1 + \[5% ÷ 2\])<sup>2</sup> = 47,590.72 |

> [!NOTE]
> 如果年金類型變更為 **期初年金**，付款將在 1 月和 7 月，而不是 6 月和 12 月進行。

### <a name="lease-4-annual-compounding-interval-and-annual-payment-frequency"></a>租賃 4：年複利間隔和年付款頻率

下表列出了付款計劃的前 12 個月。 請注意以下詳情：

- 「期間」欄中的值每 12 個月 (即每年) 都會增加 1，因為每年都是一個新的複利區間。
- 在「現值」欄的公式中利率會除以 1，因為每年有一個複利期間。 指數等於「期間」欄中的值。

| 期間 | 月 | 日期       | 付款金額 | 現值                                     |
|--------|-------|------------|----------------|---------------------------------------------------|
| 1      | 1     | 1/31/2020  | 0.00           | 0.00 ÷ (1 + \[5% ÷ 1\])<sup>1</sup> = 0           |
| 1      | 2     | 2/29/2020  | 0.00           | 0.00 ÷ (1 + \[5% ÷ 1\])<sup>1</sup> = 0           |
| 1      | 3     | 3/31/2020  | 0.00           | 0.00 ÷ (1 + \[5% ÷ 1\])<sup>1</sup> = 0           |
| 1      | 4     | 4/30/2020  | 0.00           | 0.00 ÷ (1 + \[5% ÷ 1\])<sup>1</sup> = 0           |
| 1      | 5     | 5/31/2020  | 0.00           | 0.00 ÷ (1 + \[5% ÷ 1\])<sup>1</sup> = 0           |
| 1      | 6     | 6/30/2020  | 0.00           | 0.00 ÷ (1 + \[5% ÷ 1\])<sup>1</sup> = 0           |
| 1      | 7     | 7/31/2020  | 0.00           | 0.00 ÷ (1 + \[5% ÷ 1\])<sup>1</sup> = 0           |
| 1      | 8     | 8/31/2020  | 0.00           | 0.00 ÷ (1 + \[5% ÷ 1\])<sup>1</sup> = 0           |
| 1      | 9     | 9/30/2020  | 0.00           | 0.00 ÷ (1 + \[5% ÷ 1\])<sup>1</sup> = 0           |
| 1      | 10    | 10/31/2020 | 0.00           | 0.00 ÷ (1 + \[5% ÷ 1\])<sup>1</sup> = 0           |
| 1      | 11    | 11/30/2020 | 0.00           | 0.00 ÷ (1 + \[5% ÷ 1\])<sup>1</sup> = 0           |
| 1      | 12    | 12/31/2020 | 50,000.00      | 50,000 ÷ (1 + \[5% ÷ 1\])<sup>1</sup> = 47,619.05 |

> [!NOTE]
> 如果年金類型更改為 **年金到期**，付款將在 1 月，而不是 12 月進行。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]