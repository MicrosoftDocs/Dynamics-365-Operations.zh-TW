---
title: 設定主科目類別
description: 本主題說明如何在 Dynamics 365 Finance 中設定主科目類別。
author: aprilolson
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: MainAccountCategory, MainAccountCategoryLink
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3530ba65dc0a4978ca4b1ca4b1acd96c79749a6f16e430fb260729dd3e28dbac
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450327"
---
# <a name="set-up-main-account-categories"></a>設定主科目類別

[!include [banner](../../includes/banner.md)]

本主題說明如何設定主科目類別。 主科目類別用於財務報告和 Power BI 中的預設報告。 預設建立的主科目類別可以重新命名，但不能刪除。 可以建立其他帳戶類別並用於報告和分析目的。 此主題使用 USMF 示範公司。

## <a name="create-a-main-account-category"></a>建立主科目類別
1. 在瀏覽窗格中，前往 **模組 > 總分類帳 > 會計科目表 > 科目 > 主科目類別**。
2. 選取 **新增**。
3. 在 **主科目類別** 欄位中，輸入一個唯一名稱。
4. 在 **描述** 欄位中，輸入主科目類別的描述。
5. 在 **主科目類型** 欄位中，選取將連結至該類別的主科目類型。

## <a name="link-main-accounts-to-account-category"></a>將主科目連結至科目類別
1. 按一下 **連結主科目**。
2. 在清單中勾選 **已連結** 欄中的方塊，來選取要指派給主科目類別的主科目。 將主科目指派給主科目類別，會在該類別用於財務報表與分析時彙總科目餘額。  
3. 選擇或清除 **已連結** 選項，以選擇主科目。
4. 選取 **確定**。
5. 選取 **是**。


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]