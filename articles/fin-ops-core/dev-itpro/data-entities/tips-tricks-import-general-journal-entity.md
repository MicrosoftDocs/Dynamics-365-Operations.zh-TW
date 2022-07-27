---
title: 使用一般日記帳實體匯入憑證
description: 本主題提供使用一般日記帳實體將資料匯入一般日記帳的提示。
author: rcarlson
ms.date: 04/20/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.custom: 94363
ms.assetid: 0b8149b5-32c5-4518-9ebd-09c9fd7f4cfc
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 42bc804393d050e5ff722c46c9ce50ece54c5a0b
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8460302"
---
# <a name="importing-vouchers-by-using-the-general-journal-entity"></a>使用一般日記帳實體匯入憑證

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

本主題提供使用一般日記帳實體將資料匯入一般日記帳的提示。

您可以使用一般日記帳實體匯入具有 **分類帳**、**客戶**、**廠商** 或 **銀行** 的帳戶或沖銷帳戶類型的憑證。 憑證可以作為一行輸入，同時使用 **帳戶** 欄位和 **沖銷帳戶** 欄位，或作為多行憑證，其中只有使用 **帳戶** 欄位 (並且每行的 **沖銷帳戶** 留空)。 一般日記帳實體不支援所有帳戶類型。 相反，對於需要不同帳戶類型組合的場景，存在其他實體。 例如，若要匯入專案交易，請使用專案費用日記帳實體。 每個實體都旨在支援特定場景。 這代表這些場景的實體中可能有其他欄位可用。 但是，對於不同的場景，實體中的附加欄位可能不可用。

## <a name="setup"></a>設定
在使用一般日記帳實體匯入之前，請驗證以下設定：

- **日記帳批號的數序設定** – 在預設情況下，當您使用總帳實體匯入時，日記帳批號使用在總帳參數中定義的數列。 如果您將日記帳批號的數列設定為 **手動**，不適用預設數字。 不支援此設定。
- **財務維度設定** – 在使用實體匯入交易時，每個組織都必須定義財務維度的順序。 該訂單主要為 **分類帳維度整合** 格式定義，位於 **總帳**&gt;**會計科目表**&gt;**維度**&gt;**用於整合應用程式的財務維度設定**&gt;**選取資料實體**。 匯入的分類帳科目的區段必須具有相同的順序。 否則匯入時會出錯。

## <a name="general-journal-entity-setup"></a>一般日記帳實體設定
資料管理中的兩個設定會影響預設日記帳批號或憑證號碼的應用方式：

- **以集為基礎的處理** (針對資料實體)
- **自動產生** (針對欄位對應)

以下部分描述了這些設定的效果。 他們還解釋了系統如何為日記帳和憑證號碼產生批號。

### <a name="journal-batch-number"></a>日記帳批次編號

- 一般日記帳實體上的 **以集為基礎的處理** 設定不會影響產生日記帳批號的方式。
- 如果將 **日記帳批號** 欄位設定為 **自動產生**，為匯入的每一行建立一個新的日記帳批號。 我們不建議這種行為。 **自動產生** 的設定位於匯入專案，**查看地圖** 下的 **對應詳情** 索引標籤上。
- 如果 **日記帳批號** 欄位未設定為 **自動產生**，則按如下方式建立日記帳批號：

    - 如果在匯入檔案中定義的日記帳批號與現有的未過帳每日日記帳相符，則具有相符日記帳批號的所有行都將匯入到現有日記帳中。 明細永遠不會匯入已過帳的日記帳批號。 相反，會建立一個新號碼。
    - 如果匯入檔案中定義的日記帳批號與現有的未過帳每日日記帳不相符，則具有相同日記帳批號的所有行將分組在新日記帳下。 例如，日記帳批號為 1 的所有行都匯入新日記帳，日記帳批號為 2 的所有行都匯入第二個新日記帳。 日記帳批號是使用在總帳參數中定義的數列建立的。

### <a name="voucher-number"></a>憑證號碼

- 當您使用一般日記帳實體上的 **以集為基礎的處理** 設定，必須在匯入的檔案中提供憑證號碼。 一般日記帳中的每筆交易都指派了匯入檔案中提供的憑證號碼，即使憑單未結算。 如果您想使用以集為基礎的處理，但您還想使用為憑證號碼定義的數列，請注意以下幾點。

    - 若要啟用此函數，請在用於匯入的日記帳名稱上，將 **過帳時的編號指派** 設定為 **是**。
    - 憑證號碼仍必須在匯入的檔案中定義。 但是，此編號是臨時編號，在過帳日記帳時將被憑證號碼覆寫。 確保日記帳的明細按臨時憑證號碼正確分組。 例如，在過帳期間，發現三個明細的臨時憑證號碼為 1。 所有三個明細的臨時憑證號碼都被數列中的下一個編號覆寫。 如果這三個明細不是已結算分錄，則不會過帳憑證。 接下來，如果找到具有臨時憑證號碼 2 的明細，則此編號將被序列中的下一個憑證號碼覆寫，依此類推。

- 當您不使用 **以集為基礎的處理** 設定，您不需要在匯入的檔案中提供憑證號碼。 憑證號碼是在匯入期間根據日記帳名稱的設定建立的 (**僅限一筆憑單**、**與餘額相關** 等)。 例如，如果將日記帳名稱定義為 **與餘額相關**，第一行接收一個新的預設憑證號碼。 然後系統評估該明細以確定借方是否等於貸方。 如果該行上存在沖銷帳戶，則匯入的下一行會收到一個新的憑證號碼。 如果不存在沖銷帳戶，系統會在匯入每個新明細時評估借方是否等於貸方。
- 如果將 **憑證號碼** 欄位設定為 **自動產生**，匯入則不會成功。 不支援 **憑證號碼** 欄位的 **自動產生** 設定為。

在預設情況下，一般日記帳實體使用以集為基礎的處理。 評估組織的業務需求後，您可以透過點選 **資料管理** 工作區中的 **資料實體** 來更改 **以集為基礎的處理** 設定。 以集為基礎的處理用於加快匯入過程。 如果您不使用以集為基礎的處理，則匯入常規日記帳實體的速度會較慢。


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]