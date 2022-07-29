---
title: 分發與排程問卷
description: 本主題說明如何分發您設計的問卷，以便開放給將完成問卷的個人或群組使用。
author: twheeloc
ms.date: 10/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: KMConnectionType, KMKnowledgeCollectorPlanningTabel, SysEmailParameters, HcmLearningWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 17424
ms.assetid: fd8d867a-2446-400a-b91f-ad4085427470
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: dbb069110b46c38a994a7be6276137360b14397a
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452550"
---
# <a name="distribute-and-schedule-questionnaires"></a>分發與排程問卷


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

本主題說明如何分發您設計的問卷，以便開放給將完成問卷的個人或群組使用。 

目前有多種分發問卷的方式：

-   標示問卷為 **有效**。 問卷接著即可開放給所有員工使用，除非設定問卷群組限制存取。
-   指派權利給問卷群組。 問卷隨後即可開放選取群組的所有成員使用。
-   建立規劃的解答工作階段。 問卷只開放特殊人員使用。
-   建立期程。 隨後問卷即可開放多人使用。

## <a name="marking-a-questionnaire-as-active"></a>問卷正標示為有效

藉由設定 **問卷** 頁面上的 **有效** 欄位為 **是**，您可以開放所有員工完成問卷。 受訪者可以多次完成問卷。 如果您希望收集一整年持續性的意見反應，此功能很實用。 例如，您可以製作一份員工可用來針對自助餐廳午餐服務提出意見反應的問卷。

## <a name="questionnaire-groups"></a>問卷群組

您可以設定問卷群組，然後包括應該被分發問卷的受訪者。 

您可以從下列頁面建立問卷群組：

-   **問卷群組** – 唯有問卷群組中的個人才能完成選取的問卷。 例如，您原本的受眾是承包商，因此您建立一個專門針對這些受訪者的問卷群組。
-   **問卷群組成員** – 您可以新增人到問卷群組。

若要指派問卷群組給問卷，請在 **問卷** 頁面上，點選 **使用者權利**。 待問卷儲存為有效問卷後，問卷群組成員即可完成問卷。 如果向更大群組推出問券之前，您希望先對選取群組的人測試問券，或者如果您希望確定目標在非常特定的受眾身上，本功能可以幫助您。

## <a name="planned-answer-sessions-in-a-questionnaire"></a>問卷中規劃的解答工作階段

規劃的解答工作階段是您已經設計並選取受訪者的問卷。 

> [!NOTE]
> 在您可以設定規劃的解答工作階段之前，您必須先設計一份問卷。 

您可以在 **規劃的解答工作階段** 頁面上針對個別員工建立規劃的解答工作階段。 頁面上的清單顯示所有已規劃的問卷。 

規劃的解答工作階段也會在 **問卷期程** 頁面上使用，您可以在那裡為多人規畫問卷：

-   員工
-   課程參與者
-   組織單位

每個人只能回答一次問卷。

## <a name="scheduling-a-questionnaire"></a>排程問卷

您可以選擇性地為多名受訪者排程問卷。

### <a name="planning-types"></a>規劃類型

如果您希望為多名受訪者排程規劃好的解答工作階段，您需要規劃類型。 規劃類型用來對問卷期程分類。 例如，您可以排程問券達到下列目的：

-   評估
-   問卷
-   測試

您可以在 **問卷期程** 頁面上指明問券期程的規劃類型。

### <a name="reference-types-for-questionnaire"></a>問卷的參考類型

您可以使用參考類型來輸入排程問卷時，您可能選取的受訪者標準。 

使用 **參考類型** 頁面設定問卷的參考類型。 每個參考類型對應 Microsoft Dynamics 365 Finance 中的資料表。 建立問卷期程時，您可以指明資料表的個別記錄或將與問卷相關聯的一系列記錄。 

例如，如果您選取課程資料表，您可以決定問卷針對哪一門特定課程。 當您為課程資料表設定參考時，**課程** 頁面上的一些欄位和按鈕會變為開放使用。

### <a name="questionnaire-schedules"></a>問卷期程

您可以根據參考類型，使用問卷期程針對一組使用者產生多個規劃的解答工作階段。 在 **問卷期程** 頁面上建立期程。 選取規劃類型以便對期程分門別類，也選取應該用來查詢特定使用者的系統的參考類型。 例如，如果您設定參考類型為課程資料表，您可以在 **參考** 欄位選取特定課程。 

點選 **設定細節** 以便選取問卷和其他標準。 例如，如果問卷是評估教師，則須指明教師姓名作為標準。 等您完成輸入設定細節後，系統會針對納入查詢的使用者產生規劃的解答工作階段。 

點選 **規劃的解答工作階段** 檢視期程的解答工作階段。 接著您可以手動建立額外的規劃解答工作階段或刪除尚未解答的規劃解答工作階段。 

點選 **功能**&gt;**開始** 在相關的規劃解答工作階段中，開放使用者填寫問卷。 點選 **解答** 檢視已完成的問卷回應。 您可以選擇性將問卷期程設定、規劃的解答工作階段和解答複製到新問卷排程。

## <a name="notifying-respondents-about-questionnaires-that-are-available-to-them"></a>通知受訪者開放他們填寫的問卷
當您分發問卷時，您必須通知受訪者問券已經開放他們填寫。 

### <a name="notifying-respondents-about-a-planned-answer-session"></a>通知受訪者規劃的解答工作階段

如果您使用規劃的解答工作階段，您必須直接通知本人，例如打電話或電子郵件。

### <a name="notifying-respondents-about-a-scheduling"></a>通知受訪者有關排程

使用 **問卷期排** 頁面以準備傳送電子郵件給被指派問卷的所有受訪者。 在 **員工自助服務電子郵件** 索引標籤上輸入電子郵件文字。待期程開始後，點選 **功能**&gt;**傳送電子郵件** 產生並傳送電子郵件給受訪者。 接著受訪者可以登入網站完成問卷。 

> [!NOTE]
> 在您可以使用電子郵件功能之前，您的 IT 系統管理員必須在 **電子郵件參數** 頁面上輸入電子郵件設定。

## <a name="ending-a-scheduled-questionnaire"></a>結束已排程的問卷

您可以在所有受訪者已經完成指派的解答工作階段後，結束已排程的問卷。 等到已排程的問卷結束後，您就無法複製它的設定到新期程。 

> [!NOTE]
>   如果一名或多名受訪者尚未完成問卷，但您仍希望結束排程，您必須先將這些受訪者從 **規劃的解答工作階段** 頁面刪除。 接著您可以結束期程。

## <a name="completing-questionnaires"></a>完成問券

待您已經設計和分發問卷後，選取的受訪者可以完成問卷。 您可以從下列兩處位置完成開放您填寫的問卷：

-   請在導覽窗格中點選 **問卷**&gt;**分發**&gt;**完成問卷**。
-   請在 Employee 自助服務中點選 **預計完成的問卷**。

問卷可開放特定使用者或一組使用者，或網路的所有使用者填寫。




[!INCLUDE[footer-include](../includes/footer-banner.md)]
