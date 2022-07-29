---
title: 使用者端中斷連線
description: 本主題說明如果客戶中斷與環境連線時的作法。
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
ms.openlocfilehash: b15c5db19f1b07e3d469986ac700138ecb1d1525
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452673"
---
# <a name="client-disconnects"></a>使用者端中斷連線


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

**環境細節** 

此問題會在所有環境發生。
 
**徵兆** 

客戶與環境中斷連線，原因不明。 客戶收到下列其中一則錯誤訊息：

- 我們失去您的連線。 請按一下關閉以繼續工作。
- 看起來您失去網路連線能力，請按一下重試再試一次。

**紅色標誌**

當使用者已在落實階段比較生產和測試環境的資訊，忘記他們正在工作階段之間移動時，時常發生這項問題。 如果使用者在這個階段，他們很可能會遇到這個問題。

**問題** 

**瀏覽器類型：** Google Chrome、Internet Explorer 和 Microsoft Edge

當相同使用者和瀏覽器類型同時打開兩個不同的工作階段時，Microsoft Dynamics 365 Human Resources 會中斷與使用者的連線。 (例如，使用者 A 在 Chrome 同時檢視環境 1 和環境 2。) 使用者是否打開不同的瀏覽器視窗或索引標籤並不重要。 如果同時在環境 1 和環境 2 使用相同的使用者憑證在相同的瀏覽器類型登入，人力資源部會中斷與其中一個工作階段的連線。

**解決方案**

確定預定的瀏覽器類型一次只打開一個環境。 使用者可以打開相同環境的多個工作階段 (亦即相同瀏覽器的多個索引標籤)。

希望同時在兩個環境之間跳轉的使用者應該在不同類型的瀏覽器打開每個環境。 (例如使用者 A 可以在 Chrome 檢視環境 1，而在 Microsoft Edge 檢視環境 2。)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
