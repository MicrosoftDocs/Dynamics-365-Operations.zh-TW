---
title: 全球庫存會計分類帳
description: 本主題說明全球庫存會計分類帳，也就是由貨幣、日曆、約定和與法人實體的關聯定義的法律實體。
author: AndersGirke
ms.date: 06/18/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2021-06-18
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 0130aef7212256a11ca9d27ffdd4af7a0aa6d98c
ms.sourcegitcommit: 8c17717b800c2649af573851ab640368af299981
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/23/2021
ms.locfileid: "8449490"
---
# <a name="global-inventory-accounting-ledger"></a>全球庫存會計分類帳

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]
<!--KFM: Preview until 4/30/2022 -->

全球庫存會計有屬於自己的一套分類帳。 每次為相關的法律實體處理與庫存相關的交易時，系統可以根據需求，在任意數量的全球庫存會計分類帳中對該交易進行會計處理。

分類帳是借記和貸記的量值。 這些量值使用成本元素和子分類帳戶進行分類。 全球庫存會計分類帳由貨幣、日曆、約定和與法人實體的關聯定義的法律實體。

若要設定全球會計分類帳，請前往 **全球庫存會計 \> 設定 \> 全球庫存會計分類帳**。 對於每個分類帳，設定下列欄位：

- **名稱** - 輸入分類帳的名稱。
- **描述** - 輸入該分類帳的描述。
- **會計行事曆** - 指定分類帳的會計行事曆。
- **貨幣和匯率類型** - 使用 FastTab 上的欄位，選擇分類帳使用的會計貨幣和匯率類型。 不同的法律實體可以選擇使用不同的貨幣。 在全球庫存會計中，使用者可以根據需求，定義任意數量的成本分類帳。 全球庫存會計支援多種貨幣和多種估值的庫存會計。 設定以下欄位：

    - **貨幣** - 選擇與維護庫存相關值的成本貨幣。 這些值包括庫存價值、銷貨成本、運輸中庫存和各種差異。
    - **匯率類型** - 選擇系統應使用的匯率，將交易貨幣的交易金額和項目的標準成本轉換為成本計算貨幣。

- **規範名稱** - 指定規範。 規範是建立此分類帳如何計算成本原則的集和物件。
- **法律實體** - 分類帳將對過帳到所選法律實體進行會計處理。
- **預備** - 選擇在建立分類帳之前建立的庫存交易，是否應根據分類帳中的貨幣和規範進行處理。 選擇下列其中一個值：

    - **啟用** - 分類帳應處理建立分類帳之前建立的交易。
    - **停用** - 分類帳應只處理建立分類帳之後建立的交易。

    > [!IMPORTANT]
    > 輸入新的文件之後，您將 **無法** 返回設定此欄位。

- **狀態** - 系統自動將新建立的分類帳狀態設定為 *準備*。
