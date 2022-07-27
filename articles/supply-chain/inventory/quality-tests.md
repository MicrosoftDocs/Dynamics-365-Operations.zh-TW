---
title: 品質管理測試
description: 本主題說明如何建立測試，以便在 Microsoft Dynamics 365 Supply Chain Management 中用於品質檢驗訂單。
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
ms.openlocfilehash: c10b67f86fc29b5e8c08081a9b789d4f42c24cf4
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448662"
---
# <a name="quality-management-tests"></a>品質管理測試

[!include [banner](../includes/banner.md)]

本主題說明如何建立測試，以便在 Microsoft Dynamics 365 Supply Chain Management 中用於品質檢驗訂單。

您使用 **測試** 頁面來定義和查看確定您的產品是否符合品質規格的各項測試。 您可以將一或多個單獨的測試指派給一個測試群組。 在這種情況下，您也可以指定測試特定的資訊，例如可接受的測量值。 測量值用於量化測試。 對於質化測試，則使用群組變數。

- 對於量化測試，**類型** 欄位設定為 *整數* 或 *分數*。 另外也指定了測量單位。 品質規格和測試結果會以數字表示。
- 對於質化測試，**類型** 欄位設定為 *選項*。 質化測試需要有關正在測量的測試變數及其列舉選項的額外資訊。 品質規格和測試結果會根據結果表示。

您可以視需要將測試儀器指派給測試。 但是，不需要使用測試儀器來建立和使用具有品質檢驗訂單的測試。 有關詳細資訊，請參閱[品質管理測試儀器](quality-test-instruments.md)。

您也可以選擇為測試指定一個單位，以指示記錄測試結果的測量單位。 例如，溫度測試的單位可能包括華氏度或攝氏度。

## <a name="example-of-a-test"></a>測試示例

一家製造公司對採購的材料進行兩項測試：材料品質的量化測試和包裝損壞的質化測試。 該公司指定有關質化測試的額外資訊，以定義測試變數 (例如，損壞的包裝) 及其結果。 公司使用 **測試群組** 頁面將兩個測試指派給一個測試群組，並指定測試特定的資訊。 測試組指派到一個品質檢驗訂單，以便公司可以報告兩個測試的測試結果。

## <a name="create-a-test"></a>建立測試

若要建立測試，請遵循以下步驟：

1. 移至 **庫存管理 \> 設定 \> 品質控制 \> 測試**。
1. 在動作窗格上選取 **新增**，將資料列新增至格線。 接著，在新的一列上，設定以下欄位：

    - **測試** – 輸入測試的不重複識別碼或名稱。
    - **說明** – 輸入測試的詳細說明。
    - **類型** – 選擇測試產生的結果類型。 對於量化測試，選擇 *分數* 或 *整數*。 對於質化測試，選擇 *選項*。
    - **測試儀器** – 選取應用於測試的[測試儀器](quality-test-instruments.md)。
    - **單元** – 如果您在 **類型** 欄位 (如果測試是量化測試) 選擇 *分數* 或 *整數*，請選擇記錄測試結果的測量單位。

1. 關閉頁面。

> [!NOTE]
> 儲存測試後，您就無法再編輯 **類型** 網格中的欄位。 如果您必須更改將為測試記錄的測試結果類型，請在動作窗格上選擇 **變更品質測試類型**。 在 **變更品質測試類型** 對話方塊，將 **新類型** 欄位設定為所需的類型，然後選擇 **確定** 以關閉對話方塊。

## <a name="additional-resources"></a>其他資源

- [品質管理測試群組儀器](quality-test-instruments.md)
- [品質管理測試群組](quality-test-groups.md)
- [品質管理測試群組變數](quality-test-variables.md)
- [品質關聯](quality-associations.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
