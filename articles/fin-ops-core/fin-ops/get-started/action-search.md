---
title: 動作搜尋
description: 本文介紹動作搜尋函數。 動作搜尋將幫助您在頁面上尋找和執行動作。
author: jasongre
ms.date: 03/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.custom: 62303
ms.assetid: 62c70de0-fdde-4417-8e08-0583fb095a40
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6277c37ac43b8cc05c8b53da5ca0a1909f58c4f9
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8460158"
---
# <a name="action-search"></a>動作搜尋

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

本文介紹動作搜尋函數。 動作搜尋將幫助您在頁面上尋找和執行動作。

## <a name="introduction"></a>簡介

頁面主要在動作窗格上公開命令，包括出現在頁面頂部的標準動作窗格和出現在頁面各區段的工具欄。 在先前的版本中，按鍵提示函數可讓您透過按 Alt 鍵和一系列字母來快速存取動作窗格上的任何按鈕。

[![keyTipsAX6.](./media/keytipsax6.png)](./media/keytipsax6.png)

動作搜尋函數取代了不再可用的按鍵提示。 這項新函數使您可以從任何可見的動作窗格中快速搜尋和執行按鈕。

## <a name="using-action-search"></a>使用動作搜尋

若要使用動作搜尋函數，請按照以下步驟操作。

1. 在動作窗格中，點選 **動作搜尋** 欄位。  (**動作搜尋** 欄位包含放大鏡圖示。)
2. 輸入想要執行按鈕的全部或部分名稱。 您還可以使用按鈕「路徑」中的單字搜尋。 (如需相關資訊，請參閱本文的下一節。) 通常，在您輸入兩到四個字元後，結果清單頂部附近會出現一個按鈕。
3. 在結果清單中尋找並執行按鈕 (使用您的滑鼠或鍵盤)。

執行按鈕後，焦點會回到您在頁面上的最後一個位置，這樣您就可以繼續工作。

[![action-search-field.](./media/action-search-field.png)](./media/action-search-field.png)

您也可以透過按 Ctrl+/ 或 Alt+Q 來啟動動作搜尋。 再次按下鍵盤快捷鍵可將焦點返回到頁面上的最後一個位置。

## <a name="understanding-the-results-list"></a>了解結果清單

通常，您必須知道按鈕的位置和內容才能完全理解該按鈕的用途。 因此，結果清單會顯示附加資訊，以幫助您準確了解清單中出現的按鈕。 特別是，顯示了按鈕的「路徑」。 此路徑可能包含以下 UI 元素的標籤 (如果相關)：

- 動作窗格索引標籤
- 按鈕組
- 選單鍵 (如果按鈕位於選單鍵內)
- 選單分隔符號 (如果按鈕位於選單鍵內的命名組內)
- 頁面上的群組或索引標籤 (例如，FastTab 的名稱)

例如，您在 **動作搜尋** 欄位中輸入的 **總計**，並且現在正在檢查結果清單。 第一個輸入指令，用於命名 **總計** 的按鈕，強調顯示。 **銷售訂單**&gt;**檢視** 的按鈕路徑也顯示出來。 路徑的 **銷售訂單** 部分對應於動作窗格上的 **銷售訂單** 索引標籤，以及路徑的 **檢視** 部分對應於該索引標籤上的 **檢視** 組。同樣，**總折扣** 按鈕的路徑 (**銷售**&gt;**計算**) 通知您此按鈕位於動作窗格 **銷售** 索引標籤上的 **計算** 組。 因此，此資訊可幫助您準確了解動作搜尋將觸發哪個按鈕 (如果您在結果清單中選擇該按鈕)。

[![action-search-field-with-data.](./media/action-search-field-with-data.png)](./media/action-search-field-with-data.png)

在前面的範例中，動作搜尋在頁面頂部顯示標準動作窗格的結果。 但是，動作搜尋也會顯示來自頁面其他位置的可見工具欄的結果。 例如，您正在搜尋 **銷售訂單明細** FastTab 上的 **現有庫存** 按鈕。 在這種情況下，結果清單中的按鈕路徑 (**銷售訂單明細**&gt;**庫存**&gt;**檢視**) 通知您此按鈕位於 **銷售訂單明細** FastTab 上 **庫存** 選單按鈕的 **檢視** 標題下。

[![on-hand-inventory.](./media/on-hand-inventory.png)](./media/on-hand-inventory.png)

> [!NOTE]
> 有一些按鈕未顯示在動作搜尋中。 其中包括下拉式對話按鈕和子表單中的按鈕。 

## <a name="action-search-vs-navigation-search"></a>動作搜尋與瀏覽搜尋

雖然動作搜尋旨在尋找和執行頁面上的動作，但有一個單獨的搜尋機制用於尋找和瀏覽頁面。 如需相關資訊，請參閱[瀏覽搜尋](navigation-search.md)文章。


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]