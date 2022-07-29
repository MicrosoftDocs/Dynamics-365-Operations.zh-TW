---
title: SEPA 直接借記概觀
description: 單一歐元支付區 (SEPA) 由歐盟委員會設立，並指示所有電子付款均被視為國內付款，不論個人、企業或者組織和銀行所在的國家/地區。 國內付款和跨境付款之間沒有差異。 SEPA 包含 28 個歐盟 (EU) 成員國，以及冰島、列支敦斯登、挪威、瑞士、摩納哥和聖馬利諾。 SEPA 有助於在歐洲經濟區 (EEA) 內組成單一的支付交易市場。 最終，SEPA 會減少銀行、企業和個人必須使用的支付形式數量。
author: ShivamPandey-msft
ms.date: 08/22/2017
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: BankAccountTable, CustBankAccounts, CustParameters, CustTable
audience: Application User
ms.reviewer: roschlom
ms.custom:
- "11144"
- intro-internal
ms.assetid: 3277c9b6-e46e-40c9-aa76-9b0449467842
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5f71eca0ca9ee07d43bdf737874f442f0029e87e
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/15/2022
ms.locfileid: "8451428"
---
# <a name="sepa-direct-debit-overview"></a>SEPA 直接借記概觀

[!include [banner](../includes/banner.md)]

單一歐元支付區 (SEPA) 由歐盟委員會設立，並指示所有電子付款均被視為國內付款，不論個人、企業或者組織和銀行所在的國家/地區。 國內付款和跨境付款之間沒有差異。 SEPA 包含 28 個歐盟 (EU) 成員國，以及冰島、列支敦斯登、挪威、瑞士、摩納哥和聖馬利諾。 SEPA 有助於在歐洲經濟區 (EEA) 內組成單一的支付交易市場。 最終，SEPA 會減少銀行、企業和個人必須使用的支付形式數量。   

## <a name="what-is-the-goal-of-sepa-direct-debits"></a>SEPA 直接借記的目標是什麼？

在客戶已授予債權人已簽署授權的前提下，SEPA 直接借記允許債權人從客戶的銀行帳戶中收取資金。 客戶簽署授權允許債權人收取付款並指示客戶的銀行支付該款項。 

SEPA 直接借記首次建立一種可以用於 32 個 SEPA 國家/地區的國內和跨境歐元直接借記的付款工具。 

有兩種方案可供使用：SEPA 核心直接借記方案和 SEPA 企業對企業 (B2B) 直接借記方案。 兩種方案都使用相同的文件格式。

## <a name="what-is-the-core-direct-debit-scheme"></a>核心直接借記方案是什麼？
SEPA 核心直接借記方案是基本方案。 它具有以下屬性：
-   資金以歐元轉帳 (即使銀行帳戶可能持有其他貨幣的資金)。
-   客戶和債權人必須各自在 SEPA 內的信貸機構開設帳戶。
-   客戶必須向債權人授予已簽署的授權。
-   授權在最後啟動收款的 36 個月之後到期。
-   只要授權有效，債權人必須在最後收款之後的至少 14 個月內保存授權。
-   該方案可以用於單次 (一次性) 收款或定期直接借記收款。
-   客戶在其帳戶借記後長達八週內具有接收退款“不受質詢”的權利。

## <a name="what-is-the-sepa-business-to-business-b2b-direct-debit-scheme"></a>SEPA 企業到企業(B2B) 直接借記方案是什麼？
SEPA B2B 直接借記方案適用於企業到企業的交易，並以 SEPA 核心直接借記方案為基礎。 主要差異在於：
-   當客戶為私人個體 (消費者) 時，不得使用 SEPA B2B 直接借記方案。
-   客戶沒有資格獲取已授權交易的退款。
-   客戶銀行必須根據授權資料驗證收款，以確保該收款經過授權。 客戶銀行和客戶必須同意每次直接借記進行的驗證。
-   該方案提供更短的呈報直接借記時間表，並縮短退還週期。

## <a name="can-i-use-the-cor1-scheme-for-direct-debit-mandates"></a>我能將 COR1 方案用於直接借記授權嗎？
是。 您可以在奧地利、比利時、德國、法國、義大利、西班牙和荷蘭對 SEPA 直接借記授權單使用 COR1 方案。 對於債權人的直接借記收款，該方案提供更短的提前通知期。

## <a name="what-are-international-bank-account-numbers-iban-and-bank-identifier-codes-bic"></a>國際銀行帳號 (IBAN) 和銀行識別代碼 (BIC) 是什麼?
國際銀行帳號 (IBAN) 和銀行識別代碼 (BIC) 用於識別 32 個 SEPA 國家/地區的任何帳戶。 在 SWIFT 代碼欄位中輸入 BIC，在 IBAN 欄位中輸入 IBAN。 這兩個欄位均位於 [銀行帳戶] 頁面內 [銀行帳戶] 索引標籤上的 [額外識別] FastTab 中。 對於債權人的銀行帳戶和客戶的銀行帳戶都是如此。

## <a name="where-do-i-enter-creditor-identifiers-direct-debit-ids"></a>我在何處輸入債權人識別碼 (直接借記識別碼)？
在 SEPA 中，均使用唯一的債權人識別碼識別每個債權人。 此識別碼允許客戶和客戶銀行篩選每個直接借記，然後根據客戶說明處理或拒絕該直接借記。 債權人必須透過他們的銀行申請此識別碼。 在 [直接借記識別碼] 欄位中輸入法律實體銀行帳戶的直接借記識別碼。

## <a name="what-are-mandates"></a>授權是什麼？
客戶簽署授權允許債權人收取付款並指示客戶的銀行支付該款項。 客戶能以紙本或電子形式簽發授權。 預設情況下，該授權在最後啟動直接借記的 36 個月之後到期。

## <a name="where-do-i-specify-the-sepa-direct-debit-file-format-iso-20022"></a>我在何處指定 SEPA 直接借記文件格式 (ISO 20022)?
SEPA 資料格式基於 ISO 20022 訊息標準。 當您設定應收帳款的付款方式時，您將勾選 [一般電子報表] 核取方塊並選擇 SEPA 直接借記格式作為匯出格式配置。 當您在客戶付款日記帳中產生付款檔案時，您使用該付款方式。

## <a name="in-what-file-formats-can-i-generate-sepa-direct-debit-payment-files"></a>我可以產生哪些格式的 SEPA 直接借記付款檔案？
可以按照以下格式為 SEPA 直接借記產生電子付款檔案：
-   對於比利時、德國、西班牙、法國、義大利和荷蘭，按照 PAIN.008.001.02 XML 檔案格式產生 SEPA 直接借記付款檔案。
-   對於奧地利，按照 PAIN.008.001.02 XML 檔案格式產生 SEPA 直接借記付款檔案；對於德國，按照 PAIN.008.003.02 XML 檔案格式產生 SEPA 直接借記付款檔案。

## <a name="how-do-refunds-and-returns-work-with-sepa-direct-debits"></a>如何使用 SEPA 直接借記退款和退還？
在兩種 SEPA 直接借記方案中，客戶具有某些退款權限。 在到期日後的八週內，允許客戶撤消任何已授權的交易，而不必說明原因。 在未授權交易的情況下，該時間延長至到期日的 13 個月之後。 透過使用 [客戶交易] 頁面中的 [取消付款] 按鈕，手動完成撤消任何已執行的付款。







[!INCLUDE[footer-include](../../includes/footer-banner.md)]