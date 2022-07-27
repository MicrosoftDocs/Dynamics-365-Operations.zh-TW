---
title: 計算排程工單的產能負載
description: 本主題說明如何在資產管理中計算排程工單的產能負載。
author: johanhoffmann
ms.date: 08/19/2019
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
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: ff244e51151a1cc0485cae25873566fa97253171516d48449fed75f070146431
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447168"
---
# <a name="calculate-capacity-load-on-scheduled-work-orders"></a>計算排程工單的產能負載

[!include [banner](../../includes/banner.md)]

 

您可以計算排程工作訂單的產能負載，以了解特定期間資源的工作負載摘要。 可以對以下資源進行計算：維護工作人員、工作人員群組、工具和資產。

1. 按一下 **資產管理** > **查詢** > **排程** > **產能負載**。

2. 在 **計算產能負載** 對話方塊 > **顯示** 欄位，選取您要計算的負載類型：**產能**、**保留**，或 **剩餘數量**。

3. 如果您不想顯示包含零的結果，在 **跳過零** 切換按鈕上選取 **是的**。

4. 選取要為其計算容量負載的資源類型，請到相關的切換按鈕上：**工人**、**維修工人組**、**工具**，和 **資產**，選取 **是的**。

5. 在 **起始日期** 欄位，選取計算的開始日期。

6. 在 **間隔類型** 欄位，選擇計算的間隔：**日**、**星期**、**月**，或 **季度**。

7. 在 **週期頻率** 字段，插入要計算的間隔數。 例如，如果您選擇了 **日** 作為間隔類型，並且您在此欄位中輸入數字“5”，將從開始日期開始計算五天。

8. 按一下 **確定** 以開始計算。

下圖顯示三週的負載類型計算結果 **保留**。

![圖 1。](media/08-work-order-scheduling.png)

[!NOTE]
如果您在計算選取負載類型為 **產能** 或 **剩餘數量**，如果在選定時間段內沒有為資源進行保留，則將顯示相同的結果。

有關如何計算維護排程明細及非排程工單的產能負載的資訊，請參閱[計算產能負載](../capacity-planning/calculate-capacity-load.md)。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]