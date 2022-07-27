---
title: 自動建立服務訂單
description: 在服務合約的有效期內，能以服務合約為基礎來生成服務訂單。
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
ms.openlocfilehash: 1acf4620556fe7ec5ae40f0a98b0a23602e2524a
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8447795"
---
# <a name="automatically-create-service-orders"></a>自動建立服務訂單 

[!include [banner](../includes/banner.md)]


在服務合約的有效期內，能以服務合約為基礎來生成服務訂單。

由服務合約生成的服務訂單，都被附加在服務合約上。

服務訂單是依據以下設定自動生成的：

  - 在服務合約明細中設定的服務合約間隔。 服務合約間隔指定建立服務訂單明細的頻率。 更多詳細資訊，請參閱[服務間隔](service-intervals.md)。

  - 此期間為 **建立服務訂單** 表單中的 **起始日期** 和 **結束日期** 欄位中定義的服務期間。 更多詳細資訊，請參閱[自動建立服務訂單](create-service-orders-automatically.md).

  - 服務合約標頭上的 **合併服務訂單** 選項。 此選項定義生成的服務訂單明細時，是否可以把服務合約與員工、服務任務、服務對象或服務合約合併。 更多詳細資訊，請參閱[合併建立服務訂單](combine-service-orders.md).

  - 服務協議明細上的 **時間窗口** 選項。 時間窗口定義了服務訂單明細可以距離其計算日期多遠。 如需詳細資訊，請參閱[時間窗口](time-windows.md)。


> [!NOTE]
> <P>如果服務訂單指定的日期在<STRONG>服務管理參數</STRONG>表單中選取的行事曆並未開放，將出現訊息提示存在行事曆衝突。 該訊息可以忽略；即使行事曆上關閉了這一天，服務訂單也會建立。</P>

## <a name="example-1"></a>範例 1

服務合約有效期為 2012 年 1 月 1 日至 2012 年 12 月 31 日。 如果 **建立服務訂單** 表單指定的服務期間是從 2012 年 11 月 1 日到 2013 年 2 月 1 日，服務訂單會建立在 2012 年 11 月 1 日到 2012 年 12 月 31 日。

## <a name="example-2"></a>範例 2

服務合約有效期為 2012 年 1 月 1 日至 2012 年 12 月 31 日。 服務合約附有兩條服務合約明細。 第一個服務合約明細的開始日期為 2012 年 1 月 2 日，結束日期為 2012 年 3 月 1 日。 第二個服務合約明細的開始日期為 2012 年 4 月 1 日，結束日期為 2012 年 12 月 31 日。 **建立服務訂單** 表單中指定的期間為 2012 年 10 月 1 日至 2012 年 12 月 31 日。 因此，僅第二個合約明細會生成服務訂單，因為第一個合約明細的開始日期和結束日期早於您為服務訂單指定的期間。

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]