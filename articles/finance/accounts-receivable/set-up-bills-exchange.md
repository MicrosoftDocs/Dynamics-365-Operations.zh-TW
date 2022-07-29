---
title: 設定匯票
description: 本主題介紹設定匯票的步驟。
author: ShivamPandey-msft
ms.date: 09/17/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustBillOfExchangeJour
audience: Application User
ms.reviewer: roschlom
ms.custom: 269964
ms.assetid: f2077165-da90-4359-ab12-e05717728dc7
ms.search.region: global
ms.author: shpandey
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 8dcf63717c993fe63a931c9be2b7f3dad20ec119bee7f414c8590eb40b20057d
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450822"
---
# <a name="set-up-bills-of-exchange"></a>設定匯票

[!include [banner](../includes/banner.md)]

本主題介紹設定匯票的步驟。

匯票是來自客戶的書面或電子訂單，它指定另一方 (通常是銀行) 應向公司支付規定的金額。 當您使用匯票作為銷售訂單發票或普通發票的付款時，您將貸記客戶帳戶。 該貸記由匯票擔保，直到客戶向銀行支付匯票。 通常，您將在到期日使用匯票結算發票。 當您從銀行收到匯票已兌付的通知時，就可以關閉該匯票。 您可以在以下任一時間透過您的銀行簽發匯票：

-   在到期日。 這種方法稱為託收匯款。
-   到期日之前，通常在為客戶設定的付款條件中所指定的折扣日期。 當您過帳交易時，折扣金額會過帳到費用科目。 在銀行收到客戶付款之前，剩餘金額對您而言是負債。 這種方法稱為折扣匯款。

## <a name="set-up-posting-profiles-for-bills-of-exchange"></a>設定匯票的過帳設定檔

使用 **客戶過帳設定檔** 頁面設定過帳設定檔，以便用於匯票、拒付匯票、託收匯款和折扣匯款。 在 **匯總科目** 欄位中，選擇要過帳匯票金額的匯總科目。 根據匯票交易的類型，借記或貸記該帳戶：
-   對於匯票，在過帳匯票時借記該帳戶，在過帳折扣匯款或託收匯款時貸記該帳戶。
-   對於拒付匯票，在過帳拒付匯票時借記該帳戶。
-   對於託收匯款，在過帳託收匯款時貸記該帳戶。
-   對於折扣匯款，在過帳折扣匯款時借記該帳戶。

在 **結算科目** 欄位中，選擇要過帳匯票金額的現金科目。 在結算匯票時，借記該帳戶。 在 **銷售稅預付款** 欄位，選擇在使用匯票預付時過帳銷售稅金額的匯總科目。 在 **折扣負債科目** 欄位中，選擇帳戶，以將折扣匯款的折扣金額過帳到該帳戶。 在過帳折扣匯款時，貸記該帳戶。

## <a name="set-up-accounts-receivable-parameters-for-bills-of-exchange"></a>設定匯票的應收帳款參數

在 **應收帳款參數** 頁面中，在 **分類帳和銷售稅** 索引標籤內輸入匯票的預設過帳設定檔。在 **數字序列** 索引標籤定義數字序列。

## <a name="set-up-journal-names-for-bills-of-exchange"></a>設定匯票的日記帳名稱


在 **日記帳名稱** 頁面，建立至少五個用於匯票的日記帳名稱。 以下是日記帳類型：
-   **客戶簽發匯票**：為簽發匯票日記帳建立日記帳名稱。
-   **客戶拒付匯票**：為拒付匯票日記帳建立日記帳名稱。
-   **客戶重簽匯票**：為重簽匯票日記帳建立日記帳名稱。
-   **客戶銀行匯款**：為匯款日記帳建立日記帳名稱。
-   **客戶結算匯票**：為結算匯票日記帳建立日記帳名稱。

在每個匯票日記帳的日記帳憑單頁面中，在 **匯票** 索引標籤中輸入關於匯票的資料。在過帳匯票日記帳明細後，可以在 **匯票日記帳查詢** 頁面和 **匯票統計資料** 頁面中看到這些明細。

## <a name="set-up-methods-of-payment-for-bills-of-exchange"></a>設定匯票的付款方式

在 **付款方式** 頁面中，為匯票設定至少一種付款方式。 如果您與多家銀行有業務往來，請設定與每家銀行匯票所需的匯款格式相對應的付款方式。

## <a name="set-up-payment-fees-for-bills-of-exchange"></a>設定匯票的付款費用

付款費用是與收取客戶付款過程有關的費用。 每個付款費用可以與多個付款費用設定明細關聯。 可以使用設定明細來控制如何計算付款費用的預設金額。 例如，您可以針對付款方式、付款規範、貨幣和時間段建立設定明細。 也可以根據日期間隔的百分比或金額建立設定明細。 例如，可以設定根據逾期時間長度的利息百分比。 如果銀行按不同的匯款類型 (例如 **收帳** 或 **折扣**) 收取不同的費用，則為各匯款類型設定分別的付款費用明細。

## <a name="set-up-remittance-fees-for-bank-remittance-files"></a>設定銀行匯款檔案的匯款費用

在 **銀行帳戶** 頁面中，您可以設定銀行產生每個匯款檔案收取的匯款費用。 在已確認匯款並且已知實收費用額時，過帳匯款費用。 匯款費用與付款費用不同，後者從客戶處收取並且附加到日記帳明細。

## <a name="set-up-document-layouts-for-bills-of-exchange"></a>設定匯票的單據版面配置

在 **銀行帳戶** 頁面中，按一下 **設定**，然後指定各個銀行帳戶所需的單據版面配置，該版面配置用於產生列印的匯票單據。

## <a name="set-up-customers-for-bills-of-exchange"></a>設定客戶的付款費用

對於每一個同意使用匯票支付的客戶，在 **客戶** 頁面中的 **付款預設** 索引標籤，可以設定匯票的預設付款方式。







[!INCLUDE[footer-include](../../includes/footer-banner.md)]