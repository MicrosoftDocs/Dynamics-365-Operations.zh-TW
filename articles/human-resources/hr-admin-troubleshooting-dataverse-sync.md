---
title: 重設 Dataverse 同步
description: 本主題說明如何針對 Microsoft Dynamics 365 Human Resources 與 Microsoft Dataverse 中的人力資本管理 (HCM) 共同解決方案之間，記錄無法正確同步的問題進行障礙排除。
author: jaredha
ms.date: 09/27/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2021-09-27
ms.dyn365.ops.version: Platform update 42
ms.openlocfilehash: d6b20b6b2ae4fdbbfb27a765dfb7a1dc82fe7981
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452676"
---
# <a name="reset-dataverse-synchronization"></a>重設 Dataverse 同步


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

## <a name="issue"></a>問題

Microsoft Dynamics 365 Human Resources 和 Microsoft Dataverse 中的人力資本管理 (HCM) 共同解決方案實體之間的記錄無法同步。 更多有關同步的資訊，請前往[配置 Dataverse 整合](hr-admin-integration-common-data-service.md)。 無法正確同步的問題會發生在 **Dataverse 整合重試** 或 **Dataverse 整合錯過請求同步** 批次工作卡在 **執行** 狀態時。

## <a name="resolution"></a>解決方法

當 **Dataverse 整合重試** 或 **Dataverse 整合錯過要求同步** 批次工作卡在 **執行中** 或 **取消中** 的狀態時，您可以重設狀態。 這可藉由按照[重設卡住的批次工作](hr-admin-troubleshooting-batch-execution.md)中的指引取消批次工作達成。 取消批次工作後，您可以將批次工作設定為 **等待** 狀態。 接著批次工作將在下一個排程的執行時間執行。

1. 如果您還沒有這麼做，請啟用 **功能管理** 中的 **增強的批次中止** 功能。
   1. 請前往 **功能管理** 頁 (**系統管理** > **摘要** > **功能管理**)。
   2. 選取 **全部** 索引標籤。
   3. 選取 **功能名稱** 欄位列並過濾 **增強的批次中止**。
   4. 如果尚未啟用，請選取 **啟用** 動作。

2. 關閉 Dataverse 整合。
   1. 請前往 **Microsoft Dataverse 整合** 頁 (**系統管理** 前往 **連結** > **整合** > **Dataverse組態**)。
   2. 將 **啟用 Dataverse 整合** 設定為 **否**。

3. 取消 **Dataverse 整合重試** 批次工作。
   1. 請前往 **批次工作** 頁 (**系統管理** 前往 **連結** > **批次工作** > **批次工作**)。
   2. 以 **整合** 過濾 **職位描述** 欄位。
   3. 選取 **Dataverse 整合重試** 批次工作。
   4. 請在操作功能區上選取 **批次工作**、**強制取消**，然後選取 **是** 確認。

   > [!NOTE]
   > 根據首次啟用整合的時間，批次工作的描述可能是 **Common Data Service 整合重試**。 如果已經列出，請選取此批次工作，而不是 **Dataverse 整合重試** 批次工作。

4. 刪除所有 Dataverse 整合批次工作。
   1. 請在 **批次工作** 頁選取 **Dataverse 整合錯過要求同步**、**Dataverse 整合重試** 和 **Dataverse 整合初步同步** 批次工作。
   2. 請在操作功能區上選取 **變更狀態** 動作。 
   3. 選取 **保留** 並選取 **確定**。
   4. 請在操作功能區上選取 **刪除** 動作，然後選取 **是** 確認動作。

5. 開啟 Dataverse 整合批次工作。
   1. 請前往 **Microsoft Dataverse 整合** 頁 (**系統管理** > **連結** > **整合** > **Dataverse 組態**)。
   2. 將 **啟用 Dataverse 整合** 設定為 **是**。

6. 請前往 **批次工作** 頁確認已建立 **Dataverse 整合重試** 和 **Dataverse 整合錯過要求同步** 批次工作。

重建批次工作後，您現在可以監督 **Dataverse 整合重試** 批次工作，查看工作執行需花費的時間。 接著您可以驗證記錄是否正確同步到 Microsoft Dataverse 中的 HCM 共同解決方案。

## <a name="see-also"></a>也請參閱

[配置 Dataverse 整合](hr-admin-integration-common-data-service.md)<br>
[重設卡住的批次工作](hr-admin-troubleshooting-batch-execution.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
