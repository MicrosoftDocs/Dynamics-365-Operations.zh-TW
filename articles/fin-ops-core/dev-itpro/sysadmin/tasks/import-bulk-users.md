---
title: 從 Azure Active Directory 匯入使用者
description: 系統管理員可以使用此過程手動匯入選定使用者或從 Azure Active Directory 匯入大量使用者。
author: peakerbl
ms.date: 07/07/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ce8c98add0c6d5fb07b3ba5338037d9a12b1d8e50a2d2039b0231d3d305c9ebe
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460537"
---
# <a name="import-users-from-azure-active-directory"></a>從 Azure Active Directory 匯入使用者

[!include [banner](../../includes/banner.md)]

## <a name="import-select-users"></a>匯入選定使用者

系統管理員可以使用此程序從 Azure Active Directory (Azure AD) 匯入選定使用者。

1. 將使用目前工作階段公司作為預設公司匯入使用者。 如果適用，請在匯入使用者之前更改目前公司。
2. 進入 **系統管理 > 使用者 > 使用者**。
3. 點選 **匯入使用者**。
4. 選取應匯入的使用者並選取 **匯入使用者**。

匯入完成後，需要為使用者指派角色。

## <a name="import-users-in-bulk"></a>批次匯入使用者

系統管理員可以使用此程序從 Azure Active Directory 匯入大量使用者。
請注意，使用批次匯入選項時無法選取使用者。

## <a name="run-the-import-as-a-batch-job"></a>作為批次處理作業執行匯入
1. 將使用目前工作階段公司作為預設公司匯入使用者。 如果適用，請在匯入使用者之前更改目前公司。
2. 進入 **系統管理 > 使用者 > 使用者**。
3. 點選 **批次匯入**。
4. 展開 **在背景執行** 區塊。
4. 請在 **批次處理** 欄位中選取 **是**。
6. 請在 **批次群組** 欄位中輸入或選取一值。 這是一個選取性步驟。  
7. 在 **私人** 欄位中選取 **是**。 這是一個選取性步驟。  
8. 在 **關鍵工作** 欄位中選取 **是**。 這是一個選取性步驟。  
9. 在 **監控類別** 欄位中，選取一個選項。
10. 點選 **確定**。

匯入完成後，需要為使用者指派角色。

## <a name="run-in-a-sandbox-environment"></a>在沙箱環境中執行
1. 選取 **批次匯入**。
2. 選取 **確定**。


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]