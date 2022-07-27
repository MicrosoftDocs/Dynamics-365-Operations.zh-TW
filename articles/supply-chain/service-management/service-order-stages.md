---
title: 服務訂單階段
description: 透過定義服務訂單的階段並將其指派給工作人員，您可以透過服務組織中不同人員執行的工作來控制服務訂單的流程。
author: kamaybac
ms.date: 04/30/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceOrderTable, SMAStageTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0a43cbe0cf5993a305ff500f34f0da5d3763084c
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448896"
---
# <a name="service-order-stages"></a>服務訂單階段   

[!include [banner](../includes/banner.md)]


您可以為服務訂單設定階段，以定義必須完成的工作、完成的順序以及負責完成這些工作的工作人員。 透過定義服務訂單的階段並將其指派給工作人員，您可以透過服務組織中不同人員執行的工作來控制服務訂單的流程。 階段序列必須包括初始階段。

您還可以定義在每個階段允許的動作。 例如，如果您清除所有階段 (除最後階段之外) 的 **過帳** 核取方塊，您可以防止過帳尚未經過完整階段序列處理的任何服務訂單。

## <a name="branching-in-service-order-stages"></a>服務訂單階段的分支

設定服務階段時，您可以建立多個選項或分支，以供下一個服務階段進行選擇。 初始階段完成後，您建立的所有分支都可選擇。 例如，您設定 **計劃** 作為初始階段。 建立名為 **進行中** 和 **取消** 的兩個階段，然後選擇 **計劃** 做為其上層階段。 將 **計劃** 階段指派到銷售訂單。 在完成銷售訂單的計劃階段後，如果銷售訂單已準備就緒，可以選擇 **進行中** 階段，如果銷售訂單已取消，則可以選擇 **取消** 階段。

## <a name="see-also"></a>另請參閱

[設定服務訂單階段](set-up-service-order-stages.md)

[變更服務訂單階段](change-service-order-stage.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]