---
title: Dynamics 365 Talent - Attract and Onboard 應用程式退出產品系列
description: 本主題說明 Dynamics 365 Talent - Attract and Onboard 應用程式退出產品系列。
author: twheeloc
ms.date: 01/27/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmBenefitEligibilityDetail, SysPolicyListPage, SysPolicySourceDocumentRuleType, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.scope: Human Resources
ms.custom: 16441
ms.assetid: 4ad0106f-5b07-4fd5-bc1a-5834fa9b198e
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: df33f35f66e356c3c2a99f0d81ebba1d0f34b5d9
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452538"
---
# <a name="dynamics-365-talent-attract-and-onboard-apps-retirement"></a>Dynamics 365 Talent: Attract 和 Onboard 應用程式退出產品系列


2019 年十二月，我們宣布 Dynamics 365 Talent- Attract and Onboard 應用程式於 2022 年二月 1 日退出產品系列，讓我們的客戶有兩年的計劃時間。

更多關於這些 應用程式退出產品系列的資訊，請參閱：
 - [Dynamics 365 Talent - Attract and Dynamics 365 Talent: Onboard 應用程式退出產品系列](https://community.dynamics.com/365/humanresources/b/dynamics365forhumanresources/posts/retiring-dynamics-365-talent-attract-and-onboard-apps)
 - [建構更成功的 Dynamics 365 Human Resources 人力陣容](https://cloudblogs.microsoft.com/dynamics365/bdm/2019/12/06/building-a-more-successful-workforce-with-dynamics-365-human-resources)

我們會繼續支援 Dynamics 365 Human Resources，將幫助我們的客戶獲得多領域建構資料導向員工體驗所需的人力深入解析，例如：

- 薪酬
- 福利
- 請假和缺勤
- 法令遵循
- 薪資表
- 效能意見反應
- 訓練與認證
- 自助服務專項計劃

## <a name="dynamics-365-talent-apps-retirement-faq"></a>Dynamics 365 Talent 應用程式退出產品系統常見問答集

### <a name="what-is-the-user-experience-for-both-dynamics-365-talent---attract-and-onboard-apps-starting-february-1-2022"></a>自 2022 年二月 1 日開始的兩款 Dynamics 365 Talent - Attract and Onboard Apps，使用者體驗如何？

使用者將無法使用這些應用程式，並且會重新導向到退出產品系列頁面。

### <a name="can-customers-continue-to-export-data-for-both-dynamics-365-talent---attract-and-onboard-apps-after-february-1-2022"></a>2022 年二月 1 日以後，客戶還能再繼續匯出這兩款 Dynamics 365 Talent- Attract 和 Onboard Apps 的資料嗎？
  
不能，2019 年十二月已經宣布退出產品系列，並提供必要的匯出功能，期限是 2022 年二月 1 日止。 

### <a name="will-the-customers-data-related-to-both-dynamics-365-talent---attract-and-onboard-apps-in-dataverse-be-deleted-after-february-1-2022"></a>2022 年二月 1 日之後，Dataverse 中與兩款 Dynamics 365 Talent- Attract 和 Onboard 應用程式有關的資料將會刪除嗎？

不會，Dataverse 實體將保留在客戶的 Microsoft Dataverse 環境，即時退出產品系列亦然，除非人力資本管理人才解決方案已經刪除或解除安裝。

### <a name="i-know-the-name-of-the-talent-environment-how-can-i-see-the-attract-and-onboard-data-in-dataverse"></a>我知道人才環境的名稱。 我如何在 Dataverse 查看 Attract 和 Onboard 資料？

1.  登入 Power Apps：https://make.powerapps.com
2.  選取您希望查看 Attract 和 Onboard 資料的環境。
3.  前往 **Dataverse > 資料表**。 
4.  在 **搜尋** 中鍵入 “msdyn_”。 如果您看到以 “msdyn_” + 資料表名稱開頭的資料表清單 (例如：msdyn_candidate)，那麼您已經找到含有 Attract 和 Onboard 資料的環境。

[![Power Apps](./media/Powerapps.png)](./media/Powerapps.png)

### <a name="i-dont-know-the-name-of-the-talent-environment-how-can-i-find-the-environment-that-has-the-data-for-the-dynamics-365-talent-attract-and-dynamics-365-talent-onboard-applications"></a>我不知道人才環境的名稱。 我如何找到具有 Dynamics 365 Talent: Attract 和 Dynamics 365 Talent: Onboard 應用程式資料的環境？

1)  登入 Power Platform 系統管理中心：https://admin.powerplatform.microsoft.com/
2)  選取 **環境**。
3)  選取準備評估的特殊環境。
4)  選取 **資源 > Dynamics 365 App**。
5)  如果您看到 **HCM 人才** 解決方案已經安裝，此環境應該內含儲存的 Attract 和 Onboard 資料。 

[![Power Platform](./media/HCMTalent.png)](./media/HCMTalent.png)

> [!NOTE] 
> **HCM Talent** 解決方案也用在 Dynamics 365 Human Resources。
