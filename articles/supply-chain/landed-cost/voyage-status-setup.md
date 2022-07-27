---
title: 航程狀態設定
description: 本主題介紹如何建立使用者可以指派給航程的狀態值。
author: sherry-zheng
ms.date: 01/13/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ITMStatusTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-01-13
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 01bfc5198b62cfe56df9ec6763d5d0ff95f13ed5
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448365"
---
# <a name="voyage-status-setup"></a>航程狀態設定

[!include [banner](../../includes/banner.md)]

在 **航程狀態** 頁面，可以建立使用者能指派給航程的狀態值組。 使用者可以將航程狀態值指派給航程的所有等級：航程、裝運集裝箱、帳頁、訂購單和品項 (採購行和轉移單行)。 它們用於兩個目的：

- 通知使用者航程、裝運集裝箱、帳頁、訂購單或品項 (採購行和轉移訂單行) 的狀態。
- 透過防止修改或刪除來限制成本區域的使用。

若要設定您的航程狀態，請前往 **到岸成本 \> 設定 \> 航程狀態**。 在那裡，您可以使用動作窗格上的按鈕來新增、移除和編輯狀態。

每個成本區域都有自己的航程狀態集和階層。 因此，在 **航程狀態** 面頁的 **成本區域** 欄位，必須先選擇要查看或建立航程狀態的成本區域。 然後，對於每個航程狀態，根據需要設定下表中描述的欄位。 請注意，航程的狀態也可以透過系統事件自動變更，例如使用追蹤控制中心建立的規則。

| 欄位 | 描述 |
|---|---|
| 航程狀態 | 輸入航程狀態的名稱。 |
| 描述 | 輸入航程狀態的描述。 |
| 修改 | 如果允許使用者修改具有此狀態的航程，請選取此核取方塊。 |
| 刪除 | 如果允許使用者刪除具有此狀態的航程，請選取此核取方塊。 |
| 強制 | 選取此核取方塊讓航程狀態成為強制資訊，使其不能被跳過。 |
| 上層 | 使用此欄位在狀態值之間建立階層。 航程狀態只能在階層中從上層狀態向下變更為子狀態之一 (手動或自動)。

> [!NOTE]
> 您只需設定組織使用的特定航程狀態。 典型的航程狀態包括 *已確認*、*在途貨物*、*已接收*、*成本計算已就緒* 和 *已計算成本*。 但是，可能存在其他狀態。
