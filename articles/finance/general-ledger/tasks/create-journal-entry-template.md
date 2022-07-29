---
title: 使用範本建立日記帳分錄
description: 已過帳的日記帳憑單可以儲存為憑單範本，並套用至新的日記帳憑單。
author: aprilolson
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransDaily, LedgerJournalTransVoucherTemplate
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c015bbba6784f511ac51802ea005d2114e703861370e33350cff62b6005d630c
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450315"
---
# <a name="create-a-journal-entry-using-template"></a>使用範本建立日記帳分錄

[!include [banner](../../includes/banner.md)]

已過帳的日記帳憑單可以儲存為憑單範本，並套用至新的日記帳憑單。 此程序使用的是 USMF 示範公司。

1. 前往 **導覽窗格 > 模組 > 總帳 > 日記帳分錄 > 總帳**。
2. 在 **動作窗格** 上，按一下 **新增**。 此程序會先建立和過帳日記帳憑單，但任何先前過帳的日記帳憑單都可以儲存為範本。  
3. 在 **名稱** 欄位中，點選下拉式按鈕開啟查詢。
4. 在清單中，尋找並選取所需的記錄。
5. 在清單中，點選已選取列的連結。
6. 點選 **行**。
7. 在 **科目類型** 欄位中，輸入一個值。
8. 在 **描述** 欄位中，輸入一個值。
9. 在 **借方** 欄位中輸入值。
10. 點選 **新增**。
11. 在 **科目類型** 欄位中，輸入一個值。
12. 在 **描述** 欄位中，輸入一個值。
13. 在 **借方** 欄位中輸入值。
14. 點選 **新增**。
14. 在 **科目** 欄位中，指定所需值。
15. 在 **描述** 欄位中，輸入一個值。
16. 在 **貸方** 欄位，輸入一個值來讓憑單試算餘額。
17. 在 **動作窗格** 上，按一下 **過帳**。
18. 點選 **功能**。
19. 點選 **儲存憑單** 範本。
20. 這個程序使用 **百分比範本** 類型。 點選 [確定]。
    - 百分比：將憑單中的金額轉換為百分比係數，允許在選擇憑單範本時套用任何金額。
    - 金額：將儲存和套用實際金額。  
21. 點選 **一般日記帳**。
22. 點選 **新增**。
23. 在 **名稱** 欄位中，點選下拉式按鈕開啟查詢。
24. 在清單中，點選已選取列的連結。
25. 點選 **行**。
26. 點選 **功能**。
27. 點選 **選取憑單範本**。
28. 尋找您之前建立的範本。 點選 **確定**。 如果存在其他範本，您可能需要點選 **上一步**，然後選擇正確的範本。  
29. 在 **金額** 欄位，輸入要套用至憑單的金額。 僅當憑單範本的類型為百分比時才顯示 **金額** 欄位。  
30. 點選 **確定**。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]