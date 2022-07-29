---
title: 設定集中付款
description: 按照以下步驟，準備代表您組織中的其他法律實體在一個法律實體中處理付款。
author: kweekley
ms.date: 05/09/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerInterCompany
audience: Application User
ms.reviewer: roschlom
ms.custom: 62243
ms.assetid: ffd17b5f-9aea-40e0-be49-d8702f615256
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 524d4e59e9fad38bd9104ee7e7a3e9d5311b735340bcd03376fc0ebc48eb7174
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450324"
---
# <a name="set-up-centralized-payments"></a>設定集中付款

[!include [banner](../includes/banner.md)]

按照以下步驟，準備代表您組織中的其他法律實體在一個法律實體中處理付款。 在開始之前，必須完成以下設定：

-   建立法律實體。
-   建立總帳參數和會計科目表。
-   設定應付帳款參數和應收帳款參數 (視使用集中付款的模組而定)。
-   設定公司間會計。

## <a name="set-up-an-organizational-hierarchy-for-centralized-payments"></a>設定集中付款的組織層次結構
您必須設定集中付款的組織層次結構。 將相同的組織層次結構用於處理集中的廠商付款和集中的客戶付款。 **附註：** 對於集中付款，該層次結構的結構不會產生影響。 層次結構中的任何法律實體都能代表層次結構中的任何其他法律實體處理付款。 在 **組織層次結構** 頁面中，您可以建立一個新的組織層次結構。 在 **目的** 欄位中，您必須選擇 **集中付款**。 

## <a name="set-up-an-intercompany-account-for-centralized-payments"></a>設定集中付款的公司間會計
當根據其他法律實體中的發票，結算目前法律實體中的付款交易時，將為每個法律實體建立相應的應付和應收交易。 您必須指定過帳任何適用現金折扣和已實現收益與損失金額的法律實體。 在開始前，確定您將使用哪個法律實體處理廠商和客戶付款。 如果一個法律實體處理廠商付款，另一個法律實體處理客戶付款，您必須切換到各個法律實體。 在 **公司間會計** 頁面，可以為將代表其處理付款的法律實體選擇公司間關係記錄。 

在 **集中付款** 索引標籤中，可以選擇將現金折扣過帳到付款法律實體 (或減少廠商帳戶餘額的其他交易) 或是發票的法律實體 (或增加廠商帳戶餘額的其他交易)。 此選擇與 **應付帳款參數** 和 **應收帳款參數** 頁面的 **現金折扣管理** 欄位一起使用。 對於超額付款和分值差額容差，使用付款法律實體中的設定。 對於付款不足和分值差額容差，使用發票法律實體中的設定。

## <a name="map-vendor-accounts-across-legal-entities"></a>對應法律實體的廠商帳戶
如果您從某個法律實體付款給廠商，並且希望選擇其他法律實體的廠商發票時，則必須確保每個法律實體中相應的廠商帳戶都使用相同的通訊錄識別碼。 如果您接收的付款來自在多個法律實體中支付發票的客戶，則必須確保每個法律實體中相應的客戶帳戶都使用相同的通訊錄識別碼。

## <a name="set-up-posting-profiles-for-centralized-payments"></a>設定集中付款的過帳設定檔
當您在一個法律實體中建立發票，而在其他法律實體中結算發票，過帳設定檔識別碼在這兩個法律實體中必須相同。 為了協助確保正確建立付款，請在發票的每個法律實體中，設定與付款法律實體中使用的過帳設定檔相對應的過帳設定檔。 切換到發票的第一個法律實體，然後在 **廠商過帳設定檔** 頁面中，可以建立新的過帳設定檔或編輯現有的過帳設定檔。 為發票法律實體所選的過帳設定檔無須與付款法律實體中的過帳設定檔設定相符。

## <a name="set-up-methods-of-payment-for-centralized-payments"></a>設定集中付款的付款方式
當您在一個法律實體中建立發票，而在其他法律實體中結算發票，付款方式識別碼在這兩個法律實體中必須相同。 為了協助確保正確建立付款，請在發票的每個法律實體中，設定與付款法律實體中使用的付款方式相對應的付款方式。 切換到發票的第一個法律實體，然後在 **廠商付款方式** 頁面中，可以建立新的付款方式或編輯現有的付款方式。 為發票法律實體所選的付款方式無須與付款法律實體中的付款方式設定相符。

## <a name="set-up-default-descriptions"></a>設定預設說明
您可以定義公司間結算憑單的預設說明。 預設說明包含在公司間結算流程期間的應付和應收交易中。 在 **預設說明** 頁面中可以為 **公司間客戶結算** 和 **公司間廠商結算** 建立新的說明，方式為選擇一種語言，然後輸入文字。





[!INCLUDE[footer-include](../../includes/footer-banner.md)]