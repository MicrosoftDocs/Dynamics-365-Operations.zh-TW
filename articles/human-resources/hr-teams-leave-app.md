---
title: 管理 Teams 的請假要求
description: 本主題說明如何在 Microsoft Teams 的 Dynamics 365 Human Resources 應用程式要求休假。
author: twheeloc
ms.date: 12/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeaveAbsenceWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-05-18
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d004e33d01dbd171626d7e23f93df081bc0210a9
ms.sourcegitcommit: 70ac76be31bab7ed5e93f92f4683e65031fbdf85
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/16/2021
ms.locfileid: "8451974"
---
# <a name="manage-leave-requests-in-teams"></a>管理 Teams 的請假要求

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Microsoft Teams 的 Dynamics 365 Human Resources 應用程式讓您快速要求休假並且檢視 Microsoft Teams 裡，您的休假餘數資訊。 您可以與 Bot 互動和要求資訊，並開始請假要求。 **休假** 索引標籤提供更詳細資訊。 您也可以在 Teams 和人力資源應用程式以外的聊天室傳送給人們有關您接下來的休假資訊。

## <a name="install-the-app"></a>安裝 App

您可以在 Teams 商店尋找 Dynamics 365 Human Resources App。

1. 在 Microsoft Teams，瀏覽到 應用程式清單。
 
2. 搜尋 Dynamics 365 Human Resources，然後選取 **人力資源** 圖格。

