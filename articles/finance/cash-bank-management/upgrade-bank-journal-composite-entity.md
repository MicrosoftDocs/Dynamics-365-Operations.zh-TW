---
title: 更新銀行日記帳複合實體
description: 本主題列出了將附加 BankTransactionType 欄位添加到複合 BankJournalEntity 所需的步驟。
author: panolte
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer
ms.reviewer: roschlom
ms.custom: 221654
ms.assetid: adb8146b-eb21-4be2-a338-a5b299fcc9a0
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 0d4334e9aa333aad116f0a0291d9175268661f11
ms.sourcegitcommit: e40a9fac5bac9f57a6dcfe73a1f21856eab9b6a9
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/02/2021
ms.locfileid: "8451032"
---
# <a name="update-the-bank-journal-composite-entity"></a>更新銀行日記帳複合實體

[!include [banner](../includes/banner.md)]

本主題列出了將附加 BankTransactionType 欄位添加到複合 BankJournalEntity 所需的步驟。

使用以下步驟將附加 BankTransactionType 欄位添加到複合 BankJournalEntity。

1.  編譯並同步以下銀行日記帳複合實體、實體和暫存表：
    -   複合實體\\BankJournalEntity
    -   實體\\BankJournalHeaderEntity
    -   實體\\BankJournalLineEntity
    -   表格\\BankJournalHeaderStaging
    -   表格\\BankJournalLineStaging

2.  資料管理員\\資料專案
    -   公開 **來源資料** 配置 **上的** 銀行交易類型。
        -   來源資料格式 = XML-元素
        -   實體名稱 = 銀行日記帳
        -   上傳資料檔案 = 新版本 SampleBankJournalCompositeEntity.xml
        -   按一下 **是的** 覆寫現有檔案。
        -   按一下 **是的** 從頭開始產生對應。
        -   驗證銀行交易類型是否已對應。
            -   按一下明細實體上的 **檢視對應**。
            -   驗證銀行交易類型是否從來源對應到暫存。

3.  匯入新陳述式。






[!INCLUDE[footer-include](../../includes/footer-banner.md)]
