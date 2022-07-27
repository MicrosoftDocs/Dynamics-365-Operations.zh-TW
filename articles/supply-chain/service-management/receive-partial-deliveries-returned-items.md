---
title: 接收退回品項的部分交貨
description: 部分交貨是根據退貨單明細定義，而非退貨單裝運。
author: kamaybac
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: db02356afe06244f062f4e7c67a5db0a36900469
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8447891"
---
# <a name="receive-partial-deliveries-of-returned-items"></a>接收退回品項的部分交貨    

[!include [banner](../includes/banner.md)]


部分交貨是根據退貨單明細定義，而非退貨單裝運。

這表示如果您收到一個退貨單明細上指示的完整數量，但未收到退貨單其他明細中的任何數量，則該交貨不是部分交貨。 但是，如果退貨單明細要求退回 10 單位的特定品項，但您只收到 4 單位，則其為部分交貨。

如果退回貨件包含的數量少於退貨單明細的完整數量，則您可以暫不考慮該貨件，並且等待其餘退回數量到達，或者您可以登記和過帳部分數量。

## <a name="register-and-post-a-partial-quantity"></a>登記和過帳部分數量

1.  在 **到貨概覽 - 倉庫：%1、碼頭：%2、日記帳名稱：%3** 表單中為到貨選擇退貨單後，按一下 **開始到貨** 建立到貨日記帳，然後按一下 **日記帳** \> **顯示收貨的到達** 以開啟 **位置日記帳** 表單。

2.  選擇要使用的日記帳明細，然後按一下 **明細** 以開啟 **日記帳明細，位置** 表單。

3.  選擇僅部分數量到達的品項編號明細，然後按一下 **功能** \> **分割** 以開啟 **分割** 表單。

4.  在 **分割數量** 欄位，輸入已收到品項總數的數量，然後按一下 **確定**。

5.  在 **日記帳明細，位置** 表單，選擇已到達品項數量的明細，然後按一下 **過帳**。 您可以在品項到達後過帳額外的數量明細。






[!INCLUDE[footer-include](../../includes/footer-banner.md)]