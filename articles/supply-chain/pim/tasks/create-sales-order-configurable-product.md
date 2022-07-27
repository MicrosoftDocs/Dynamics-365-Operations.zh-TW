---
title: 為可設定產品建立銷售訂單
description: 此程序說明如何將設定範本套用至銷售訂單上的產品。
author: t-benebo
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, SalesOrderProcessingWorkspace, SalesCreateOrder, SalesTable, PCRuntimeConfigurator, PCTemplateConfigurationSelection
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e42f121d1efa66f85a3dd811606962b907ed177d
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448323"
---
# <a name="create-a-sales-order-for-a-configurable-product"></a>為可設定產品建立銷售訂單

[!include [banner](../../includes/banner.md)]

此程序說明如何將設定範本套用至銷售訂單上的產品。 本範例使用 USMF 示範資料公司的 D0006 喇叭型號。 通常，銷售訂單處理器會使用此過程。

## <a name="create-a-sales-order"></a>建立銷售訂單

1. 前往 **銷售和營銷 \> 工作區 \> 銷售訂單處理和查詢**。
1. 選擇 **新增**。
1. 選擇 **銷售訂單**。
1. 在 **客戶帳戶** 欄位中選擇 *US-001*。 
1. 選擇 **確定**。
1. 在 **項目編號** 欄位中選擇 *D0006*。
    * 對於此工作，您必須選擇可設定產品。  
1. 選擇 **產品和供應**。
1. 選擇 **設定行**。
    * 請注意該價格已根據所選設定發生變更，並且 **包括纜線** 欄位現在已設為 *真*。  
    * 請注意為纜線選擇的預設價格和設定。  
1. 選擇 **載入範本**。
    * 此範例說明如何套用範本來選擇預先定義的設定。 如果您將此程序用作工作指南，並希望查看其他可用的屬性值，則必須選擇 **解除鎖定** 按鈕。  
1. 選擇 **確定**。
1. 選擇 **確定**。
1. 展開 **行詳細資訊** 區段。
1. 選擇 **產品** 索引標籤。
    * 該項目的設定現在列在產品尺寸下方。  
1. 關閉頁面。


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]