> [!NOTE]
> 自 2021 年十二月 20 日開始，Microsoft 租用戶託管的人力資源應用程式 Bot 服務 (版本 1.1.4) 將除役。 最新擴允版 (版本 1.1.5) 開放安裝。 更多資訊，請參閱[管理 Teams 的請假要求](hr-admin-teams-leave-app.md#update-app)。

3. 選取 **新增** 按鈕安裝應用程式。

如果應用程式未自動讓您登入，選取 **設定** 索引標籤登入。

> [!NOTE]
> 如果您沒有看到登入對話方塊，請更新您的瀏覽器設定為允許彈出式視窗。 

如果您可以存取多個 Human Resources 執行個體，您可以在 **設定** 索引標籤選取希望連線的環境。

> [!NOTE]
> 應用程式現在支援系統管理員資訊安全角色。
 
## <a name="use-the-bot"></a>使用 Bot

應用程式安裝後會出現歡迎訊息，讓您知道 Bot 可以代表您執行的動作類型。

> [!NOTE]
> 當您第一次與機器人互動時，您可能需要登入。 如果您沒有看到登入對話方塊，請更新您的瀏覽器設定為允許彈出式視窗。

您可以要求 Bot：

- 檢視您目前的請假餘數。 例如，傳送訊息寫明，"檢視請假餘數。"

- 開始為您要求請假。 例如，傳送訊息寫明，"請假" 或 "我想在下週四和下週五休假"，更具體要求假日請假類型的請假。 

  ![在 Teams 聊天室提出請假要求。](./media/hr-teams-leave-app-initiate.png)

- 聊天室 Bot 將為您填寫請假要求。 選取 **要求休假** 並且編輯您的要求細節。

   如果您希望提交相同日期多個請假類型的請假要求，請從 **更多選項** 功能表選取 **單日分割** 選項。 

   如果您在請假單位為天時選取半天假，您可以藉由從 **更多選項** 功能表選取 **半天定義** 選項，指明您是否希望要求上半天休假或下半天休假。
   
   ![半天定義。](./media/HalfDayDefinitions.png)

- 請假要請細節編輯完成後，選取 **提交** 以提交核准。

  ![提交請假要求。](./media/hr-teams-leave-app-submit.png)

## <a name="manage-your-leave-in-teams"></a>管理您在 Teams 的請假

**休假** 索引標籤允許您檢視： 

- 您已經登記每種請假類型的餘數資訊

- 接下來的請假要求

- 休假要求

- 草擬請假要求
 
### <a name="create-a-new-request"></a>建立新要求。

1. 若要建立新請假要求，選取 **新要求**。

2. 輸入您希望休假的天數，然後選取 **新增**。

   ![人力資源 Teams 請假應用程式新增休假。](./media/TimeOffHours.png)

3. 如果適用，請輸入原因代碼。 也輸入任何留言和新增任何附件。

4. 如果您希望提交相同日期不同請假類型的多項請假要求分錄項，請從 **更多選項** 功能表選取 **單日分割** 選項。

5. 選取 **半天定義** 選項指明您希望要求前半天休假或後半天休假。 此選項開放在請假要求以天為單位，並且要求量為 0.5 天時使用。

6. 輸完資訊後，輸入 **提交** 以提交核准。 你也可以輸入 **儲存為草稿**，稍候返回操作。

### <a name="manage-draft-requests"></a>管理草稿要求

1. 選取 **草稿** 索引標籤。

2. 選取鉛筆編輯要求，或選取垃圾桶刪除要求。

3. 進行任何必要的更改。 輸完資訊後，鍵入 **提交** 以提交核准。 你也可以選取 **儲存為草稿**，稍候返回操作。
   
### <a name="respond-to-teams-notifications"></a>回應 Teams 通知

當您或身為核准者的背景工作角色提交請假要求時，您將在 Teams 的人力資源應用程式收到通知。 您可以選取通知檢視請假要求。 通知也會在 **Chat** 區域出現。

如果您是核准者，您可以在通知中選取 **核准** 或 **駁回**。 您也可以提供選擇性訊息。

## <a name="send-upcoming-time-off-information-to-your-coworkers"></a>傳送接下來的休假資訊給您的同事

待您為 Teams 安裝 Human Resources 應用程式後，您可以輕鬆地傳送有關接下來的休假資訊給 Teams 或聊天的同事。

1. 在團隊或 Teams 的聊天中，選取聊天視窗下方的人力資源按鈕。

   ![聊天視窗下方的人力資源按鈕。](./media/hr-teams-leave-app-chat-button.png)

2. 選取您要共用的請假要求。 如果您希望共用請假要求草稿，請先選取 **草稿**。

您的請假要求將顯示在聊天中。

如果您共用草稿要求，它將顯示為草稿。

## <a name="view-your-teams-leave-calendar"></a>檢視您的團隊的請假行事曆

如果您是下屬的經理，您可以檢視您的團隊的已核准和待核定休假。

1. 請在 Teams 的人力資源應用程式，選取 **休假**。

2. 選取 **Team 行事曆**。 行事曆顯示您的下屬的已核准和待核定休假。

   > [!NOTE]
   > 如果您看不到團隊行事曆，請您的管理員啟用它。 更多資訊，請參閱[安裝和設定](hr-admin-teams-leave-app.md#install-and-setup)。

## <a name="supported-languages"></a>支援的語言

Teams 的 Dynamics 365 Human Resources 應用程式支援語言如下：

| 地區設定識別碼 | 語言 |
| --- | --- |
| de-DE | 德文 (德國) |
| es-ES | 西班牙文 (西班牙) |
| es-MX | 西班牙文 (墨西哥) |
| fr-CA | 法文 (加拿大) |
| fr-FR | 法文 (法國) |
| it-IT | 義大利文 (義大利) |
| nl-NL | 荷蘭文 (荷蘭) |
| pt-BR | 葡萄牙文 (巴西) |
| tr-TR | 土耳其文 (土耳其) |
| zh-CN | 中文 (簡體) |

## <a name="troubleshooting"></a>疑難排解

如果您在登入或使用 Dynamics 365 Human Resources Teams 應用程式有困難，請嘗試按照這些疑難排解說明操作。 如果疑難排解後仍有問題，請聯絡支援中心。 更多資訊，請參閱[取得支援](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md)。

### <a name="cant-sign-into-the-human-resources-app-in-teams"></a>無法登入 Teams 的人力資源應用程式

如果您無法登入應用程式，可能是您用來登入 Microsoft Teams 的帳戶與 Dynamics 365 Human Resources 的員工記錄尚未產生關聯。 請聯絡您的系統管理員確保您的員工記錄已正確產生關聯。

### <a name="cant-find-the-dynamics-365-human-resources-environment-in-settings"></a>設定中找不到 Dynamics 365 Human Resources 環境

如果您無法選取正確的 Dynamics 365 環境，可能是使用者記錄尚無法正確同步的緣故。 請聯絡您的系統管理員重建使用者記錄並與使用者憑證產生關聯。 接著在幾分鐘內嘗試登入 Microsoft Teams 人力資源應用程式。

### <a name="translations-dont-display-correctly"></a>翻譯無法正確顯示

如果翻譯未如預期顯示，請確定您在 Teams 選取的語言與人力資源 **使用者選項** 選取的語言相符。

請在 Teams 的 **設定** 查看 **應用程式語言**。

![Teams 設定。](./media/hr-teams-leave-app-settings.png)

請在人力資源選取 **設定** 然後選取 **使用者選項**。 驗證 **語言** 欄位是否與 Teams 的 **應用程式語言** 欄位相符。

![人力資源使用者選項。](./media/hr-teams-leave-app-user-options.png)

如果您仍然經歷翻譯問題，請告訴我們。 相關資訊，請參閱[取得對財務和營運應用程式或 Lifecycle Services (LCS) 的支援](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md?toc=%2fdynamics365%2fhuman-resources%2ftoc.json)。

### <a name="error-when-approving-leave-requests-in-the-human-resources-app-in-teams"></a>在 Teams 的人力資源應用程式中核准請假要求時出錯

如果您正嘗試在 Teams 應用程式核准請假要求時收到錯誤，請嘗試疑難排解步驟如下：

1. 驗證您用來登入 Microsoft Teams 的帳戶是否與您存取 Dynamics 365 Human Resources 的相同。

2. 藉由檢查請假核准的工作流程設定驗證您是否為有效的要求核准者。 更多有關請假要求工作流程資訊，請參閱[建立請假要求工作流程](hr-leave-and-absence-workflow.md)。

### <a name="leave-approvers-dont-receive-teams-chat-messages-to-approve-leave-requests"></a>請假核准者不會收到 Teams 聊天訊息來核准請假要求

1. 確保已啟用環境和使用者通知。 更多資訊，請參閱[針對 Teams 的人力資源應用程式啟用通知](hr-admin-teams-leave-app.md#enable-notifications-for-the-human-resources-app-in-teams)和[針對個別使用者開啟或關閉 Teams 通知](hr-admin-teams-leave-app.md#turn-teams-notifications-on-or-off-for-individual-users)。

2. 確保使用者登入 **聊天** 索引標籤的憑證與他們用來核准請假要求的相同。 使用 "登出" 訊息，然後以正確的憑證 "登入"。

3. 如果問題仍然存在，請檢查身為系統管理員的 **商業事件系統** 批次工作狀態。 如果它在 **等待** 或 **執行** 階段，幾分鐘內再檢查一次。 如果狀態保持不變，請記錄支援票證，方便我們的團隊幫助修正問題。

## <a name="known-accessibility-issues"></a>已知的協助工具問題

Teams 的人力資源應用程式存在下列的協助工具問題，我們正努力在未來發行版本中修正。

| 問題 | 應變方法或解釋 |
| --- | --- |
| 在桌面上縮放 400%，讓視圖隱藏一些動作按鈕。 | 我們建議改用放大鏡，直到我們可以支援此縮放等級為止。 |
| 請在 **休假** 索引標籤上，由 Voiceover 在讀取休假格線標題時宣告按鈕動作。 | 格線的標題和元素按年份分組，並且可以收合。 Voiceover 將這份簡報詮釋為可執行動作的項目，但它不是。 |
| 瀏覽到 **休假** 索引標籤上的新要求 **原因代碼** 時，有另外的撥動手勢。 | 撥動瀏覽嘗試到達隱藏控制項失敗。 |
| 如果您在行事曆打開或編輯要求時，在 **休假** 索引標籤上撥動，您會到達控制項以外的底部，而不是新要求最上方。 | 當你到達 **前往今天** 時，考慮到將前往控制項末端並往反方向撥動返回最上方。 |
| 當您使用輔助工具或鍵盤瀏覽輸入日期時，**聊天** 索引標籤的焦點會跳回最上方。 | 持續按 Tab 鍵直到您再次觸及輸入區域為止。 |

## <a name="privacy-notice"></a>隱私權注意事項

### <a name="microsoft-language-understanding-intelligent-service-luis"></a>Microsoft Language Understanding Intelligent 服務 (LUIS)

隨著 Microsoft Teams 的 Dynamics 365 Human Resources Bot，分析使用者的文字輸入，了解基本查詢/意圖。 使用者的輸入 (例如 "搜尋帳戶 Contoso") 路由到 Microsoft 的其中一個 Cognitive Service，稱為 Language Understanding Intelligent 服務 (LUIS)。 閱讀更多有關 LUIS  [點選這裡](https://www.luis.ai/)。 LUIS 服務消除或了解使用者輸入的意圖 (此時的用意是尋找資訊) 和目標實體 (此時目標實體是名為 Contoso 的帳戶)。 接著此項資訊傳遞給 Microsoft 的 [Azure Bot Framework](https://azure.microsoft.com/services/bot-service/)，它與來自 Dynamics 365 Human Resources 的資料互動並檢索使用者查詢想要的資訊。 

藉由安裝和允許存取使用 Bot，表示您同意允許 LUIS 服務和 Azure Bot Framework 處理輸入背後的用意，強化會話中的使用者體驗。 LUIS 服務和 Azure Bot Framework，相較於 Dynamics 365 Human Resources，法令遵循等級種類可能繁多。 儘管 LUIS 服務只能存取使用者查詢，並非設計來連接使用者的 Dynamics 365 Human Resources 資料或帳戶，Dynamics 365 Human Resources Bot 使用者可以自願輸入包含客戶資料、個人資料或其他資料的查詢，而此類查詢內容可以傳送到 LUIS 服務和 Azure Bot Framework。 

使用者查詢和訊息內容最多在 LUIS 系統保留 30 天，靜態加密，不用在訓練或服務改善。 閱讀更多有關認知服務 [這裡](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/)。 

若要管理 Microsoft Teams 應用程式管理員設定，請前往 [Microsoft Teams 系統管理中心](https://admin.teams.microsoft.com/)。

### <a name="microsoft-teams-azure-event-grid-and-azure-cosmos-db"></a>Microsoft Teams、Azure 事件格線和 Azure Cosmos DB

在 Microsoft Teams 使用 Dynamics 365 Human Resources 應用程式時，特定客戶資料可能流出您部署租用戶的人力資源服務的地理區域。

Dynamics 365 Human Resources 傳輸員工的請假要求和工作流程任務細節到 Microsoft Azure 事件格線和 Microsoft Teams。 此項資料可儲存在 Microsoft Azure 事件網格長達 24 小時，並將在美國境內處理，傳輸時靜態加密，Microsoft 或其子處理器不會用在訓練或服務改善用途。 若要了解您在 Teams 儲存資料的位置，請參閱：[Microsoft Teams 資料的位置](/microsoftteams/location-of-data-in-teams?preserve-view=true&view=o365-worldwide)。

在人力資源應用程式與聊天 Bot 交談時，對話內容以儲存在 Azure Cosmos DB 並傳輸到 Microsoft Teams。 此項資料可儲存在 Azure Cosmos DB 長達 24 小時，並可以在您部署租用戶的人力資源服務地理區域以外處理，傳輸時靜態加密，並且 Microsoft 或其子處理器不會用在訓練或服務改善用途。 若要了解您在 Teams 儲存資料的位置，請參閱：[Microsoft Teams 資料的位置](/microsoftteams/location-of-data-in-teams?preserve-view=true&view=o365-worldwide)。
 
若要針對貴組織或貴組織內部使用者限制對 Microsoft Teams 人力資源應用程式的存取，請參閱[管理 Microsoft Teams 應用程式權限政策](/MicrosoftTeams/teams-app-permission-policies)。

## <a name="see-also"></a>也請參閱

[下載和安裝 Microsoft Teams](https://support.office.com/article/download-and-install-microsoft-teams-422bf3aa-9ae8-46f1-83a2-e65720e1a34d)</br>
[Microsoft Teams 求助中心](https://support.office.com/teams)</br>
[Teams 的人力資源應用程式](hr-admin-teams-leave-app.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
