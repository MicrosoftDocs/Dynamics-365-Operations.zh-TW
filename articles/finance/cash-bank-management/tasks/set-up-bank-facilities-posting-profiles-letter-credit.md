---
title: 設定信用狀的銀行融資和過帳設定檔
description: 本程序會逐步指引建立所需的「銀行融資和過帳設定檔」，以便處理「信用狀」。
author: kweekley
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: BankParameters, DefaultDashboard, BankDocumentSetup, BankDocumentPosting
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9cdfceef4099a8f2ebfde22949d6439dfc623ac153578265da5bfb4052ee639d
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450468"
---
# <a name="set-up-bank-facilities-and-posting-profiles-for-letter-of-credit"></a>設定信用狀的銀行融資和過帳設定檔

[!include [banner](../../includes/banner.md)]

本程序會逐步指引建立所需的「銀行融資和過帳設定檔」，以便處理「信用狀」。 

此工作使用的示範公司是 USMF。






## <a name="general-ledger-parameter"></a>總帳參數
1. 前往 [現金和銀行管理] > [設定] > [現金和銀行管理參數]。
2. 展開 [銀行單據] 區段。
3. 選擇 [啟用進口信用狀] 選項。
4. 選擇 [啟用出口信用狀] 選項。
5. 按一下 [儲存]。
6. 關閉頁面。

## <a name="create-bank-facility"></a>建立銀行融資
1. 前往 [現金和銀行管理參數] > [設定] > [銀行融資]。
2. 按一下 [新建]。
3. 在 [融資群組] 欄位中，輸入銀行融資群組名稱。
4. 在 [說明] 欄位中，輸入銀行融資群組說明。
5. 按一下 [儲存]。
6. 按一下 [融資類型] 索引標籤。
7. 按一下 [新建]。
8. 在 [融資類型] 欄位中，輸入唯一代碼。
9. 在 [描述] 欄位中，輸入一個值。
10. 在 [融資群組] 欄位中，按一下下拉式按鈕開啟查詢。
11. 在清單中，尋找並選取所需的記錄。
12. 在清單中，點選已選取列的連結。
13. 在 [融資性質] 欄位中，選擇銀行融資的性質。
14. 按一下 [儲存]。
15. 關閉頁面。

## <a name="bank-posting-profile"></a>銀行過帳設定檔
1. 前往 [現金和銀行管理參數] > [設定] > [銀行單據過帳設定檔]。
2. 按一下 [新建]。
3. 在 [帳戶/群組號碼] 欄位中，按一下下拉式按鈕開啟查詢。
4. 在清單中，尋找並選取所需的記錄。
5. 在清單中，點選已選取列的連結。
6. 選擇主科目以進行結算。
    * 此科目用於計算現金流量預測。  
7. 在 [收費科目] 欄位中，選擇費用交易的科目。
8. 在 [保證金帳戶] 欄位中，選擇保證金交易的帳戶。
    * 此科目在過帳期初保證金時記入借方，並在過帳付款時記入貸方。  
9. 按一下 [儲存]。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]