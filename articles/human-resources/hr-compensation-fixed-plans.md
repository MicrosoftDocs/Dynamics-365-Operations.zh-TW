---
title: 建立固定薪酬計劃
description: 本主題說明您可以建立固定薪酬計劃和註冊員工之前必須設定的組成部份。
author: twheeloc
ms.date: 08/25/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HRCCompGrid, HRCCompRefPointSetup, HRMCompEligibility, HRMCompEvent, HRMFixedCompPlanTable, HcmCompensationWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 15991
ms.assetid: ef8cf992-176c-4c98-9dff-6510e1eb9f1c
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 46dbc167a76782cfa8a72da8ce8bed2ce29e4dc6
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452622"
---
# <a name="create-a-fixed-compensation-plans"></a>建立固定薪酬計劃


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

固定薪酬係指員工的正規薪資或工資總額。 本主題說明您可以建立固定薪酬計劃和註冊員工之前必須設定的組成部份。

可以根據績效、區域和預算增加等因素為您的員工計算固定薪酬金額。 Dynamics 365 Human Resources 支援級距、分級和波段薪酬類型。

## <a name="fixed-compensation-components"></a>固定薪酬組成部份
### <a name="compensation-levels"></a>薪酬等級

您可以使用 **薪酬等級** 為各種工作設定薪酬，幫助保證從事這些工作的員工能獲得公平的報酬。 您可以在 **薪酬等級** 頁面上設定每個級距、分級和波段計劃所需的薪酬等級。 使用 **向上** 和 **向下** 按鈕根據類型以正確的順序放入等級。 藉由設定工作的薪酬等級，您可以幫助保證擔任該工作職位的所有員工都能獲得相同等級的薪酬。

### <a name="reference-points"></a>參考點

**參考點** 是格線中定義各等級薪酬範圍的欄位。 薪酬等級是格線中的各行。 等級類型計劃的典型參考點是最小值、中點和最大值。 您在 **參考點設定** 頁面上建立參考點。

### <a name="compensation-grids"></a>薪酬格線

待您設定等級和參考點後，可以組合起來建立 **薪酬格線**。 請在 **薪酬格線** 頁面上定義有關格線的資訊。 例如，指明格線的設計用途、預計使用的計劃類型和格線必要的參考點或欄位。 待您完成資訊輸入動作後，點選 **薪酬結構** 新增等級和金額到您的格線。 

**秘訣：** 使用薪酬結構上的 **大量更改** 功能設定初始金額，然後跨等級或參考點地按佔比或金額遞增。

### <a name="pay-frequencies"></a>支付頻率

**支付頻率** 用來定義指明員工工資或薪薪的方式 (例如每小時 $10 元和每年 $50,000 元)，以及時薪、週薪、月薪 (12 個月) 和年薪費率之間的轉換。 例如，針對時薪員工採用每週 38 小時工時的公司，設定時薪費率 1、週薪 38、月薪 164.6666666667 和年薪 1,976 的支付頻率。 這些轉換用來計算出現在員工固定薪酬記錄的各種支付費率。

## <a name="fixed-compensation-plans"></a>固定薪酬計劃
您可以設計固定薪酬計劃來組合已經配置的所有組成部份。 若要建立固定薪酬計劃，請打開 **固定薪酬計劃** 頁。 您可以在這裡賦予您的計劃名稱和說明、選取計劃類型 (級距、分級或波段)、選取您預計用在員工支付費率的支付頻率 (每小時金額、每年金額等)，並設定一些控制薪酬處理方式的選項。 

**超出容差範圍** 設定讓您指明確定有關最小和最大薪酬金額之間的嚴謹程度。 **硬** 容差要求薪酬在預定等級定義的範圍內。 **軟** 容差則在薪酬金額超出範圍時提醒您，但允許您繼續。 如果您將容差設定為 **無**，您可以輸入員工的任何薪酬金額，不會收到警告或錯誤訊息。 

**錄用規則** 設定允許您指明所有員工是否都應該獲得相同的加薪幅度，不管錄用他們的日期 (**錄用規則** = **無**)，或者員工是否應該獲得根據他們在週期內僱用的時間長短獲得某個佔比的獎勵 (**錄用規則** = **佔比**)。 

