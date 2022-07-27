---
title: 使用 Excel 查看和更新實體資料
description: 本主題說明如何在 Microsoft Excel 中打開實體資料，然後使用 Microsoft Dynamics Excel 增益集查看、更新和編輯資料。
author: jasongre
ms.date: 10/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.custom: 267914
ms.assetid: 4e6c7194-a059-4057-bd62-ec0c802c36fd
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d1593206e8e22aed518ebca9bee0772c6620bec9
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8460255"
---
# <a name="view-and-update-entity-data-with-excel"></a>使用 Excel 查看和更新實體資料 

[!include [applies to](../includes/applies-to-commerce-finance-scm.md)]

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]


本主題說明如何在 Microsoft Excel 中打開實體資料，然後使用 Microsoft Dynamics Excel 增益集查看、更新和編輯資料。 若要打開實體資料，您可以從 Excel 或財務和營運應用程式開始。

透過在 Excel 中打開實體資料，您可以使用 Excel 增益集快速輕鬆地查看和編輯資料。 此增益集需要 Microsoft Excel 2016 年或更新版本。

> [!NOTE]
> 如果您的 Microsoft Azure Active Directory (Azure AD) 租使用者設定為使用 Active Directory 同盟服務 (AD FS)，您必須確保已套用 Office 2016 年 5 月更新，以便 Excel 增益集可以正確登入。

