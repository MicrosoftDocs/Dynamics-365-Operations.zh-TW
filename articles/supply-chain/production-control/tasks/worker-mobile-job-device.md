---
title: 使用行動作業裝置配置工作人員
description: 本主題介紹如何為工作人員的使用者帳戶指派正確的角色，使工作人員能夠進行車間登記。
author: johanhoffmann
ms.date: 07/09/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SysUserManagement, HcmWorker, JmgRegistrationSetupTouch, JmgRegistrationSetupAssignUsers
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9d9745995752c06385acc31e529de52eefaa6f96
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448626"
---
# <a name="configure-a-worker-using-the-mobile-job-device"></a>使用行動作業裝置配置工作人員

[!include [banner](../../includes/banner.md)]

本主題介紹如何為工作人員的使用者帳戶指派正確的角色，使工作人員能夠進行車間登記。

## <a name="verify-that-a-worker-is-assigned-a-certain-role"></a>驗證是否為工作人員指派了特定角色

對於此範例，請在配置工作人員帳戶之前驗證是否為使用者「SHANON」指派了機器操作員角色。

1. 前往 **瀏覽窗格 > 模組 > 系統管理 > 使用者 > 使用者**。
2. 在快速篩選中搜尋使用者。 在此範例中，輸入 `shannon`。
3. 在顯示的使用者帳戶的 **使用者識別碼** 資料行中選擇連結。
4. 在 **使用者角色** 樹狀圖中，選擇 **角色 > 機器操作員**。
5. 關閉 **使用者詳細資料** 和 **使用者** 頁面返回主頁。

## <a name="configure-worker-account"></a>配置工作人員帳戶
1. 前往 **瀏覽窗格 > 模組 > 人力資源 > 工作人員 > 工作人員**。
2. 在快速篩選中搜尋使用者。 在此範例中，輸入 `shannon`。
3. 在顯示的使用者帳戶的 **名稱** 資料行中選擇連結。
4. 選擇 **時間登記** 索引標籤。
5. 選擇 **在登記終端上啟用**。
6. 在下列欄位中輸入或選擇值：  

    - **計算群組**  
    - **預設計算群組**  
    - **核准群組**  
    - **標準設定檔**  
    - **設定檔群組**  

7. 選取 **確定**。
8. 選擇 **編輯** 輸入新時間登記工作人員的徽章編號。 在 **徽章識別碼** 欄位中輸入值。
9. 選取 **儲存**。
10. 關閉 **工作人員詳細資料** 和 **工作人員** 頁面。

## <a name="assign-worker-to-device-group"></a>將工作人員指派到裝置群組
1. 前往 **產品控制 > 設定 > 製造執行 > 設定裝置的作業卡**。
2. 選取 **新增**。
3. 在清單中，選擇所需的工作人員。 對於此範例，選取 **SHANNON**。
4. 選取 **確定**。
5. 選擇 **編輯**。
6. 在 **生產單位** 欄位，您可以為工作人員設定預設篩選。 這將確保在工作人員登入裝置時僅顯示所選生產單位的生產作業。 輸入所需的值。
7. 關閉頁面。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]