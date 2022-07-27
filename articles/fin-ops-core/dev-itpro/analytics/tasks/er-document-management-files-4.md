---
title: ER 在格式輸出中使用文件管理檔案 (第 4 章節 - 執行格式)
description: 本主題介紹如何設定電子報表格式以在 ER 輸出中使用文件管理檔案。 (第 4 章節)
author: NickSelin
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CustOpenInvoicesListPage, CustInvoiceJournal, SalesTable, ERSolutionTable
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 11b446d21a7ae57ffa2cccf983777beb882bf77de6b54c2d1aef810028a6d343
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460260"
---
# <a name="er-use-document-management-files-in-format-outputs-part-4---run-format"></a>ER 在格式輸出中使用文件管理檔案 (第 4 章節 - 執行格式)

[!include [banner](../../includes/banner.md)]

以下步驟說明了指派給系統管理員或電子報表開發人員角色的使用者如何設定電子報表 (ER) 格式以使用 ER 輸出中的文件管理檔案 (附件)。 這些步驟可以在 DEMF 公司進行。

若要完成這些步驟，必須先填寫「ER使用文件管理檔案以格式輸出 (第 3 章節：建立格式)」程序中的步驟。

此程序是 Dynamics 365 for Operations 版本 1611 中增加的函數。


## <a name="add-necessary-attachments-for-sales-order-of-a-single-invoice"></a>為單個發票的銷售訂單新增必要的附件
1. 進入應收帳款 > 發票 > 開啟客戶發票。
2. 使用快速篩選器尋找記錄。 例如，發票欄位上的過濾器以及「CIV-000148」值。
    * CIV-000148  
3. 點選以追蹤所選發票的連結。
    * CIV-000148  
4. 點選以追蹤銷售訂單欄位中的連結。
    * 000148  
5. 在明細或標題欄位中，選取標題選項。
    * 選取標題以指示這將是新增附件的目標。  
6. 點選連結。
    * 新增一些檔案作為此銷售訂單的附件。 使用文件管理支援的文件類型的檔案 (檔案副檔名為 DOCX、DPF、XML、JPG 等)。 瀏覽並選取要附加的檔案，並與 ER 電子訊息中的相關發票一起進一步處理。  
7. 點選新增。
8. 點選檔案。
9. 點選新增。
10. 點選檔案。
11. 關閉頁面。
12. 關閉頁面。
13. 關閉頁面。
14. 關閉頁面。

## <a name="run-the-designed-report-for-the-selected-invoice"></a>為選定的發票執行設計的報表
1. 進入組織管理 > 電子報表 > 設定。
2. 在樹狀結構中，展開「Customer invoice model」。
3. 在樹狀結構中，展開「Customer invoice model\Customer invoice model (custom)」。
4. 在樹狀結構中，選取「Customer invoice model\Customer invoice model (custom)\Electronic invoice sample message」。
5. 點選執行。
6. 展開記錄以包含 () 區段。
7. 點選「篩選」。
8. 選取客戶發票日記帳資料列和銷售訂單欄位。
9. 在條件欄位中，輸入「000148」。
    * 在條件「銷售訂單」欄位中，輸入訂單編號 000148。  
10. 點選確定。
11. 點選確定。
    * 查看產生的輸出。 請注意，已為每個附件建立了一個 XML 節點。 附件的內容以 MIME (base64) 文字格式填入到 XML 輸出中。  



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]