若要進一步了解有關如何使用 Excel 增益集，請觀看短片[為頁頭和線條圖案建立 Excel 範本](https://youtu.be/RTicLb-6dbI)。

## <a name="open-entity-data-in-excel-when-you-start-from-a-finance-and-operations-app"></a>從財務和營運應用程式啟動時在 Excel 中打開實體資料
1. 在財務和營運應用程式的頁面上，選取 **在 Microsoft Office 中開啟**。

    如果頁面的根資料來源 (資料表) 與任何實體的根資料來源相同，則會為頁面產生預設的 **在 Excel 中打開** 選項。 **在 Excel 中打開** 可以在常用頁面上找到選項，例如 **所有廠商** 和 **所有客戶**。
 
2. 選取 **在 Excel 中打開** 選項，然後打開產生的活頁簿。 此活頁簿具有實體的繫結資訊、指向您環境的指針和指向 Excel 增益集的指針。
3. 在 Excel 中，選取 **啟用編輯** 以啟用 Excel 增益集執行。 Excel 增益集在 Excel 視窗右側的窗格中執行。
4. 如果您是第一次執行 Excel 增益集，請選取 **信任此增益集**。
5. 如果系統提示您登入，請選取 **登入**，然後使用您用於登入財務和營運應用程式的相同認證進行登入。 Excel 增益集將使用瀏覽器中以前的登入內容並自動讓您登入 (如果可以)。 (如需基於作業系統使用之瀏覽器的相關資訊，請參閱[Office 增益集使用的瀏覽器](/office/dev/add-ins/concepts/browsers-used-by-office-web-add-ins.)為確保登入成功，請驗證 Excel 增益集右上角的使用者名。 

Excel 增益集會自動讀取您選取的實體的資料。 請注意，在 Excel 增益集將其讀取之前，活頁簿中不會有任何資料。

## <a name="open-entity-data-in-excel-when-you-start-from-excel"></a>從 Excel 啟動時在 Excel 中打開實體資料
1. 在 Excel 中，在 **插入** 索引標籤，在 **增益集** 組，選取 **Store** 打開 Office Store。
2. 在 Office Store 中，搜尋關鍵字 **Dynamics**，然後選取 **Microsoft Dynamics Office 增益集** (Excel 增益集) 旁邊的 **新增**。
3. 如果您是第一次執行 Excel 增益集，請選取 **信任此增益集** 以啟用 Excel 增益集來執行。 Excel 增益集在 Excel 視窗右側的窗格中執行。
4. 選取 **新增伺服器資訊** 打開 **選項** 窗格。
5. 在您的瀏覽器中，複製目標財務和營運應用程式實體的 URL，將其貼到 **伺服器 URL** 欄位，然後刪除主機名稱之後的所有內容。 產生的 URL 應該只有主機名稱。

    例如，如果 URL 是 `https://xxx.dynamics.com/?cmp=usmf&amp;mi=CustTableListPage`，請刪除所有東西，除了 `https://xxx.dynamics.com`。

6. 選取 **確定**，然後選取 **是** 以確認更改。 Excel 增益集重新啟動並載入中繼資料。

    **設計** 按鈕現在可提供。 如果 Excel 增益集有 **載入小程式** 連結，您可能沒有以正確的使用者身份登入。 如需解決此問題的相關資訊，請參閱[載入小程式](../office-integration/office-integration-troubleshooting.md#issue-the-excel-add-in-loads-but-instead-of-showing-data-it-displays-load-applets-in-the-task-pane)疑難排解分錄。

7. 選取 **設計**。 Excel 增益集擷取實體中繼資料。
8. 選取 **新增資料表**。 出現實體清單。 該實體以「名稱 - 標籤」格式列出。
9. 在清單中選取一個實體，例如 **客戶 - 客戶**，然後選取 **下一個**。
10. 若要將 **可用欄位** 清單中的欄位新增到 **選定欄位** 清單，請選取該欄位，然後選取 **新增**。 或者，按兩下點選 **可用欄位** 清單。
11. 將欄位新增到 **選定欄位** 清單後，請確保游標位於工作表中的正確位置 (例如，儲存格 A1)，然後選取 **完成**。 然後選取 **完成** 退出設計工具。
12. 選取 **重新整理** 提取一組資料。

## <a name="view-and-update-entity-data-in-excel"></a>在 Excel 中查看和更新實體資料
Excel 增益集將實體資料讀取活頁簿後，您可以隨時透過選取在 Excel 增益集中的 **重新整理**。

## <a name="edit-entity-data-in-excel"></a>在 Excel 編輯實體資料
您可以根據需要更改實體資料，然後透過在 Excel 增益集中選取 **發佈** 將其發佈回財務和營運應用程式。 若要編輯記錄，請在工作表中選取一個儲存格，然後更改儲存格值。 若要新增新記錄，請執行以下步驟之一：

- 點選資料來源表中的任意位置，然後選取在 Excel 增益集中的 **新建**。
- 點選資料來源表最後一列中的任意位置，然後按 Tab 鍵，直到游標移出該列的最後一欄並建立新列。
- 點選資料來源表正下方資料列中的任意位置，然後開始在儲存格中輸入資料。 當您將焦點移出該儲存格時，該資料表會展開以包含新列。
- 對於標題記錄的欄位繫結，選取其中一個欄位，然後選取在 Excel 增益集中的 **新建**。

請注意，只有在工作表中繫結了所有關鍵欄位和必填欄位，或者使用篩選條件填入了預設值時，才能建立新記錄。

若要刪除記錄，請執行以下步驟之一：

- 按右鍵點選應刪除的工作表列旁邊的列號，然後選取 **刪除**。
- 按右鍵點選工作表列中應刪除的任意位置，然後選取 **刪除**&gt;**資料表列**。

如果已將資料來源新增為相關資料來源，則在該行之前發布標題。 如果其他資料來源之間存在相依性，您可能必須更改預設發佈順序。 若要更改發佈順序，請在 Excel 增益集中，選取 **選項** 按鈕 (齒輪符號)，然後，在 **資料連接器** FastTab，選取 **設定發佈順序**。

## <a name="add-or-remove-columns"></a>新增或移除資料欄
您可以使用設計工具來調整自動新增到工作表的資料欄。

> [!NOTE]
> 如果 Excel 增益集中的 **篩選** 按鈕下方未顯示 **設計** 按鈕，則必須啟用資料來源設計工具。 選取 **選項** 按鈕 (齒輪符號)，然後選取 **啟用設計** 核取方塊。

1. 在 Excel 增益集中，選取 **設計**。 列出了所有資料來源。
2. 在資料來源旁邊，選取 **編輯** 按鈕 (鉛筆符號)。
3. 在 **選定欄位** 清單，根據需要調整欄位清單：

    - 若要將 **可用欄位** 清單中的欄位新增到 **選定欄位** 清單，請選取該欄位，然後選取 **新增**。 或者，按兩下點選 **可用欄位** 清單。
    - 若要從 **選定欄位** 清單中刪除欄位，請選取該欄位，然後選取 **刪除**。 或者，按兩下點選該欄位。
    - 若要更改 **選定欄位** 清單中的欄位順序，請選取一個欄位，然後選取 **向上** 或 **向下**。

4. 若要將更改套用到資料來源，請選取 **更新**。 然後選取 **完成** 退出設計工具。
5. 如果您新增了欄位 (欄)，請選取 **重新整理** 提取一組更新的資料。

## <a name="change-the-publish-batch-size"></a>更改發佈批次大小
當使用者使用 Excel 增益集發佈對資料記錄的更改時，將分批送出更新。 預設發佈批次大小為 100 列。 在 10.0.17 及更高版本中，**允許在 Excel 增益集中設定發布批次大小** 功能使您可以彈性控制發布批次大小。

系統管理員可以透過在 **Office 應用程式參數** 頁面的 **應用程式參數** 區塊中設定 **發布批次限制** 欄位來指定「在 Excel 中打開」活頁簿的發布批次大小的系統範圍限制。

也可以使用 Excel 增益集更改單個活頁簿的發布批次大小。

1. 在 Excel 中打開活頁簿。
2. 選取 Excel 增益集右上角的 **選項** (齒輪) 按鈕。
3. 根據需要 **設定發布批次大小** 欄位。 您設定的值必須小於系統範圍的發布批次限制。
4. 選取 **確定**。
5. 儲存活頁簿。 如果在對增益集設定進行更改後不儲存活頁簿，則重新打開活頁簿時這些更改將不會保留。

Excel 活頁簿範本作者可以在將範本上傳到系統之前使用相同的過程來設定範本的發布批次大小。

## <a name="copy-environment-data"></a>複製環境資料

從一個環境讀取活頁簿的資料可以複製到另一個環境。 但是，您不能只更改連線 URL，因為活頁簿中的資料快取將繼續將資料視為現有資料。 相反，您必須使用複製環境資料函數將資料作為新資料發佈到新環境。

1. 選取 **選項** 按鈕 (齒輪符號)，然後，在 **資料連接器** FastTab，選取 **複製環境資料**。 
2. 輸入新環境的伺服器 URL。 
3. 選取 **確定**，然後選取 **是** 以確認動作。 Excel 增益集重新啟動並連線到新環境。 活頁簿中的任何現有資料都被視為新資料。

    重新啟動 Excel 增益集後，會出現一個訊息方塊，指出活頁簿處於環境複製模式。

4. 若要將資料作為新資料複製到新環境中，請選取 **發佈**。 若要取消環境複製作業並查看新環境中的現有資料，請選取 **重新整理**。

## <a name="troubleshooting"></a>疑難排解
有一些問題可以透過一些簡單的步驟來解決。

- **顯示「載入小程式」連結** - 如需此問題的相關資訊，請參閱[載入小程式](../office-integration/office-integration-troubleshooting.md#issue-the-excel-add-in-loads-but-instead-of-showing-data-it-displays-load-applets-in-the-task-pane)疑難排解分錄。 
- **您收到「禁止」訊息** – 如果您在 Excel 增益集載入中繼資料時收到「禁止」訊息，則表示登入到 Excel 增益集的帳戶無權使用目標服務、實體或資料庫。 若要解決此問題，請驗證 Excel 增益集的右上角是否顯示正確的使用者名。 如果出現不正確的使用者名稱，請選取它，登出，然後重新登入。
- **Excel 上顯示空白網頁** – 如果在登入過程中打開空白網頁，則該帳戶需要 AD FS，但執行 Excel 增益集的 Excel 版本不夠新，無法載入登入對話方塊。 若要解決此問題，請更新您正在使用的 Excel 版本。 若要在處於延遲通路的企業中更新 Excel 版本，請使用[Office 部署工具](/deployoffice/overview-office-deployment-tool)到[從延遲通道移動到目前通道](/deployoffice/overview-update-channels)。
- **您在發布資料更改時收到逾時** – 如果您在嘗試將資料更改發佈到實體時收到逾時訊息，請考慮減少受影響活頁簿的發布批次大小。 在記錄更改上觸發大量邏輯的實體可能需要以較小的批次發送更新，以幫助防止逾時。


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
