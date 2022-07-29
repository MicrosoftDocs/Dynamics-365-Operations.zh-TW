---
title: 人力資源不在 Microsoft Dynamics 365 應用程式出現
description: 本主題說明如果 Microsoft Dynamics 365 Human Resources 未列入 Microsoft Dynamics 365 應用程式的作法。
author: twheeloc
ms.date: 08/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 4bdbe6c4065a8266fd30a3b093743ded91524f6a
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452571"
---
# <a name="human-resources-app-doesnt-appear-in-microsoft-dynamics-365-apps"></a>人力資源應用程式不在 Microsoft Dynamics 365 應用程式出現


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

**問題**

客戶看不到 Microsoft Dynamics 365 應用程式當中的 Dynamics 365 Human Resources。

**解決方案**

使用者必須新增到 Microsoft Power Apps 環境的 Environment Maker 角色。

1. 擁有 Power Apps 計劃 2 授權的管理員使用者必須打開 [Power Apps 管理入口網站](https://preview.admin.powerapps.com/)。

2. 請選取 **環境**，並為人力資源選取正確環境。

3. 請在 **安全性** 索引標籤上的 **環境角色** 索引標籤選取 **環境製造商**。

    ![環境角色索引標籤。](media/environment-roles.png)

4. 請在 **使用者** 索引標籤上新增使用者或貴組織。

    ![使用者索引標籤。](media/environment-maker.png)

5. 選取 **儲存**。

6. 使用者現在必須登入 [Microsoft Dynamics 365](https://home.dynamics.com/)。

7. 選取 **同步** 更新使用者應用程式。

    ![同步按鈕。](media/get-more.png)

    同步完成後，人力資源將在首頁出現。


[!INCLUDE[footer-include](../includes/footer-banner.md)]
