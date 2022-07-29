---
title: 設定信用狀的銀行融資和銀行擔保書
description: 此工作建立處理銀行擔保書所需的銀行融資和過帳設定檔。
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
ms.openlocfilehash: 1a7e60903e31d98e24f578dc381bb0b140944e07a88516a6a81bbba1b8981982
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450435"
---
# <a name="set-up-bank-facilities-and-posting-profiles-for-letters-of-guarantee"></a>設定信用狀的銀行融資和銀行擔保書

[!include [banner](../../includes/banner.md)]

此工作建立處理銀行擔保書所需的銀行融資和過帳設定檔。



此工作使用 USMF 公司進行示範。 




## <a name="general-ledger-parameter"></a>總帳參數
1. 前往 [現金和銀行管理] > [設定] > [現金和銀行管理參數]。
2. 展開 [銀行單據] 區段。
3. 選擇 [啟用銀行擔保書] 選項。
4. 在 [交易日記帳] 欄位中，按一下下拉式按鈕開啟查詢。
5. 在清單中，尋找並選取所需的記錄。
6. 在清單中，點選已選取列的連結。
7. 按一下 [數字序列] 索引標籤。
    * 定義銀行擔保書編號和銀行擔保書交易參考的數字序列代碼  
8. 按一下 [儲存]。
9. 關閉頁面。

## <a name="create-bank-facility"></a>建立銀行融資
1. 前往 [現金和銀行管理參數] > [設定] > [銀行融資]。
2. 按一下 [新建]。
3. 在 [融資群組] 欄位中，輸入銀行擔保書交易的銀行融資群組名稱。
4. 在 [描述] 欄位中，輸入一個值。
5. 按一下 [儲存]。
6. 按一下 [融資類型] 索引標籤。
7. 按一下 [新建]。
8. 在 [融資類型] 欄位中，輸入與銀行融資合約相關的銀行融資類型名稱。
9. 在 [描述] 欄位中，輸入一個值。
10. 在 [融資群組] 欄位中，按一下下拉式按鈕開啟查詢。
11. 在清單中，尋找並選取所需的記錄。
12. 在清單中，點選已選取列的連結。
13. 在 [融資性質] 欄位中，選擇一個選項。
14. 按一下 [儲存]。
15. 關閉頁面。

## <a name="bank-posting-profile"></a>銀行過帳設定檔
1. 前往 [現金和銀行管理參數] > [設定] > [銀行單據過帳設定檔]。
2. 按一下 [新建]。
3. 在 [帳戶/群組號碼] 欄位中，按一下下拉式按鈕開啟查詢。
4. 在清單中，尋找並選取所需的記錄。
5. 在清單中，點選已選取列的連結。
6. 在 [結算科目] 欄位中，選擇結算的主科目。
7. 在 [收費科目] 欄位中，選擇費用交易的科目。
8. 在 [保證金帳戶] 欄位中，選擇保證金交易的帳戶。
9. 在 [清算帳戶] 欄位中，選擇銀行擔保書交易的清算帳戶。 
10. 按一下 [儲存]。
11. 關閉頁面。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]