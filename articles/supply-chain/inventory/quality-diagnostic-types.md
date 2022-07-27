---
title: 不符合項的診斷類型
description: 本主題介紹如何使用和建立可用於不符合項的診斷類型。
author: yufeihuang
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestDiagnosticType, InventTestCorrection
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: edaa3a8b5c6446f039f33589166d832dcd9d0b9a
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449367"
---
# <a name="diagnostic-types-for-nonconformances"></a>不符合項的診斷類型

[!include [banner](../includes/banner.md)]

本主題介紹如何使用和建立可用於不符合項的診斷類型。

您可以使用 **診斷類型** 頁面來定義診斷操作的類別。 然後，當您為不符合項建立更正時，您可以選擇診斷。 更正指定應針對已核准的不符合項採取何種類型的診斷措施，以及應由誰採取該措施。 其也指定要求的完成日期和計劃完成日期。

## <a name="examples-of-diagnostic-types"></a>診斷類型示例

您在一家製造公司工作，有幾個品項未通過品質測試。 這些品項轉移到隔離區並標記為不符合項。 在 Microsoft Dynamics 365 Supply Chain Management 中建立了不符合項記錄，以透過問題解決方法來追蹤詳細資料。

在這種情況下，因為包裝品項的機器軸承損壞而且過熱，導致發生品質問題。 此問題的解決方法是更換機器中的零件。

設定診斷類型時，您可以建立多筆記錄，每筆記錄代表機器可能遇到的不同類型的問題。 或者，您可以建立一種表示機器維修的通用診斷類型。

## <a name="create-a-diagnostic-type"></a>建立新的診斷類型

1. 移至 **庫存管理 \> 設定 \> 品質管理 \> 診斷類型**。
1. 在動作窗格上選取 **新增**，將資料列新增至格線。 接著，在新的一列上，設定以下欄位：

    - **診斷** – 輸入診斷類型的不重複識別碼或名稱。
    - **說明** – 輸入診斷類型的詳細說明。

1. 關閉頁面。

## <a name="additional-resources"></a>其他資源

- [品質管理概觀](quality-management-processes.md)
- [啟用品質和不符合項管理](enable-quality-management.md)
- [負責核准不符合項的工作人員](quality-responsible-workers.md)
- [不符合項隔離區](quality-quarantine-zones.md)
- [不符合項的問題類型](quality-problem-types.md)
- [不符合項的品質收費](quality-charges.md)
- [不符合項操作](quality-operations.md)
- [倉庫流程的品質管理](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
