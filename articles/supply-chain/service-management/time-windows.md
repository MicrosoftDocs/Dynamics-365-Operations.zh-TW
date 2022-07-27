---
title: 時間範圍
description: 您可以使用時間範圍來最佳化服務訂單行的排程。
author: kamaybac
ms.date: 02/20/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMATimeAgreement
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1a0ac2c038b76d64ff8d55708e57f7c3b88c3393
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448773"
---
# <a name="time-windows"></a>時間範圍  

[!include [banner](../includes/banner.md)]

您可以使用時間範圍來最佳化服務訂單行的排程。 您可以設定系統，使其自動建立服務訂單。 根據時間範圍指定的條件，您可以將盡可能多的服務訂單行連接到盡可能少的服務訂單。

時間窗口指定了服務訂單明細可以距離其計算日期多遠。 計算日期是服務訂單行計劃發生的日期。 該日期是基於其間隔設定和您在 **建立服務訂單** 頁面中定義的服務期。 您可以使用下列資料表中的值定義時間範圍。

| 方法 | 描述                                                                                                                                                                                                                                                                                           |
|--------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 週   | 可以將服務訂單行移至與初始計算日期在同一週內的任何開放日日期。                                                                                                                                                                                    |
| 月  | 可以將服務訂單行移至與初始計算日期在同一個月份內的任何開放日日期。 例如，服務訂單行的計算日期是 2017 年 2 月 15 日。 服務訂單行可以安排在 2017 年 2 月 1 日至 2 月 28 日之間的任何工作日。 |
| 手動 | 您可以定義服務訂單明細在最初規劃日期前後可移動的最大天數。                                                                                                                                                                           |

如果您沒有為服務合約行指定時間範圍，則從服務合約派生的服務訂單行必須位於最初計劃的確切日期。

## <a name="related-topics"></a>相關主題

[建立時間範圍](create-time-windows.md)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]