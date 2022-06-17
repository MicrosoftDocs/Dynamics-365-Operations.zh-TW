---
title: 年末結帳缺少的期初餘額
description: 本主題會說明為什麼您在將一年結帳時可能會缺少期初餘額，以及在缺少期初餘額時該如何重建這些餘額。
author: kweekley
ms.date: 05/12/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2020-12-14
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 4478f2b46f984c97ff01588098d64953dedf476e7f3f76aeecb29a0ff0074b9d
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8452745"
---
# <a name="year-end-close-missing-opening-balances"></a>年末結帳缺少的期初餘額

[!include [banner](../includes/banner.md)]

本主題會說明為什麼您在將一年結帳時可能會缺少期初餘額，以及在缺少期初餘額時該如何重建這些餘額。

### <a name="symptom"></a>徵兆

為什麼在執行總帳年末結帳後沒有任何期初餘額？ 

### <a name="resolution"></a>解決方法

如果您在總帳中將一年結帳，然後產生了未為下一個會計年度顯示期初餘額的試算表時，可以檢查以下事項。

如果 **復原上一次結帳** 欄位設定為 **是**，則代表相同會計年度的上一個年末結帳正在沖銷。 當您執行程序來沖銷年末結帳時，則期末與期初餘額的所有項目都會受到刪除，就像是該年從未結帳一樣。 憑單也會受到刪除。 年末結帳程序將不會再次自動執行。 您必須重新開始程序，這次請將 **復原上一次結帳** 選項更新為 **否**。

年末結帳常見問題主題中涵蓋了此案例。 如需詳細資訊，請參閱[年末活動常見問題](faq-year-end-activities.md)。

### <a name="symptom"></a>徵兆

我在 **復原上一次結帳** 選項設定為 **否** 的情況下執行了年末結帳，但我的會計年度仍然沒有期初餘額。

### <a name="resolution"></a>解決方法

首先檢查批次作業的狀態。 將一年結帳包含了許多獨立的任務，但最關鍵的步驟是帶有任務描述 **步驟 5.0.0** 的批次任務。 在此步驟中，會將期初交易及可選的結帳交易過帳至總帳。 

[![批次歷程記錄清單。](./media/yec-mssng-open-blnces-01.png)](./media/yec-mssng-open-blnces-01.png)

如果此步驟成功結束，但您未在 **試算表查詢** 頁面 (**總帳 > 查詢和報告 > 試算表**) 上看到期初餘額，則請檢閱年末結帳批次工作的結果，確認重建餘額步驟是否有成功完成。

[![年末結帳批次工作的結果。](./media/yec-mssng-open-blnces-02.png)](./media/yec-mssng-open-blnces-02.png)

如果此步驟因為任何理由失敗，則期初 (和選擇性的期末) 交易很可能已成功過帳。 您可以使用 **憑單交易查詢** 頁面來驗證總帳交易是否已成功過帳，方式是指定您所結帳年份之年末結帳對話方塊上提供的憑單編號與日期，(**總帳 > 查詢和報告 > 憑單交易**)。

[![憑單交易查詢。](./media/yec-mssng-open-blnces-03.png)](./media/yec-mssng-open-blnces-03.png)

如果期初 (和選擇性的期末) 憑單存在，您就不需要重新執行年末結帳。 反之，請參閱下節以取得有關如何繼續的資訊。

### <a name="symptom"></a>徵兆

年末結帳中的「重建餘額」步驟失敗，我是否需要重新執行整個年末結帳程序？

### <a name="resolution"></a>解決方法

重建餘額步驟會更新產生試算表查詢時所使用的總帳餘額。  這是年末結帳程序的最後一步。  如果這是唯一失敗的步驟，則代表總帳交易已成功過帳。  您不需要重新執行年末結帳。 您可以使用 **財務維度集** 頁面 (**總帳 > 會計科目表 > 維度 > 財務維度集**)，手動執行程序來重建餘額。

[![財務維度集頁面上的重建餘額按鈕。](./media/yec-mssng-open-blnces-04.png)](./media/yec-mssng-open-blnces-04.png)

如果此步驟的處理時間過長，我們建議檢閱財務維度集的最佳做法，如[更新財務維度集的最佳做法](https://community.dynamics.com/365/financeandoperations/b/dynamics-365-finance-blog/posts/best-practices-for-updating-financial-dimension-set-dimension-sets)中所述。 

