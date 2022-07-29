---
title: 建立固定資產
description: 本主題說明如何從固定資產清單頁面建立新的固定資產記錄。
author: moaamer
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: AssetTable, AssetBook
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7bf6e74253d2cf4150914fcb8bcc51aa2f32c0435c563b677def40115e0163fa
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450612"
---
# <a name="create-a-fixed-asset"></a>建立固定資產

[!include [banner](../../includes/banner.md)]

本主題說明如何從 **固定資產** 清單頁面建立新的固定資產記錄。

系統根據分配給固定資產群組的編號序列分配資產編號。 如果您使用固定資產範本透過Microsoft Excel 增益集匯入資產，或者如果您使用其他匯入作業，系統會自動建立固定資產記錄並累加資產編號。

要手動建立資產記錄，請執行以下步驟。

1. 前往 **瀏覽窗格 \> 模組 \> 固定資產 \> 固定資產 \> 固定資產**。
2. 在 **動作窗格** 上，選擇 **新增**。
3. 在 **固定資產群組** 欄位中，輸入或選取一個值。 如果您在 **固定資產參數** 和 **固定資產群組** 中啟用了 **自動編號固定資產功能**，則 **編號** 欄位將使用預設。 如果未啟用該功能，您必須輸入唯一編號來識別固定資產。
4. 在 **名稱** 欄位中，輸入一個值。 輸入您的企業對此資產所需的附加資訊。
5. 在 **動作窗格** 上，選取 **帳簿**。
6. 在 **購置日期** 欄位，輸入日期。
7. 在 **購置價格** 欄位中，輸入一個數字。

    - 輸入您的企業對此帳簿所需的附加資訊。
    - 輸入您的企業對剩餘帳簿所需的附加資訊。

8. 關閉頁面。

您還可以透過使用 Excel 增益集或從 **資料管理** 工作區執行匯入作業來匯入固定資產。 在執行匯入之前，請在範本中輸入必填欄位的值。

如果您沒有在 Excel 增益集的範本中或在資料管理中定義固定資產編號，系統會為每個匯入的資產建立一個固定資產編號，並為每個資產自動累加編號序列。 但是，如果您在範本中匯入資產並定義資產編號，系統 **不會** 自動累加編號序列。 在這種情況下，管理員可能必須手動更新編號序列。 如果您在 Excel 增益集的範本中定義了固定資產編號，系統將使用定義的固定資產編號並累加編號序列。

> [!NOTE]                                                                                                         
> 過帳折舊後，**帳簿** 頁面上的 **投入使用** 和 **折舊執行日期** 欄位將鎖定。 此外，這兩個欄位都不會從資料實體更新。

> [!WARNING]
> 如果交易記錄已過帳到關聯帳簿，或者如果新建立的固定資產輸入到日記帳行但未過帳，則不會刪除固定資產記錄。 


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]