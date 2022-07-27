---
title: 不符合項操作的費用
description: 本主題說明如何建立品質費用，以用於不符合項的操作。
author: yufeihuang
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestMiscCharges
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ac3306f3f9215ab03f408b8026f335dcf496515a
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449370"
---
# <a name="charges-for-nonconformance-operations"></a>不符合項操作的費用

[!include [banner](../includes/banner.md)]

本主題說明如何建立品質費用，以用於不符合項的操作。

您使用 **品質費用** 頁面來定義可以新增到不符合項操作的費用類型。 費用可讓您追蹤有關您因不符合項產品而積欠客戶的費用或收費；或是廠商因您收到的不符合項產品而積欠您的費用或收費的詳細資料。 您也可以使用費用來追蹤外部廠商或服務執行操作所需的成本。

## <a name="examples-of-quality-charges"></a>品質費用示例

您在一家製造公司工作。 貴公司與多家廠商簽訂了契約。 這些契約概述了品項的準時裝運時間、損壞和產品品質標準。 同樣，您的一些客戶與您的公司就退貨、損壞和產品品質達成了協議。

針對每種情況定義了費用結構並在契約中指定。 您可以設定品質費用以概述各種類型的費用，例如 *損害賠償*、*延遲發貨* 和 *品質*。 然後，當您建立不符合項時，您會新增一或多項操作。 對於每個操作，您選擇 **費用** 以定義有關費用的詳細資料。

## <a name="create-a-quality-charge"></a>建立品質費用

1. 移至 **庫存管理 \> 設定 \> 品質管理 \> 品質費用**。
1. 在動作窗格上選取 **新增**，將資料列新增至格線。 接著，在新的一列上，設定以下欄位：

    - **費用代碼** – 輸入品質費用的不重複識別碼或名稱。
    - **說明** – 輸入品質費用的詳細說明。

1. 關閉頁面。

## <a name="add-a-quality-charge-to-an-operation-for-a-nonconformance"></a>將品質費用新增到不符合項的操作中

有關如何將操作新增到不符合項並對其計費的詳細資料，請參閱[不符合項操作](quality-operations.md)。

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
