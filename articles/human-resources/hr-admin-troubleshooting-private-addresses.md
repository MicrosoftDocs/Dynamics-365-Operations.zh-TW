---
title: 憑藉資訊安全角色存取私人位址
description: 本主題說明當客戶無法存取私人位址時的解決方法。
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
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 05895d58cfd108c45c3c75921cb6930b904a6482
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452445"
---
# <a name="access-to-private-addresses-by-security-role"></a>憑藉資訊安全角色存取私人位址


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

**問題**

待客戶複製資訊安全角色並以此新角色登入後，客戶無法看到標記為私人的位址。

**解決方案**

若要解決此問題，客戶必須針對重複的資訊安全角色跟隨這些步驟。

1. 前往 **組織管理\>全球通訊錄\>全球通訊錄參數**。
2. 請在 **私人位置安全性** 選項卡將新安全角色從 **可用角色** 清單移到 **選取角色** 清單。
3. 請選取 **儲存**。

![全球通訊錄參數頁面。](media/GAD-parameters.png)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
