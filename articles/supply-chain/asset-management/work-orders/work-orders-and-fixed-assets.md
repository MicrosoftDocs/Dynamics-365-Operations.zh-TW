---
title: 工單和固定資產
description: 本主題說明資產管理中的工單和固定資產。
author: johanhoffmann
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: ad4af6bb0df557314f844d3e7a6c5fb84a6331d86f16e1bc76150f78ce3039e4
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447030"
---
# <a name="work-orders-and-fixed-assets"></a>工單和固定資產

[!include [banner](../../includes/banner.md)]


在資產管理中，資產可以與固定資產相關聯，您可以為這些資產建立工單。 如果使用此功能，您可以在 Microsoft Dynamics 365 for Finance and Operations 的 **專案管理和核算** 和 **固定資產** 模組中，取得全面在投資專案中登記的固定資產、相關投資專案以及成本的完整概觀。

>[!NOTE]
>僅當選擇 **投資** 作為工單作業專案的專案類型時，才會設定工單作業專案的 **固定資產編號** 欄位。

下圖顯示 **專案管理與核算** 模組中的投資專案與工單作業專案之間的關係。

![圖 1。](media/24-work-orders.png)

以下程序描述資產、工單、工單作業專案和固定資產之間的關係。

1. 您將建立與固定資產相關的資產。

![圖 2。](media/25-work-orders.png)

2. 在 **工單類型** 頁面設定工單類型 (**資產管理** > **設定** > **工單** > **工單類型**) 時，將建立工單類型來處理投資。 另請參閱[工單類型](../setup-for-work-orders/work-order-types.md)。

![圖 3。](media/26-work-orders.png)

3. 在 **工單專案設定** 頁面的 **專案群組** 索引標籤上設定工單專案群組 (**資產管理** > **設定** > **工單** > **專案設定**) 時，將在 **專案管理與核算** 模組中 **專案群組** 頁面上在用於投資的工單類型與為投資建立的專案群組之間建立關係 (**專案管理與核算** > **設定** > **過帳** > **專案群組**)。

![圖 4。](media/27-work-orders.png)

4. 建立與固定資產相關的工單時，請選擇用於處理投資的工單類型，例如 **投資**。

5. 建立工單後，將在在 **所有工單** 頁面顯示相關工單類型。

![圖 5。](media/28-work-orders.png)

6. 建立工單後，將在 **專案管理和核算** 模組中的 **所有專案** 頁面建立與工單相關的專案 (**專案管理和核算** > **專案** > **所有專案**)。 若要查看專案相關資訊，請在 **資產管理** 模組中 **所有工單** 頁面的詳細資料檢視表中，在 **行明細** 快速索引標籤上的 **一般** 索引標籤上，在 **專案識別碼** 欄位選擇連結 (**資產管理** > **通用** > **工單** > **所有工單**) 。

![圖 6。](media/29-work-orders.png)

7. 要查看與固定資產相關的專案概覽，請選擇 **固定資產** > **固定資產** > **固定資產**，然後，在 **固定資產編號** 欄位，選擇固定資產的連結以打開詳細資訊檢視表。 展開頁面右側的 **相關資訊** 窗格，然後選擇 **相關專案** 快速索引標籤。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]