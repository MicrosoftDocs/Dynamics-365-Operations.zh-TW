---
title: SEPA 貸方轉帳概觀
description: 本文提供有關 ISO 20022 貸方轉帳的一般資料，包括單一歐元支付區 (SEPA) 貸方轉帳和任何其他廠商電子支付。 SEPA 貸方轉帳是一種特定類型的歐元付款，用於從一家公司或個人付款給另一家公司或個人。 本主題還說明如何設定和傳輸貸方轉帳付款檔案。
author: sunfzam
ms.date: 06/20/2017
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTransVendInvoice, LedgerJournalTransVendPaym, VendPaymMode
audience: Application User
ms.reviewer: roschlom
ms.custom:
- "11124"
- intro-internal
ms.assetid: 36b0f870-16d4-4bbb-8da5-e747e69b970d
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fc37dde8829abdd26a224adbd788538834f4d320
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/15/2022
ms.locfileid: "8451422"
---
# <a name="sepa-credit-transfer-overview"></a>SEPA 貸方轉帳概觀

[!include [banner](../includes/banner.md)]

本文提供有關 ISO 20022 貸方轉帳的一般資料，包括單一歐元支付區 (SEPA) 貸方轉帳和任何其他廠商電子支付。 SEPA 貸方轉帳是一種特定類型的歐元付款，用於從一家公司或個人付款給另一家公司或個人。 本主題還說明如何設定和傳輸貸方轉帳付款檔案。

## <a name="what-is-a-credit-transfer-message"></a>什麼是貸方轉帳訊息？
貸方轉帳訊息是發起方 (您的公司) 為了將資金從自己的帳戶轉移到貸方而發出的請求。 貸方轉帳訊息有許多特定國家/地區和特定銀行的措施。 其中一些在單個國家/地區內使用，一些正成為標準。 一項完善的全球標準是 ISO 20022 及其初始訊息，例如：貸方轉帳。 下圖顯示選定貸方轉帳訊息的關係和範圍。 
![貸方轉帳。](./media/credit-transfer.jpg) 貸方轉帳訊息 

## <a name="what-are-iso-20022-and-sepa-payments"></a>ISO 20022 和 SEPA 付款是什麼？
單一歐元支付區 (SEPA) 由歐盟委員會設立，並指示所有電子付款均被視為國內付款，不論個人、企業或者組織和銀行所在的國家/地區。 國內付款和跨境付款之間沒有差異。 SEPA 包含歐盟 (EU) 的 28 個成員國，以及冰島、列支敦斯登、挪威、瑞士、摩納哥和聖馬利諾。 SEPA 有助於在歐洲經濟區 (EEA) 內組成單一的支付交易市場。 最終，SEPA 會減少銀行、企業和個人必須使用的支付形式數量。 歐盟委員會透過支付服務指令 (PSD) 建立 SEPA 付款的法律基礎。 歐元支付委員會 (EPC) 經由以下活動支援 SEPA：

-   它使用 ISO 20022 金融業通用訊息方案 (ISO 20022 Universal financial industry message scheme) XML 格式設定 SEPA 電子支付標準。
-   它建立有關處理歐元付款的規則和指南。

EPC 由歐洲銀行組成，開發 SEPA 付款方式的商業和技術框架。 使用三種類型的 SEPA 付款：

-   貸方轉帳
-   直接借記
-   卡

## <a name="what-is-a-sepa-credit-transfer"></a>SEPA 貸方轉帳是什麼？
SEPA 貸方轉帳是一種付款方式，用於從一家公司或個人付款給另一家公司或個人。 付款必須以歐元支付，並且必須包括雙方的國際銀行帳號 (IBAN) 和銀行識別代碼 (BIC)。 (BIC 也稱為全球銀行金融電信協會 \[SWIFT\] 代碼。) 此外，交易成本必須由雙方分攤。 雙方之間的貸方轉帳應使用符合 ISO 20022 支付處理標準的 XML 格式和由 EPC 指定的 XML 格式。

## <a name="how-is-a-credit-transfer-implemented"></a>如何實施貸方轉帳？
歐洲國家/地區的貸方轉帳付款格式是使用 Microsoft Dynamics 365 Finance 中的電子報表 (ER) 和付款方式功能來實施的。 一些其他地區使用的貸方轉帳格式仍採用傳統的付款框架。 在多種其他格式中，有十二種 ISO 20022 貸方轉帳檔案格式可供使用。 這些匯出格式符合 SEPA ISO 20022 XML 標準。 它們的用途是，按照 EPC 發佈的 SEPA Credit Transfer Scheme Rulebook 8.2 版中的規定，為使用它們的國家/地區和歐元付款產生非歐元付款轉帳。 在您可以實施貸方轉帳前，必須與您的銀行連絡，以取得上傳電子銀行檔案所需的軟體。 您將使用該軟體將包含付款訂單的 XML 檔案傳輸到您的銀行。

