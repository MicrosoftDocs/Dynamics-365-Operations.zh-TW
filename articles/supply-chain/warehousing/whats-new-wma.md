---
title: Warehouse Management 行動應用程式中的新增功能或變更
description: 本主題列出了 Microsoft Dynamics 365 Supply Chain Management 的 Warehouse Management 行動應用程式的每個已發行版本的新增或變更功能。
author: Mirzaab
ms.date: 03/11/2022
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-06-07
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: c4731c5f0b0a1553deb53753d82d29a34e5525df
ms.sourcegitcommit: 399d0d3f8e2ebb81b6b9d640365ebe182690bab2
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/15/2022
ms.locfileid: "8450129"
---
# <a name="whats-new-or-changed-in-the-warehouse-management-mobile-app"></a>Warehouse Management 行動應用程式中的新增功能或變更

[!include [banner](../includes/banner.md)]

本主題列出了 Microsoft Dynamics 365 Supply Chain Management 的 Warehouse Management 行動應用程式的每個已發行版本的新增功能、修復、改進和已知問題。

## <a name="version-20190"></a>版本 2.0.19.0

此版本引入了以下新增功能、修復和改進：

- 改進了通用資料查詢流程。
- 改進了 **工作清單** 和 **項目查詢** 頁面的抖動問題。
- 降低電池耗電量。
- 移除了工作卡欄位數量限制。
- 調整了工作卡的高度，使它們都具有相同的大小，無論每個工作卡中的欄位數如何。
- 修復了條碼中的空格字元會被修掉的問題。
- 新增了 **按鈕樣式** 設定，可讓您在所有類型的裝置上切換滑桿檢視表和按鈕檢視表。
- 修復了可能導致應用程式崩潰的各種問題。
- 將焦點自動設定在自訂頁面上的第一個文字方塊上。
- 進行了與亮度、對比度、旁白和缺少預留位置文字相關的協助工具改進。

## <a name="version-20170"></a>版本 2.0.17.0

此版本引入了以下新增功能、修復和改進：

- 修復了條碼掃描不正確的問題。
- 修復了相機掃描器的 GS1 掃描問題。
- 修復了 Zebra 裝置上條碼掃描器的 GS1 掃描問題。
- 改進了繞道查詢流程，在繞道中選擇卡片現在將返回到主流程。
- 新增了對通用資料查詢流程的支援。
- 新增了一則訊息，告知使用者網路連線狀態的變化。
- 將儲存權限與 Android 10 中的儲存隱私權原則保持一致。
- 對於需要它的流，數量微調按鈕現在包含一個位置，允許使用者提交空白數值。
- 修復了數量微調按鈕方向的問題。
- 修復了數量微調按鈕會跳轉到錯誤值的問題。
- 修復了從詳細資料頁面填入主頁面輸入時會遺失輸入的問題。
- 修復了預留位置文字將視為選擇清單中最初選擇的值的問題。
- 如果有預選值，現在會在確認步驟上自動啟用 [提交] 按鈕。
- 修復了詳細資料卡以盡量顯示具有多行的文字欄位的行。
- 修復了 [提交] 和 [更多動作] 按鈕的高度，現在它們在畫面上佔用的空間更少。
- 新增了缺少的選擇清單標題。
- 修復了返回按鈕無法運作的問題。
- 新增了幾個鍵盤瀏覽修復和改進，包括以下頁面：
  - 使用者登入
  - 選取連線
  - 編輯連線
- 修復了使用鍵盤瀏覽時的滾動。
- 增強了協助工具，包括以下改進：
  - 修復了色彩可見度和對比度。
  - 防止彈出頁面關閉時鍵盤焦點遺失。
  - 在旁白中新增了錯誤訊息。
  - 增加了步驟橫幅中預留位置值的大小。
- 修復了示範模式下自訂舊頁面的範例。

## <a name="version-20150"></a>版本 2.0.15.0

此版本引入了以下新增功能、修復和改進：

- 透過修復內存洩漏問題提高了效能。
- 修復了在詳細資料頁面上選擇時，某些欄位值時未正確更新的問題。

## <a name="version-20140"></a>版本 2.0.14.0

此版本引入了以下新增功能、修復和改進：

- 修復了停用預設 [提交] 按鈕的問題。

## <a name="version-20130"></a>版本 2.0.13.0

此版本引入了以下新增功能、修復和改進：

