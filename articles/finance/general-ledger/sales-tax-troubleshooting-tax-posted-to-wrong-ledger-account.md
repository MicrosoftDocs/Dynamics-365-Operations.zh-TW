---
title: 稅款過帳到憑單中錯誤的分類帳科目
description: 本主題提供的資料可在稅款過帳到憑單中錯誤的分類帳科目時，協助疑難排解。
author: qire
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 3d60265df7ff1f447e20866b8b8a447d88db8cc4b3dccedebc0f18ce8f0f70dc
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450489"
---
# <a name="tax-is-posted-to-the-wrong-ledger-account-in-the-voucher"></a>稅款過帳到憑單中錯誤的分類帳科目

[!include [banner](../includes/banner.md)]

過帳期間，稅款可能會過帳到憑單中錯誤的會計科目。 若要解決此問題，請根據需要按照以下各部分中的步驟操作。 本主題中的範例使用銷售訂單作為商業文件。

## <a name="find-the-tax-code-of-the-incorrectly-posted-tax-transaction"></a>查找錯誤過帳稅務交易的稅籍代碼

1. 在 **憑單交易** 頁面中，選擇要處理的交易，然後選擇 **已過帳銷售稅**。

    [![憑單交易頁面的已過帳銷售稅按鈕。](./media/tax-posted-to-wrong-ledger-account-Picture1.png)](./media/tax-posted-to-wrong-ledger-account-Picture1.png)

2. 查看 **銷售稅代碼** 欄位中的值。 在這個範例中，是 **增值稅 19**。

    [![已過帳銷售稅頁面上的銷售稅代碼欄位。](./media/tax-posted-to-wrong-ledger-account-Picture2.png)](./media/tax-posted-to-wrong-ledger-account-Picture2.png)

## <a name="check-the-ledger-posting-group-of-the-tax-code"></a>檢查稅籍代碼的分類帳過帳群組

1. 前往 **稅務** \> **間接稅** \> **銷售稅** \> **銷售稅代碼**。
2. 查找並選擇稅籍代碼，然後查看 **分類帳過帳群組** 欄位。 在這個範例中，是 **增值稅**。

    [![銷售稅代碼頁面中的分類帳過帳群組欄位。](./media/tax-posted-to-wrong-ledger-account-Picture3.png)](./media/tax-posted-to-wrong-ledger-account-Picture3.png)

3. **分類帳過帳群組** 欄位中的值是一個連結。 若要查看群組設定的詳細資料，則選擇該連結。 或者，在欄位中選擇並按住 (或以右鍵按一下)，然後選擇 **檢視詳細資料**。

    [![檢視詳細資料命令。](./media/tax-posted-to-wrong-ledger-account-Picture4.png)](./media/tax-posted-to-wrong-ledger-account-Picture4.png)

4. 在 **應納銷售稅** 欄位中，根據交易類型驗證科目編號是否正確。 如果不正確，請選擇要過帳到的正確科目。 在此範例中，應將銷售訂單的銷售稅過帳到應納銷售稅科目 222200。

    [![分類帳過帳群組頁面的應納銷售稅欄位。](./media/tax-posted-to-wrong-ledger-account-Picture5.png)](./media/tax-posted-to-wrong-ledger-account-Picture5.png)

    下表提供有關 **分類帳過帳群組** 頁面上每個欄位的資料。

    | 欄位                  | 描述 |
    |------------------------|-------------|
    | 應納銷售稅      | 應繳納給稅務機關的輸出銷售稅的主科目。 |
    | 應收銷售稅   | 從稅務機關收到進項稅的主科目。 |
    | 支出使用稅        | 此主科目用於過帳廠商不在歐盟 (EU) 反向計費商品勞務稅 (GST)/統一銷售稅(HST) 中向稅務機關要求或報告的可扣減銷項稅。 必須為在交易中使用的銷售稅群組之銷售稅代碼選擇 **銷項稅**。 如果在 **總帳參數** 頁面中選擇 **應用銷售稅納稅規則**，則此欄位不可用。 |
    | 應納使用稅        | 用於過帳應繳納給稅務機關的使用稅的主科目。 |
    | 結算帳戶     | 用於過帳在 **應納使用稅** 和 **應收銷售稅** 欄位中指定會計科目的淨餘額的主科目。 |
    | 廠商現金折扣   | 用於過帳與此分類帳過帳組關聯的銷售稅代碼之現金折扣的主科目。 |
    | 客戶現金折扣 | 用於過帳與此分類帳過帳組關聯的銷售稅代碼之現金折扣的主科目。 |

    如需更多資料，請參閱[設定銷售稅分類帳過帳群組](tasks/set-up-ledger-posting-groups-sales-tax.md)

## <a name="debug-in-code-to-check-ledger-dimensions"></a>偵錯代碼以檢查分類帳維度

在代碼中，過帳科目由分類帳維度決定。 分類帳維度將科目的記錄識別碼保存在資料庫中。

1. 對於銷售訂單，在 **Tax::saveAndPost()** 和 **Tax::post()** 方法處加入中斷點。 注意 **\_ledgerDimension** 的值。

    [![具有中斷點的銷售訂單代碼範例。](./media/tax-posted-to-wrong-ledger-account-Picture6.png)](./media/tax-posted-to-wrong-ledger-account-Picture6.png)

    對於採購訂單，在 **TaxPost::saveAndPost()** 和 **TaxPost::postToTaxTrans()** 方法處加入中斷點。 注意 **\_ledgerDimension** 的值。

    [![具有中斷點的採購訂單代碼範例。](./media/tax-posted-to-wrong-ledger-account-Picture7.png)](./media/tax-posted-to-wrong-ledger-account-Picture7.png)

2. 執行以下 SQL 查詢，根據分類帳維度保存的記錄識別碼在資料庫中查找科目的顯示值。

    ```sql
    select * from DIMENSIONATTRIBUTEVALUECOMBINATION where recid={the value of _ledgerDimension}
    ```

    [![記錄識別碼的顯示值。](./media/tax-posted-to-wrong-ledger-account-Picture8.png)](./media/tax-posted-to-wrong-ledger-account-Picture8.png)

3. 檢查呼叫堆疊，以查找指派給 **_ledgerDimension** 的值。 通常，該值來自於 **TmpTaxWorkTrans**。 在這種情況下，您應該在 **TmpTaxWorkTrans::insert()** 和 **TmpTaxWorkTrans::update()** 處加入中斷點來查找指派值的位置。

## <a name="determine-whether-customization-exists"></a>確認是否存在自訂

如果您已完成前幾部分中的步驟，但仍未發現問題，請確認是否存在自訂。 如果自訂不存在，請建立 Microsoft 服務要求以獲得更多支援。

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
