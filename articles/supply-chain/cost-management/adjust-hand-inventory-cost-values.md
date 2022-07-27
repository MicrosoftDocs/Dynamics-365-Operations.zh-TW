---
title: 調整現有庫存成本值
description: 執行庫存結算程序後，運用調整現有庫存頁面來調整現有庫存數量的成本值。
author: AndersGirke
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventAdjInventOnHand
audience: Application User
ms.reviewer: kamaybac
ms.custom: 53231
ms.assetid: bc1fde9f-5ad9-4339-8ae8-e2839b792eb2
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fe79369fe4a85f34f7648699e90b726356ce6122594e60f21b27180982b7b149
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447222"
---
# <a name="adjust-on-hand-inventory-cost-values"></a>調整現有庫存成本值

[!include [banner](../includes/banner.md)]

執行庫存結算程序後，運用調整現有庫存頁面來調整現有庫存數量的成本值。

執行庫存結算程序後，您可以運用 **調整現有庫存頁面** 來調整現有庫存數量的成本值。 **注意：** 若要開啟 **調整現有庫存** 頁面，在 **結算和調整** 頁面，選取已完成庫存結算程序的記錄，然後按一下 **調整**&gt;**現有**。 **範例：** 您在 2 月份有以下交易：

-   2 月 1 日：數量為 2 的庫存財務收據，成本為 10.00 美元
-   2 月 5 日：數量為 1 的庫存財務收據，成本為 13.00 美元
-   2 月 19 日：數量為 1 的庫存財務開票，移動平均成本為 11.00 美元

此品項設定為先進先出 (FIFO) 庫存模型，並於 2 月 28 日執行庫存結算。 11.00 美元的財務出貨交易將根據日期為 2 月 1 日的財務收據進行結算，並進行 1.00 美元調整。 然後，以下庫存收據將包含未結庫存數量：

-   2 月 1 日：數量為 1，成本為 10.00 美元
-   2 月 5 日：數量為 1，成本為 13.00 美元

要將這兩個品項的成本設定為 15.00 美元，請使用現有調整選項來調整最後庫存結算期間的未結現有量。 **請注意：** 現有量調整交易的過賬日期將是最後庫存結算的日期。 此日期無法修改。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]