- 改進了頁面之間的滾動，並且動畫更流暢。
- 修復了對撥動動作和偶爾螢幕凍結的反直覺回應。
- 改進了深色模式文字和背景色彩組合，以提高可讀性。
- 修復了調整應用程式視窗大小時某些文字可能變得非常小的問題。
- 修復了掃描條碼有時會導致應用程式崩潰的問題。
- 新增了用按鈕替換滑桿的可能性。
- 修復了可能導致應用程式顯示以下錯誤訊息的問題：「AADSTS7000215：提供了無效的用戶端密碼」。
- 修復了顯示如何使用向下撥動手勢關閉頁面的提示動畫。
- 新增了使用向下撥動手勢關閉頁面的可能性。
- 修復了在 **使用者設定** 頁面上顯示下拉清單標題的問題。
- 修復了應用程式無法將逗號 (,) 識別為小數分隔符號的在地語系化問題。
- 改進了可存取性。
- 修復了 **新連線** 頁面上的導航問題以提供改進的協助工具。
- 修復了選擇輸入欄位時不顯示軟 (螢幕) 鍵盤的問題。
- 修復了使用者快速調整應用程式視窗大小時，可能導致應用程式崩潰的問題。
- 修復了快速按鍵有時被解釋為長按的問題。
- 修復了應用程式配置可能因 Supply Chain Management 中的欄位自訂而損壞的問題。
- 修復了物料位置未正確顯示的問題。
- 修復了與產品變型工作流程揀料短缺相關的問題。
- 刪除了包含預設預設值的欄位的不必要驗證。
- 提高效能。
- 新增了一個新設定，可讓使用者選擇欄位在卡片頁面上的篩選和排序方式。

## <a name="version-20110"></a>版本 2.0.11.0

此版本引入了以下新增功能、修復和改進：

- 新增了對升階欄位的支援。
- 新增了對硬體鍵盤瀏覽的支援。
- 改進了可存取性。
- 增強了詳細資料卡。
- 增強了功能表項目步驟的繞道。
- 使用者介面進行了小改進。
- 修復了可能導致應用程式在掃描條碼時崩潰的問題。
- 修復了可能導致系統停止回應的各種問題。

## <a name="version-20100"></a>版本 2.0.10.0

此版本引入了以下新增功能、修復和改進：

- 新增了撥動清單和頁面時的動畫。
- 文字現在在連線錯誤頁面上正確換行。
- 沒有預設值的下拉式方塊現在可以正確顯示。
- 子標題區域中的資訊現在僅顯示在完整詳細資料頁面上。
- 詳細資料卡上不再顯示空白輸入欄位。
- 詳細資料卡上不再重複確認值。
- 修復了導致系統停止回應的各種問題。

## <a name="version-2090"></a>版本 2.0.9.0

此版本修復了如果使用者從清單頂端向上翻頁，應用程式可能會停止回應的問題。

## <a name="version-2080"></a>版本 2.0.8.0

此版本引入了以下新增功能、修復和改進：

- 新增了對 Supply Chain Management 版本 10.0.21 中引入的[步驟說明功能](mobile-app-titles-instructions.md)的支援。
- 新增了提示動畫，向使用者說明他們可以透過向下撥動來關閉重疊。
- 新增了對動作清單和功能表上的功能鍵的支援。 使用者可以按住任意功能鍵三秒鐘來取得可用命令清單。
- 修復了導致在某些裝置上顯示以下錯誤訊息的問題：「找不到適合指定尺寸的檢視表」。
- 修復了使用螢幕鍵盤時全螢幕模式並不一定可用的問題。
- 修復了在 Windows 裝置上無法進行頁面撥動的問題。
- 修復了導致系統停止回應的各種問題。

## <a name="version-2070"></a>版本 2.0.7.0

### <a name="new-features-fixes-and-improvements-in-version-2070"></a>版本 2.0.7.0 中的新增功能、修復和改進

- 將某個部分新增到 **關於** 頁面，該頁面會檢查應用程式的最新已發佈版本。
- 更容易在頁面之間活動和撥動。
- 變更了工作清單中遞增/遞減按鈕的圖示。
- 減少了 **詳細資料** 卡上的邊距以使卡能夠容納更多資訊。
- 套用了各種效能改進，以減少應用程式隨時間變慢的問題。
- 如果控制項的數量超出了螢幕的大小，從而導致分頁，則微調按鈕控制項不再以與頁面相同的方式滾動。
- 將優先顯示上次掃描的值，而不是顯示工作標題，因此如果它們重疊，將截斷工作標題。
- 修復了導致系統停止回應的各種問題。
- 在某些語言中，不同位置的文字不再被截斷。
- 該應用程式現在預設以全螢幕模式執行。
- 修復了有時會導致某些裝置在主頁上忽略掃描的問題。

### <a name="known-issues-in-version-2070"></a>2.0.7.0 版本中的已知問題

- 在某些裝置上，當您啟動應用程式或開始工作時，您會收到以下錯誤訊息：「找不到指定大小的合適檢視表」。 如果您在任何裝置上看到此錯誤訊息，則必須在該裝置上將 Warehouse Management 行動應用程式降級到版本 2.0.6.0 並等待升級，直到該應用程式的下一個版本發佈。

