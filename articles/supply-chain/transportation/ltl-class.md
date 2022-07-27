---
title: 零載量 (LTL) 類別
description: 本主題說明何謂零載量 (LTL) 類別，並介紹如何在 Microsoft Dynamics 365 Supply Chain Management 中進行設定。
author: Henrikan
ms.date: 04/05/2021
ms.topic: article
ms.search.form: WHSLTLClass
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-04-05
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 4349e649e48e5103a53a5e6ab332d127fd1de27aa7b06953533198d3928d250a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447342"
---
# <a name="less-than-truckload-ltl-classes"></a>零載量 (LTL) 類別

[!include [banner](../includes/banner.md)]

零載量 (LTL) 類別是一種貨運類別，用於對可運輸的品項進行分類。 一般來說，每種類型的產品或商品都有一個美國國家汽車貨運分類 (NMFC) 代碼，該代碼對應於 LTL 裝運的特定貨運類別編號。 LTL 貨運分類代表物品的類別，而 NMFC 代碼會與 18 個貨運分類裡的每一個分類中的特定商品相關。

此功能允許您使用系統執行以下工作：

- 定義貴公司使用的 LTL 貨運分類。
- 在 **NMFC 代碼** 頁面上，將每個 LTL 類別指派給一個 NMFC 代碼。 如需詳細資訊，請參閱[美國國家汽車貨運分類 (NMFC) 代碼](nmfc-codes.md)。
- 為 **產品** 頁面上的每個產品指派一個 NMFC 代碼 (因此它是相關的 LTL 代碼)。
- 準確評估已指派 NMFC 代碼的每個產品的 LTL 類別。
- 透過檢查國際 LTL 標準來判斷每個 LTL 類別的揀貨要求。 透過這種方式，您可以確保您的產品得到妥善保護並安全運輸。
- 根據每種產品的 LTL 貨運分級取得準確的運送估算。

本主題介紹如何在 Microsoft Dynamics 365 Supply Chain Management 中建立 LTL 類別。

## <a name="create-an-ltl-class"></a>建立 LTL 類別

若要建立 LTL 類別，請按照以下步驟。

1. 請執行以下其中一個步驟：

    - 前往 **倉庫管理 \> 設定 \> 庫存 \> LTL 類別**。
    - 移至 **運輸管理 \> 設定 \> 運輸標準 \> LTL 類別**。

2. 在動作窗格上，選擇 **新增** 以建立 LTL 類別。 然後設定以下欄位：

    - **LTL 類別** – 為商品類型輸入貴公司的內部 LTL 類別識別碼 (ID)。 大多數公司使用國際標準。 在這種情況下，此欄位的值將與 **類別** 欄位的值相符。 但是，如果您的公司使用自己的標準，請輸入符合該標準的代碼。
    - **名稱** – 輸入有助於您和其他使用者為每個 NMFC 代碼選擇正確 LTL 類別的描述性名稱。
    - **類別** – 輸入商品類型的國際標準 LTL 類別識別碼。 您在此處輸入的代碼必須符合官方標準。

## <a name="example-set-up-ltl-classes"></a>範例：設定 LTL 類別

以下範例顯示如何設定兩個您可用於不同類型產品的不同 LTL 類別。

1. 前往 **倉庫管理 \> 設定 \> 庫存 \> LTL 類別**。
1. 在動作窗格上，選擇 **新增**。
1. 在新的明細上，設定以下值：

    - **LTL 類別：** *92.5*
    - **名稱：** *電腦、顯示器、冰箱*
    - **類別：** *92.5*

1. 在動作窗格上，選擇 **儲存**。
1. 在動作窗格上，選擇 **新增**。
1. 在新的明細上，設定以下值：

    - **LTL 類別：** *125*
    - **名稱：** *小家電*
    - **類別：** *125*

1. 在動作窗格上，選擇 **儲存**。

## <a name="additional-resources"></a>其他資源

- [美國國家汽車貨運分類 (NMFC) 代碼](nmfc-codes.md)
- [建立提單](create-bill-of-lading.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
