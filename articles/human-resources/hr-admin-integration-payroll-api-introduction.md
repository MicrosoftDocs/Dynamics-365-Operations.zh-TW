---
title: 工資單整合 API 簡介
description: 本主題說明 Dynamics 365 Human Resources 工資單整合 API。
author: andreabichsel
ms.date: 02/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2021-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 4c71d31d7045c73097b81671793181a29dcac3b5
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452079"
---
# <a name="payroll-integration-api-introduction"></a>工資單整合 API 簡介


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

本文件說明 Dynamics 365 Human Resources 工資單整合 API。 API 啟用人力資源和合作夥伴薪資系統之間的端對端整合簡易版。 整合體驗從人力資源開始，包含員工設定檔、薪資和扣除額及貢獻資訊。 當您錄用員工並將必要的個人資料和薪資資訊輸入人力資源時，工資單系統會拉出這項資訊用於處理工資單。 對員工或工資資訊的任何更新也會拉出用於日後工資的執行。

[![工資單整合流程。](media/hr-admin-integration-payroll-api-introduction-flow.png)](media/hr-admin-integration-payroll-api-introduction-flow-2.png#lightbox)

為了啟用整合功能，人力資源包括組成部份如下：

- [將員工標示為準備付款的功能。](hr-compensation-payroll.md)
- 整合 API 扛開全新的整合應用程式功能。

## <a name="microsoft-dataverse"></a>Microsoft Dataverse

這個 API 內建於 Microsoft Dataverse 中 (前身為 Common Data Service)。 與此 API 的所有 RESTful 互動都是透過使用 OData 的 Microsoft Dataverse Web API 進行。 此 API 是 Dataverse Web API 的子集合。 Dataverse Web API 定義如驗證、SLA、批次、同時控制和錯誤處理等特性。

更多有關 Microsoft Dataverse Web API 一般資訊，請參閱：

- [何謂 Microsoft Dataverse？](/powerapps/maker/data-platform/data-platform-intro)
- [使用 Microsoft Dataverse Web API](/powerapps/developer/data-platform/webapi/overview)
- [Microsoft Dataverse 開發人員指引](/powerapps/developer/data-platform)

本文件包括使用 Dataverse Web API 細節和開發人員指引，包括主題如下：

- [驗證 Microsoft Dataverse 搭配 Web API](/powerapps/developer/data-platform/webapi/authenticate-web-api)
- [使用 Web API 執行作業](/powerapps/developer/data-platform/webapi/perform-operations-web-api)
- [搭配 Web API 使用 Postman](/powerapps/developer/data-platform/webapi/use-postman-web-api)
- [使用追蹤修訂與外部系統資料同步](/powerapps/developer/data-platform/use-change-tracking-synchronize-data-external-systems)

### <a name="virtual-tables-for-human-resources-in-dataverse"></a>Dataverse 人力資源虛擬資料表

工資單整合 API 端點使用 Microsoft Dataverse 的虛擬資料表平台功能。 預設情況下，人力資源環境不會佈署虛擬資料表及其關聯 API 端點，促使組織判定將針對環境揭露的 OData 端點。 若要使用 API，必須針對環境產生人力資源實體的虛擬資料表。

關於針對 API 產生虛擬資料表的資訊，請參閱[配置 Dataverse 虛擬資料表](./hr-admin-integration-common-data-service-virtual-entities.md)。

## <a name="data-model"></a>資料模型

下圖說明 API 內的關係。 目前幾種類型有人力資料預先存在實體的外部索引鍵，未納入這裡的說明。 本文件提供工資單整合方案的具體資訊。 然而適用人力資源 Dataverse Web API 中的其他許多實體也可能攸關您的整合。 當中某些實體會在外部索引鍵關係或導航屬性中引用。

[![工資單整合 API 資料模型。](media/hr-admin-payroll-api-data-model.png)](media/hr-admin-payroll-api-data-model.png#lightbox)

## <a name="payroll-employee-and-related-entities"></a>工資單員工和相關實體

實體：

- [工資單員工](hr-admin-integration-payroll-api-payroll-employee.md)
- [工資單背景工作角色地址](hr-admin-integration-payroll-api-payroll-worker-address.md)
- [工資單固定薪酬計劃](hr-admin-integration-payroll-api-payroll-fixed-compensation-plan.md)
- [工資單變動薪酬計畫](hr-admin-integration-payroll-api-payroll-variable-compensation-plan.md)
- [工資單職位工作](hr-admin-integration-payroll-api-payroll-position-job.md)
- [工資單職位](hr-admin-integration-payroll-api-payroll-position.md)

## <a name="see-also"></a>也請參閱

[產生和審核工資單實體](hr-admin-integration-payroll-api-generate-review-entities.md)<br>
[配置人力資源參數](hr-setup-parameters.md)<br>
[配置人力資源共用參數](hr-setup-shared-parameters.md)<br>
[何謂 Microsoft Dataverse？](/powerapps/maker/data-platform/data-platform-intro)<br>
[使用 Microsoft Dataverse Web API](/powerapps/developer/data-platform/webapi/overview)<br>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
