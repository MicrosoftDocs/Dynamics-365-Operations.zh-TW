---
title: 排程工作負載產能
description: 本主題說明如何為倉庫的工作人員或整個倉庫設定和排程工作負載產能。
author: Mirzaab
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WMSWorkloadCapacity
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f66eb1b2f35d19aba0f4f8f2804577a62ac14e79
ms.sourcegitcommit: fd6270dc7f49f93a8155d2b827153b13edb7be8a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/09/2021
ms.locfileid: "8449514"
---
# <a name="schedule-workload-capacity"></a>排程工作負載產能

[!include[banner](../includes/banner.md)]

您可以排程倉庫的工作負載產能，也可以為各個倉庫中的工作人員預測目前和未來的工作負載。 您可以計劃整個倉庫的工作負載，也可以為進貨和出貨工作負載分別計劃工作負載。

若要預測所選倉庫的工作負載輸出，這些倉庫必須有可用的總排程資料。 更多資訊，請參閱[主計劃概觀](../master-planning/master-plans.md)。

## <a name="schedule-and-view-workloads-for-a-warehouse"></a>排程和查看倉庫的工作負載

要排程倉庫的工作負載產能，您需要為一個或多個倉庫建立工作負載設定，然後將工作負載設定與主計劃相關聯。 在工作負載產能設定中，您可以定義進貨和出貨交易的重量或體積限制。 您還可以為每個倉庫建立多個設定，然後將設定與各個主計劃相關聯。 例如，您可以使用這種方法來應對勞動力的季節性變化。

如果倉庫的工作人員處理進貨和出貨工作負載的交易，您可以配置倉庫產能設定，以便在合併檢視表中計劃工作負載。

要排程和查看倉庫的工作負載，您必須完成以下任務：

1. 建立工作負載產能設定並為一個或多個倉庫定義工作負載產能限制。
2. 將工作負載產能設定與主計劃相關聯，以建立工作負載預測並指定這些預測的適用時長。

### <a name="create-a-workload-capacity-setup-for-a-warehouse"></a>建立倉庫的工作負載產能設定

1. 選擇 **庫存管理** \> **設定** \> **倉庫監視** \> **工作負載產能**。
2. 在動作窗格上，選擇 **新增** 建立工作負載產能設定。
3. 在 **倉庫** FastTab 卡上選取 **新增**，然後在該行中輸入值以將倉庫與工作負載產能設定相關聯。
4. 如果 **工作負載產能** 報表應在一個檢視表中顯示進貨和出貨交易的總工作負載，請選擇 **合併入庫和出庫工作負載** 核取方塊。
5. 在 **交易類型** FastTab 上，選擇將套用工作負載限制的進貨和出貨交易的類型。

    > [!NOTE]
    > 您必須為進貨工作負載和出貨工作負載選擇至少一個交易類型。

#### <a name="define-limits-for-volume-or-weight"></a>定義體積或重量的限制

您可以設定體積或重量限制，具體取決於與倉庫勞動力相關的限制。 您指定的限制包含在您可以在 **工作負載能力** 報表中查看的工作負載產能預測中。

若要預測有關品項體積和重量的資訊，必須為所有產品指定一個庫存品項的標準體積和一個庫存品項的重量。 **已發布產品詳情** 頁面 **管理庫存** FastTab 上的以下欄位群組中提供必填欄位：

- 正在處理
- 物理維度
- 重量測量

如果未正確指定此資訊，則在產生 **工作負載產能** 報表時，將收到訊息。 然後，您可以從報表中向下切入以確定預測未來工作負載所需的缺失資訊。

### <a name="associate-a-workload-capacity-setup-with-a-master-plan"></a>將工作負載產能設定與主計劃相關聯

1. 選擇 **庫存管理** \> **定期** \> **排程工作負載**。
2. 在 **主計劃** 欄位中，選擇用於工作負載預測的主計劃。
3. 在 **天數** 欄位中，指定工作負載預測涵蓋的天數。
4. 在 **工作負載** 欄位中，選擇要與主計劃關聯的工作負載設定。

### <a name="view-workload-capacity"></a>查看工作負載產能

1. 選擇 **庫存管理** \> **查詢和報表** \> **實際庫存報告** \> **工作負載產能**。
2. 在 **行數** 欄位中，指定要在報表中顯示的行數。
3. 在 **訂單類型** 欄位中，選擇 **已計劃並確認**、**已計劃** 或 **已確認**，以指示要在報表上預測的訂單類型。
4. 在 **負載類型** 欄位中，選擇負載類型以指定是否應根據體積或重量預測工作負載產能。
5. 在 **工作負載產能** 欄位中，選擇工作負載產能設定。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]