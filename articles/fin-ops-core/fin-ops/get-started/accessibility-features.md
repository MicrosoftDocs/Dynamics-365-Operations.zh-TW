---
title: 協助工具函數
description: 本主題介紹旨在幫助有各種殘疾使用者的函數。
author: TLeforMicrosoft
ms.date: 12/02/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: tlefor
ms.search.validFrom: 2017-12-31
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: 022c51f7050d11caf5ce67c5df8f9f9040a54b98
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8460159"
---
# <a name="accessibility-features"></a>協助工具函數

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

本主題介紹旨在幫助有各種殘疾使用者使用此應用程式的函數。 例如，有一些函數適用於使用視力輔助技術的人，例如 Microsoft Windows 朗讀程式。

## <a name="windows-narrator-and-keyboard-only-access"></a>Windows 朗讀程式和鍵盤專用存取

每個欄位和控制項都有一個標籤和適用捷徑的描述。 螢幕讀取器可以讀取標籤和說明。

## <a name="shortcuts-for-the-most-frequently-performed-actions"></a>最常執行的操作的捷徑

對於大多數使用者而言，日常系統使用涉及大量資料輸入和鍵盤互動。 為了提升使用者體驗，我們建立了捷徑來幫助您在螢幕上「瞬移」，並建立了專門操作的捷徑。 如需相關資訊，請參閱[快捷鍵](shortcut-keys.md)。

## <a name="navigation-search"></a>瀏覽搜尋

使用瀏覽窗格選單 (最左側的窗格) 存取的任何頁面也可從 **搜尋** 框存取。 按 Alt+G 將焦點移至 **搜尋** 框，然後輸入頁面的名稱或說明。

![在搜尋框中輸入「Bank accounts」](media/6d08b0be32808221023e2aa92d69fd70.png "在搜尋框中輸入「bank accounts」")

如需相關資訊，請參閱[瀏覽搜尋](navigation-search.md)。

> [!NOTE]
> 您只能直接瀏覽到最高層頁面。 次級頁面需要於其父代頁面的資訊或內容。

## <a name="action-search-for-keyboard-only-users-or-for-heads-down-data-entry"></a>僅使用鍵盤的使用者或無錯誤資料輸入專用的操作搜尋

頁面上提供的每個操作都可以透過鍵盤的 Tab 序列存取。 有關 Tab 序列的資訊稍後會在本主題中提供。 若要更直接地執行操作，您可以使用操作搜尋函數。

### <a name="example"></a>範例

您想執行出現在操作窗格、**銷售訂單** 索引標籤、**電子郵件通知** 組中的 **電子郵件通知記錄**。

![操作窗格上的電子郵件通知記錄操作。](media/f0d78399e7fafcd85ded1cd1e3d34f3c.jpg "操作窗格上的「電子郵件通知記錄」操作")

有一個選項是使用鍵盤。 按 Ctrl+F6 將焦點移至操作窗格，然後重複按 Tab 鍵在所有索引標籤和操作之間移動，直到 **電子郵件通知記錄** 操作找到重點。

但是，您也可以更直接地執行該操作。 在頁面上的任意位置，按 Ctrl + 撇號 (') 以顯示操作搜尋框。

![用於執行操作的搜尋框。](media/80f7e8c5ac412fdf2c8a12f7728f135a.jpg "用於執行操作的搜尋框")

在搜尋框中，輸入描述該操作的字詞。 該操作可供您使用，您可以直接執行它。 例如，透過輸入 **email**、**notific** (部分字詞)，或 **log**，您可以「跳至」電子郵件通知記錄函數。

![在搜尋框中輸入「Email」](media/image4.png "在搜尋框中輸入「email」")

![在搜尋框中輸入「Notific」](media/image5.png "在搜尋框中輸入「notific」")

![在搜尋框中輸入「Log」](media/image6.png "在搜尋框中輸入「log」")

完成後，您可以再次按 Ctrl + 撇號在您執行操作搜尋之前將重點退回到您在使用的欄位。

如需相關資訊，請參閱[操作搜尋](action-search.md)。

## <a name="tab-sequence"></a>Tab 序列

在日常系統使用中，並非每個欄位都需要執行典型任務。 因此，在預設情況下，Tab 序列是已經過「最佳化」。 僅在典型案例的必要欄位上設定定位點。

但是，您可能會發現您經常用於執行任務的某些欄位未包含在預設 Tab 序列中。 在這種情況下，如果您使用 Windows 朗讀程式，則可以使用 Windows 朗讀程式的鍵盤操作來存取這些欄位並檢查其內容。 或者，您可以打開 **選項** 頁面上的 **增強的 Tab 序列** 選項。 此選項使所有可編輯和讀取專用欄位成為 Tab 序列的一部分。 然後，您可以使用頁面個人化來建立自訂 Tab 序列並省略不必成為 Tab 序列一部分的欄位。 如需有關個人化的相關資訊，請參閱[個人化使用者體驗](personalize-user-experience.md)。

![「增強的 Tab 序列」選項](media/8c0f12bbb3f26032997ef0ba95d89b6a.png "「增強的 Tab 序列」選項")

## <a name="form-patterns"></a>板型模式

應用程式中幾乎 90% 的頁面都根據一小組模式。 這些模式被稱為 *板型模式*。 每個板型模式都用於提供頁面上最常執行的操作。 板型模式有助於保證熟悉度和理解度，因為經常使用的操作和資料總是顯示在不同頁面的相同位置。 由於板型模式少，使用者可以輕鬆學習該系統，無論系統有多少頁，在識別板型模式後都可以放心使用。

若要進一步了解板型模式，請參閱[板型樣式和模式](../../dev-itpro/user-interface/form-styles-patterns.md).

## <a name="responsive-layout"></a>回應式配置

該產品設計用於各種裝置和板型規格，從最小的螢幕到具有最高解析度的大螢幕。 我們的回應式配置引擎允許使用者放大到 200% (或者，在某些情況下，超過 200%) 的程度。

在智慧型手機和其他小螢幕上，控制項和板型配置將做出回應式調整，以確保核心資料受到青睞。 這些回應式行為還可以包括減少資料欄組數並按 Tab 鍵跳至單資料欄、隱藏殼層元素和折疊操作窗格。

## <a name="guidance-to-help-developers-and-customers-incorporate-accessible-thinking-in-their-customizations"></a>幫助開發人員和客戶在其自訂中融入可存取思維的指南

若要進一步了解啟用協助工具的 Microsoft 最佳做法，請參閱[板型、產品和控制項的協助工具](../../dev-itpro/user-interface/enable-accessibility.md)。


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]