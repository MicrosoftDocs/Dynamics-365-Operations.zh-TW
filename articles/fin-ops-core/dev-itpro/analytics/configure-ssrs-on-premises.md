---
title: 為內部部署設定 SQL Server Reporting Services
description: 本主題提供有關為內部部署設定 SQL Server Reporting Services (SSRS) 的信息。
author: PeterRFriis
ms.date: 06/23/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 55651
ms.assetid: ''
ms.search.region: Global
ms.author: peterfriis
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 8
ms.openlocfilehash: 3853158afdab545dacda996c984b265eb8947db7f90faf80319841eb01c14910
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460529"
---
# <a name="configure-sql-server-reporting-services-for-on-premises-deployments"></a>為內部部署設定 SQL Server Reporting Services

[!include [banner](../includes/banner.md)]

使用本主題中的步驟為您的 Microsoft Dynamics 365 Finance + Operations (on-premises) 部署設定 SQL Server Reporting Services (SSRS)。

1. 開啟 Reporting Services 設定管理員應用程式。
2. 保留預設 **伺服器名稱** (應該是現行機器的名稱) 和 **報表伺服器實體** **MSSQLSERVER**。
3. 點選 **連線**。

    [![報表服務設定連接。](./media/ssrs-config-manager-01.png)](./media/ssrs-config-manager-01.png)

4. 點選 **服務帳戶** 索引標籤並驗證設定是否與下圖相符。

    [![服務帳戶索引標籤。](./media/ssrs-config-manager-02.png)](./media/ssrs-config-manager-02.png)

5. 點選 **Web 服務 URL** 索引標籤並驗證設定是否與下圖相符。

    [![Web 服務 URL 索引標籤。](./media/ssrs-config-manager-03.png)](./media/ssrs-config-manager-03.png)

6. 點選 **資料庫** 索引標籤並驗證 **資料庫名稱** 和 **認證設定** 是否與下圖相符。

    > [!NOTE]
    > 您將需要建立一個新資料庫。 為此，請點選 **更改資料庫**，然後驗證新的資料庫名稱是：**DynamicsAxReportServer**。

    [![資料庫索引標籤。](./media/ssrs-config-manager-04.png)](./media/ssrs-config-manager-04.png)

7. 點選 **Web 入口網站 URL** 索引標籤並驗證設定是否與下圖相符。

    > [!NOTE]
    > 您必須點選 **申請** 建立和正確設定入口網站。

    [![入口網站 URL 索引標籤。](./media/ssrs-config-manager-05.png)](./media/ssrs-config-manager-05.png)

    在設定入口網站後，**入口網站** 索引標籤將與下圖相符。

    [![入口網站索引標籤。](./media/ssrs-config-manager-06.png)](./media/ssrs-config-manager-06.png)

8. 點選報表 URL 以檢視 SQL Server Reporting Services 入口網站。
9. 當您在入口網站中時，建立一個名為 **Dynamics** 的新資料夾

    [![動態資料夾。](./media/ssrs-config-manager-07.png)](./media/ssrs-config-manager-07.png)

10. 在 **Reporting Services 設定管理員**，點選 **電子郵件設定** 索引標籤並驗證設定是否與下圖相符。

    [![電子郵件設定索引標籤。](./media/ssrs-config-manager-08.png)](./media/ssrs-config-manager-08.png)

11. 點選 **執行帳戶** 索引標籤並驗證設定是否與下圖相符。

    [![執行帳戶索引標籤。](./media/ssrs-config-manager-09.png)](./media/ssrs-config-manager-09.png)

    不要更改 **加密金鑰** 索引標籤上的預設設定。

    [![加密金鑰索引標籤。](./media/ssrs-config-manager-10.png)](./media/ssrs-config-manager-10.png)

12. 點選 **訂閱設定** 索引標籤並驗證設定是否與下圖相符。

    [![訂閱設定索引標籤。](./media/ssrs-config-manager-11.png)](./media/ssrs-config-manager-11.png)

    不要更改 **擴增部署** 索引標籤上的預設設定。

    [![擴增部署索引標籤。](./media/ssrs-config-manager-12.png)](./media/ssrs-config-manager-12.png)

    不要更改 **Power BI 整合** 索引標籤上的預設設定。

    [![Power BI 整合索引標籤。](./media/ssrs-config-manager-13.png)](./media/ssrs-config-manager-13.png)

13. 點選 **退出** 以關閉 **Reporting Services 設定管理員**。

    [![關閉報表服務設定管理員。](./media/ssrs-config-manager-14.png)](./media/ssrs-config-manager-14.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
