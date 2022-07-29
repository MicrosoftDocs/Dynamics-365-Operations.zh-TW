---
title: 匯入廠商發票時產生發票行
description: 本主題介紹在匯入發票時自動在廠商發票上產生發票行的功能。
author: sunfzam
ms.date: 09/10/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.custom: intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2021-08-30
ms.dyn365.ops.version: 10.0.23
ms.openlocfilehash: e452bda02c814b78c4bb48140b07f0113ab4a571
ms.sourcegitcommit: 9cbff8a2cdeaf606488fb0044b3de4ab4409c9dc
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/26/2022
ms.locfileid: "8451647"
---
# <a name="generate-invoice-lines-when-you-import-vendor-invoices"></a>匯入廠商發票時產生發票行

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

本主題介紹在匯入發票時自動在廠商發票上產生發票行的功能。

有時，廠商發票包含有限的資訊，例如收件人資訊和小計。 但是，它們不包含行項目的資訊。 匯入發票時，系統將根據相應訂購單上的資訊自動產生發票行。

若要啟用自動建立發票行，請執行以下步驟。

1.  前往 **應付帳款\>設定\>應付帳款參數**。
2.  在 **廠商發票自動化** 索引標籤上，在 **為匯入的發票自動建立行** 下，將 **自動建立發票行** 選項設定 **是**。 
4.  在 **選擇將自動發票行建立的預設發票行數量** 欄位，選擇應用於自動產生發票行的數量：

    - **訂購數量** – 行將從訂購單行產生。 此值為預設值。
    - **產品收貨數量** – 訂購單編號將用於查找相關產品收據。 然後將使用產品收據數量來產生發票行。

## <a name="data-entity-changes"></a>資料實體變更

為了支援本主題中介紹的功能，**廠商發票抬頭** 資料實體已得到增強。 新增了三個欄位：

- **HeaderOnlyImport** – 該欄位必須設定為 **是**，才能為發票抬頭產生行。
- **PurchIdRange** – 訂購單編號清單。 發票編號可以是一個範圍，例如 **INV0001..INV0009** (其中兩個點分隔範圍的開始和結束)，或離散值，例如 **INV0001、INV0003、INV0006**。 所有訂購單必須屬於發票抬頭上的同一個廠商帳戶。 否則，您將收到以下錯誤訊息：「無法產生發票行。 訂購單具有不同的廠商帳戶。」
- **PackingslipRange** – 產品收據編號清單。 可以從產品收據建立廠商發票行。 但是，產品收據編號通常不包含在廠商發票中。 僅當您可以確定特定發票的產品收據時，再於此欄位中輸入產品收據編號。 可以根據產品收據產生發票行。 如果使用此欄位，將忽略 **應付帳款參數** 頁面上 **選擇將自動建立的預設發票行數量** 欄位的設定。 

**限制**：如果輸入多個產品收據編號，將使用相同的發票編號建立多個待處理廠商發票。 您必須先手動合併它們，然後才能進一步處理發票。 在未來的版本中，我們計劃自動合併發票，因此將取消此限制。

所有產品收據必須屬於發票抬頭上的同一個廠商帳戶。

## <a name="result"></a>結果

如果成功產生行，則會在廠商發票自動化歷史記錄中記錄以下訊息：「自動建立發票行：成功。」

如果未產生行，則會記錄以下錯誤訊息：「自動建立發票行：失敗。」
