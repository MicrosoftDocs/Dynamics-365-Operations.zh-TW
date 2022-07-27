---
title: 入庫和出庫資產
description: 本主題說明如何在資產管理中註冊入庫和出庫資產。
author: johanhoffmann
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetOutboundObjectsListPage, EntAssetOutboundObjectsDeliver, EntAssetInboundObjectsListPage, EntAssetInboundObjectsRecieve
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 0bd3127df1b583acc6841c3e115d3beceabcab2756098e567b2269c1dcc94004
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447108"
---
# <a name="inbound-and-outbound-assets"></a>入庫和出庫資產

[!include [banner](../../includes/banner.md)]

 

如果貴公司對從其他位置或客戶收到的資產進行維修或維護工作，資產管理可以追蹤正運往貴公司的入庫資產和退回的出庫資產。

> [!NOTE]
> 如果要使用入庫和出庫生命週期狀態來管理進出的資產，則必須設定維護請求生命週期狀態和生命週期模型以支援這些動作。 如需詳細資訊，請參閱[維護要求](../setup-for-maintenance-requests/requests.md)。

資產管理的設定決定了您是否可以使用入庫和出庫資產。

## <a name="register-assets-as-inbound"></a>將資產註冊為入庫

1. 選擇 **資產管理** \> **通用** \> **維護要求** \> **使用中維護要求**。
2. 選擇維護要求。
3. 選擇 **更新維護要求狀態**。
4. 選擇 **入庫** (或您為入庫資產建立的另一個生命週期狀態)，然後選擇 **確定**。

![將資產註冊為入庫。](media/07-manage-maintenance-requests.png)

## <a name="register-inbound-assets-as-received"></a>將入庫資產註冊為已收到

1. 選擇 **資產管理** \> **通用** \> **入庫/出庫** \> **入庫資產**。
2. 選擇資產或維護要求。
3. 選擇 **接收資產**。
4. 在 **已收到** 欄位輸入日期和時間。 然後選擇 **確定**。 該記錄已從 **入庫資產** 清單頁面移除。

![將入庫資產註冊為已收到。](media/08-manage-maintenance-requests.png)

## <a name="register-assets-as-outbound"></a>將資產註冊為出庫

完成維護或維修工作後，您可以將資產註冊為已退回。

1. 選擇 **資產管理** \> **通用** \> **維護要求** \> **使用中維護要求**。
2. 選擇維護要求。
3. 選擇 **更新維護要求狀態**。
4. 選擇 **出庫** (或您為出庫資產建立的另一個生命週期狀態)，然後選擇 **確定**。

## <a name="register-outbound-assets-as-delivered"></a>將出庫資產註冊為已交貨

1. 選擇 **資產管理** \> **通用** \> **入庫/出庫** \> **出庫資產**。
2. 選擇資產或維護要求。
3. 選擇 **交貨資產**。
4. 在 **已交貨** 欄位輸入日期和時間。 然後選擇 **確定**。 該記錄已從 **出庫資產** 清單頁面移除。


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]