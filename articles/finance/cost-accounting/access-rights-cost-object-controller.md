---
title: 成本物件控管者的存取權限
description: 本主題提供有關成本物件控管者存取權限的資訊。
author: AndersGirke
ms.date: 06/24/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CAMCostControlWorkspace, CAMParameters
audience: Application User
ms.reviewer: roschlom
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roschlom
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: c30a7c2765647aad17a475ba8705b8e688d166593adf242fcd15d90e49334189
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450333"
---
# <a name="access-rights-for-cost-object-controllers"></a>成本物件控管者的存取權限

[!include [banner](../includes/banner.md)]

**成本控制** 工作區是經理可以查看其成本物件績效的中心點。 即使他們不是成本會計員，該工作區也可以讓經理使用成本核算資料。 出於安全原因，應允許經理僅查看與其負責的特定成本物件相關的成本核算資料。

成本核算中有四個唯一角色。

| 角色名稱               | 授權      |
|-------------------------|--------------|
| 成本會計經理 | 活動     |
| 成本會計員         | Operations   |
| 成本核算員   | Operations   |
| 成本物件控管者  | 團隊成員 |

本主題說明如何將 **成本物件控管者** 角色指派給經理。

將 **成本物件控管者** 角色指派給經理，經理可以執行以下任務：

- 存取 **成本控制** 工作區 (在使用者端中)。

    - 鑽研並取得支援鑽研體驗的頁面的查看權限。

- 存取 **成本控制** 工作區 (在行動裝置應用程式中)。

> [!NOTE]
> **成本物件控管者** 角色不控制使用者可以存取和查看其資料的成本物件。 列等級安全性透過維度階層和存取清單階層結構提供。

## <a name="grant-access-rights"></a>授與存取權限
以下範例顯示了維度階層的概觀。

**維度階層詳細資料**

| 維度階層名稱 | 維度    | 維度階層類型名稱      | 存取清單階層 |
|--------------------------|--------------|------------------------------------|-----------------------|
| 組織             | 成本中心 | 維度分類階層 | **是**               |

您可以使用階層設計工具中的 **使用者** FastTab，在每各節點上插入一個或多個使用者使用者。

|             節點                 | 使用者            | 來源維度成員     |   目標維度成員   |
|-----------------------------------|------------------|---------------------------|-------------------------|
| 組織                      | Benjamin, Claire |                           |                         |
| &nbsp;&nbsp;系統管理員                 | 四月            |                           |                         |
| &nbsp;&nbsp;&nbsp;&nbsp;Finance   | Alicia           | CC002                     | CC003                   |
|                                   |                  | CC007                     | CC007                   |
| &nbsp;&nbsp;&nbsp;&nbsp;人力資源        | Arnie            | CC001                     | CC001                   |
| &nbsp;&nbsp;生產            | Dav使用者            |                           |                         |
| &nbsp;&nbsp;&nbsp;&nbsp;裝箱 | Ellen            | CC005                     | CC005                   |
| &nbsp;&nbsp;&nbsp;&nbsp;組件  | Chris            | CC006                     | CC006                   |

> [!NOTE]
> 成本會計應指派到階層的頂端，以便他們可以查看成本會計中的所有分錄。

在套用存取清單階層及其安全性設定之前，**成本核算參數** 頁面 **一般** 索引標籤上的 **為成本物件維度成員啟用查看存取權** 選項必須設定為 **是** (**成本核算** > **設定** > **參數**)。

存取清單階層的設定用於控制以下區域中顯示的資料：

- **成本控制** 工作區 (在用戶端中)：

    - 用於鑽研的頁面上的資料

- **成本控制** 工作區 (在行動裝置應用程式中)：

    - 卡內餘額

- Microsoft Power BI：

    - Power BI 視覺化中顯示的資料
    - 在Dynamics 365 Finance 用戶端中嵌入的資料 Power BI 視覺化項

> [!IMPORTANT]
> - 在存取清單階層影響 Power BI 中的資料之前， Power BI 中的存取清單階層和列等級安全性必須配對。 有關詳細資訊，請參閱[設定成本會計內容套件的安全性](../../fin-ops-core/dev-itpro/analytics/setup-security-cost-accounting-content-pack.md)。
> - 本主題說明使用 **成本控制** 工作區之前必須具備的先決條件。

其他資源

- [成本控制工作區](cost-control-workspace.md)
- [維度階層](dimension-hierarchy.md)
- [設定成本核算內容套件的安全性](../../fin-ops-core/dev-itpro/analytics/setup-security-cost-accounting-content-pack.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
