---
title: 建立應計方案
description: 本主題說明如何建立應計方案。
author: aprilolson
ms.date: 07/19/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerAccrualTable
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8ab36250365fefe37329f87769f16f546ca7326654db42aa7acb61fb37604ce2
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450864"
---
# <a name="create-accrual-schemes"></a>建立應計方案

[!include [banner](../../includes/banner.md)]

本主題說明如何建立應計方案。 此工作使用 USMF 公司進行示範。

1. 前往 **瀏覽窗格 > 模組 > 總帳 > 日記帳設定 > 應計方案**。
2. 選取 **新增**。
3. 在 **應計識別碼** 欄位中，輸入一個值。
4. 在 **應計方案的描述** 欄位中，輸入一個值。
5. 在 **借方** 欄位中，指定所需值。 定義的主科目將替換日記帳憑證行上的借方主科目，它還將用於根據分類帳應計交易沖銷遞延。  
6. 在 **貸方** 欄位中，指定所需值。 定義的主科目將替換日記帳憑證行上的貸方主科目，它還將用於根據分類帳應計交易沖銷遞延。  
7. 在 **憑證** 欄位，選擇您希望在過帳交易時確定的憑證。
8. 在 **描述** 欄位，輸入一個值來描述將過帳的交易。
9. 在 **週期頻率** 欄位，選擇交易發生的頻率。
10. 在 **發生次數 (根據週期)** 欄位中，輸入一個數字。
11. 在 **過帳交易** 欄位，選擇何時應過帳交易，例如 **每月**。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]