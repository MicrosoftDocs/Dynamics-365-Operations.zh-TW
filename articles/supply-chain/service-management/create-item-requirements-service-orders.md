---
title: 為服務訂單創建項目需求
description: 本主題介紹如何為服務訂單創建項目需求。
author: kamaybac
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 75a05147883f1592b3a09e02e238661f6c20cf27
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448806"
---
# <a name="create-item-requirements-for-service-orders"></a>為服務訂單創建項目需求

[!include [banner](../includes/banner.md)]

您可以創建服務訂單，來追蹤和管理提供給客戶的服務。 如果您需要為服務訂單預留特定項目，您可以為其創建庫存項目需求。 項目需求可以從庫存中立即消耗，也可以為項目啟動生產訂單。

通過使用項目需求而不是項目交易，您可以在項目實際使用之前計劃交貨，創建採購訂單，將項目包括在貿易合約框架中，並將項目要求包括在生產計劃中。

服務訂單的項目需求通過專案處理。 若要在服務訂單上創建項目需求，必須將服務訂單指派至專案。 為服務訂單創建項目需求後，您可以在所選的 **專案** 表單中檢視項目需求。

## <a name="create-an-item-requirement-for-a-service-order"></a>為服務訂單創建項目需求

1. 前往 **服務管理** \> **一般** \> **服務訂單** \> **服務訂單**。
1. 選擇您要為其創建項目需求的服務訂單。
1. 在 **動作窗格** 上的 **分派** 索引標籤，選擇 **項目需求**。
1. 在 **項目需求** 表格中，輸入項目所需的信息。 有關特定欄位的更多信息，請參閱[項目需求 (表單)](https://technet.microsoft.com/library/aa552021\(v=ax.60\))。

## <a name="create-an-item-requirement-for-a-service-agreement"></a>為服務合約創建項目需求

1. 前往 **服務管理** \> **一般** \> **服務合約** \> **服務合約**。
1. 打開您要為其創建項目需求的服務合約。
1. 在 **行** FastTab，選擇 **新增** 來創建新的一行。
1. 請在 **交易類型** 欄位，選擇 **項目**。
1. 在 **項目設定** 欄位中，選擇 **項目需求**。
1. 在 **項目編號** 欄位中，選擇服務合約所需的項目。
1. 在 **行詳細資料** FastTab 的 **產品尺寸** 索引標籤上，從 **地點** 欄位選擇項目的庫存地點。
1. 若要從合約行創建服務訂單，請在 **行** FastTab，選擇 **創建服務訂單**，然後在 **創建服務訂單** 輸入表單相關的資訊。

## <a name="see-also"></a>另請參閱

[自動建立服務訂單](create-service-orders-automatically.md)。

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
