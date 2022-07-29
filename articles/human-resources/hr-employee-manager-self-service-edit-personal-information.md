---
title: 編輯個人資訊
description: 本文說明如何在 Employee 和 Manager 自助服務中編輯個人資訊。
author: twheeloc
ms.date: 08/26/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HRMParameters, EssWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 51941
ms.assetid: 2cfb061a-a616-4bf9-9d98-9cde00039eec
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-03-19
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: e798646263b9939445f49a3866532cd229c668cd
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452148"
---
# <a name="edit-personal-information"></a>編輯個人資訊


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

您可以在 **Employee 自助服務** 工作區的 Dynamics 365 Human Resources 編輯您的個人資訊。

您可以編輯的個人資訊包括：

- 地址
- 連絡人細節
- 個人連絡人
- 身份證號碼
- 付款方式
- 人力資源使用的影像

>[!NOTE]
>您可能無法編輯特定類型的個人資訊，例如業務聯絡細節。 更多資訊，請參閱[限制編輯個人資訊](hr-employee-self-service-restrict-editing.md)。

**全球通訊錄參數** 頁面上設定的參數可判定會看到您的個人資訊的角色。

1. 請在人力資源中選取 **Employee 自助服務**。

2. 選取 **編輯個人細節**。

3. 若要更改您的地址，請選取 **地址** 索引標籤。您進行的更改會在 **人事管理** 工作區出現，用來警示 HR。

    - 若要新增地址，請選取 **新增**。
    - 若要編輯既有地址，請選取地址，然後選取 **編輯**。
    - 若要檢視地圖，請選取 **地圖**。
    - 若要新增或移除聯絡，請選取 **更多選項** 然後選取 **進階**。 請在 **聯絡資訊** 下方選取 **新增** 或 **移除**，並依必要性編輯欄位。
    - 若要設定您的時區和位置，請選取 **更多選項** 然後選擇 **進階**。 請在 **一般** 下方依必要性編輯欄位。

4. 若要更改您的聯絡細節，請選取 **聯絡細節** 索引標籤。您可以提供不同類型的聯絡資訊，包括電話、電子郵件和社交媒體連結。 您可以將聯絡細節設定為主要，但您只能將其中一種類型設定為主要。

    - 若要新增聯絡資訊，請選取 **新增**。 依必要性編輯欄位。
    - 若要編輯既有的聯絡資訊，請選取項目，然後選取 **編輯**。 依必要性編輯欄位。
    - 要將設定聯絡細節為私人，請選取項目和 **進階**，然後設定 **私人** 切換為 **是**。 選取 **確定**。
      >[!NOTE]
      >如果您的管理員已經在您的環境裡啟用 **(預覽版) 限制員工為達特定目的而新增或編輯地址和聯絡資訊** 功能，**進階** 按鈕即無法使用。 更多資訊，請參閱[限制編輯個人資訊](hr-employee-self-service-restrict-editing.md)。
  
5. 若要更改您的個人聯絡，請選取 **個人聯絡** 索引標籤。您可以指定緊急聯絡、受益人和家屬。 聯絡可以是個人或組織。 **福利管理** 功能使用個人聯絡資訊。 更多資訊，請參閱[配置個人聯絡資格選項](hr-benefits-setup-contact-eligibility-options.md)。

6. 若要更改您的身份證號碼，例如社會安全號碼，請選取 **身份證號碼** 索引標籤。如果貴組織設定考核工作流程，更改可能會歷經核准流程。

    - 若要新增身份證號碼，請選取 **新增**。 依照必要性填妥欄位並選取 **儲存**。
    - 若要編輯號碼，請選取 **編輯**。 依照必要性編輯欄位並選取 **儲存**。

7. 若要更改您的付款方式，請選取 **我的付款資訊** 索引標籤。唯有在 **人力資源參數** 頁啟用付款方式才能使用此索引標籤。 HR 可以啟用 **銀行匯票**、**現金**、**支票**、**電子支付** 或 **其他**。 HR 也會停用電子支付驗證 (美國工資單專用) 及銀行帳戶和路由號碼驗證。

8. 若要更改人力資源中，您的設定檔顯示影像，請選取 **影像** 索引標籤。影像可能依照貴組織設定路由以便核准。

    - 若要上傳影像，請選取 **上傳新影像**。
    - 若要移除影像，請選取影像和 **移除**。



[!INCLUDE[footer-include](../includes/footer-banner.md)]
