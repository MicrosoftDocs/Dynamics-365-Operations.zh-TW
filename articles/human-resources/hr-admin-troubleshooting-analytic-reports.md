---
title: 排除障礙分析報告
description: 本主題說明如果客戶的資料變更未在客戶的任何工作區出現，如何排除障礙和診斷問題。
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
ms.openlocfilehash: 6ea04c06858cc98b0e233b9133d9dfbebfe59fd6
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452388"
---
# <a name="troubleshoot-analytic-reports"></a>排除障礙分析報告


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

**問題**

客戶的資料變更不在任何客戶工作區的 **分析** 索引標籤上出現。

**原因**

預設情況下，Microsoft Power BI 報告會根據部署測量批次工作排程每四小時重新整理一次。

**解決方案**

此問題可能只是時間問題。 請按照這些步驟開始批次工作並更新分析工作區。

1. 請打開 **系統管理\>連結\>批次工作\>批次工作** 的 **批次工作** 頁。 或者使用搜尋並輸入 **批次工作** 亦可。
1. 找到清單裡的 **部署測量** 工作。
1. 選取本頁最上方的 **編輯**，並將排程的開始日期/時間設定為將重新整理分析到更接近目前時間的值。

![批次工作。](media/batch-jobs.png)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
