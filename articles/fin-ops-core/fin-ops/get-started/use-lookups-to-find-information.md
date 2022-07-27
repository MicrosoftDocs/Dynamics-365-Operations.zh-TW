---
title: 使用查閱功能尋找資訊
description: 在本主題中，您將了解查詢功能，並將收到一些有用的提示，以充分利用系統中的查詢。
author: jasongre
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.custom: 269934
ms.assetid: f20cbd2c-14e0-47e7-b351-8e60d3537f96
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e7135487e5d87564163c643d1315c51231fa66de
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8460300"
---
# <a name="find-information-by-using-lookups"></a>使用查閱功能尋找資訊

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

許多欄位都有查詢功能，可以幫助您輕鬆找到正確或所需的值。 已為查詢新增了幾項增強功能，使這些控制項更易於使用並提高使用者的工作效率。 在本主題中，您將了解這些新查詢功能，並將收到一些有用的提示，以充分利用系統中的查詢。

## <a name="responsive-lookups"></a>回應式查詢

在以前的版本中，當與查詢控制項互動時，使用者必須執行明確動作才能打開下拉式選單。 這可能是透過在控制項中輸入星號 (\*) 以根據控制項的目前值篩選查詢、點選下拉式按鈕或使用 **Alt**+**向下箭頭** 快捷鍵。 查詢控制項已透過以下方式進行了修改，以更好地與目前的網路做法保持一致：

- 現在，查詢下拉式選單將在輸入稍有暫停後自動打開，下拉式選單內容會根據查詢控制項的值進行篩選。

    請注意，在輸入星號 (\*) 後自動打開下拉式清單的舊行為已被棄用。

- 打開查詢下拉式選單後，將出現以下情況：

    - 游標將停留在查詢控制項中 (而不是焦點移動到下拉式選單中)，因此您可以繼續修改控制項的值。 但是，使用者仍然可以使用 **向上箭頭** 和 **向下箭頭** 來更改下拉式選單中的資料列，然後輸入以選取下拉式選單中的目前資料列。
    - 在對查詢控制項的值進行任何修改後，下拉式選單的內容將進行調整。

例如，考慮一個名為 **城市** 的查詢欄位。

當焦點在 **城市** 欄位中，您可以透過輸入幾個字母 (例如「col」) 開始查詢您想要的城市。 停止輸入後，查詢將自動打開，篩選出以「col」開頭的城市。

[![typeaheadLookupExample。](./media/typeaheadlookupexample.png)](./media/typeaheadlookupexample.png)

此時，游標仍在查詢欄位中。 如果您繼續輸入以使值為「資料欄」，則查詢內容會自動調整以反映控制項中的最新值。

![updateFilterLookupExample。](./media/updatefilterlookupexample.png)

即使焦點仍在查詢控制項中，您也可以使用 **向上箭頭** 或 **向下箭頭** 鍵強調顯示要選取的資料列。 如果按 **Enter** 鍵，將從查詢中選取突出顯示的資料列，並且將更新控制項的值。

![changingSelectionLookup。](./media/changingselectionlookup.png)

## <a name="typing-in-more-than-ids"></a>輸入多個 ID

輸入資料時，使用者很自然地會嘗試根據名稱而不是代表實體的識別碼來識別實體，例如客戶或廠商。 許多 (但不是全部) 查詢現在允許內容資料輸入。 這個強大的功能允許使用者在查詢控制項中輸入 ID 或相應的名稱。

例如，在建立銷售訂單時考慮 **客戶帳號** 欄位。 此欄位顯示客戶的 **帳戶 ID**，但使用者在建立銷售訂單時通常更願意為此欄位輸入 **帳戶名稱** 而不是 **帳戶 ID**，例如「Forest Wholesales」而不是「US-003」。

如果使用者開始將 **帳戶 ID** 輸入到查詢控制項，下拉式選單將自動打開，如上一節所述，使用者將看到如下所示的查詢。

[![輸入客戶帳戶 ID 時的內容查詢。](./media/howtocontextuallookups-1.png)](./media/howtocontextuallookups-1.png)

但是，使用者現在也可以輸入 **帳戶名稱** 的開頭。 如果偵測到這一點，則使用者將看到以下查詢。 請注意 **名稱** 欄是如何移動到查詢中的第一欄的，以及查詢是如何根據 **名稱** 欄進行排序和篩選的。

[![輸入客戶名稱時的內容查詢。](./media/howtocontextuallookups-2.png)](./media/howtocontextuallookups-2.png)

## <a name="using-grid-column-headers-for-more-advanced-filtering-and-sorting"></a>使用格線欄標題進行更高級的篩選和排序

前兩節中討論的查詢增強功能極大地提高了使用者在查詢中基於對 **ID** 或 **名稱** 欄位的「開始於」搜尋在查詢中導覽資料列的能力。 但是，在某些情況下，需要更進階的篩選 (或排序) 來找到正確的資料列。 在這些情況下，使用者需要在查詢內的格線欄標題中使用篩選和排序選項。 例如，考慮輸入銷售訂單明細的員工，他需要將正確的「纜線」定位為產品。 將「纜線」輸入 **項目編號** 控制沒有幫助，因為沒有以「纜線」開頭的產品名稱。

![emptyitemlookup。](./media/emptyitemlookup.png)

相反，使用者需要清除查詢控制項的值，打開查詢下拉式選單，並使用格線欄標題篩選下拉式選單，如下所示。 滑鼠 (或觸控) 使用者只需點選 (或觸控) 任何欄標題即可存取該欄的篩選和排序選項。 對於鍵盤使用者，使用者只需再次按 **Alt**+**向下** **箭頭** 即可將焦點移動到下拉式選單中，之後使用者可以按 Tab 跳到到正確的資料欄，然後按 **Ctrl**+**G** 打開格線欄標題下拉式選單。

[![gridfilteritemlookup。](./media/gridfilteritemlookup.png)](./media/gridfilteritemlookup.png)

套用篩選器後 (見下圖)，使用者可以像往常一樣找到並選取資料列。

![filtereditemlookup。](./media/filtereditemlookup.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]