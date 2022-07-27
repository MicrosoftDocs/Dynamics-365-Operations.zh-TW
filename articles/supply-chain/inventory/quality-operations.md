---
title: 不符合項操作
description: 本主題說明如何建立和使用不符合項的操作。
author: yufeihuang
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestOperations, InventTestRelatedOperations
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 35619454af8b1cb1b7d383d393362f58d9dd0ea6
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448665"
---
# <a name="operations-for-nonconformances"></a>不符合項操作

[!include [banner](../includes/banner.md)]

本主題說明如何建立和使用不符合項的操作。

您可以使用 **操作** 頁面來定義可以為已批准的不符合項執行的工作類別。 當您將相關操作指派給不符合項時，您可以提供執行該操作所需的詳細資料，例如相關材料、工時和操作費用。 系統會使用這些資訊來計算操作的估計成本。 詳細資訊及估計成本僅供參考。 與品質相關的操作與可以為生產途程定義的操作不同。

> [!NOTE]
> 儘管您可以追蹤成本、時間和在與不符合項相關的操作中使用的品項，但您輸入的資料僅供參考。 這些資料不會與總帳、庫存子分類帳或 **時間及出勤** 模組自動整合。

## <a name="examples-of-operations"></a>操作示例

您在一家製造公司工作。 為未通過品質測試的品項建立及核准不符合項。 已建立更正以表明該問題與機器上的軸承損壞有關。 更換軸承需要幾個步驟，並追蹤每個操作的責任。 例如，可能需要執行以下步驟：

1. 生產線停止，並執行清理程序。
1. 維修人員更換軸承。
1. 品質保證人員在機器重新啟動前對其進行檢查。

對於此示例，可以建立以下操作來表示必須完成的工作：

- 停止生產線。
- 清理生產線。
- 進行機器維修。
- 檢查機器。

## <a name="create-an-operation"></a>建立操作

1. 移至 **庫存管理 \> 設定 \> 品質管理 \> 操作**。
1. 在動作窗格上選取 **新增**，將資料列新增至格線。 接著，在新的一列上，設定以下欄位：

    - **操作** – 輸入操作的不重複識別碼或名稱。
    - **說明** – 輸入操作的詳細說明。
    - **類型** – 如果操作只能用於與特定訂單類型相關的不符合項，請選擇訂單類型 (*訂購單* 或 *銷售訂單*)。

1. 關閉頁面。

## <a name="additional-resources"></a>其他資源

- [品質管理概觀](quality-management-processes.md)
- [啟用品質和不符合項管理](enable-quality-management.md)
- [建立和處理不符合項](tasks/create-process-non-conformance.md)
- [負責核准不符合項的工作人員](quality-responsible-workers.md)
- [不符合項隔離區](quality-quarantine-zones.md)
- [不符合項的診斷類型](quality-diagnostic-types.md)
- [不符合項的品質收費](quality-charges.md)
- [不符合項的問題類型](quality-operations.md)
- [倉庫流程的品質管理](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
