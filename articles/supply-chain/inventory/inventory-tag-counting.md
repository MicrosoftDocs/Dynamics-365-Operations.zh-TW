---
title: 庫存標籤盤點
description: 本主題提供有關標籤盤點的資訊，您可以使用這些資訊將倉庫的實際內容與現有庫存進行比較。
author: yufeihuang
ms.date: 06/10/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventJournalCount, InventJournalCountTag
audience: Application User
ms.reviewer: kamaybac
ms.custom: 11594
ms.assetid: 03772d0e-5c37-454c-ab85-82bc8b60a76d
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 64315b8c5f0be1dbd19239a8b07746e90aebb0d4
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448005"
---
# <a name="inventory-tag-counting"></a>庫存標籤盤點

[!include [banner](../includes/banner.md)]

本主題提供有關標籤盤點的資訊，您可以使用這些資訊將倉庫的實際內容與現有庫存進行比較。

透過在 **標籤盤點** 頁面上建立明細，您將在每個庫存品項上放置一個標籤編號，例如從 1 到 500 的數字。 在盤點期間，您會在對應的標籤上輸入品項編號和數量。 然後此標籤便可以用作標籤盤點日記帳中輸入的基礎。 在您過帳標籤盤點日記帳之後，**盤點** 頁面將建立新的盤點日記帳。 新日記帳是以您建立的標籤盤點日記帳明細為基礎。 如要按特定庫存維度為品項執行標籤盤點，請選擇在您建立標籤盤點日記帳時顯示的 **顯示維度** 頁面上的維度。 例如，要盤點特定倉庫中的品項，請選擇 **倉庫** 核取方塊。 如果 **庫存和倉庫管理參數** 頁面上的 **在盤點期間鎖定品項** 滑桿已選取，則品項在盤點過程中不能進行實體更新。 但是，標籤盤點日記帳中的品項在盤點期間不會被鎖定。 在將標籤盤點明細過帳並轉移至盤點日記帳之前，不會建立庫存交易。 如果標籤是隨機輸入的，且您想識別缺少的標籤，請按一下 **標籤** 欄標題以按標籤對明細進行排序。

## <a name="additional-resources"></a>其他資源

[週期盤點](../warehousing/cycle-counting.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]