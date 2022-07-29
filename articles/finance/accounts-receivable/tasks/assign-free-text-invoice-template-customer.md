---
title: 將普通發票範本分配給客戶
description: 此工作說明如何將普通發票範本分配給客戶。
author: ShivamPandey-msft
ms.date: 08/12/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CustTable, CustRecurrenceInvoice
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: fb8a683792051a95b443fac47b4670f37c12cc4b4142ee2290b89ee1845662cf
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450420"
---
# <a name="assign-a-free-text-invoice-template-to-a-customer"></a>將普通發票範本分配給客戶

[!include [banner](../../includes/banner.md)]

此工作說明如何將普通發票範本分配給客戶。 此工作使用 USMF 示範公司，適用於負責管理和處理應收帳款發票的使用者。

1. 在 **瀏覽窗格** 中，前往 **模組 > 應收帳款 > 客戶 > 所有客戶**。
2. 在清單中，尋找並選取所需的記錄。
3. 在 **動作窗格** 上按一下 **發票**。
4. 點擊 **週期性發票**。 使用此頁面將普通發票範本分配給客戶，並指定將發票發送給客戶的頻率。  
5. 點擊 **新增** 將新範本分配給客戶。
6. 在 **範本** 欄位，選擇您要分配給客戶的普通發票範本。
7. 在清單中，尋找並選取所需的記錄。
8. 在清單中，點選已選取列的連結。
9. 在 **記帳開始日期** 欄位，輸入產生第一張發票的日期。
10. 在 **週期結束** 區段，輸入週期的結束日期。  
    * 選擇以下選項之一：無結束日期 - 將無限期產生發票，直到從客戶帳戶中刪除範本。
    * 計費結束日期 - 選擇此選項並輸入可以產生發票的最後日期。  
11. 在 **最大累計金額** 欄位，輸入最大累計金額，達到此值後將停止產生發票。 輸入使用所選範本可以達到的最大累積金額。 例如，如果您輸入 1,000.00，並在每月產生 100.00 金額的發票，則發票在產生第十個時將停止產生。  
12. 在 **使用預設值產生週期發票** 區段，選擇普通發票範本或客戶帳戶。 建立發票時，選擇是否使用普通發票範本或客戶帳戶來確定語言、過帳範本、銷售稅組、品項銷售稅組、清單代碼、交貨國家/地區、幣種、付款期限、付款方式、付款說明、付款計劃、現金折扣、財務維度和轉帳單的預設值。  
13. 在 **週期模式** 欄位，選擇週期模式。
    + 每日 - 選擇此選項並在「每」欄位中輸入天數。 例如，如果您輸入 15，則會每 15 天為該客戶產生一次發票。
    + 每週 - 選擇此選項並在「每」欄位中輸入週數。 例如，如果您輸入 2，則會每 2 週為該客戶產生一次發票。
    + 每月 - 選擇此選項並在「每」欄位中輸入月數。 例如，如果您輸入 6，則會每 6 個月為該客戶產生一次發票。
    + 每年 - 選擇此選項並在「每」欄位中輸入年數。 例如，如果您輸入 2，則會每 2 年為該客戶產生一次發票。  
14. 在 **每** 欄位中，輸入數字。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]