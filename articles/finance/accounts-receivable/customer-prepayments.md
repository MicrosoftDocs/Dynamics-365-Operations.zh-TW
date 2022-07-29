---
title: 客戶預付款
description: 本主題說明如何設定和處理客戶預付款 (也稱為客戶保證金)。
author: roschlom
ms.date: 04/30/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustPosting, LedgerJournalTransCustPaym, CustParameters
audience: Application User
ms.reviewer: ''
ms.search.scope: Core, Operations
ms.custom: 24651
ms.assetid: cb82245e-8c02-429c-b36e-8db0e3e6f7e5
ms.search.region: Global
ms.author: raprofit
ms.search.validFrom: ''
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e83c8be1b397f90445230835e415ea4fcea5a8d0bf695e6cc5eadc55275ded7f
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450729"
---
# <a name="customer-prepayments"></a>客戶預付款

[!include [banner](../includes/banner.md)]

當您收到客戶的付款時，將使用客戶預付款，但沒有可用於結算付款的發票。 這些類型的付款也稱為客戶保證金。

設定和使用客戶預付款的流程包括以下基本步驟。

1. 為預付款建立客戶過帳設定檔。
2. 設定 **包含預付款日記帳憑單的過帳設定檔** 參數。
3. 建立客戶付款日記帳，然後選擇每行上的 **預付款日記帳憑單** 核取方塊。
4. 過帳客戶付款日記帳。
5. 產生發票後，使用 **結算未結交易** 頁面透過發票結算預付款。

## <a name="create-a-customer-posting-profile-for-prepayments"></a>為預付款建立客戶過帳設定檔

通常，當您在交付貨物或服務之前或在系統中存在發票之前接受客戶的預付款或保證金時，您會希望在會計科目表中將現金記錄為負債而不是資產。 但是，在總帳中記錄這些金額的要求可能會有所不同，具體取決於您所在的國家或地區。 因此，請務必向您的會計師諮詢適用的當地法規。

通常，建立可用於預付款的過帳設定檔的流程與建立其他過帳設定檔的流程相同。 主要區別在於您在 **匯總科目** 欄位中選擇的主科目。 如需相關資訊，請參閱[客戶過帳設定檔](customer-posting-profiles.md)。

## <a name="define-parameters-for-customer-prepayments"></a>定義客戶預付款的參數

在為客戶預付款設定系統時，您必須考慮兩個主科目應收帳款參數。 請按照以下步驟設定這些參數。

1. 前往 **應收帳款 \> 設定 \> 應收帳款參數**。
2. 選用：在 **分類帳和銷售稅** 索引標籤的 **付款** FastTab 上，將 **預付款日記帳憑單的銷售稅** 選項設定為 **是**。
3. 在 **包含預付款日記帳憑單的過帳設定檔** 欄位中，選擇過帳客戶預付款時要使用的客戶過帳設定檔。
4. 關閉頁面。

## <a name="create-customer-prepayment-vouchers"></a>建立客戶預付款憑單

建立客戶付款日記帳時，對於每筆預付款，必須在 **客戶付款日記帳** 頁面上將 **預付款日記帳憑單** 選項設定為 **是**。 請按照下列步驟建立客戶預付款。

1. 前往 **應收帳款 \> 付款 \> 客戶付款日記帳**。
2. 選取 **新增** 以建立日記帳。
3. 在 **名稱** 欄位中，選擇要使用的日記帳名稱。

    > [!IMPORTANT]
    > 如果在上一個流程中，將 **預付款日記帳憑單的銷售稅** 選項設定為 **是**，則必須選擇已選取 **金額包括營業稅** 參數日記帳名稱。 

4. 在 **描述** 欄位中，輸入詳細描述。
5. 選取 **行**。
6. 如果不存在空白行，請選擇 **新增** 建立行。
7. 請在 **日期** 欄位，輸入應過帳預付款的日期。
8. 在 **帳戶** 欄位，選擇預付款的客戶。
9. 在 **描述** 欄位中，輸入交易的詳細描述。
10. 在 **信用** 欄位中，輸入預付款的金額。
11. 在 **沖銷帳戶** 欄位中，選擇要抵消付款的帳戶。 例如，選擇要向其過帳付款的銀行或主科目。
12. 在 **付款方式** 欄位中，選擇客戶的付款方式。
13. 在 **付款** 索引標籤，將 **預付款日記帳憑單** 選項設定為 **是**。
14. 對必須過帳的所有其他預付款重複步驟 7 到 13。
15. 選擇 **過帳** 完成日記帳。

## <a name="settle-prepayments-with-invoices"></a>用發票結算預付款

您可以使用 **客戶付款** 工作區輕鬆尋找和結算尚未完全結算的付款。

1. 在 **首頁** 儀表板，選擇 **客戶付款** 圖格。
2. 在 **客戶交易** 區段的 **未結算款項** 索引標籤上，搜尋並選擇要結算的付款。
3. 選取 **結算交易**。
4. 選擇發票和將要結算的付款的 **標記** 核取方塊。
5. 選取 **過帳**。

有關如何結算未結交易的更多資訊，請參閱[結算概觀](/cash-bank-management/settlement-overview.md)。
