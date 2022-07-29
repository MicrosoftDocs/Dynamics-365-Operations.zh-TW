---
title: Teams 的人力資源應用程式
description: 本主題介紹 Microsoft Teams 裡的 Microsoft Dynamics 365 Human Resources 應用程式。
author: twheeloc
ms.date: 12/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: FeatureManagementWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-05-18
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: ffd6967431227b578e227ee570dbe06c356fb8d6
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452301"
---
# <a name="human-resources-app-in-teams"></a>Teams 的人力資源應用程式


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Microsoft Teams 裡的 Microsoft Dynamics 365 Human Resources 應用程式讓員工得以快速要求休假並且檢視他們在 Microsoft Teams 裡的休假餘額資訊。 員工可以和 Bot 互動要求資訊。 **休假** 索引標籤提供更詳細資訊。 此外，他們可以在人力資源應用程式以外向人們傳送有關 Teams 和聊天室接下來的休假資訊。

![人力資源團隊離開 App Bot。](./media/hr-teams-leave-app-bot.png)

![人力資源 Teams 離開 App “休假” 索引標籤。](./media/hr-teams-leave-app-timeoff-tab.png)

![人力資源休假要求卡。](./media/hr-teams-leave-app-chat-card.png)

## <a name="install-and-setup"></a>安裝和設定

您可以在 Teams 商店尋找 Dynamics 365 Human Resources App。 有關 Teams App 的安裝資訊，請參閱[在 Teams 管理休假要求](hr-teams-leave-app.md)。

有關在 Teams 管理 App 權限的資訊，請參閱[在 Microsoft Teams 管理 App 權限政策](/MicrosoftTeams/teams-app-permission-policies)。

如果您希望您的使用者在 App 檢視休假和缺勤行事曆，您必須在功能管理中啟用 **Teams 休假和缺勤行事曆**。 更多有關啟用功能的資訊，請參閱[管理功能](hr-admin-manage-features.md)。

## <a name="update-app"></a>更新 App
>[!NOTE]
> 自 2021 年 12 月 20 日開始，Microsoft 租使用者託管的人力資源 App Bot 服務將會停止委託。 這不影響開放安裝的最新擴充版本 (版本 1.1.5)。 主要影響將是過時的擴充版本 (版本 1.1.4)。 此版本的聊天 Bot 將停止工作。 **休假** 索引標籤將繼續在兩個擴充版本工作。

1.1.4 版本的聊天 Bot 將停止回應任何訊息。 例如，**登入**、**檢視餘額** 和 **查看休息時間**。 App 必須手動更新到最新版本。 更多資訊，請參閱[更新 Microsoft Teams 的 App](/MicrosoftTeams/apps-update-experience)。

若要更新到版本 1.1.5，請完成步驟如下：
1. 請在 Microsoft Teams 前往 **Apps**。
2. 找出 **人力資源** App。
3. 請選取 **升級**。

您可以藉由前往 **關於** 索引標籤或 **個人 App** 專區查看人力資源 App 版本。 

![人力資源**關於**索引標籤。](./media/HR-teams-about.png)

## <a name="enable-notifications-for-the-human-resources-app-in-teams"></a>在 Teams 的人力資源 App 啟用通知

如果您希望使用者在 Teams App 收到休假要求通知，您必須在 Dynamics 365 Human Resources 啟用通知功能。

>[!NOTE]
>只有登入 Teams 並使用 Dynamics 365 Human Resources Teams App 的使用者將收到通知。

1. 請在人力資源選取 **系統管理**。

2. 請選取 **連結**。

3. 請在 **設定** 下方選取 **系統參數**。

4. 請在 **一般** 索引標籤將 **Teams App 啟用通知** 設定為 **是**。

   ![請在系統參數中啟用 Teams App 通知。](./media/hr-admin-teams-leave-app-enable-notifications.png)

5. 若要開啟所有使用者的 Teams 通知功能，請在收到提示時選取 **是**。

   ![啟用所有使用者的 Teams 通知。](./media/hr-admin-teams-leave-app-notifications-all-users.png)

