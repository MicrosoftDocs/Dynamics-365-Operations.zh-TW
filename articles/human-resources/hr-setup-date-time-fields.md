---
title: 了解日期和時間欄位
description: 本主題說明在 Microsoft Dynamics 365 Human Resources 中使用日期和時間欄位時，預期發生的狀況。
author: twheeloc
ms.date: 10/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmPersonnelManagementWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 7c81155f0c5150af44982f224c8eca2026a78ee7
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8451998"
---
# <a name="understand-date-and-time-fields"></a>了解日期和時間欄位

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



**日期和時間** 欄位是 Microsoft Dynamics 365 Human Resources 的基本概念。 重要的是您必須了解如何搭配 Dataverse 頁面上的 **日期和時間** 資料和外部來源操作。

## <a name="understanding-the-difference-between-date-and-date-and-time-field-data-types"></a>了解日期與日期和時間欄位資料類型之間的區別

**日期和時間** 欄位包含時區資訊，而 **日期** 欄位則沒有。 **日期** 欄位在任何位置顯示相同資訊。 當您在 **日期** 欄位輸入日期時，相同的日期會寫入資料庫。

當資料顯示在 **日期和時間** 欄位時，日期和時間會根據使用者在 **使用者選項** 頁 (**常用\>設定\>使用者選項**) 上選取的時區基礎調整。 您在欄位輸入的日期和時間資訊可能與寫入資料庫的資訊不同。

[![使用者選項頁面。](./media/Useroptionsform.png)](./media/Useroptionsform.png)

## <a name="understanding-date-and-time-fields-on-pages"></a>了解頁面上的日期和時間欄位 

如果使用者的時區未設定為協調世界時間 (UTC)，螢幕上顯示的 **日期和時間** 資料會與資料庫儲存的資料不同。 **日期和時間** 欄位裡的資料永遠儲存為 UTC。

[![背景工作角色頁面 UTC。](./media/worker-form.png)](./media/worker-form.png)

## <a name="understand-date-and-time-fields-in-the-database"></a>了解資料庫的日期和時間欄位 

當 **日期和時間** 值寫入資料庫時，資料會儲存為 UTC。 因此，使用者可以看見任何 **日期和時間** 與其選項定義時區有關。
 
上述範例的開始時間是時間點，不是特殊日期。 憑藉使用者登入時區從 GMT +12:00 更改為 GMT UTC，相同記錄會顯示 04/30/2019 12:00:00 而不是 05/01/2019 12:00:00。

下方範例中，員工 000724 的雇用狀態同時變成有效，不論時區如何。 員工將在 GMT 時區的 04/30/2019 有效，與 GMT+12:00 時區的 05/01/2019 相同。 兩者皆指同一個時間點，而不是特殊日期。 

[![背景工作角色頁面 GMT。](./media/worker-form2.png)](./media/worker-form2.png)

## <a name="date-and-time-data-in-data-management-framework-excel-dataverse-and-power-bi"></a>資料管理框架、Excel、Dataverse 和 Power BI 中的日期和時間資料 

資料管理框架 (DMF)、Excel 插件、Dataverse 和 Power BI 報表皆設計為與資料庫等級上的資料互動。 既然目前客戶皆無法調整 **日期和時間** 資料為使用者的時區，所有 **日期和時間** 值皆以 UTC 為單位，輸入或檢視資料時會導致一些不正確的假設。
 
當 **日期和時間** 資料透過 DMF、Excel 或 Dataverse 提交時，資燉庫會假定它為 UTC。 不過，如果檢視資料的使用者未將其使用者時區設定為 UTC，則提交的 **日期和時間** 值將不如預期出現，而使用者可能會變得困惑不解。 
 
反過來匯出資料時，也會發生同樣的事情。 匯出的 DMF 實體中的 **日期和時間** 資料會與 Dynamics 用戶端顯示的不同。 
 
使用 DMF 等外部資源檢視或著作資料時，請記住 **日期和時間** 值皆預設視同 UTC 時間，不論使用者電腦的時區或他們目前的使用者時區如何設定。 

## <a name="examples-of-the-same-record-being-displayed-in-different-product-areas"></a>相同記錄在不同產品區域顯示的範例 

**使用者時區設定為 UTC 的人力資源**

[![背景工作角色頁面設定為 UTC。](./media/worker-form3.png)](./media/worker-form3.png)

**使用者時區設定為 GMT + 12:00 的人力資源** 

[![背景工作角色頁面設定為 GMT。](./media/worker-form4.png)](./media/worker-form4.png)

**Excel 透過 OData**

[![Excel 透過 OData](./media/Excelviaodata.png)](./media/Excelviaodata.png)

**DMF 暫存**

[![DMF 暫存。](./media/DMFStaging.png)](./media/DMFStaging.png)

**DMF 匯出**

[![DMF 匯出。](./media/DMFExport.png)](./media/DMFExport.png)

**Excel 透過 Dataverse**

[![Excel 透過 Dataverse。](./media/ExcelCDS.png)](./media/ExcelCDS.png)

## <a name="see-also"></a>也請參閱

[日期和時間資料](/dynamics365/unified-operations/fin-and-ops/organization-administration/date-time-zones)<br></br>
[使用者偏好時區](/dynamics365/unified-operations/fin-and-ops/organization-administration/tasks/set-users-preferred-time-zone) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
