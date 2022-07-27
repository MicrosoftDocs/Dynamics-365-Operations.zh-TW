---
title: 為退貨執行發票更新
description: 此功能支援會選擇同時由同一個人開具退貨單和銷售訂單發票的組織的業務流程。
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
ms.openlocfilehash: 736496a0499e70987f80f3d4687414371606cd8c
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449139"
---
# <a name="perform-invoice-updates-for-returns"></a>為退貨執行發票更新 

[!include [banner](../includes/banner.md)]


退貨單是一種標記為退貨單的銷售訂單。 因此，**所有銷售訂單** 清單頁面用於產生退貨單的發票，而不是 **退貨單** 表單。 此功能支援會選擇同時由同一個人開具退貨單和銷售訂單發票的組織的業務流程。

因為退回品項的發票是負數金額，所以稱為貸項通知單。

當您為批次處理設定發票更新時，類型為 **退貨單** 的銷售訂單其退貨行狀態必須是 **已收到**，表示訂單的裝箱單已更新。

## <a name="post-an-invoice-for-a-return-order"></a>過帳退貨單的發票

1.  按一下 **應收帳款**\> **一般** \> **銷售訂單** \> **所有銷售訂單**。

2.  選擇一個銷售訂單，其中 **退貨單** 顯示在 **訂單類型** 欄位中。

3.  在動作窗格的 **發票** 索引標籤上，在 **產生** 群組中按一下 **發票**。

4.  在 **參數** 索引標籤上，選擇 **過帳** 核取方塊。

5.  檢閱表單中的資訊，並進行必要的變更。

6.  按一下 **確定**。 隨即將貸項通知單過帳。

## <a name="see-also"></a>另請參閱

[退貨的裝箱單更新](packing-slip-updates-returns.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]