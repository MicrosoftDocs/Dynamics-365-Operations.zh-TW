---
title: " Dynamics 365 Human Resources 的新面貌或新轉變 (2020 年五月 1 日)"
description: 本文說明 Microsoft Dynamics 365 Human Resources 於 2020 年五月1 日新增或更改的功能。
author: andreabichsel
ms.date: 05/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: ae4b0619a7006bad623e3cee4d9f099e2632b10eeabb78aac16abe53b0911b3a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8451923"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-may-1-2020"></a> Dynamics 365 Human Resources 的新面貌或新轉變 (2020 年五月 1 日)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

本文說明在 Dynamics 365 Human Resources 的新增或更改的功能。 更改適用組建編號 8.1.3196。 某些標題括號裡的數字意指 LCS 支援參考的編號。

## <a name="new-performance-management-entities-available-in-data-management-framework-dmf"></a>資料管理框架 (DMF) 開放使用新績效管理實體

下列實體現在開放使用。 如果您在實體清單沒看見這些實體，請使用 **框架參數 > 實體設定 > 重新整理實體清單** 的 **重新整理實體** 選項。

- **討論適任度**
- **討論目標**
- **討論度量**
- **討論主題**
- **績效日記帳**
- **度量**
- **目標度量**

此外，**總分** 和 **平均分數** 新增到 **討論** 實體。

## <a name="increase-length-of-leave-request-comments-275641"></a>增加請假要求留言的長度 (275641)

請假要求留言現在允許超過 100 個字元。

## <a name="final-comments-on-reviews-dont-appear-when-the-manager-or-employee-is-signed-into-a-different-company-431688"></a>當經理或員工登入不同的公司時，不會出現對審核的最終留言 (431688)

檢視評論時將顯示所有留言。

## <a name="user-defined-links-arent-supported-on-new-worker-form-390374"></a>新背景工作角色表單不支援使用者定義的連結 (390374)

使用者定義的連結現在可到簡化的 **背景工作角色** 表單上啟用。

## <a name="hcmratinglevelentity-causes-odata-api-crash-439476"></a>HcmRatingLevelEntity 導致 OData API 崩潰 (439476)

本項更改改正 API 崩潰現象。 重複的名稱造成此錯誤。

## <a name="in-preview"></a>預覽中

## <a name="leave-suspension"></a>請假暫停

您可以暫停員工在人力資源的請假和缺勤。 暫停請假會停止選取請假類型的請假累計。 如果累計處理之後發生暫停，暫停請假會對員工的請假餘數按比例調整。 更多資訊，請參閱[暫停請假](hr-leave-and-absence-suspend-leave.md)。

## <a name="update-user-experience-to-indicate-that-accrual-is-suspended-429550"></a>更新使用者體驗為指出累計已經暫停 (429550)

使用者體驗現在指出計劃的累計已經暫停。

## <a name="suspend-leave-accrual-for-specified-leave-types-272447"></a>暫停特定請假類型的累計請假 (272447)

此次發行版本中，HR 可以針對無薪請假輸入請假要求的員工，建立暫停累請假的規則。 無薪假可以為類型，但不是必要選項。 您可以暫停以另一個請假類型為主的任何請假。

## <a name="dmf-entity-available-for-accrual-suspensions-429549"></a>DMF 實體開放用於累計暫停 (429549)

DMF 實體現在開放用在累計暫停。

## <a name="add-reason-code-to-accrual-suspensions-429547"></a>新增原因代碼到累計暫停 (429547)

原因代碼已經新增到累計暫停。

## <a name="begin-transitioning-from-human-resources-parameters-to-leave-and-absence-parameters"></a>開始從人力資源參數過渡到請假和缺勤參數

此次發行版本開始結合人力資源參數和請假與缺勤參數。

## <a name="carry-forward-rules"></a>結轉規則

您可以針對轉移結轉調整的結轉餘數指明結轉假期類型。 例如，如果員工結轉 10 天，您可以為那 10 天選取不同的請假類型。 更多資訊，請參閱[配置請假和缺勤類型](hr-leave-and-absence-types.md)。

## <a name="known-issues"></a>已知問題

## <a name="sharepoint-preview-doesnt-work-in-some-environments"></a>SharePoint 預覽功能在一些環境行不通

如果儲存在 SharePoint 的文件預覽行不通，請嘗試下列步驟：

1. 驗證管理使用者帳戶的電子郵件是否與使用者記錄相關聯。 您可以在 **使用者** 頁面檢視這項資訊。 如果電子郵件尚未設定，您需要使用 OData Excel 增益集新增電子郵件和提供商。 電子郵件地址預設不在 Excel 設計範圍。 您將需要編輯 Excel 設計、新增所有欄位、套用和重新整理。 一旦完成這些步驟，您就可以更新管理帳戶。

2. 待管理帳戶有關聯的電子郵件帳號後，使用管理員憑據登入人力資源。

3. 存取 SharePoint 的附件開始文件預覽。

4. 使用可存取附件的另一個使用者帳戶登入並驗證預覽是否如預期運作。

## <a name="see-also"></a>也請參閱

[人力資源的新面貌或新轉變](hr-admin-whats-new.md)</br>
[Dynamics 365 Human Resources 2019 年發行版本第 2 波概觀](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[更新流程](hr-admin-setup-update-process.md)</br>
[管理功能](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]