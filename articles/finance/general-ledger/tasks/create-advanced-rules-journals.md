---
title: 建立日記帳進階規則
description: 此程序介紹如何為日記帳建立進階規則。
author: aprilolson
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalSetup, LedgerJournalControl, CompanyLookup, LedgerJournalPostControl
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: fe26409ebaa83595885756056810a4a2037045f0f8ad312b52c507343dec3b2d
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450861"
---
# <a name="create-advanced-rules-for-journals"></a>建立日記帳進階規則

[!include [banner](../../includes/banner.md)]

此程序介紹如何為日記帳建立進階規則。 這包括設定日記帳控制和使用者過帳限制。 這段程序使用 USMF 示範資料公司。


## <a name="set-up-journal-control"></a>設定日記帳控制
1. 在 **瀏覽窗格** 中，前往 **模組 > 總帳 > 日記帳設定 > 日記帳名稱**。
2. 在清單中，尋找並選取所需的記錄。
3. 請在 **動作窗格** 上，點擊 **日記帳控制**。
4. 在 **可以過帳哪些科目類型** 快速選項卡，點擊 **新增**。
5. 在 **公司帳戶** 欄位中，點擊下拉式按鈕以開啟查詢。
6. 在清單中，尋找並選取所需的記錄。
7. 在清單中，點選已選取列的連結。
8. 在 **哪些區段值對此日記帳有效** fastTab，點擊 **新增**。
9. 在 **科目結構** 欄位，點選下拉式按鈕打開查閱功能。
10. 在清單中，尋找並選取所需的記錄。
11. 在清單中，點選已選取列的連結。
12. 在 **區段** 欄位中，點擊下拉式按鈕以開啟查詢。
13. 在清單中，點選已選取列的連結。
14. 在 **起始值** 欄位中，點擊下拉式按鈕以開啟查詢。
15. 在清單中，尋找並選取所需的記錄。
16. 在清單中，點選已選取列的連結。
17. 在 **目標值** 欄位中，點擊下拉式按鈕以開啟查詢。
18. 在清單中，尋找並選取所需的記錄。
19. 在清單中，點選已選取列的連結。

## <a name="set-up-posting-restrictions"></a>設定過帳限制
1. 關閉頁面。
2. 點擊 **過帳限制**。
3. 在 **如何設定過帳限制** 欄位，選擇 [按使用者群組]。
4. 在樹狀圖中，選取 [您允許過帳此日記帳的群組]。
5. 點擊 **確定**。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]