---
title: 信用卡設定、授權和獲取
description: 本文提供 Microsoft Dynamics 365 Finance 中信用卡授權的概觀。 其中包括有關如何設定支付服務、將信用卡新增到銷售訂單以及取消授權的資訊。
author: ShivamPandey-msft
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CreditCardProcessors, CustTable, SalesTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 3041
ms.assetid: 678f6899-bfa5-439b-aaca-b4affcc338ba
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 932949f31cbc4e4e8c07a2e489b8a0848843c54ad8d27d5d77f2b7031c68c30a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450741"
---
# <a name="credit-card-setup-authorization-and-capture"></a>信用卡設定、授權和獲取

[!include [banner](../includes/banner.md)]

本文提供 Microsoft Dynamics 365 Finance 中信用卡授權的概觀。 其中包括有關如何設定支付服務、將信用卡新增到銷售訂單以及取消授權的資訊。

## <a name="setting-up-the-credit-card-payment-service"></a>設定信用卡支付服務

要使用信用卡，您必須在支付服務頁面上設定並啟用支付服務。 支付服務充當您的法律實體與處理客戶信用卡費用的銀行之間的橋樑。 您必須與支付連接器欄位中列出的信用卡提供商合作，並在該提供商處設定帳戶。 然後，您必須在支付服務頁面上設定其他選項，在信用卡類型頁面上為 American Express、Discover、MasterCard 和 Discover 設定信用卡類型，並將提供商啟用為預設提供商。 您還必須按照以下步驟完成設定：
-   在應收帳款參數頁面上，指定用於信用卡授權的參數。
-   在 [支付期限] 頁面，設定信用卡的支付期限。 在 [支付類型] 欄位中，選擇 [信用卡]。
-   在客戶信用卡頁面上，輸入客戶的信用卡資訊。

## <a name="adding-a-new-credit-card"></a>新增信用卡
您可以使用客戶、設定、信用卡在客戶頁面上建立新的信用卡記錄。 在銷售訂單頁面上輸入銷售訂單時，還可以透過使用管理、客戶、信用卡、登記建立信用卡記錄。

## <a name="adding-a-credit-card-to-a-sales-order"></a>將信用卡新增到銷售訂單

您可以透過在銷售訂單頁面的 [價格和折扣] FastTab 上的信用卡查詢中選擇信用卡，來將信用卡新增到銷售訂單。 要啟動授權過程，請在動作窗格的管理索引標籤上，選擇信用卡和授權。

## <a name="authorizing-a-credit-card"></a>授權信用卡

在對某信用卡進行授權時，會驗證卡號和持卡人姓名，並確認可用信用餘額。 也可能會驗證信用卡檢查碼和持卡人地址。 然後從客戶的可用信用卡餘額減去發票金額。 支付服務將發送信用卡已核准或拒絕的資訊。 為銷售訂單開立發票時，會從信用卡中收取 (獲取) 發票金額。

### <a name="card-verification-value"></a>信用卡檢查碼

您可以要求提供信用卡檢查碼，有時也稱為信用卡的安全碼。 對於美國運通來說，這是一個四位數的值。 對於 Discover、MasterCard 和 Visa，這是一個三位數的值。

### <a name="address-verification"></a>地址驗證

地址驗證資訊一律發送給支付提供商。 您可以決定接受交易需要的資訊量。 請務必與您的提供商確定其是否接受此資訊。 以下是地址驗證的選項：
-   **一律接受交易** – 無論地址驗證結果如何，都接受交易。
-   **帳戶持有人** – 將交易中的持卡人姓名與信用卡公司的資訊進行比較。
-   **帳單地址** – 將交易中的持卡人姓名和帳單地址與信用卡公司的資訊進行比較。
-   **帳單郵遞區號** – 將交易中的持卡人姓名、帳單地址和郵遞區號與信用卡公司的資訊進行比較。

## <a name="data-support"></a>資料支援
對於支援的每種信用卡類型，您可以指定資料支援的等級。 該等級控制有多少有關交易的資訊傳輸到支付服務。 請務必與您的提供商確定其是否可提供此資訊。 以下是資料支援等級的選項：
-   **等級 1** - 傳輸交易日期、交易金額和描述。
-   **等級 2** - 傳輸等級 1 資訊，加上運送和商家地址以及稅務資訊。
-   **等級 3** - 傳輸等級 2 資訊和訂單明細資訊。

## <a name="partial-payments"></a>部分支付
如果運送一部分的訂單，則會獲取部分訂單的金額，並關閉針對整個訂單金額的授權。 然後為尚未發貨之訂單的剩餘金額提交新的授權。

## <a name="voiding-an-authorization"></a>取消授權
要取消信用卡授權，您可以將付款方式變更為沒有 [信用卡類型] 的其他方式。







[!INCLUDE[footer-include](../../includes/footer-banner.md)]