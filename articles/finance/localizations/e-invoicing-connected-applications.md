---
title: 已連接的應用程式
description: 本主題說明如何在電子開票中設定已連接的應用程式。
author: dkalyuzh
ms.date: 02/07/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkalyuzh
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 59b67589139c0ce332716acf998825c6a024bded
ms.sourcegitcommit: ffdb6794746ffe5461f9dcf34ed8e64976d22d2d
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/02/2022
ms.locfileid: "8451677"
---
# <a name="connected-applications"></a>已連接的應用程式

[!include [banner](../includes/banner.md)]

已連接的應用程式是您可能希望透過 Regulatory Configuration Service (RCS) 觸達的 Microsoft Dynamics 365 Finance 和 Dynamics 365 Supply Chain Management 的執行個體。 透過連接的應用程式，您可以在 Finance 或 Supply Chain Management 中設定部分全球化功能，以使電子開票方案運作。

當您部署全球化功能時，適用於您 Finance 或 Supply Chain Management 應用程式的設定資訊可以直接從 RCS 發佈到適當的連接應用程式。

當您有多個應用程式環境 (例如使用者驗收測試 (UAT) 和生產環境) 並且您希望透過將相同參數部署到不同環境來保持設定一致時，RCS 中 Finance 或 Supply Chain Management 參數的可用性非常有用。

## <a name="create-a-connected-application"></a>建立連接的應用程式

1. 登入您的 RCS 帳戶。
2. 在 **全球化功能** 工作區的 **環境** 區段中，選擇 **電子開票** 圖格。
3. 在 **環境設定** 頁面的動作窗格上，選擇 **連接的應用程式**。
4. 請選取 **新增** 建立連接的應用程式。
5. 請在 **姓名** 欄位，輸入要連接的應用程式的名稱。
6. 在 **類型** 欄位選擇 **Dynamics 365 Finance**。
7. 在 **應用程式** 欄位，輸入要連接的環境的 URL。
8. 在 **租用戶** 欄位，指定應用程序的提供者。
9. 選擇 **儲存**。
10. 在動作窗格上，選擇 **檢查連接** 測試與環境的連接。 然後關閉頁面。

## <a name="link-connected-applications-to-environments"></a>將連接的應用程式連結到環境

1. 在 **環境設定** 頁面，選擇 **新增** 將連接的應用程式指派給環境。
2. 在 **已連接的應用程式** 欄位，選擇已連接的應用程式。
3. 在 **服務環境** 欄位，選擇服務環境。
4. 請選取 **儲存**，然後關閉此頁。
