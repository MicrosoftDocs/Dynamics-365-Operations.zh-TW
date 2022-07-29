---
title: 重設卡住的批次工作
description: 本主題說明如何解決卡住的批次工作問題。
author: andreabichsel
ms.date: 03/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2021-03-19
ms.dyn365.ops.version: Platform update 42
ms.openlocfilehash: 859f039a928cdc57c9f227885d0f00ef79980f28
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452631"
---
# <a name="reset-stuck-batch-jobs"></a>重設卡住的批次工作


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

## <a name="issue"></a>問題

Microsoft Dynamics 365 Human Resources 會經歷批次工作卡在 **執行** 或 **取消** 狀態未能完成的問題。

## <a name="resolution"></a>解決方案

當批次工作卡在 **執行** 或 **取消** 狀態時，您可以強制取消工作重設狀態。 取消後，您可以將批次工作設定為 **等待** 狀態。 然後它將再次撿拾方便下次排程批次執行。

1. 請在 **系統管理** 工作區選取 **連結** 頁和 **批次工作**。

2. 請在 **批次工作** 清單頁選取需要重設的工作。

3. 請在操作功能區上選取 **強制取消**，並確認操作。

   > [!NOTE]
   > **強制取消** 動作只在選取的批次工作狀態為 **執行** 或 **取消**，並且沒有批次執行或取消流程時才能使用。

4. 請在操作功能區上選取 **變更狀態**。

5. 請在 **選取新狀態** 頁上選取 **等待**，然後選取 **確認**。

   ![選取新批次工作狀態。](./media/hr-admin-reset-batch-job-status.png)

## <a name="see-also"></a>也請參閱

[藉由排程下班後的批次工作來最佳化效能](hr-admin-troubleshooting-batch-jobs.md)<br>
[使用自動清理任務來最佳化效能](hr-admin-troubleshooting-batch-history.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
