---
title: 指派租約使用者角色
description: 本主題說明資產租約中使用的資訊安全角色。 它也解釋如何指派使用者給這些角色。
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SysOperationTemplateForm
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 7a3443cf9fa5b14ac0b3c4560ed45874939aa50cd665f4db46290f5af04bf6ce
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450774"
---
# <a name="assign-lease-user-roles"></a>指派租約使用者角色

[!include [banner](../includes/banner.md)]

本主題說明資產租約中使用的資訊安全角色。 它也解釋如何指派使用者給這些角色。

三個使用者角色區分資產租約中的存取權。 一個角色適合維護租約、一個適合檢視租約，以及另一個適合履行租約文書員的職責。 每個角色對所有租約頁面都有特定權限，每個角色讓使用者根據他們的工作職責檢視、建立、編輯或刪除租約。

| 角色           | 描述 |
|----------------|-------------|
| 維護租約 | 本角色的使用者可以新增、編輯、刪除和檢視租約。 此角色專為日常使用者設計，任務包括建立和過帳每月日記帳分錄及新增新租約。 此角色給所有資產租約功能存取權。 |
| 檢視租約     | 此角色的使用者只能檢視租約記錄、排程和跑報表。 他們無法建立新租約、編輯既有租約或根據租約建立日記帳分錄。 此角色專為只需檢視租約、租約期程和這些租約發生的交易使用者設計。 |
| 租約文書人員    | 此角色的使用者只建立新租約。 他們無法編輯或刪除既有租約、檢視租約期程或過帳租約日記帳分錄。 此角色專為從事資料輸入容量的使用者設計。 |

按照下列步驟指派使用者給資產租約使用的角色。

1. 前往 **系統管理\>安全性\>指派使用者給角色**。
2. 選取 **維護租約**、**租約文書人員** 或 **檢視租約** 角色，然後選取 **手動指派/排除使用者**。
3. 選取要指派給角色的使用者，然後選取 **指派給角色**。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
