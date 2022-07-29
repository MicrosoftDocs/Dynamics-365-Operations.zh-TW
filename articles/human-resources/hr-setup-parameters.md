---
title: 配置人力資源參數
description: 本主題說明如何在 Dynamics 365 Human Resources 設定特定公司參數。
author: twheeloc
ms.date: 11/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HRMParameters, HcmPersonnelManagementWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 51941
ms.assetid: 2cfb061a-a616-4bf9-9d98-9cde00039eec
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: fd9bb907f95ba4c368871a470ca9b2bc807646ee
ms.sourcegitcommit: 7e0e2a266d9a9473df72e207554d9bd150e17ce3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/05/2021
ms.locfileid: "8451971"
---
# <a name="configure-human-resources-parameters"></a>配置人力資源參數

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

一些人力資源參數的設定是跨公司共用，而其他參數的設定是公司特定的。 本主題解釋如何設定特定公司的人力資源參數。

兩頁用來設定人力資源參數。 跨公司共用參數方面，您使用 **人力資源共用參數** 頁。 特定公司參數方面 (換言之，設定適用一間公司)，您使用 **人力資源參數** 頁。

![前往人力資源參數。](./media/hr-employee-self-service-human-resources-parameters.png)

**人力資源參數** 頁面上的設定分割成六大索引標籤：

- **一般**
- **招募** (此索引標籤不納入 Dynamics 365 Human Resources)
- **薪酬**
- **數字順序**
- **FMLA**
- **Employee 自助服務**
- **Manager 自助服務**
- **福利管理**
- **請假和缺勤**
- **付款方式**

每個索引標籤包含與一間公司相關的資訊。

## <a name="general"></a>一般

**一般** 索引標籤上的設定定義有關缺勤、受傷和疾病，以及新錄用員工資訊的外觀。 此索引標籤上的設定也定義一些您工作時出現的預設登錄項。 具體而言，此索引標籤讓您：

- 選取顏色套用在未結算的缺勤交易。
- 指明用在報表的樣式工作單。
- 啟用訓練課程和缺勤登記之間的整合。
- 選取用來控制此整合的缺勤代碼。
- 指出受傷和疾病案例事件的保存時間。
- 指明錄用新員工時顯示的預設識別號碼。
- 指明用來計算服務年資的日期。 

![一般索引標籤。](./media/hr-setup-parameters-general.png)

## <a name="recruitment"></a>招募

**招募** 索引標籤上的設定定義用於來自動傳送給申請人書信的文件類型。 您也可以指出用於自薦申請的招募專案。

**招募專案時效** 定義的期間可判定 **招募管理** 工作區中的 **時效專案** 圖格納入的招募專案。 針對申請截止日期警告定義的期間，用來顯示正在逼近 **招募** 工作區中，**申請截止日期逼近** 圖格上，他們申請截止日期的招募專案。

更多有關招募的資訊，請參閱[招募工作求職者](hr-personnel-recruit.md)。

## <a name="compensation"></a>薪酬

Dynamics 365 Finance 中，**薪酬** 索引標籤上的設定定義使用者是否必須確認他們希望儲存固定或變動薪酬計劃的資訊。 如果您選取 **啟用儲存驗證**，當使用者關閉薪酬相關頁面時，他們會收到一則訊息，詢問他們是否希望儲存記錄。 薪酬管理中的一些頁面不讓使用者刪除資訊。 藉由提示使用者驗證他們是否希望儲存資訊，您可能可以限制已經儲存，但日後無法刪除的資訊量。 如果你清除 **啟用儲存驗證**，記錄可能會在使用者準備好之前就立即儲存。 如果您正在使用績效管理，**薪酬** 索引標籤也會讓您在評等績效時，選取預計使用的評等模型，而不是指派給薪酬計劃的模型。

您可以在人力資源使用 **薪酬** 索引標籤選擇限制對薪酬計劃的存取，並設定預設貨幣。

更多有關薪酬的資訊，請參閱 [薪酬計劃概觀](hr-compensation-overview.md)。

![薪酬索引標籤。](./media/hr-setup-parameters-compensation.png)

## <a name="number-sequences"></a>數字順序

**數字順序** 索引標籤可判定用來自動指派識別碼給人力資源項目的順序，例如：

- 應用程式
- 缺勤註冊
- 薪酬流程結果
- 案號
- 課程
- 課程議程

若要維護數字順序參考和代碼，請使用 **數字順序** 清單頁 (選取 **組織管理 > 數字順序 > 數字順序**)。

更多資訊，請參閱[數字順序概觀](../fin-ops-core/fin-ops/organization-administration/number-sequence-overview.md?toc=%2fdynamics365%2fhuman-resources%2ftoc.json)。

> [!NOTE]
> 已工作的時數不能超過 1,250 小時，雇用時長不能超過十二個月。 這些最大值依循美國聯邦法律。

![數字順序索引標籤。](./media/hr-setup-parameters-number-sequences.png)

## <a name="fmla"></a>FMLA

您在 FMLA 索引標籤上設定 FMLA 資格要求和 FMLA 權利時數。 更多資訊，請參閱[配置請假和缺勤參數](hr-leave-and-absence-parameters.md)。

![FMLA 索引標籤。](./media/hr-setup-parameters-fmla.png)

## <a name="employee-self-service"></a>Employee 自助服務

**Employee 自助服務** 索引標籤上的設定影響 **Employee 自助服務** 出現在員工面前的方式。 您可以在此索引標籤上完成下列任務：

- 輸入 **Employee 自助服務** 工作區名稱
- 選取經理可以為員工輸入的資訊
- 新增對員工實用的連結
- 限制員工新增或編輯商業聯絡人細節。 更多資訊，請參閱[限制編輯個人資訊](hr-employee-self-service-restrict-editing.md)。

更多有關設定 **Employee 自助服務** 方式的資訊，請參閱 [Employee 和 Manager 自助服務概觀](hr-employee-manager-self-service-overview.md)。

![Employee 自助服務索引標籤。](./media/hr-setup-parameters-employee-self-service.png)

## <a name="manager-self-service"></a>Manager 自助服務

**Manager 自助服務** 索引標籤的設定影響經理在 **Manager 自助服務** 看見的內容。 您可以在此索引標籤上配置下列選項：

- 到期記錄的範圍
- 資訊管理員可以檢視到期記錄
- 經理是否可以檢視擴充報表的職缺
- 離職背景工作角色視圖
- 經理的實用連結

更多有關設定 **Manager 自助服務** 方式的資訊，請參閱 [Employee 和 Manager 自助服務概觀](hr-employee-manager-self-service-overview.md)。

![Ｍanager 自助服務索引標籤。](./media/hr-setup-parameters-manager-self-service.png)

## <a name="benefits-management"></a>福利管理

您可以在 **福利管理** 索引標籤上針對福利管理配置電子郵件選項。 有關福利管理設定方式和使用的資訊，請參閱[福利管理概觀](hr-benefits-management-overview.md)。

![福利管理索引標籤。](./media/hr-setup-parameters-benefits-management.png)

## <a name="leave-and-absence"></a>請假和缺勤

有關請假和缺勤的設定和使用資訊，請參閱[請假和缺勤概觀](hr-leave-and-absence-overview.md)。

## <a name="payment-methods"></a>付款方式

您可以在 **付款方式** 索引標籤上選取貴組織支援的付款方式。 更多有關配置薪酬的資訊，請參閱 [薪酬計劃概觀](hr-compensation-overview.md)。

![付款方式索引標籤。](./media/hr-setup-parameters-payment-methods.png)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
