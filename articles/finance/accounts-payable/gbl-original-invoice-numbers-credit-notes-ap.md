---
title: 參考同意折讓照會通知裡的原始發票 (供應商發票)
description: 本主題說明建立同意折讓照會通知時建立原始發票的參照依據方法。
author: v-oloski
ms.date: 09/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: v-oloski
ms.search.validFrom: 2021-09-23
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 6114ffb4d3b9e942887cbfa10c6039b0d73af7e1
ms.sourcegitcommit: 86f0574363fb869482ef73ff294f345f81d17c5b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8450993"
---
# <a name="reference-original-invoices-in-credit-notes-vendor-invoices"></a>參考同意折讓照會通知裡的原始發票 (供應商發票)

[!include [banner](../includes/banner.md)]

本主題說明建立同意折讓照會通知時建立原始發票的參照依據方法。

## <a name="prerequisites"></a>前提條件

請在 **功能管理** 工作區啟用 **為供應商發票啟用開立貸方憑證發票** 功能。 更多資訊，請參閱[功能管理概觀](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)。

本主題描述的功能適用下列商業文件。

**應付帳款：**

- 採購訂單
- 發票日記帳
- 發票登記

**總帳：**

- 普通日記帳

## <a name="define-a-reference-to-an-original-invoice"></a>定義原始發票的參照依據

請使用下列程序定義對特定商業文件類型中原始發票的參照依據。

### <a name="vendor-credit-note-purchase-order"></a>供應商同意折讓照會通知 (採購訂單)

1. 請前往 **應付帳款**\>**採購訂單**\>**所有採購訂單**。
2. 新建採購訂單，或使用既有訂單建立同意折讓照會通知。
3. 請在動作窗格的 **發票** 選項卡上的 **簡介** 群組選取 **開立貸方憑證發票**。
4. 請輸入更正的原因和原始發票的參照依據。

### <a name="vendor-credit-note-ledger-journals"></a>供應商貸方同意折讓照會通知 (總帳日記帳)

1. 請執行以下其中一個步驟：

    - 請前往 **應付帳款**\>**發票日記帳**。
    - 請前往 **應付帳款**\>**發票登錄**。
    - 請前往 **總帳**\>**日記帳分錄**\>**普通日記帳**。

2. 新建日記帳和日記帳行項。
3. 請在動作窗格上選取 **功能**\>**開立貸方憑證發票**。
4. 請輸入更正的原因和原始發票的參照依據。

> [!NOTE]
> 如果 **科目類型** 欄位設定為 **供應商**，可在普通日記帳憑證看見 **開立貸方憑證發票** 指令。
