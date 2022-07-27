---
title: 不符合項的問題類型
description: 本主題說明如何建立和使用不符合項的問題類型。
author: yufeihuang
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventProblemType, InventProblemTypeSetup
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 26705dd12f478f4ca6046c7265d4ae3cb1d08c69
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448149"
---
# <a name="problem-types-for-nonconformances"></a>不符合項的問題類型

[!include [banner](../includes/banner.md)]

本主題說明如何建立和使用不符合項的問題類型。

您可以使用 **問題類型** 頁面來定義及分類各種不符合類型可能出現的品質問題。 對於您建立的每種問題類型，您必須指定該問題類型適用的不符合項類型。 您可以設定以下不符合類型：

- **內部** – 此類型的不符合項與現有庫存相關 (例如，品質檢驗訂單或檢疫訂單)。
- **客戶** – 此類型的不符合項與銷售訂單有關。
- **廠商** – 此類型的不符合項與訂購單有關。
- **服務要求** – 此類型的不符合項與服務訂單有關。
- **生產** – 此類型的不符合項與批次訂單或生產訂單有關。
- **副產品生產** – 此類型的不符合項與副產品的批次訂單有關。

建立新問題類型時，請在動作窗格上選擇 **不符合類型** 以建立一份清單，其中列出了一或多種已針對問題類型授權的不符合類型。 例如，與缺陷代碼相關的問題類型可能適用於所有不符合類型。 但是，與客戶申訴相關的問題類型可能僅適用於 **客戶** 和 **服務要求** 不符合類型。

## <a name="examples-of-problem-types"></a>問題類型示例

以下示例提供適用於不同不符合類型的問題類型情境：

- **客戶：** 客戶提出申訴、客戶退貨或不符合品質規格。
- **廠商：** 產品損壞，不符合品質規格，或收到錯誤的產品。
- **服務要求：** 未符合品質規格、客戶提出申訴或需要進行機器維護。
- **生產：** 不符合品質規格，需要機器維護，或產品損壞。
- **副產品生產：** 不符合品質規格，需要機器維護，或產品損壞。

## <a name="create-a-problem-type-and-assign-it-to-nonconformance-types"></a>建立問題類型並將其指派給不合格類型

1. 移至 **庫存管理 \> 設定 \> 品質管理 \> 問題類型**。
1. 在動作窗格上選取 **新增**，將資料列新增至格線。 接著，在新的一列上，設定以下欄位：

    - **問題類型** – 輸入問題類型的不重複識別碼或名稱。
    - **說明** – 輸入問題類型的詳細說明。

1. 在新列仍處於選取狀態時，在動作窗格上選擇 **不符合類型**。
1. 在動作窗格上選取 **新增**，將資料列新增至格線。 然後，針對新列，將 **不符合類型** 欄位設定為您要允許用於問題類型的不符合類型。
1. 對您要為問題類型授權的每個其他不符合類型，重複上一步驟。
1. 關閉頁面。

## <a name="additional-resources"></a>其他資源

- [品質管理概觀](quality-management-processes.md)
- [啟用品質和不符合項管理](enable-quality-management.md)
- [負責核准不符合項的工作人員](quality-responsible-workers.md)
- [不符合項隔離區](quality-quarantine-zones.md)
- [不符合項的診斷類型](quality-diagnostic-types.md)
- [不符合項的品質收費](quality-charges.md)
- [不符合項操作](quality-operations.md)
- [倉庫流程的品質管理](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
