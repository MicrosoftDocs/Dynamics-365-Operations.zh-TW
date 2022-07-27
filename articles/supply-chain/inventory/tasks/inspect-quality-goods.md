---
title: 檢查商品品質
description: 本主題介紹如何處理品質檢驗訂單。
author: yufeihuang
ms.date: 03/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventQualityOrderTable, InventQualityOrderLineResults, HcmWorkerLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: cc2fbbedb608b38c6855fbd48ff0c3e26ee3e0bc
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448848"
---
# <a name="inspect-the-quality-of-goods"></a>檢查商品品質

[!include [banner](../../includes/banner.md)]

本主題介紹如何處理品質檢驗訂單。 品質檢查通常由品質檢驗員進行。

如果已安裝標準示範資料，則您可以使用它來完成本主題中的過程。 如要使用此示範資料，您必須在開始前先選擇 *USMF* 法律實體。 然後您必須確認訂購單 *000016* 並過帳產品收據。 品質檢驗訂單會自動產生。

## <a name="step-1-select-a-quality-order"></a>第 1 步：選擇品質檢驗訂單

如要選擇品質檢驗訂單，請執行以下步驟。

1. 前往 **庫存管理 \> 定期工作 \> 品質管理 \> 品質檢驗訂單**。
1. 選擇在您開始此程序之前產生的品質檢驗訂單。

## <a name="step-2-record-test-results"></a>第 2 步：記錄測試結果

若要記錄測試結果，請遵循以下步驟。

1. 選擇 **結果**。
1. 選擇 **編輯**。
1. 在 **結果數量** 欄位中，輸入一個數字。
1. 在 **結果** 欄位中，尋找並選擇所需的記錄。 在此範例中，該結果是根據預先定義的結果。 通常，您將記錄更具體的測試結果，例如尺寸或其他維度。
1. 選擇 **儲存**。
1. 關閉頁面。

## <a name="step-3-validate-the-quality-order"></a>第 3 步：驗證品質檢驗訂單

如要驗證品質檢驗訂單，請執行以下步驟。

1. 選擇 **驗證**。
1. 在 **驗證者** 欄位中，選擇進行檢查的使用者。
1. 選擇 **選擇**。
1. 選擇 **確定**。
1. 關閉頁面。

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
