---
title: ER 透過採用該格式的新基底版本來升級您的格式
description: 本主題介紹如何維護電子報表 (ER) 格式配置。
author: NickSelin
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: bfcb85d964234063fd3c6a8e5ea29f7b222e966124b48e46b72b04f457c91e6c
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460391"
---
# <a name="er-upgrade-your-format-by-adopting-a-new-base-version-of-that-format"></a>ER 透過採用該格式的新基底版本來升級您的格式

[!include [banner](../../includes/banner.md)]

以下步驟說明了系統管理員或電子報表開發人員角色的使用者如何維護電子報表 (ER) 格式配置。 此過程說明如何根據從配置提供者 (CP) 接收的格式建立格式的自訂版本。 它還解釋了如何採用該格式的新基底版本。

若要完成這些步驟，您必須先完成「建立配置提供者並將其標記為作用中」和「使用建立的格式產生用於付款的電子文件」程序中的步驟。 這些步驟可以在 GBSI 公司進行。

## <a name="select-format-configuration-for-customization"></a>選取格式配置進行自訂
1. 進入組織管理 > 工作區 > 電子報表。

    在此範例中，樣本公司 Litware, Inc. (https://www.litware.com)將充當配置提供者，支援特定國家/地區的電子支付格式配置。    樣本公司 Proseware, Inc. (http://www.proseware.com)將充當 Litware, Inc. 提供的格式配置的消費者。 Proseware, Inc. 在該國家/地區的某些地區使用格式。  
2. 點選報表設定。
3. 點選顯示篩選條件。
4. 套用以下篩選器： 使用「開頭為」篩選器運算子在「名稱」欄位中輸入篩選器值「BACS (UK fictitious)」。
  
    所選格式配置 BACS (UK fictitious) 歸提供商 Litware, Inc. 擁有。  

5. 點選顯示篩選條件。
6. 在清單中，尋找並選取所需的記錄。

    Proseware, Inc. 將使用狀態為已完成的格式版本進行自訂。  

## <a name="create-a-new-configuration-for-your-custom-format-of-electronic-document"></a>為您的自訂電子文件格式建立新配置
Proseware, Inc. 收到了 BACS (UK fictitious) 配置的 1.1 版，其中包含根據服務訂閱從 Litware, Inc. 產生電子支付文件的初始格式。 Proseware, Inc. 希望開始將此作為其國家/地區的標準，但需要進行一些自訂以支援特定的區域要求。 Proseware, Inc. 還希望保留在 Litware, Inc. 的新版本 (為支援新的國家/地區特定要求而進行更改) 後立即升級自訂格式的能力，並且他們希望以最低的價格執行此升級成本。  

為此，Proseware, Inc. 需要使用 Litware, Inc. 配置 BACS (UK fictitious) 作為基底建立配置。  

1. 關閉頁面。
2. 選取 Proseware, Inc. 使其成為有效提供者。
3. 點選設定為有效。
4. 點選報表設定。
5. 在樹狀結構中，展開「付款 (簡化模型)」。
6. 在樹狀結構中，選取「付款 (簡化模型)\BACS (UK fictitious)」。

    從 Litware, Inc. 選取 BACS (UK fictitious) 配置。Proseware, Inc. 將使用版本 1.1 作為自訂版本的基底。  

7. 點選建立設定即可打開下拉式對話方塊。

    這使您可以為自訂付款格式建立新配置。  

8. 在新建欄位中，輸入「名稱來源：BACS (UK fictitious)，Litware, Inc.」。

    選取衍生選項以確認使用 BACS (UK fictitious) 作為建立自訂版本的基底。  

9. 在名稱欄位，輸入「BACS (UK fictitious custom)」。
10. 在描述欄位，輸入「BACS 廠商付款 (UK fictitious custom)」。

    有效配置提供者 (Proseware, Inc.) 會自動在此處輸入。 此提供者將能夠維護此設定。 其他提供者可以使用此設定，但無法維護它。  

11. 點選建立設定。

## <a name="customize-your-format-for-the-electronic-document"></a>自訂電子文件的格式
1. 點選設計工具。
2. 點選展開/摺疊。
3. 點選展開/摺疊。
4. 在樹狀結構中，選取「Xml\訊息\付款\項目\廠商\銀行」。
5. 點選新增以開啟下拉式對話方塊。
6. 在樹狀結構中，選取「XML\元素」。
7. 在名稱欄位，輸入「IBAN」。
8. 點選確定。
9. 在樹狀結構中，選取「Xml\訊息\付款\項目\廠商\銀行\IBAN」。
10. 點選新增以開啟下拉式對話方塊。
11. 在樹狀結構中，選取「文字\字串」。
12. 點選確定。
13. 在樹狀結構中，選取「Xml\訊息\付款\項目\廠商\名稱\字串」。
14. 在最大長度欄位中，輸入「60」。
15. 點選對應索引標籤。
16. 在樹狀結構中，展開「模型」。
17. 在樹狀結構中，展開「模型\付款」。
18. 在樹狀結構中，展開「模型\付款\債權人」。
19. 在樹狀結構中，展開「模型\付款\債權人\帳戶」。
20. 在樹狀結構中，選取「模型\付款\債權人\帳戶\IBAN」。
21. 在樹狀結構中，選取「Xml\訊息\付款\項目 =  model.Payments\廠商\銀行\IBAN\字串」。
22. 點選繫結。
23. 點選儲存。

## <a name="validate-the-customized-format"></a>驗證自訂格式
1. 點選「驗證」。

    驗證自訂格式配置和資料對應更改以確保所有繫結都正常。  

2. 關閉頁面。

## <a name="change-the-status-of-the-current-version-of-the-custom-format-configuration"></a>更改目前版本自訂格式配置的狀態
將設計格式配置的狀態從草稿更改為已完成，以使其可用於產生付款文件。  

1. 點選更改狀態。

    請注意，所選配置的目前版本處於草稿狀態。  

2. 點選完成。
3. 在描述欄位中，輸入一個值。
4. 點選確定。
5. 在清單中，尋找並選取所需的記錄。

    請注意，建立的配置儲存為已完成的版本 1.1.1。 這意味著它是自訂 BACS (UK fictitious custom) 格式的第 1 版，它基於 BACS (UK fictitious) 格式的第 1 版，它基於付款 (簡化模型) 資料模型的第 1 版。  

## <a name="test-the-customized-format-to-generate-payment-files"></a>測試自訂格式產生付款檔案
在並行的財務和營運應用程式工作階段中完成「使用建立的格式產生用於付款的電子文件」程序中的步驟。 在電子付款方式參數中選取 BACS (UK fictitious custom) 格式。 確保建立的付款檔案包含最近引入的 XML 節點，該節點根據區域要求呈現 IBAN 代碼。  

## <a name="update-the-existing-country-specific-configuration"></a>更新現有的國家/地區特定配置
Litware, Inc. 需要更新 BACS (UK fictitious) 配置並採用新的國家/地區要求來管理電子文件的格式。 稍後，這將包含在此配置的新版本中，將提供給服務訂閱者，包括 Proseware, Inc.  

在實際的服務佈建相關流程中，每個新版本的 BACS (UK fictitious) 都可以由 Proseware, Inc. 從 Litware, Inc. 配置的 LCS 存放庫中匯入。 在此程序中，我們將透過代表服務提供者更新 BACS (UK fictitious) 來模擬這一點。  

1. 關閉頁面。
2. 選取 Litware, inc. 提供者。
3. 點選設定為有效。
4. 點選報表設定。
5. 在樹狀結構中，展開「付款 (簡化模型)」。
6. 在樹狀結構中，選取「付款 (簡化模型)\BACS (UK fictitious)」。

    選取 Litware, Inc. 提供者 BACS (UK fictitious) 擁有的草案版本進行更改以支援新的國家/地區特定要求。  

## <a name="localize-the-base-format-of-the-electronic-document"></a>本地化電子文件的基底格式
假設 Litware, Inc. 支援新的特定國家/地區要求：  

- 每次付款交易中債權人銀行 SWIFT 代碼的值。
- 產生檔案中廠商名稱的文字長度限制為 100 個字元。  
- 新國家/地區特定要求  
- 選取所需配置的草稿版本以引入所需的更改。  


1. 點選設計工具。
2. 點選展開/摺疊。
3. 點選展開/摺疊。
4. 在樹狀結構中，選取「Xml\訊息\付款\項目\廠商\銀行」。
5. 點選新增以開啟下拉式對話方塊。
6. 在樹狀結構中，選取「XML\元素」。
7. 在名稱欄位，輸入「SWIFT」。
8. 點選確定。
9. 在樹狀結構中，選取「Xml\訊息\付款\項目\廠商\銀行\SWIFT」。
10. 點選新增以開啟下拉式對話方塊。
11. 在樹狀結構中，選取「文字\字串」。
12. 點選確定。
13. 在樹狀結構中，選取「Xml\訊息\付款\項目\廠商\名稱\字串」。
14. 在最大長度欄位中，輸入「100」。
15. 點選對應索引標籤。
16. 在樹狀結構中，展開「模型」。
17. 在樹狀結構中，展開「模型\付款」。
18. 在樹狀結構中，展開「模型\付款\債權人」。
19. 在樹狀結構中，展開「模型\付款\債權人\代理程式」。
20. 在樹狀結構中，選取「模型\付款\債權人\代理程式\SWIFT」。
21. 在樹狀結構中，選取「Xml\訊息\付款\項目 =  model.Payments\廠商\銀行\SWIFT\字串」。
22. 點選繫結。
23. 點選儲存。

## <a name="validate-the-localized-format"></a>驗證本地化格式
1. 點選「驗證」。
2. 關閉頁面。

## <a name="change-the-status-of-the-current-version-of-the-base-format-configuration"></a>更改目前版本基底格式配置的狀態
將更新的基底格式配置的狀態從草稿更改為已完成，以使其可用於產生付款文件和更新從它衍生的格式配置。  

1. 點選更改狀態。

    請注意，所選配置的目前版本處於草稿狀態。  

2. 點選完成。
3. 在描述欄位中，輸入一個值。
4. 點選確定。
5. 在清單中，尋找並選取所需的記錄。

## <a name="change-the-base-version-for-the-custom-format-configuration"></a>更改自訂格式配置的基底版本

Proseware, Inc. 獲悉 BACS (UK fictitious) 配置的新版本 1.2 可用於根據最近公佈的國家/地區特定要求產生電子付款檔案。 Proseware, Inc. 希望開始將其用作該國的標準。  

為此，Proseware, Inc. 需要更改自訂配置 BACS (UK fictitious custom) 的基底配置版本。 使用 1.2 版代替 BACS (UK fictitious) 的 1.1 版。  

1. 進入組織管理 > 工作區 > 電子報表。
2. 選取 Proseware, Inc. 提供者以將其標記為作用中。
3. 點選設定為有效。
4. 點選報表設定。
5. 在樹狀結構中，展開「付款 (簡化模型)」。
6. 在樹狀結構中，展開「付款 (簡化模型)\BACS (UK fictitious)」。
7. 在樹狀結構中，選取「付款 (簡化模型)\BACS (UK fictitious)\BACS (UK fictitious custom)」。

    選取由 Proseware, Inc. 擁有的 BACS (UK fictitious custom) 配置。  

    使用所選配置的草稿版本來引入所需的更改。  

8. 點選重訂基底。

    選取要應用的基底配置的新版本 1.2 作為更新配置的新基底。  

9. 點選確定。

    請注意，在合併自訂版本和表示無法自動合併的某些格式更改的新基底版本之間發現了一些衝突。  

## <a name="resolve-rebase-conflicts"></a>解決重訂基底衝突
1. 點選設計工具。
    
    請注意，無法自動解決對廠商名稱文字長度限制的更改。 因此，這顯示在衝突清單中。 對於更新類型的每個衝突，可以使用以下選項：- 套用先前的基底值 (格線頂部的按鈕) 以引入先前的基底版本值 (在我們的範例中為 0)。  - 套用一個基底值 (格線頂部的按鈕) 以引入新的基底版本值 (在我們的範例中為 100)。  - 保留您自己的 (自訂) 值 (在我們的範例中為 60)。  點選套用基底值以應用特定於國家/地區的 100 個字元的廠商名稱文字長度限制。  

    請注意，Proseware, Inc. 和 Litware, Inc. 具有此格式的自訂和本地版本，使用 IBAN 和 SWIFT 代碼以及在管理格式中自動合併的相關組件。  

2. 點選套用基底值。

    點選套用基底值以應用特定於國家/地區的 100 個字元的廠商名稱限制。  

3. 點選儲存。

    儲存格式將從衝突清單中刪除已解決的衝突。  

4. 關閉頁面。

## <a name="change-the-status-of-the-new-version-of-the-custom-format-configuration"></a>更改新版本自訂格式配置的狀態
1. 點選更改狀態。

    將更新的自訂格式配置的狀態從草稿更改為已完成。 這將使格式配置可用於產生付款檔案。 請注意，所選配置的目前版本處於草稿狀態。  

2. 點選完成。
3. 在描述欄位中，輸入一個值。
4. 點選確定。

    注意建立的配置儲存為完成版本 1.2.2：基底 BACS (UK fictitious custom) 格式的版本 2，它基於基底 BACS (UK fictitious) 格式的版本 2，它基於付款 1 的版本 (簡化模型) 資料模型。  

## <a name="test-the-customized-format-for-payment-files-generation"></a>測試付款檔案產生的自訂格式
在並行的財務和營運應用程式工作階段中完成「使用建立的格式產生用於付款的電子文件」程序中的步驟。 在電子付款方式參數中選取建立的「BACS (UK fictitious custom)」格式。 確保建立的付款檔案包含 Proseware, Inc. 最近引入的 XML 節點，該節點根據區域要求提供 IBAN 帳戶代碼。 該檔案還應包含 Litware, Inc. 最近引入的 XML 節點，該節點根據國家/地區要求呈現 SWIFT 銀行代碼。  



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]