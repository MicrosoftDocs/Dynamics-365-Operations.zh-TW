---
title: 批次和牌照確認
description: 本主題介紹如何從行動裝置設定和套用批次和牌照確認。
author: Mirzaab
ms.date: 11/11/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSRFAutoConfirm
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 13e246f9a496dcc38829eef788d09c50300c99fb95daffad134012733341e4af
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446739"
---
# <a name="batch-and-license-plate-confirmation"></a>批次和牌照確認

[!include [banner](../includes/banner.md)]

批次確認允許您從行動裝置中確認揀選的批次是否正確。 關於最初的揀選工作僅限 *批次以上\[地點\]* 品項，其中批次以上指示批次放置在搜尋階層中較高的位置，您必須驗證揀選的批次與工作明細上的批次相符。

牌照確認允許您從行動裝置中確認揀選的牌照是否正確。 從暫存位置揀選工作時，您必須驗證揀選的牌照是否與與工作關聯的牌照相符。 如果工作是從掃描牌照開始的，則將跳過此確認步驟。

## <a name="where-it-applies"></a>適用處

確認適用於以下情境：

- 批次確認適用於批次以上品項的初始揀選工作。
- 牌照牌確認適用於暫存位置的揀選。

> [!IMPORTANT]
> 牌照確認不支援補貨。 執行補貨工作時，不會建立牌照確認步驟。

## <a name="set-up-batch-and-license-plate-confirmation"></a>設定批次和牌照確認

您可以從行動裝置功能表項目設定批次和牌照確認。

1. 從行動裝置功能表項目中，輸入工作確認設定。  
1. 選取批次或牌照確認選項。 這兩個選項都可用於未啟用自動確認的工作類型揀選。  


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
