---
title: 產品配置的求解器策略
description: 本主題介紹如何使用求解器策略來提高產品配置的效能。
author: t-benebo
ms.date: 02/19/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PCCreateProductConfigurationModel, PCProductConfigurationModelListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 37e8f2c9557ee6fc827d60ca6dc83cd638b6378a
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8447849"
---
# <a name="solver-strategy-for-product-configuration"></a>產品配置的求解器策略

[!include [banner](../includes/banner.md)]

本主題介紹如何使用求解器策略來提高產品配置的效能。

求解器策略的概念最初是在 Microsoft Dynamics AX 2012 R2 的累積更新 (CU7) 中引入的。 並在 Microsoft Dynamics AX 2012 R3 的累積更新 8 (CU8) 和 Microsoft Dynamics 365 for Finance and Operations Enterprise edition 7.3 中得以延伸。

求解器策略概念現在包含以下策略：

- 預設
- 最小域數量優先
- 自上而下
- Z3

## <a name="solver-strategy"></a>求解器策略 

產品配置模型可以編制為[條件約束滿足問題 (CSP)](http://aima.cs.berkeley.edu/2nd-ed/newchap05.pdf)。 Microsoft Solver Foundation (MSF) 提供了兩種類型的求解器策略來解決可從產品配置模型中使用的 CSP。 這些求解器策略依賴於[啟發學習](https://techterms.com/definition/heuristic)，其用於確定在解決問題時考慮 CSP 變數的順序。 解決一個問題或一類問題時，啟發學習會明顯影響效能。

產品配置模型的求解器策略決定哪個求解器與啟發學習一起使用。 **預設**、**最小域數量優先** 和 **自上而下** 策略使用 MSF 中的兩個求解器，而 **Z3** 策略使用 Z3 求解器。 

真實的客戶實施研究表明，改變產品配置模型的求解器策略可以將回應時間從幾分鐘縮短到幾毫秒。 因此，值得嘗試不同的求解器策略來為您的產品配置模型找到最有效率的策略。

## <a name="change-the-settings-for-the-solver-strategy"></a>變更求解器策略的設定

若要變更求解器策略，請在 **產品配置模型** 頁面的在動作窗格上，選擇 **模型屬性**。 然後，在 **編輯模型詳細資料** 對話框中，選擇求解器策略。

[![變更求解器策略。](./media/solver-strategy.png)](./media/solver-strategy.png)

目前，沒有邏輯可以自動偵測哪個求解器策略將是條件約束型產品配置最有效的策略。 因此，必須一一嚐試求解器策略。

下表提供了有關在各種案例中使用的求解器策略的建議。

| 求解器策略      | 策略的使用方案 |
|----------------------|-----------------------------------|
| 預設              | **預設** 策略已經過最佳化，可解決依賴資料表條件約束的模型。 客戶實施研究表明，在廣泛使用資料表條件約束的案例中，該策略是最有效的策略。 |
| 最小域數量優先 | **最小域數量優先** 和 **自上而下** 策略密切相關。 客戶實施研究表明，**自上而下** 策略比 **最小域數量優先** 策略優秀。 但產品中仍保留了 **最小域數量優先** 策略，以實現回溯相容性。 研究已表明，在求解其中包含多個不使用資料表條件約束的算術運算式的模型時，這兩種求解器策略的效率更高。 但在某些情況下，**預設** 策略比這兩種策略更優秀。 因此，請務必嘗試每種策略。 |
| 自上而下             | **最小域數量優先** 和 **自上而下** 策略密切相關。 客戶實施研究表明，**自上而下** 策略比 **最小域數量優先** 策略優秀。 但產品中仍保留了 **最小域數量優先** 策略，以實現回溯相容性。 研究已表明，在求解其中包含多個不使用資料表條件約束的算術運算式的模型時，這兩種求解器策略的效率更高。 但在某些情況下，**預設** 策略比這兩種策略更優秀。 因此，請務必嘗試每種策略。 |
| Z3                   | 建議您使用 **Z3** 策略作為預設求解器策略。 如果您注重效能和可擴縮性，則可以評估其他策略。 |

## <a name="additional-resources"></a>其他資源

[產品配置概觀](build-product-configuration-model.md)

[啟發學習](https://techterms.com/definition/heuristic)

[條件約束滿足問題](http://aima.cs.berkeley.edu/2nd-ed/newchap05.pdf)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]