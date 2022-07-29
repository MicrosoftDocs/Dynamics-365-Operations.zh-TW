---
title: 進階銀行對帳 MT940 匯入 - 綜合資料實體升級
description: 需要將序號新增至銀行對帳單匯入實體以支援 MT940 格式。
author: panolte
ms.date: 06/20/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer
ms.reviewer: roschlom
ms.custom: 221594
ms.assetid: dddc99ae-56ae-48df-856a-131079c17dcb
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: c891a5139ff7de85e6762513f57236e24f1644529d7825c9ce5e1dfda50fbad8
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450405"
---
# <a name="advanced-bank-reconciliation-mt940-import--composite-data-entity-upgrade"></a>進階銀行對帳 MT940 匯入 - 綜合資料實體升級

[!include [banner](../includes/banner.md)]

需要將序號新增至銀行對帳單匯入實體以支援 MT940 格式。 

使用以下步驟新增銀行對帳單匯入實體以支援 MT940 格式。

1.  編譯並同步以下作業：
    -   複合實體\\BankStatementImportEntity
    -   實體\\BankStatementBalanceEntity
    -   實體\\BankStatementDocumentEntity
    -   實體\\BankStatementEntity
    -   實體\\BankStatementLineEntity
    -   資料表\\BankStatementStaging

2.  資料管理\\資料專案。
    1.  載入 MT940 匯入專案
        1.  變更 XSLT。
            -   點擊 **查看對應**。
            -   在銀行對帳單文件上點擊 **查看對應**。
            -   點擊 **轉換**
            -   刪除 BankReconiliation-to-Composite.xslt 檔案。
            -   新增新版本 BankReconiliation-to-Composite.xsl。

        2.  在 **資料來源** 版面配置上公開 **序號**。
            1.  來源資料格式 = XML-Element。
            2.  實體名稱 = 銀行對帳單
            3.  上傳資料檔案 = 新版本 SampleBankCompositeEntity.xml。
            4.  按一下 **是的** 覆寫現有檔案。
            5.  按一下 **是** 從產生新對應。
            6.  驗證 **序號** 是否已對應。
                -   在對帳單實體上點擊 **查看對應**。
                -   驗證 **SequenceNumber** 是否從來源對應到暫存。

3.  匯入新陳述式。






[!INCLUDE[footer-include](../../includes/footer-banner.md)]