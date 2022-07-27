---
title: 使用在新視窗中的開啟函數並排顯示頁面
description: 本文介紹了如何並排顯示頁面。
author: aneesmsft
ms.date: 11/20/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.custom: 17611
ms.assetid: fc589d76-3927-4486-ab83-e86b9b47ba2c
ms.search.region: Global
ms.author: aneesa
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a4c8086d511892f8965dfefca2789742a006f63f
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8460183"
---
# <a name="show-pages-side-by-side-using-the-open-in-new-window-feature"></a>使用在新視窗中的開啟函數並排顯示頁面

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

本文介紹了如何並排顯示頁面。

您可能希望並排查看多個頁面以快速完成工作。 例如，您可能想要驗證或在多個期刊中輸入明細。 通常，要驗證或在多個期刊中輸入明細，您必須在顯示日記帳清單的頁面和顯示給定日記帳明細的頁面之間來回切換。 但是，**在新視窗中打開** 函數使您能夠並排顯示這些頁面，以便您可以快速執行工作。

繼續上面提到的範例，查看明細時，您可以點選 **在新視窗中打開** 圖示。

[![點選在新視窗中打開圖示。](./media/open-in-new-window-icon.png)](./media/open-in-new-window-icon.png)

點選 **在新視窗中打開** 圖示在新的彈出式瀏覽器中打開明細頁面，然後在歷史記錄中將原始瀏覽器導覽回顯示日記帳清單的頁面。 然後，您可以並排顯示兩個頁面。 查看日記帳後，您可以在日記帳清單頁面更改選取的日記帳，彈出式視窗的明細頁面會自動顯示新選取日記帳的明細。

[![您可以並排顯示兩個頁面。](./media/pages-show-side-by-side.png)](./media/pages-show-side-by-side.png)

動態連結和重新整理是由於支援這些頁面的資料之間存在的關係而發生的。 如果系統不知道資料之間的關係，則彈出式視窗將不會自動重新整理以回應其來源視窗的變化。

某些頁面具有多個視圖，例如格線視圖、標題視圖和詳情視圖。 在 **新視窗中打開** 圖示使整個頁面在新的瀏覽器視窗中打開。 因此，您不能使用 **在新視窗中打開** 函數並排保持同一頁面的兩個視圖。 幾乎所有此類頁面都有一個導覽清單，您可以使用它在記錄之間切換並獲得類似的體驗。

在使用 **在新視窗中打開** 函數之前，您應該設定瀏覽器的彈出式視窗封鎖程式以允許來自網站 URL 的彈出視窗。 例如，您可以允許來自「\*.dynamics.com」的彈出式視窗。

僅當視窗中打開多個頁面時，**在新視窗中打開** 函數才可用。 此外，當沒有更多頁面打開時 (即，當您關閉該視窗中的最後一頁時)，彈出式視窗會自動關閉。 當您導覽到應用程式中的不同區域時，系統也會關閉打開的頁面。 因此，如果您打開了彈出式視窗並導覽到應用程式中的不同區域，則彈出式視窗會自動關閉，因為系統關閉了這些視窗中的頁面。

彈出式視窗中的頂部欄顯示有關打開頁面的公司的信息，並且是只讀的。 彈出式視窗也依賴於主瀏覽器視窗。 如果主視窗關閉或重新整理，所有打開的彈出式視窗都將變為讀取專用。 如果出現這種情況，您仍然可以在這些視窗中查看信息，但您將無法與之互動。


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]