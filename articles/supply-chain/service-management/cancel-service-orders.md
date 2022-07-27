---
title: 取消服務訂單
description: 您可以從該服務訂單本身取消服務訂單或服務訂單明細，也可以執行定期作業來取消多個服務訂單。
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
ms.openlocfilehash: cca6c34bb43702e2c33935a73dc24f1a630065c0
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448428"
---
# <a name="cancel-service-orders"></a>取消服務訂單   

[!include [banner](../includes/banner.md)]


您可以從該服務訂單本身取消服務訂單或服務訂單明細，也可以執行定期作業來取消多個服務訂單。


> [!NOTE]
> <P>如果服務訂單的階段不允許取消，如果服務訂單有品項需求，或者如果服務訂單已經過帳，則無法取消服務訂單。</P>


## <a name="cancel-a-service-order-in-the-service-orders-form"></a>在服務訂單表單中取消服務訂單

1.  點選 **服務管理** \> **常用** \> **服務訂單** \> **服務訂單**。 選取服務訂單，然後在動作窗格上，按一下 **取消訂單**。

## <a name="cancel-a-service-order-line"></a>取消服務訂單明細

1.  點選 **服務管理** \> **常用** \> **服務訂單** \> **服務訂單**。 按兩下要取消的明細其所屬的服務訂單。

2.  選取要取消的服務訂單明細，然後按一下 **取消訂單明細** 將明細狀態變更為 **取消**。


> [!TIP]
> <P>若要還原服務訂單明細取消，並將狀態更改回<STRONG>已建立</STRONG>，按一下<STRONG>撤銷取消</STRONG>。</P>


## <a name="cancel-multiple-service-orders"></a>取消多個服務訂單

1.  按一下 **服務管理** \> **定期** \> **服務訂單** \> **取消服務訂單**。

2.  按一下 **取消** 按鈕。

3.  在 **詢問** 表單，在 **標準** 欄，選取您要取消的服務訂單。

4.  按一下 **確定** 關閉 **查詢** 表單。

5.  選取 **顯示資訊日誌** 核取方塊，以產生列出已取消服務訂單的資訊日誌。

6.  如果你想還原服務訂單的 **取消** 狀態，選取 **撤銷取消** 核取方塊。

7.  按一下 **確定**。

選定的服務訂單為已取消，或者其進度狀態為 **取消** 已還原為 **進行中**.


> [!NOTE]
> <P>如果您選取<STRONG>撤銷取消</STRONG>核取方塊，服務訂單的進度狀態為<STRONG>取消</STRONG>的被還原，並且服務訂單的進度狀態為<STRONG>進行中</STRONG>的不被取消。</P>


  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]