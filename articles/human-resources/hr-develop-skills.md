---
title: 配置技能
description: 您可以在 Dynamics 365 Human Resources 追蹤背景工作角色的技能。 您也可以指明特定工作所需的技能。
author: twheeloc
manager: tfehr
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmSkill, HcmSkillGapProfile, HcmSkillMapping, HcmSkillType, HcmEmployeeDevelopmentWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 3361
ms.assetid: c2ce94c0-933d-4edb-822c-7f0e7b49e4ee
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 13206bb3c961f001620e8b65a8b1bb39bf95ee49
ms.sourcegitcommit: 89655f832e722cefbf796a95db10c25784cc2e8e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452682"
---
# <a name="configure-skills"></a>配置技能

> [!IMPORTANT]
> 本主題註明的功能目前開放財務基礎架構上的人力資源客戶使用。  


您可以在 Dynamics 365 Human Resources 追蹤背景工作角色的技能。 您也可以指明特定工作所需的技能。

您可以追蹤的技能範例包括：

- 監督 - 監督其他人的工作情況。
- 領導力 - 帶領員工和業務領域的能力。
- 規劃 - 展望未來，形成願景語句口號並且過關嶄將。
- HTML – 撰寫 HTML 程式碼的能力。

如果您尚未設定技能類型和評等模型，您將需要再新增一些才能建立技能。

可以輸入背景工作角色技能的人如下：

- 背景工作角色可以在員工自助服務中為自己輸入技能。 這些技能需要經理核准。
- 經理可以為他們的背景工作角色輸入技能。 您可以建立自動核准這些技能的工作流程。

## <a name="create-a-skill-type"></a>建立技能類型

技能類型是個人技能所屬類別，例如行政管理或銷售。

1. 請在 **員工發展** 工作區中選取 **連結**。

2. 請在 **適任度設定** 下方選取 **技能類型**。

3. 選取 **新增**。

4. 請完成下列欄位的填寫：

   - **技能類型**：輸入技能類型名稱。
   - **說明**：輸入技能類型說明。

5. 選取 **儲存**。

## <a name="create-a-rating-model"></a>建立評等模型

評等模型有助於評估個人實際技能程度、他們應該努力達到的程度或工作所需的技能程度。 評等模型中的每個等級都已指派因子。

1. 請在 **員工發展** 工作區中選取 **連結**。

2. 請在 **適任度設定** 下方選取 **評等模型**。

3. 選取 **新增**。

4. 請完成下列欄位的填寫：

   - **評等**：輸入評等模型名稱，例如 **技能**。
   - **遻明**：輸入評等模型說明，例如 **技能評等**。

5. 請在 **等級** 專區中選取 **新增**。 對於您希望新增的每個等級，請完成下列欄位的填寫：

   - **等級**：輸入等級的名稱。
   - **說明**：輸入等級說明。
   - **因子**：輸入 0-9 的因子值。 因子有助於規範使用不同等級模型的技能分數。 每個等級必須要有獨一無二的因子。 因子值較高的等級在評等模型中攜帶更大的權重。

   按照需求繼續新增等級。 您最多針對每個評等模型輸入 10 個等級。

6. 選取 **儲存**。

## <a name="create-a-skill"></a>建立技能

在您可以指派技能或建立技能測繪搜尋或技能設定檔之前，您必須先在 **技能** 頁面上輸入技能相關資訊。 每個技能方面，您可以選取技能類型和評等模型。

1. 請在 **員工發展** 工作區中選取 **連結**。

2. 請在 **適任度設定** 下方選取 **技能**。

3. 選取 **新增**。

4. 請完成下列欄位的填寫：

   - **技能**：輸入技能名稱。
   - **說明**：輸入技能說明。
   - **評等**：請選取您希望用在這項此技能的評等模型。
   - **技能類型**：請從技能類型清單選取。

5. 選取 **儲存**。

## <a name="see-also"></a>也請參閱

[輸入技能](hr-develop-enter-skills.md)<br>
[測繪技能](hr-develop-map-skills.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
