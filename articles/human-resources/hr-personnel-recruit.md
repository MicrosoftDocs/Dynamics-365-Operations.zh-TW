---
title: 招募工作求職者
description: 本主題說明如何在 Dynamics 365 Human Resources 招募工作求職者。
author: twheeloc
ms.date: 10/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-12-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 77d37cba84fcd6fb8f93da79b10db2db91d91db0
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452244"
---
# <a name="recruit-job-candidates"></a>招募工作求職者


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Dynamics 365 Human Resources 幫助您管理招募要求。 它也幫助您無縫過渡求職者為員工。 如果貴組織使用分開的招募應用程式，您的招募流程可能包括下列步驟：

- 在人力資源輸入您的招募要求。
- 從招募申請收取人力資源的求職者推薦信。
- 在人力資源完成求職者核准流程。

如果您不用分開的招募應用程式，您也可以在人力資源手動管理求職者。

> [!NOTE]
> 如果您是系統管理員或開發人員，並且希望整合人力資源和第三方招募應用程式申請，請參閱[配置 Dataverse 整合](hr-admin-integration-common-data-service.md)與[配置 Dataverse 虛擬資料表](hr-admin-integration-common-data-service-virtual-entities.md)
>
> 您也可以在 [AppSource](https://appsource.microsoft.com/marketplace/apps?search=recruiting%20dynamics) 尋找招募整合 App。
>
## <a name="enable-recruiting-requests"></a>啟用招募要求

如果您希望在人力資源提交招募要求，您必須先在 **人力資源共用參數** 啟用該功能。

1. 請在 **人事管理** 工作區中選取 **連結**。
2. 請在 **設定** 下方選取 **人力資源共用參數**。
3. 請在 **招募** 下方的 **招募** 索引標籤上，設定 **啟用招募要求** 為 **是**。

## <a name="add-a-recruiting-request-location"></a>新增招募要求位置

如果貴組織位置不只一處，您可以新增，方便要求者可以選取新招募員工將工作的位置。 位置將納入工作佈告。

1. 在搜尋列中，輸入 **招募要求位置**。
2. 選取 **新增**。
3. 在 **招募要求位置** 欄位，輸入位置名稱。

    ![新增招募要求位置。](./media/hr-recruit-0a-add-location.png)

4. 在 **說明**，輸入位置說明。
5. 在 **位置** 下方，選取 **新增**。 如果出現 **新地址** 對話方塊，輸入該處位置的地址。

    ![輸入地址。](./media/hr-recruit-0b-address.png)

6. 在 **聯絡資訊** 下方，輸入該處位置聯絡人資訊。
7. 選取 **儲存**。

## <a name="add-a-recruiting-request"></a>新增招募要求

經理可以在人力資源提交招募要求。 如果您使用分開的招募應用程式，完成這些步驟將傳送招募要求並在該應用程式開始招募流程。 否則，請完成此道程序開始您自己的內部招募流程的工作流程。

1. 選取 **Employee 自助服務**。
2. 選取 **My 團隊** 索引標籤。
3. 選取 **招募要求**。

    ![開始招募要求。](./media/hr-recruit-1-request-to-recruit.png)

4. 填完 **說明**、**工作** 和 **預計開始日期** 欄位。

    ![填完招募要求。](./media/hr-recruit-2-request-to-recruit.png)

5. 選取 **繼續**。 出現您職位的招募要求。
6. 在 **一般** 下方，從 **招募人員** 下拉式清單選取招募人員，然後從 **招募要求位置** 下拉式清單選取位置。
7. 在 **工作** 下方，根據需要更改任何資訊，然後選取 **從工作建立細節**。

    ![從工作建立細節。](./media/hr-recruit-3-create-details-from-job.png)

    招募要求的其餘部分將以您輸入工作的預設資訊填寫。

8. 在 **外部說明** 下方，輸入向外招募的職位說明。
9. 在 **職位** 下方，選取 **新增**，然後針對此項招募要求選取職位。

    ![新增職位。](./media/hr-recruit-4-select-position.png)

10. 在 **技能** 下方，選取 **新增**，然後選取技能。
11. 在 **教育要求** 下方，選取 **新增**，然後從 **教育** 和 **教育程度** 下拉式清單選取值。

    ![新增教育要求。](./media/hr-recruit-5-select-educational-requirements.png)

12. 在 **留言** 下方，根據必要性新增留言。
13. 在 **薪酬** 下方，從 **等級** 下拉式清單選取等級，然後依必要性調整 **低門檻**、**控制點** 和 **高門檻**。
14. 當您的招募要求完成並且準備好開始招募流程時，在選單列選取 **啟動**。

    ![啟動招聘要求。](./media/hr-recruit-6-activate-recruit-request.png)

15. 選取 **儲存**。

## <a name="view-and-edit-your-recruiting-requests"></a>檢視和編輯您的招募要求

如果您是經理，並且希望檢視自己的要求：

1. 選取 **Employee 自助服務**。
2. 選取 **My 團隊** 索引標籤。
3. 請在 **我的團隊資訊** 下方選取 **招募要求** 索引標籤。

    ![選取招募要求索引標籤。](./media/hr-recruit-7-recruiting-requests.png)

4. 若要檢視或編輯招募要求，請在格線中選取。

如果您是 HR 專業人員並希望檢視所有招募要求：

1. 選取 **人事管理**。
2. 選取 **招募要求**。

    ![在人事管理檢視招募要求。](./media/hr-recruit-8-recruiting-requests-personnel-management.png)

3. 若要檢視或編輯招募要求，請在格線中選取。

## <a name="add-or-edit-a-candidate-profile"></a>新增或編輯求職者設定檔

如果貴組織已經整合另一個應用程式管理招募要求，則招募要求會轉傳到該應用程式。 接著，招募應用程式將求職者資訊傳回人力資源。 否則，您可以按照自己的內部招募流程手動輸入求職者資訊。

1. 選取 **人事管理**。
2. 選取 **連結**。
3. 在 **招募** 下方，選取 **求職者**。

    ![檢視求職者。](./media/hr-recruit-9-candidates.png)

4. 若要新增求職者，選取 **新增**。 若要編輯既有的求職者，請從清單選取求職者然後 **編輯**。 出現求職者設定檔。
5. 在 **求職者總結** 下方，根據需要輸入或編輯求職者資訊。
6. 在 **招募要求** 下方，選取連結求職者的招募要求。 然後適當填完 **預計開始日期**、**錄用經理**、**職位** 和 **說明欄位**。

    ![招募要求連結。](./media/hr-recruit-10-link-to-recruiting-request.png)

7. 填完您希望納入求職者記錄的下列區域的資訊：

    - **附註**
    - **專業經驗**
    - **連絡資訊**
    - **學歷**
    - **技能**
    - **證書**
    - **篩選**

8. 選取 **儲存**。

## <a name="hire-a-candidate"></a>錄用求職者

當您準備好錄用求職者時，請按照此程序將求職者轉換為員工。

1. 在 **求職者** 頁面上，選取 **錄用**。

    ![錄用求職者。](./media/hr-recruit-11-hire.png)

2. 在 **錄用新背景工作角色** 頁的 **細節** 下方，填完所有欄位。

    ![輸入新錄用員工的細節。](./media/hr-recruit-12-hire-new-worker.png)

3. 在 **職位細節** 下方根據需要驗證和更改資訊。
4. 在 **到職核對清單** 下方，為此員工選取相關的到職核對清單。
5. 選取 **繼續** 建立員工記錄。

    > [!NOTE]
    > 根據貴組織的工作流程，求職者記錄成為員工記錄之前，可能經歷額外的核准步驟。

## <a name="decide-not-to-hire-a-candidate"></a>決定不錄用求職者

如果您決定不錄用求職者，請按照此程序將他們從審查流程移除。 

1. 在 **求職者** 頁面上，選取 **不錄用**。

    ![不錄用求職者。](./media/hr-recruit-13-do-not-hire.png)

2. 選取 **原因代碼** 並包括任何留言。
3. 選取 **確定**。

## <a name="dismiss-a-candidate"></a>淘汰求職者

必要時，您可以在錄用求職者後淘汰他們。 例如，求職者可能會駁回您的建議或第一天沒有現身。

- 在 **求職者** 頁面上，選取 **淘汰求職者**。

    ![淘汰求職者。](./media/hr-recruit-14-dismiss-candidate.png)

## <a name="see-also"></a>也請參閱

[配置 Dataverse 虛擬資料表](hr-admin-integration-common-data-service-virtual-entities.md)<br>
[組織您的人力](hr-personnel-departments-jobs-positions.md)<br>
[設定工作的組成要素](hr-personnel-jobs.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