## <a name="what-credit-transfer-formats-are-currently-supported"></a>目前支援哪些貸方轉帳格式？
應隨時造訪 Microsoft Dynamics Lifecycle services (LCS) 中的共享資產庫，並查看資產類型為 **GER 配置** 的可用檔案最新清單。 下一部分「我必須執行哪些設定？」提供一個主題連結，該主題說明如何建立 LCS 儲存庫以查看可用設定和匯入所選配置。

## <a name="what-do-i-have-to-set-up"></a>我必須執行哪些設定？
-   在可以建立貸方轉帳檔案前，必須匯入至少一個有效的貸方轉帳配置到您的 ER 配置。 有關說明，請參閱[從 Lifecycle Services 下載電子報表編製配置](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md)。
-   在設定應付帳款付款方式時，選擇 **一般電子報表** 核取方塊，並選擇相應的貸方轉帳格式 (例如：**ISO 20022 貸方轉帳 (AT)**) 作為匯出格式配置。
-   還必須設定法律實體和銀行帳戶資料。
-   需要銀行帳號、IBAN，有時還需要 SWIFT 代碼 (BIC) 或其他 ID，才能建立有效的貸方轉帳付款。 因此，必須為廠商銀行帳戶和請求轉帳組織的銀行帳戶設定這些資料。
-   可能需要更多資料，例如：貸方轉帳訊息中提及的各方增值稅 (VAT) 號。 如果請求此資料，則必須為廠商和法律實體進行設定。
-   某些應付帳款付款方式 (大多數為根據 ISO 20022 的付款方式) 可能需要為 **付款格式代碼集** 執行更多設定，例如：**服務類型** =  = **SLEV**。 這些代碼在處理付款期間作為付款交易的額外標記。 可在兩處設定付款代碼的預設值，例如：**類別目的**、**費用責任人**、**本地工具** 和 **服務等級**。 第一處為 **應付帳款付款日記帳標題**，第二處為 **應付帳款付款方式**。 建立付款日記帳明細之後，將把在付款日記帳標題中設定的付款代碼值轉移到日記帳明細，如果未設定該值，則使用付款方式中的值。

## <a name="what-parameters-are-available-for-generating-credit-transfer-payments"></a>哪些參數可用於產生貸方轉帳付款？
具體參數清單視貸方轉帳格式而異。 下表顯示在廠商付款日記帳中為德國產生 ISO 20022 貸方轉帳付款檔案時可用的參數。 透過使用 **在背景執行** 索引標籤中的選項，您能以批次處理模式執行付款產生。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>欄位</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>批次預訂</td>
<td>選取此核取方塊以在 XML 檔案中加入批次預訂標籤。</td>
</tr>
<tr class="even">
<td>處理日期</td>
<td>輸入銀行應處理付款的日期。</td>
</tr>
<tr class="odd">
<td>格式</td>
<td>根據您所在國家/地區或銀行的要求，選擇匯款資料的格式：
<ul>
<li><strong>Strd</strong> – 選擇此選項，可在針對一張發票結算一個付款明細時使用結構化的格式。 此選項不適用於法國、德國或荷蘭的特定國家/地區的匯出格式。</li>
<li><strong>Ustrd</strong> – 選擇此選項，可在針對多張發票結算一個付款時使用非結構化的格式。 已結算發票的發票編號連接到一起，並且用作匯款資料。 根據 ISO 20022 指南，非結構化匯款資料不得超過 140 個字元。</li>
</ul></td>
</tr>
<tr class="even">
<td>發票數</td>
<td>輸入從<strong>付款通知</strong>報表中列印的發票數量。</td>
</tr>
<tr class="odd">
<td>序號</td>
<td>輸入序號以識別檔案。 序號顯示在<strong>出席單</strong>報告上。</td>
</tr>
<tr class="even">
<td>列印出席單</td>
<td>選取此核取方塊，可列印<strong>出席單</strong>報告。</td>
</tr>
<tr class="odd">
<td>列印控制報告</td>
<td>選取此核取方塊，可列印含有付款資料的報告。</td>
</tr>
<tr class="even">
<td>列印隨函</td>
<td>選取此核取方塊，可列印<strong>付款通知</strong>報告。</td>
</tr>
</tbody>
</table>

## <a name="what-are-ibans-and-bics"></a>IBAN 和 BIC 是什麼？
國際銀行帳號 (IBAN) 和銀行識別代碼 (BIC) 用於識別全球眾多國家/地區的任何帳戶。 其中包括 34 個 SEPA 國家/地區。 在 **SWIFT 代碼** 欄位中輸入 BIC，在 **IBAN** 欄位中輸入 IBAN。 對於貸方的銀行帳戶和客戶的銀行帳戶，這些欄位位於 **銀行帳戶** 頁面中 **銀行帳戶** 索引標籤的 **額外識別** FastTab。 SEPA 付款不再強制使用 BIC。

## <a name="how-do-i-transmit-a-payment-file-to-the-bank"></a>如何將付款檔案傳輸到銀行？
在您產生付款時，將產生付款檔案，並且系統會請求您從 Web 瀏覽器中將其保存到任何可用的位置。 下一步是將 XML 檔案發送到您的銀行。 此流程根據銀行的不同而變。 按照您銀行的說明將檔案提交給銀行進行處理。





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
