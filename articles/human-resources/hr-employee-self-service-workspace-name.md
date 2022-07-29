---
title: 更改 Employee 自助服務工作區名稱
description: 本主題說明如何在 Dynamics 365 Human Resources 更改 Employee 自助服務工作區名稱。
author: twheeloc
ms.date: 08/26/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EssWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-07-09
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 31e8c3e572e0f95f4331fbd858150897c9ed0105
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452658"
---
# <a name="change-employee-self-service-workspace-name"></a>更改 Employee 自助服務工作區名稱


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

如果您有志工或其他非員工人士，您可能需要更改 **Employee 自助服務** 工作區名稱。 您反而可以將此工作區更改為 **Self 服務**。

> [!NOTE]
> 更改 **Employee 自助服務** 工作區名稱同時也更改 Dynamics 365 Human Resources 內部使用的選單項目。 如果您之前將安全性自訂套用到 **HcmEmployeeSelfServiceWorkspace** 選單項目，我們建議將相同更改內容套用到 **HcmSelfServiceWorkspace** 以維持同位。

1. 請在人力資源中選取 **人事管理**、**連結** 和 **人力資源參數**。

2. 選取 **Employee 自助服務** 索引標籤。

3. 在 **顯示名稱** 下方選取 **Self 服務**。

   ![更改 Employee 自助服務工作區名稱為 Self 服務。](./media/hr-employee-self-service-workspace-name.png)

4. 選取 **儲存**。

## <a name="additional-resources"></a>其他資源

- [Employee 和 Manager 自助服務概觀](hr-employee-manager-self-service-overview.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