### <a name="turn-teams-notifications-on-or-off-for-individual-users"></a>開啟或關閉個別使用者的 Teams 通知

在您啟用 Dynamics 365 Human Resources Teams App 的通知功能後，您可以開啟或關閉個別使用者通知功能。

1. 請在人力資源選取 **系統管理**。

2. 請選取 **連結**。

3. 請在 **使用者** 下方選取 **使用者選項**。

4. 請選取 **工作流程** 索引標籤。

5. 設定 **Teams App 啟用通知** 為 **是**，啟用使用者通知或 **否**，停用使用者通知。

   ![請在使用者選項工作流程索引標籤中啟用 Teams App 通知。](./media/hr-admin-teams-leave-app-notifications.png)

6. 選取 **儲存**。

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

## <a name="notes"></a>附註

下列工作項目用於未來版本：

| 工作項目 | 狀態 |
| --- | --- |
| 提交未來日期的休假時餘額不正確。 | 預測功能尚未開放使用。 顯示目前日期的餘額。 |
| 無法取消 **審查中** 要求。 | 此功能目前不支援，將在未來版本新增。 |
| 餘額資訊算到今天為止。 | 系統目前不顯示截至累計期間的餘額，即使它已經在 **休假和缺勤參數** 頁配置。 |

## <a name="troubleshooting"></a>排除障礙

如果使用者在登入或使用人力資源 Teams App 時遇到困難，請嘗試按照這些排除障礙說明操作。 如果疑難排解後仍有問題，請聯絡支援中心。 更多資訊，請參閱[取得支援](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md)。

### <a name="ensure-the-teams-human-resources-application-is-up-to-date"></a>確保 Teams 人力資源應用程式是最新版本
如果你在使用 Teams 人力資源 App 時遇到問題，你必須確認你執行的是最新版本。 最低支援版本 1.1.5。 有關 Teams 應用程式更新方法說明，請參閱[Teams 文件](/MicrosoftTeams/apps-update-experience)。

### <a name="cant-sign-into-the-human-resources-app-in-teams"></a>無法登入 Teams 的人力資源應用程式

如果使用者因為無法登入 App 而聯絡您，請驗證他們在人力資源已有關聯的員工記錄。

### <a name="error-when-approving-leave-requests-in-the-human-resources-app-in-teams"></a>在 Teams 的人力資源應用程式中核准請假要求時出錯

如果使用者嘗試在 Teams App 中核准休假要求時收到錯誤，請嘗試排除障礙步驟如下：

1. 驗證他們的 Teams 帳戶是否與他們用來存取人力資源的帳戶相同。

2. 藉由檢查休假核准的工作流設定來驗證他們是否為有效的要求核准者。 更多有關請假要求工作流程資訊，請參閱[建立請假要求工作流程](hr-leave-and-absence-workflow.md)。

### <a name="leave-approvers-dont-receive-teams-chat-messages-to-approve-leave-requests"></a>請假核准者不會收到 Teams 聊天訊息來核准請假要求

1. 確保已啟用環境和使用者通知。 更多資訊，請參閱[針對 Teams 的人力資源應用程式啟用通知](hr-admin-teams-leave-app.md#enable-notifications-for-the-human-resources-app-in-teams)和[針對個別使用者開啟或關閉 Teams 通知](hr-admin-teams-leave-app.md#turn-teams-notifications-on-or-off-for-individual-users)。

2. 確保使用者登入 **聊天** 索引標籤的憑證與他們用來核准請假要求的相同。 使用 "登出" 訊息，然後以正確的憑證 "登入"。

3. 如果問題仍然存在，請檢查身為系統管理員的 **商業事件系統** 批次工作狀態。 如果它在 **等待** 或 **執行** 階段，幾分鐘內再檢查一次。 如果狀態保持不變，請記錄支援票證，方便我們的團隊幫助修正問題。

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
[管理 Teams 的請假要求](hr-teams-leave-app.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
