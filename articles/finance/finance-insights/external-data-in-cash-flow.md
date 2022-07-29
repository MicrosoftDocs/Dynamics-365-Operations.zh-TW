---
title: 現金流量預測中的外部資料
description: 本主題描述了必須完成的設定步驟，以便可以將外部資料輸入或匯入到現金流預測中。
author: rcarlson
ms.date: 02/16/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalSetup, LedgerJournalTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2020-06-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 23342114c25cd1b59d47aa7ce63f09de029fa690
ms.sourcegitcommit: 465c84eb5cdc211692e2ae09b45d1400f9a315ee
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/17/2022
ms.locfileid: "8451617"
---
# <a name="external-data-in-cash-flow-forecasts"></a>現金流量預測中的外部資料

[!include [banner](../includes/banner.md)]

外部資料可以輸入或匯入現金流量預測。 本主題描述特定於使用外部資料並使外部資料能夠包含在現金流量預測中的設定步驟。

## <a name="external-data-setup"></a>外部資料設定

使用 **外部來源** 選項卡上 **現金流量預測設定** 頁 (**現金和銀行管理\>現金流量預測\>現金流量預測設定**) 輸入支持在現金流量預測中使用外部資料的設定。

外部資料可以輸入或匯入現金流量預測。 在輸入或匯入外部資料之前，必須設定外部來源。 在 **外部來源** 選項卡，設定外部現金流量類別。 類別可以是 **傳出** 或 **傳入**。 **流動性** 應選擇作為過帳類型。 在裡面 **法人實體設定** 網格，選擇外部現金流量類別適用的法人實體和相應的主賬戶。

有關如何設定現金流量預測的更多資訊，請參閱[現金流量預測](../cash-bank-management/cash-flow-forecasting.md)。

## <a name="enter-external-data"></a>輸入外部資料

要輸入和修改現金流量預測的外部資料，您可以使用 **在 Excel 中打開** 經驗。 選擇 **外部資料** 按鈕 **現金流量預測** 工作區頁面，然後選擇 **新增外部資料** 或 **編輯現有的外部資料**. 當 Microsoft Excel 檔案打開後，您可以在以下欄位中輸入資訊：

- **目錄識別碼** (獨特)
- **描述** (選用)
- **外部來源名稱** – 選擇您在設定 Finance Insights 時定義的列表中的值之一。
- **法律實體**
- **日期**
- **以交易貨幣計價的金額**
- **貨幣代碼**
- **預設維度** (選用)
- **文件編號** (選用)
- **帳戶編號** (選用)
- **帳戶名稱** (選用)

## <a name="importing-external-data-by-using-the-data-management-framework"></a>使用資料管理框架匯入外部資料

您可以使用 **資料管理** 工作區和命名的實體 **現金流量預測外部來源輸入**。

此外，如果您必須將設定資料從一個環境移動到另一個環境，則以下實體區域可用於所需的設定表：

- 現金流預測外部來源設定
- 現金流預測外部來源法律實體設定

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