## <a name="version-2060"></a>版本 2.0.6.0

### <a name="new-features-fixes-and-improvements-in-version-2060"></a>版本 2.0.6.0 中的新增功能、修復和改進

此版本引入了以下新增功能、修復和改進：

- 示範模式現在以裝置語言顯示所有標籤。
- 您不太可能收到以下錯誤訊息：「找不到適合指定大小的檢視表。」
- 增加了工作卡的最小高度 (對於設定三個或更少欄位以顯示在工作清單中的情況)。
- 已改進詳細資料卡底部的邊距 (淡出)。
- 現在可以正常處理與伺服器交換的 XML 檔案中的無效符號。 (例如，現在可以正常處理非列印字元，並且不再導致應用程式停止回應。)
- 現在可以正常處理提交伺服器要求時的 HTTP 錯誤 (例如「錯誤 503」)。
- 顯示錯誤時，下拉式方塊控制項不再自動顯示選項清單。
- 應用程式不再因使用者設定中選擇的顯示方向而停止回應。
- 產品影像現在顯示在自助服務環境中。 (此變更僅適用於低解析度版本。 文件管理服務不支援自助環境中的全尺寸影像。)
- 已修復涉及零數量短缺領料的問題。
- 當詳細資料卡顯示多個相同的欄位時，應用程式不再停止回應。

### <a name="known-issues-in-version-2060"></a>2.0.6.0 版本中的已知問題

此版本中存在以下已知問題：

- 應用程式 (尤其是工作清單) 會隨著時間的推移而變慢。
- **Windows 版本：** 在 Windows 上使用 USB 掃描槍進行掃描時，不一致的結果會導致掃描的符號混淆。

## <a name="version-2050"></a>版本 2.0.5.0

此版本引入了以下新增功能、修復和改進：

- 用戶端密碼不再隱藏在連線設定的設定中。
- 您現在可以長按任何文字以使其完全顯示。
- 已改進缺少儲存權限時的錯誤訊息。
- 為某些流程新增了新的控制序列。
- 提交按鈕不再因視窗大小而錯誤地變為可用。
- 當使用較大的按鈕尺寸時，滑桿現在可以在較小的螢幕上進行。
- 四個按鈕覆蓋不再被切斷。
- 鍵盤現在支援刪除按鈕。
- 已修復按下鍵盤時可能出現的亮度問題。
- 已修復各種示範資料問題。
- 已修復影響詳細資料頁面上的數字欄位的問題。
- 螢幕鍵盤不再偶爾在某些裝置上消失。
- 已修復各種使用者介面 (UI) 錯誤，例如影響背景色彩和定位的錯誤。
- 已改進俄文使用者介面。
- 已修復導致系統停止回應的各種問題。
- 已修復與重新打開計算器相關的問題。
- **Android 版本：** 已修復導致 Android 4.4 在啟動時停止回應的問題。
- **Android 版本：** 最小縮放比例已降至 50%。

## <a name="version-2040"></a>版本 2.0.4.0

版本 2.0.4.0 是 Warehouse Management 行動應用程式的第一個正式發行的版本。

### <a name="new-features-fixes-and-improvements-in-version-2040"></a>版本 2.0.4.0 中的新增功能、修復和改進

此版本引入了預覽版中未提供的以下新增功能、修復和改進：

- 如果詳細資料卡包含兩個具有相同資料的標籤，則會隱藏其中一個標籤。
- 現在預設顯示特殊字元，隱藏它們的選項已從使用者設定中移除。
- 停用的提交按鈕現在在精簡型手持檢視表中顯示為不可用。
- 對控制項排序邏輯的變更可確保跨裝置更順利地縮放。 因此，不需調整字體或按鈕的縮放比例。
- 預設色彩主題已變更為 *深色*。
- 已在功能區檢視表中新增了停用提交按鈕的缺失圖示。
- 逾時例外狀況現在將您帶到連線頁面，而不是顯示內嵌錯誤。
- 如果沒有可用的提交動作 (例如 **確定**、**是**、**接受**、**完畢** 或 **完成**)，將停用提交按鈕。
- 已改善應用程式穩定性。
- 修復了安全性漏洞 [CVE-2021-26701](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-26701)。
- **Windows 版本：** 已修復在 Windows 上調整視窗大小後功能表無回應的問題。

### <a name="known-issue-in-version-2040"></a>版本 2.0.4.0 中的已知問題

此版本中存在以下已知問題：

- 此版本使用 Android 4.4 的裝置存在問題。 在此 Android版本上使用應用程式時，可能會發生問題。
