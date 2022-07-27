---
title: 用戶端 FAQ
description: 本文提供有關 Finance and Operations 使用者端的常用問題解答。
author: jasongre
ms.date: 09/11/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.custom: 12334
ms.assetid: a9a57f0e-a67c-46b1-83c9-5d6350fb3b86
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e64fb2453f17760b17ca2a7d3f593ac34cde0cc9
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8460241"
---
# <a name="client-faq"></a>用戶端 FAQ

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

本文提供有關 Finance and Operations 使用者端的常用問題解答。

## <a name="why-arent-symbols-loaded"></a>為什麼沒有載入符號？

瀏覽器上的安全設定可能會阻止符號正確載入。 若要解決此問題，請嘗試以下步驟：

- 如果您在 Internet Explorer 中遇到此問題，請點選 **工具**，然後點選 **網路選項**。 在網路選項對話方塊的 **隱私** 索引標籤上，點選 **自訂級別**，並確保選中 **字型下載** 選項。
- 否則，您可能必須將應用網站新增到受信任網站清單中。

## <a name="i-miss-the-ribbon-from-dynamics-ax-2012-can-i-keep-action-pane-tabs-open-all-the-time"></a>我想念 Dynamics AX 2012 的函數區。 我可以一直打開操作窗格索引標籤嗎？

我們計畫盡快實施此函數。 然後，使用者將能夠選取始終打開操作窗格上的索引標籤。 否則，索引標籤將在不使用時折疊起來，為頁面獲得更多螢幕空間。

## <a name="why-do-i-sometimes-see-different-shortcut-menus-when-i-right-click"></a>為什麼有時我在按右鍵點選時會看到不同的捷徑選單？

如果在可編輯欄位中點選鼠標右鍵 (或者如果選取了文字)，則會顯示瀏覽器的捷徑選單。 此選單讓您可以存取 **剪下**、**複製** 和 **貼上** 命令。 我們不能將這些命令嵌入到捷徑選單中，因為出於安全原因，瀏覽器不允許我們以編程方式存取系統剪貼簿。

如果您按右鍵點選欄位標籤或讀取專用控制項目的值，您將看到捷徑選單。

為了使鍵盤存取更容易，我們計畫在將來實施一個可以打開捷徑選單的鍵盤快捷鍵方式。

## <a name="where-is-the-view-details-functionality"></a>查看詳情函數在哪裡？

**查看詳情** 選項提供了多種方式：

- 如果控制項目具有 **查看詳情** 函數，並且控制項目具有值，則該值將顯示為超連結。 您可以點選超連結以打開包含其他詳情的頁面。
- **查看詳情** 也是捷徑選單上的一個選項。 如需按右鍵點選時何時顯示捷徑選單的相關資訊，請參閱上一節。


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]