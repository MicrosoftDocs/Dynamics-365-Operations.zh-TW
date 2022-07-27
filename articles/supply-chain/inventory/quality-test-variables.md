---
title: 品質管理測試群組變數
description: 本主題介紹如何建立測試群組，以便在 Microsoft Dynamics 365 Supply Chain Management 中建立可在品質檢驗訂單上用於質化測試的測試變數。
author: yufeihuang
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4495c3d3f8df9f07ec079d8e497a17979abbe3ee
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448851"
---
# <a name="quality-management-test-variables"></a>品質管理測試群組變數

[!include [banner](../includes/banner.md)]

本主題介紹如何建立測試群組，以便在 Microsoft Dynamics 365 Supply Chain Management 中建立可在品質檢驗訂單上用於質化測試的測試變數。

對於在 **測試** 頁面定義的每個質化測試，您必須定義一個測試變量及其可能的成果 (結果)。 (對於質化測試，**測試** 頁面上的 **類型** 欄位設定為 *選項*。)

您使用 **測試變數** 頁面來設定、編輯和查看與質化測試有關的測試變數的可能結果。 對於每個結果，您指派的結果狀態為 *通過* 或 *失敗*，以指示當選擇該結果作為測試結果時，測試是通過還是失敗。 您使用 **測試群組** 頁面以將測試變數及其預設結果指派給單一質化測試。

對於每個測試變數，我們建議您至少定義兩個結果：一個結果狀態為 *通過*，另一個結果狀態為 *失敗*。 可以定義的變數或結果的總數沒有限制。 此外，多個測試可以使用相同的測試變數來記錄結果。

## <a name="examples-of-test-variables"></a>測試變數示例

### <a name="example-1"></a>示例 1

一家製造公司對製造的材料進行兩次測試。 在一項測試中，pH 值與色帶有關。 可接受的 pH 值以較淺的顏色顯示，不可接受的 pH 值以較深的顏色顯示。 在另一項測試中，進行了多次目視檢查，品管工作人員根據他們的判斷來確定品項是否通過目視檢查。

### <a name="example-2"></a>示例 2

一家生產餅乾的製造公司對成品進行檢查測試。 該檢查測試有幾個變數。 一個變數是口味，可能結果有好有壞。 第二個變數是顏色，可能結果為太暗、太淺和適宜。

## <a name="create-a-test-variable"></a>建立測試變數

若要建立測試變數，請遵循以下步驟。

1. 移至 **庫存管理 \> 設定 \> 品質控制 \> 測試變數**。
1. 在動作窗格上選取 **新增**，將資料列新增至格線。 接著，在新的一列上，設定以下欄位：

    - **變數** – 輸入變數的不重複識別碼或名稱。
    - **說明** – 輸入變數的詳細說明。

1. 在新列仍處於選取狀態時，在動作窗格上選擇 **結果**。
1. 在 **測試變數結果** 頁面，在動作窗格上，選擇 **新增**，在網格中新增一列。 接著，在新的一列上，設定以下欄位：

    - **結果** – 輸入結果的不重複識別碼或名稱。
    - **說明** – 輸入結果的詳細說明。
    - **結果狀態** – 選取 *通過* 或 *失敗*，以指示當選擇該結果作為測試結果時，測試是通過還是失敗。

1. 對每個附加結果重複上一步驟。 確保至少一個結果的結果狀態為 *通過*，並且至少有一個結果狀態為 *失敗*。
1. 關閉頁面。

## <a name="additional-resources"></a>其他資源

- [品質管理測試群組儀器](quality-test-instruments.md)
- [品質管理測試](quality-tests.md)
- [品質管理測試群組](quality-test-groups.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
