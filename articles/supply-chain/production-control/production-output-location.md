---
title: 生產輸出位置
description: 本主題說明用於標示生產輸出位置的階層。
author: johanhoffmann
ms.date: 04/04/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: 221264
ms.assetid: dde49743-1541-4353-a030-63ca3069cd7d
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: f4c8086e9179ff51f62ce77620af96360c6123060372dfd1c0e06dad79998b75
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446688"
---
# <a name="production-output-location"></a>生產輸出位置

[!include [banner](../includes/banner.md)]

本主題說明用於標示生產輸出位置的階層。

生產輸出位置是指成品在生產後首先儲存的位置。 一般來說，此位置靠近生產成品的生產過程。 生產輸出位置是在材料移動到裝運區域、儲存位置、下游生產過程的生產輸入位置等位置之前，作為材料的中間儲存位置。 

當生產訂單或批次訂單上回報成品時，系統會設定預設的生產輸出位置。 以下階層用於標示此輸出位置：

1. 使用在生產訂單或批次訂單標題上定義的輸出位置。
2. 如果在那裡找不到位置，請使用在生產途程中定義的最後一項作業使用的資源上定義的輸出位置。
3. 如果在那裡找不到位置，請使用在生產途程中定義的最後一項作業使用的資源群組上定義的輸出位置。
4. 如果在那裡找不到位置，請使用在為生產訂單定義的倉庫中定義的輸出位置。

系統只為使用進階倉庫流程設定的產品設定預設生產輸出位置。 當此類項目報告為已完成時，系統會建立 **成品入庫** 或 **聯產品和副產品入庫** 類型的倉庫工作。 這種類型的工作使用生產輸出地點作為揀選地點。 入庫位置是由位置指引決定。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]