**範圍利用率矩陣** 很有用，尤其是您希望縮短員工抵達其範圍中點的時間，或者拉長員工抵達範圍中最大參考點的時間時。 例如，您希望給薪資範圍內底線 25% 的員工 110% 的目標獎勵，但您又希望給薪資範圍內前 25% 的員工 80% 的目標獎勵，為了防止他們太快抵達最大值。 

待您定義固定薪酬計劃的基本準則，您就能設定計劃的薪酬結構。 點選 **設定薪酬**。 打開的對話方塊滑條會給您三個選項：

-   憑藉參考點設定並賦予格線名稱來 **建立新的薪酬矩陣**。
-   憑藉製作您可以當成起始點使用的既有格線，**建立新的薪酬矩陣**。
-   已經定義的 **使用既有的薪酬矩陣**。 如果格線更改，則使用相同格線的所有薪酬計劃都會收到更新版。

待您選取好一個選項後，**薪酬結構** 頁面會打開，此時您可以更改為新的薪酬格線或既有的薪酬格線。

## <a name="fixed-compensation-enrollment"></a>固定薪酬註冊
### <a name="determine-who-is-eligible-for-the-plan"></a>判定具備享有計劃資格的人

幫員工註冊固定薪酬計劃的第一步是判定具備享有計劃定義的薪酬的員工。 我們必須先判定您的資格，您才能指派計劃給任何員工。 若要設定資格，請打開 **資格規則** 頁。 您會在這裡為薪酬計劃建立新資格規則，並且定義員工必須符合才能具備享受計劃資格的標準。 您可以根據部門、工會、薪酬區域 (位置)、工作、工作職能、工作類型或薪酬等級限制資格。 只有符合資格規則設定的所有條件的員工才能註冊薪酬計劃。 

**注意事項：** 資格規則用來判定固定和變動薪酬計劃的資格。 

資格規則考量 **工作**、**位置** 和 **員工** 記錄中的特定欄位，判定員工是否具備享有薪酬計劃的資格。

-   **工作** 頁面上的資格規則考量會考量下列欄位：
    -   **工作** 欄位
    -   **職位分類** 索引標籤上的 **職能** 和 **工作類型** 欄位
    -   **薪酬** 索引標籤上的 **等級** 欄位
-   **職位** 頁面上的資格規則會考量 **部門** 和 **薪酬區域** 欄位。

資格規則也會考量與員工相關聯的工會 (請在 **員工** 頁面上的 **背景工作角色** 索引標籤上點選 **個人資訊**&gt;**工會**)。

### <a name="define-fixed-compensation-actions"></a>定義固定薪酬動作

**固定薪酬動作** 是用在您設定或套用更改到員工的固定薪酬時。 固定薪酬動作讓您提供薪酬和福利經理可以執行動作類型的描述性名稱。 不同的動作類型背後的邏輯特殊，因此可以在特定的時間使用。 

例如，當為員工設定固定薪酬時，只能使用類型為 **錄用/重新錄用** 的動作。 此時您可能希望建立三個不同的 **錄用/重新錄用** 類型動作，並且命名它們為 **錄用**、**重新錄用** 和 **轉調**。 然後，您可以更詳細解釋給員工固定薪酬或更改固定薪酬的原因。

### <a name="enroll-the-employee"></a>註冊員工

您現在可以指派員工到固定薪酬計劃。 打開 **員工** 頁面，然後選取要註冊薪酬計劃的員工。 請在動作窗格上點選 **薪酬**&gt;**固定計劃**。 您現在可以為該名員工建立新的固定薪酬動作。 

**注意事項：** **薪酬計劃** 欄位只會顯示按照每項計劃設定的資格規則，員工具備資格的計劃。 如果沒有為計劃設定資格規則，將沒有員工具備計劃註冊資格。 

按照分級或波段類型的薪酬計劃所指定的薪酬金額會先驗證是否在員工任職工作預定薪酬等級的最小和最大參考點內。 如果薪酬金額超出允許範圍，會顯示警告或錯誤訊息，一切端賴固定薪酬計劃設定的容差等級。



[!INCLUDE[footer-include](../includes/footer-banner.md)]