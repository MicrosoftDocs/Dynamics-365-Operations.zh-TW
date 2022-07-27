---
title: 不符合項隔離區
description: 本主題說明如何建立和使用不符合項的隔離區。
author: yufeihuang
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventQuarantineZone
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 207950a2ff4057853488f75d0e302a049d228b76
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449115"
---
# <a name="quarantine-zones-for-nonconformances"></a>不符合項隔離區

[!include [banner](../includes/banner.md)]

本主題說明如何建立和使用不符合項的隔離區。

您使用 **隔離區** 頁面來定義可以指派給不符合項的區域。 建立不符合項時，您可以在 **不符合項** 頁面的 **一般** 索引標籤設定 **隔離區** 和 **隔離類型** 欄位。 **隔離區** 欄位通常表示品項所在的區域或位置。 **隔離類型** 欄位將品項定義為 *限制使用* 或 *無法使用*。

當您為不符合項列印不符合項或更正報告時，您可以查看品項所在的隔離區。

您也可以為不符合項列印不符合標籤。 此報告顯示指派的隔離區和有關使用情況的資訊，以提供有關缺陷材料處置方式的指導。 隔離區可能對應於庫存位置或營運資源。

## <a name="examples-of-quarantine-zones"></a>隔離區示例

### <a name="example-1"></a>示例 1

您在一家生產和分銷電視、揚聲器和媒體播放器的電子製造公司工作。 在此案例中，您可以設定一個隔離區來代表每種產品。

### <a name="example-2"></a>示例 2

三個間隔和兩個貨架用於存放不符合的品項。 在此案例中，您可以設定五個隔離區，每個間隔和貨架各設定一個。

## <a name="create-a-quarantine-zone"></a>建立隔離區

1. 移至 **庫存管理 \> 設定 \> 品質管理 \> 隔離區**。
1. 在動作窗格上選取 **新增**，將資料列新增至格線。 接著，在新的一列上，設定以下欄位：

    - **隔離區** – 輸入隔離區的不重複識別碼或名稱。
    - **說明** – 輸入隔離區的詳細說明。

1. 關閉頁面。

## <a name="additional-resources"></a>其他資源

- [品質管理概觀](quality-management-processes.md)
- [啟用品質和不符合項管理](enable-quality-management.md)
- [負責核准不符合項的工作人員](quality-responsible-workers.md)
- [不符合項的問題類型](quality-quarantine-zones.md)
- [不符合項的診斷類型](quality-diagnostic-types.md)
- [不符合項的品質收費](quality-charges.md)
- [不符合項操作](quality-operations.md)
- [倉庫流程的品質管理](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
