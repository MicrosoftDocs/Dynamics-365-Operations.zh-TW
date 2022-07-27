---
title: 將 Microsoft Power Apps 入口網站與參與方資料模型一起使用
description: 本主題介紹了由於雙重寫入中的參與方資料模型而對 Microsoft Power Apps 入口網站的 Web 角色所做的更改。
author: RamaKrishnamoorthy
ms.date: 03/22/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2021-03-22
ms.openlocfilehash: 8242a74b8b2251a8489b772f5c4746b113fe2987
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8460571"
---
# <a name="using-microsoft-power-apps-portals-with-the-party-data-model"></a>將 Microsoft Power Apps 入口網站與參與方資料模型一起使用

[!INCLUDE[banner](../../includes/banner.md)]



雙重寫入應用程式編排解決方案版本 2.0.999.0 及更高版本包括對帳戶和聯絡人表的參與方和全球通訊錄的資料模型更改。 這些更改允許支援進階商業場景的多對多關係。 入口網站 Web 角色 (包括客戶入口網站) 不支援這些更改，這些角色是立即可用的或在您安裝雙重寫入之前存在於您的環境中的。 若要使 Web 角色按預期工作，您需要使用新資料模型建立新的 Web 角色。 

總之，資料表互動的方式已經改變，但客戶入口網站中的資料表權限沒有改變。 本主題說明如何建立與新的進階資料模型一起使用的新 Web 角色。

此圖顯示了 **沒有** 參與方和全球通訊錄資料模型的資料表關係：

   ![沒有參與方模型。](media/without-party-model.PNG)

此圖顯示了 **有** 參與方和全球通訊錄資料模型的資料表關係：

   ![有參與方模型。](media/with-party-model.png)

## <a name="create-a-new-table-permission"></a>建立新表權限

若要建立這些新表權限，請執行以下步驟：

1. 登入到[Power Apps](https://make.powerapps.com)，然後進入您的應用程式。
2. 選取您的入口網站管理應用程式。
3. 在側列中，選取 **安全性 > 資料表權限**。

    您必須建立三個新權限：

    + **聯絡人** 到 **合作對象** 資料表連線
    + **合作對象** 到 **帳戶** 資料表連線
    + **帳戶** 到 **訂單** 資料表連線

4. 為聯絡人到合作對象連線建立並儲存新權限，設定以下參數：

    + **名稱**：**合作對象** 到 **帳戶** 資料表連線 (或您的選取)
    + **資料表名稱**：msdyn_contactforparty
    + **網站**：客戶入口網站
    + **範圍**：聯絡人
    + **權限**：全選
    + **Web 角色**：經過身份驗證的使用者、客戶代表 (或您的選取)

5. 為合作對象到帳戶連線建立並儲存新權限，設定以下參數：

    + **名稱**：合作對象到帳戶連線 (或您的選取)
    + **資料表名稱**：帳戶
    + **網站**：客戶入口網站
    + **範圍**：父系
    + **權限**：全選
    + **上層資料表權限**：聯絡人到合作對象連線

6. 為帳戶到訂單連線建立並儲存新權限，設定以下參數：

    + **名稱**：帳戶到訂單連線 (或您的選取)
    + **資料表名稱**：銷售訂單
    + **網站**：客戶入口網站
    + **範圍**：父系
    + **權限**：全選
    + **上層資料表權限**：合作對象到帳戶連線

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
