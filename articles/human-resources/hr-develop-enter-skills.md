---
title: 輸入技能
description: 工作和經理可以在 Dynamics 365 Human Resources 輸入技能。
author: andreabichsel
manager: tfehr
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmSkill, HcmSkillGapProfile, HcmSkillMapping, HcmSkillType, HcmEmployeeDevelopmentWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 3361
ms.assetid: c2ce94c0-933d-4edb-822c-7f0e7b49e4ee
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: c2a35079f43b92b5ff6d68aa7068f3e1f68ce8c2c32d23cdd22798f95c9a0ff4
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8451890"
---
# <a name="enter-skills"></a>輸入技能

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

您可以在 Dynamics 365 Human Resources 中輸入背景工作角色、申請人或聯絡人的確定目標技能或實際技能。 確定目標技能是個人計劃達成的技能。 實際技能是個人目前擁有的技能。

## <a name="create-a-workflow-to-auto-approve-skills"></a>建立工作流程以便自動核准技能

若要在不需要核准情況下輸入技能，您必須建立工作流程自動核准技能。

> [!NOTE]
> 背景工作角色輸入的技能總是需要經理核准。 這項工作流程只會自動核准經理代表背景工作角色輸入的技能。

1. 請在 **人事管理** 工作區中選取 **連結**。

2. 請在 **設定** 下方選取 **人力資源工作流程**。

3. 選取 **新增**。

4. 請在 **建立工作流程** 窗格中選取 **背景工作角色技能**。

   [![選取背景工作角色技能工作流程。](media/hr-develop-skills-new-workflow.png)](media/hr-develop-skills-new-workflow.png)

5. 請在 **打開這個檔案？** 對話中選取 **打開**。 出現提示訊息時，請輸入您的認證。

6. 請在工作流程編輯器中選取 **核准技能** 工作流程元素並且拖曳到畫布上。

   [![選取核准技能工作流程元素。](media/hr-develop-skills-element.png)](media/hr-develop-skills-element.png)

7. 連接 **開始** 元素到 **核准技能 1** 元素，然後連接 **核准技能 1** 元素到 **結束** 元素。 您可能需要捲軸向下滾動才能看到 **結束** 元素。 您可以拖曳到更靠近其他元素的位置。

   [![連接工作流程元素。](media/hr-develop-skills-connect-elements.png)](media/hr-develop-skills-connect-elements.png)

8. 點選兩次 **核准技能 1** 工作流程元素，然後在 **第 1 步** 元素上方按滑鼠右鍵。 在 **第 1 步** 元素上方按滑鼠右鍵，然後選取 **屬性**。

9. 請在 **屬性** 視窗中選取左手邊瀏覽列上的 **條件**。

10. 請選取 **只在符合下列條件下才需執行此步驟**。

11. 選取 **新增條件**。 請在 **其中** 後面選取 **員工自助服務技能**，然後選取 **員工自助服務 skills.Person**。 請在 **是** 後面選取 **欄位**，然後選取 **使用者與個人的 relationship.Person**。

    [![指明條件。](media/hr-develop-skills-condition.png)](media/hr-develop-skills-condition.png)

12. 請在左手邊瀏覽列上選取 **指派**。

13. 請在 **指派類型** 索引標籤上選取 **階層結構**。

14. 請在 **階層結構選取** 索引標籤上的 **階層結構類型：** 欄位中選取 **管理階層結構**。

    [![指明管理階層結構。](media/hr-develop-skills-hierarchy.png)](media/hr-develop-skills-hierarchy.png)

15. 請在畫布頁面路徑中選取 **關閉** 和 **工作流程**，然後選取 **儲存和關閉**。

更多有關建立工作流程資訊，請參閱[工作流程系統概觀](../fin-ops-core/fin-ops/organization-administration/overview-workflow-system.md?toc=/dynamics365/human-resources/toc.json)。

## <a name="enter-skills-for-a-worker"></a>請輸入背景工作角色的技能

1. 請選取背景工作角色。

2. 請在 **背景工作角色** 頁面的動作列選取 **個人**，然後選取 **技能**。

3. 請在 **技能** 頁面上填完每項技能的欄位，分列如下：

   - **技能**：選取技能。
   - **等級類型**：選取背景工作角色已經擁有的 **實際** 技能，或選取背景工作角色正在努力的 **確定目標** 技能。
   - **等級**：選取背景工作角色的技能等級。
   - **等級日期**：請在行事曆工具選取日期。
   - **考核官**：請依合適狀況從清單選取一名考核官。 您可以篩選搜尋。
   - **經驗年數**：輸入經驗年數。
   - **已驗證**：如果技能已經通過驗證，請勾選此方塊。
   - **驗證人員**：輸入驗證人員姓名。

4. 技能輸入後，選取 **儲存**。

## <a name="see-also"></a>也請參閱

[配置技能](hr-develop-skills.md)<br>
[測繪技能](hr-develop-map-skills.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]