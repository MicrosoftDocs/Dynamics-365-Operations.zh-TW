---
title: 閾值限制和異常閾值限制
description: 本主題介紹從源頭扣除稅款 (TDS) 的閾值和異常限制。
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 8391953024f302e75f23c72f8078d59a5541e24b
ms.sourcegitcommit: 6dc2b877cf8ea9185a07964ec05c5ddb7a78471b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/12/2022
ms.locfileid: "8451827"
---
# <a name="threshold-limit-and-exception-threshold-limit"></a>閾值限制和異常閾值限制

[!include [banner](../includes/banner.md)]

本主題介紹從源頭扣除稅款 (TDS) 的閾值和異常限制。 在針對發票和付款計算 TDS 時，始終考慮在 **扣繳稅款組成部分** 頁面上為 TDS 稅務組成部分定義的閾值限制和異常閾值限制。 TDS 稅務組成部分附加到包含在 TDS 稅組中的 TDS 稅碼。 TDS 稅組附加到廠商和客戶，以在發票級別或付款級別計算 TDS。

如果透過廠商的特定 TDS 群組過帳的交易或累計交易的金額超過在 **扣繳稅款組成部分** 頁面上指定的閾值限制，將計算 TDS。 在累計交易金額超過指定閾值限制之前，不會計算 TDS。

如果同時指定異常閾值限制和 TDS 群組成部分的閾值限制，則在特定交易金額超過異常閾值限制時，即使累計交易金額未超過指定的閾值限制，也會計算 TDS。

### <a name="example"></a>範例
名為 TDS 的稅務組成部分已設定並附加到名為 Contractor 的 TDS 稅務群組。 對於 TDS 稅務組成部分，閾值已定義為 50,000，異常閾值已定義為 20,000。 對於廠商 1，TDS 群組承包商將定義為默認預設的 TDS 群組。

對於廠商 1，將為 10000 過帳採購發票 001。 不計算發票的 TDS，因為發票金額未超過閾值限制或異常閾值限制。 對於廠商 1，將為 25,000 過帳採購發票 002。 計算發票的 TDS，因為發票金額已超過異常閾值限制。 對於廠商 1，將為 20,000 過帳採購發票 003。 計算發票的 TDS，因為為廠商開具的三張發票的發票總金額已超過閾值限制。 根據為廠商簽發的之前尚未計算 TDS 的所有發票計算 TDS。 因此，TDS 以 30,000 計算，即發票 001 和 003 的發票總金額。

如果對於附加到交易的 TDS 群組中的 TDS 稅碼選取 **忽略閾值** 核取方塊，則在計算 TDS 時不考慮閾值限制和異常閾值限制。 將不在選取了 **忽略閾值** 核取方塊的 TDS 群組的 TDS 稅碼中使用異常限制。

如果針對某些發票的特定 TDS 群組，但不針對已為特定廠商/客戶建立其他發票選取 **忽略閾值** 核取方塊，考慮到之前尚未計算 TDS 的所有發票的累計金額，可能會在不忽略少數發票的閾值限制的情況下計算 TDS。

例如，閾值限制為 25000。 為廠商 A 建立以下發票。

- 發票 1 – 2,0000 – (未選取 **忽略閾值** 核取方塊)：不計算 TDS。

- 發票 2 – 4,000 – (選取 **忽略閾值** 核取方塊)：根據 4,000 計算 TDS。

- 發票 2 – 3,000 – (未選取 **忽略閾值** 核取方塊)：當累計發票金額 27,000 (20000+4000+3000) 超過閾值限制時計算 TDS。 TDS 是根據之前未計算 TDS 的累計發票金額計算的，即 23,000 (20000+3000)。
