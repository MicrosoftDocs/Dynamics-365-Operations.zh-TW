---
title: 庫存帳齡報表儲存體
description: 本主題說明可讓您執行庫存帳齡報表，並以表單和圖表形式輸出庫存帳齡報表的功能。
author: AndersGirke
ms.date: 11/11/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventAgingStorage, InventAgingStorageChart, InventAgingStorageDetails
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2019-01-10
ms.dyn365.ops.version: ''
ms.openlocfilehash: 2ddddb0b1e377ed525b7c17fec5a4b3305573d0eba551bc03f075109a2ed769b
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447330"
---
# <a name="inventory-aging-report-storage"></a>庫存帳齡報表儲存體

[!include [banner](../includes/banner.md)]

在 Microsoft Dynamics 365 Supply Chain Management 中，你可以執行 **庫存帳齡報表儲存體** 報告，並以表單和圖表的形式輸出報告。 在表單中，欄和彙總餘額會根據您的配置設定進行動態調整。 圖表以視覺化方式呈現概觀，支援篩選功能，讓您可以深入瞭解詳細資訊。 此外，名為 **庫存帳齡報表** 的資料實體，可以讓您匯出 **庫存帳齡報表儲存體** 報告結果，並以例如：Microsoft Excel 檔案或 PDF 檔案的格式執行。

輸出結果包含很多行的情況下，使用這種方法執行 **庫存帳齡報表儲存體** 報告很有幫助。 例如，如果您有 50,000 個項目和 300 間商店，且分別做為倉庫，而您的庫存帳齡要求項目、位置和倉庫，則輸出結果會包含許多行。

## <a name="enable-the-inventory-value-storage-report-feature"></a>啟用庫存值儲存報表功能

使用該功能之前，必須先在系統中啟用。 系統管理員可以使用[功能管理](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)設定檢查功能狀態，並在需要時予以啟用或停用。 在這裡，該功能被列為：

- **模組**- 成本管理
- **功能名稱** - 庫存帳齡報表儲存體

## <a name="run-an-inventory-aging-report-storage"></a>執行庫存帳齡報表儲存體

1. 前往 **成本管理 \> 查詢和報告 \> 庫存帳齡報表儲存體**。
1. 選擇 **新增**。
1. 在 **程序識別碼 – 名稱** 欄位中，輸入報表的唯一名稱。
1. 選擇 **識別碼 – ID** 報告，並根據需求進行篩選。

    報表執行每一次都會在批次作業中完成。

1. 批次作業完成之後，輸出結果會顯示於 **庫存帳齡報表儲存體** 頁面。
1. 若要以傳統的格線配置檢視輸出結果的表單，請選擇 **檢視詳細資料**。 若要以彙總的圖表檢視輸出結果，請選擇 **檢視圖表**。

    > [!NOTE]
    > 表單不會包括報表配置中定義的小計。

**庫存帳齡報表** 資料實體，可以讓您透過 **程序識別碼 – 名稱** 欄位，套用至任何支援的資料管理格式，匯出一份 **庫存帳齡報表儲存體** 報告。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]