---
title: 服務訂單
description: 本主題概述了如何使用服務訂單。
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
ms.openlocfilehash: 8dc88d445e1331e1532cb3b7385cda39c4f22e80
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8447885"
---
# <a name="service-orders"></a>服務訂單

[!include [banner](../includes/banner.md)]

服務訂單代表服務技術人員在特定日期造訪客戶站點。 每個服務訂單都由一個或多個服務訂單行組成。 服務訂單行代表服務技術人員必須執行的工作時間，以及相關的品項、支出和費用。

您可以將工作和物件附加到服務訂單行。 然後，您可以按工作或按物件對服務訂單行進行分組。 您還可以將庫存中列出的品項附加到服務訂單行。

## <a name="create-service-orders"></a>建立服務訂單

您可以根據服務合約和該合約中包含的行建立服務訂單。 但是，您只能在合約中指定的期間建立與服務合約關聯的服務訂單。 例如，如果服務合約在 2011 日曆年有效，您可以為從 2011 年 1 月 1 日到 2011 年 12 月 31 日的合約建立服務訂單。

您還可以單獨建立服務訂單，而無需將它們與合約相關聯。 這些服務訂單可用於處理排程外或一次性登門服務。 例如，在 3 月份，您的客戶決定對服務合約中指定的機器之外的兩台機器執行服務。 對於此工作，您會建立服務訂單但不將其與合約相關聯。


> [!NOTE]
> 若要建立不與服務合約關聯的服務訂單，您必須選擇 **服務管理參數** 頁面中的 **允許，但沒有服務合約** 核取方塊。

### <a name="scenario"></a>案例

以下場景描述了另一種情況，在這種情況下建立與服務合約無關的服務訂單會很實用。

公司分派員接到一通電話，要求對電梯進行緊急服務。 沒時間為服務設定服務合約和專案。 因此，分派員直接在 **服務訂單** 頁面，將服務訂單附加到現有品項，並建立服務訂單行。 分派員還為現有服務訂單建立工作或物件關係，以記錄與服務合約無關的工作。 有關詳細資訊，請參閱[手動建立服務訂單](create-service-orders-manually.md)和[建立服務工作關係](create-service-task-relations.md)。

## <a name="monitor-the-progress-of-service-orders"></a>監視服務訂單的進度

若要透過不同的團隊和工作流程監視銷售訂單的進度，您可以為服務訂單設定階段和原因代碼系統。 對於每個階段，您可以指定允許的動作。 如需詳細資訊，請參閱[建立原因代碼](create-reason-codes.md)。

### <a name="example"></a>範例

服務訂單由分派員核准。 分派員會更新服務訂單的階段並指定指示服務訂單已下達給服務技術人員的原因代碼。 技術人員前往客戶站點並執行服務。

## <a name="specify-item-requirements-for-service-orders"></a>為服務訂單指定項目要求

您可以指定服務訂單所需的庫存品項。 但是，服務訂單必須與專案相關聯。 服務訂單的項目需求通過專案處理。 

### <a name="example"></a>範例

根據服務合約建立的服務訂單由分派員處理。 對於第一個服務訂單，分派員意識到服務技術人員需要一個不在現有庫存中的重要備件。 因此，分派員直接從服務訂單建立備件的品項要求。

## <a name="move-and-post-lines"></a>移動和過帳行

服務技術人員從登門服務返回，然後修改和更新服務訂單行。 在登門服務期間，技術人員執行了計劃在下一次登門服務執行的服務工作。 因此，技術人員將行從後續登門服務移動到目前登門服務。 然後，技術人員過帳服務訂單。 更多詳細資訊，請參閱[移動服務訂單行](move-service-order-lines.md)。

## <a name="cancel-service-orders"></a>取消服務訂單

為 1 月份產生的其他服務訂單之一已淘汰，因為該作業已取消。 因此，服務分派員取消服務訂單。 更多詳細資訊，請參閱[取消服務訂單](cancel-service-orders.md)。

## <a name="post-from-projects"></a>從專案過帳

在每週結束時，分派員會需要過帳附加到特定專案的所有服務訂單。 因此，分派員會將相關專案置於 **專案** 頁面，並過帳已完成的服務訂單。 更多詳細資訊，請參閱[過帳建立服務訂單 (類別表單)](https://technet.microsoft.com/library/aa574685\(v=ax.60\))。

## <a name="delete-service-orders"></a>刪除服務訂單

在下半年，您的客戶認為登門服務太少。 您必須為服務合約的剩餘時間建立一系列更頻繁的新登門服務。 因此，您必須刪除現有的服務訂單並建立新的服務訂單。 更多詳細資訊，請參閱[刪除服務訂單](delete-service-orders.md)。

## <a name="see-also"></a>另請參閱

[服務訂單 (表單)](https://technet.microsoft.com/library/aa554361\(v=ax.60\))

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]