---
title: 用於單位間會計的平衡日記帳
description: 本文介紹在「分類帳」頁面上選擇平衡財務維度時如何自動平衡日記帳。
author: kweekley
ms.date: 10/30/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerParameters
audience: Application User
ms.reviewer: roschlom
ms.custom: 15791
ms.assetid: 301bd80e-f8b1-4f12-8194-e6d7de736084
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7f6ffccb2ee504f182250dbf6d316823efafddf5
ms.sourcegitcommit: 4f8465729d7ae0bf5150a2785a6140c984c7030e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2021
ms.locfileid: "8451125"
---
# <a name="balanced-journals-for-interunit-accounting"></a>用於單位間會計的平衡日記帳

[!include [banner](../includes/banner.md)]

本文介紹在「分類帳」頁面上選擇平衡財務維度時如何自動平衡日記帳。 

如果科目分錄未在財務維度值級別平衡，則會自動創建其他科目分錄以平衡日記帳。 這些帳戶條目使用 **單位間 - 借方** 和 **單位間 - 信貸** 上的張貼類型 **自動交易帳戶** 頁面來確定主帳戶。 例如，會計科目第二段的業務單元被選為平衡財務維度，下面的會計分錄即將創建。

| &nbsp;               | &nbsp;    |
|----------------------|-----------|
| 6100 – MSP – OU\_256 | 100.00 DR |
| 6100 – NY – OU\_249  | 100.00 DR |
| 2100 – MSP – OU\_256 | 200.00 CR |

在這種情況下，將確定以下餘額：

-   對於業務單位 MSP = 100.00 CR
-   對於業務單位 NY = 100.00 DR

因此，會自動創建以下會計分錄以平衡財務維度值級別的日記帳。

| &nbsp;                            | &nbsp;    |
|-----------------------------------|-----------|
| (單位間借方) – MSP – OU\_256 | 100.00 DR |
| (單位間貸方) – NY – OU\_249 | 100.00 CR |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
