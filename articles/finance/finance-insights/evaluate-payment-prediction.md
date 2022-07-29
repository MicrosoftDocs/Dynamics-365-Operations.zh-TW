---
title: 評估初始客戶付款預測模型
description: 本主題描述了您可以採取的步驟來了解客戶付款預測模型並評估其有效性。
author: ShivamPandey-msft
ms.date: 07/16/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-05-28
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: 874c6e938681537a0420eece6835a4c2124e11fc
ms.sourcegitcommit: 133aa728b8a795eaeaef22544f76478da2bd1df9
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/13/2022
ms.locfileid: "8451365"
---
# <a name="evaluate-the-initial-customer-payment-prediction-model"></a>評估初始客戶付款預測模型

[!include [banner](../includes/banner.md)]

本主題說明如何在您打開 Finance Insights 並生成並訓練您的第一個模型後評估預測模型。 本主題介紹用於預測客戶付款的模型。 描述了您可以採取的步驟來了解客戶付款預測模型並評估其有效性。

## <a name="getting-details-about-the-model"></a>獲取有關模型的詳細資訊

在 Microsoft Dynamics 365 Finance 的 **Finance Insights 參數** 頁面上，**改良模組準確性** 連結會出現在準確度分數旁邊。

[![提高模型準確性連結](./media/prediction-model.png)](./media/prediction-model.png)

這個連結會帶你前往 AI Builder，您可以在其中了解有關當前模型的更多資訊，並採取措施對其進行改進。 下圖顯示了打開的頁面。

[![AI Builder。](./media/what-to-predict.png)](./media/what-to-predict.png)

下圖顯示了打開的頁面：

- 在 **效能** 部分，模型效能等級提供了模型質量的視角。 有關此等級的更多資訊，請參閱 AI Builder 文件中的[預測模型效能](/ai-builder/prediction-performance)。
- 這 **最具影響力的資料** 部分顯示了不同輸入類型的資料對您的模型的重要性。 您可以評估此列表和相應的百分比，以確定該資訊是否與您對您的業務和市場的了解一致。

    [![預測模型的效能和最具影響力的資料部分。](./media/models.png)](./media/models.png)

- 在裡面 **表現** 部分，選擇 **查看詳細資訊** 了解有關成績和其他注意事項的更多資訊。 在下圖中，詳細資訊顯示模型使用的資訊少於推薦的資訊。 因此，系統已生成警告訊息。

    [![模型效能的警告。](./media/details.png)](./media/details.png)

## <a name="digging-deeper"></a>深層發掘

雖然準確性是評估模型的良好起點，而效能等級提供了視角，AI Builder提供可用於評估的更詳細的指標。 要下載詳細資訊，請在 **表現** 部分，選擇省略號按鈕 (**...**) 旁邊 **使用型號** 按鈕，然後選擇 **下載詳細指標**。

[![下載詳細的指標命令。](./media/performance.png)](./media/performance.png)

下圖顯示了您可以下載資料的格式。

[![下載資料的格式。](./media/data-format.png)](./media/data-format.png)

要對結果進行更深入的分析，一個好的起點是查看「混淆矩陣」指標。 例如，這是上圖中針對該指標顯示的資料。

`{"name": "Confusion Matrix", "value": {"schema_type": "confusion_matrix", "schema_version": "1.0.0", "data": {"class_labels": ["0", "1", "2"], "matrix": [[71, 9, 21], [5, 0, 27], [2, 0, 45]]}}, "type": "dictionaryNumericalList", "isGlobalScore": false}`

以這種方式，您可以實現以下目標：

| &nbsp;                   | 準時預計 | 預計遲到 | 已預測嚴重延遲 |
|--------------------------|-------------------|----------------|---------------------|
| 實際按時付款   | **71**            | 0              | 21                  |
| 實際逾期付款      | 5                 | **0**          | 27                  |
| 實際嚴重逾期付款 | 2                 | 0              | **45**              |

混淆矩陣顯示了從訓練過程中隨機選擇的測試資料集的結果。 因為這些封閉的發票不用於訓練模型，所以它們是模型的良好測試用例。 另外，由於發票的實際狀態是已知的，模型的效能也可以被看到。

首先要尋找的是最常見的實際值。 儘管該值可能與整個數據集不完全一致，但它是一個合理的近似值。 在這種情況下，**實際按時付款** 出現在 171 張總發票中的 92 張中，是最常見的實際值。 因此，它是您模型的一個很好的基準。 如果您只是猜測所有發票都會按時交付，那麼在 171 次中您將正確 92 次（即 54% 的時間）。

了解數據集的平衡程度很重要。 在這種情況下，171 張發票中有 92 張按時付款，32 張延遲付款，47 張延遲付款。 這些值表示一個合理平衡的數據集，因為每個分類中都有重要的結果。 對於機器學習模型來說，其中一個狀態的結果很少的情況可能具有挑戰性。

模型的準確性表示測試數據集的正確預測數量。 這些正確的預測是前面示例中以粗體顯示的值。 在這種情況下，這些值產生的計算精度為 67.8 % (=\[ 71 + 0 + 45\] ÷ 171)。 該值表示比基線猜測的 54% 提高了 14%，並且是模型質量的一個指標。

如果您更仔細地查看混淆矩陣，您會注意到該模型在預測準時和非常晚的發票付款方面做得很好。 但是，所有 32 份發票實際上遲付 (但不是很遲) 都是錯誤的。 這一結果表明需要對模型進行額外的探索和改進。

代表模型效能優於準確性的一個數字是 F1 宏分數。 該分數考慮了每個分類狀態（準時、遲到和非常遲到）的結果。 例如，這是上圖中針對該「F1 Macro」指標顯示的資料。

`{"name": "F1 Macro", "value": 0.4927170868347339, "type": "percentage", "isGlobalScore": false}`

在這種情況下，大約 49。3% 的 F1 Macro 分數表明該模型無法在每個狀態下提供有效的預測，儘管總體準確度分數似乎相當高。

## <a name="improving-the-model"></a>正在改良模型

在您更好地了解第一個模型的結果後，您可能希望通過添加或刪除特徵列或過濾數據集中不支持準確預測的任何部分來改進模型。 關閉AI Builder，然後使用 **改進模型** 鏈接Dynamics 365 Finance重新啟動AI Builder過程。 您可以在不影響已發布模型的情況下試驗不同的特徵。 僅當您選擇時，已發布的模型才會受到影響 **發布**。 請記住，單個模型用於您的 Dynamics 365 Finance 實例執行個體。 因此，您應該在發布之前仔細檢查任何新模型。

## <a name="for-more-information"></a>如需相關資訊

有關如何評估預測模型的更多資訊，[機器學習模型的結果](/confusion-matrix.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
