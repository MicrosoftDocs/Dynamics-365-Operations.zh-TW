---
title: 產生包含內嵌影像的 Office 格式的報表
description: 本主題介紹如何設計電子報表 (ER) 設定以在 Excel 和 Word 中產生包含內嵌影像的電子文件。
author: NickSelin
ms.date: 06/13/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6ec9f3013c1e365a3ca1a4c6cabe71a22e3e8b730eac38155ef023fe68107524
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460239"
---
# <a name="generate-reports-in-office-format-that-have-embedded-images"></a>產生包含內嵌影像的 Office 格式的報表

[!include [banner](../../includes/banner.md)]

以下步驟說明扮演「系統管理員」或「電子報表開發人員」角色的使用者如何設計電子報表 (ER) 設定以產生包含內嵌影像的 MS Office 格式 (Excel 和 Word) 的電子文件。

在此範例中，您將使用建立的 ER 設定為樣本公司，「Litware，Inc.」。  若要完成這些步驟，您必須先完成「ER 製作帶有內嵌影像的 MS Office 格式的報表 (第 2 節：查看設定)」工作指南中的步驟。 這些步驟可以在「USMF」公司進行。


## <a name="run-format-with-initial-model-mapping"></a>帶有初始模型對應的執行格式
1. 進入現金和銀行管理 > 銀行帳戶 > 銀行帳戶。
2. 使用快速篩選條件以篩選含有「DEMF OPER」值的銀行帳戶。
3. 在動作窗格上，點選安裝。
4. 點選檢查。
5. 點選列印測試。
    * 執行格式以獲取測試目的。  
6. 在可轉讓支票格式欄位中選取是。
7. 點選確定。
    * 查看建立的輸出。 報表中顯示公司標誌以及授權人的簽名。 簽名影像取自與所選銀行帳戶相關的支票配置記錄的「容器」資料類型欄位。  
8. 展開副本區段。
9. 點選編輯。
10. 在浮水印欄位中，輸入「將浮水印列印為無效」。
    * 更改浮水印配置設定以在 Excel 形狀元素中產生文件時顯示浮水印文字。  
11. 點選列印測試。
12. 點選確定。
    * 查看建立的輸出。 浮水印根據選取選項顯示在建立的報表中。  
13. 關閉頁面。
14. 在動作窗格上，點選「管理付款」。
15. 點選檢查。
16. 點選顯示過濾器。
17. 套用以下過濾器：使用「is one of」過濾器運算子在「支票號碼」欄位中輸入過濾器值「381」、「385」、「389」。
18. 在清單中，標記所有資料列。
19. 點選列印支票副本。
    * 執行格式以重新列印選定的支票。  
    * 查看建立的輸出。 所選支票已重新列印。 公司標誌和標籤沒有列印出來，因為它們顯示在預列印的表格上。  

## <a name="modify-the-mapping-of-the-imported-data-model"></a>修改匯入資料模型的對應
1. 關閉頁面。
2. 關閉頁面。
3. 進入組織管理 > 電子報表 > 設定。
4. 在樹狀結構中，選取「Model for cheques」。
5. 點選設計工具。
6. 點選將模型對應到資料來源。
7. 點選設計工具。
    * 我們將更改資料模型的簽名項的繫結，以從已附加到與所選銀行帳戶相關的支票配置記錄的檔案中獲取簽名影像。  
8. 關閉顯示詳情。
9. 在樹狀結構中，展開「layout」。
10. 在樹狀結構中，展開「layout\signature」。
11. 在樹狀結構中，選取「layout\signature\image = chequesaccount.'<Relations'.BankChequeLayout.Signature1Bmp」。
12. 在樹狀結構中，展開「chequesaccount」。
13. 在樹狀結構中，展開「chequesaccount\<Relations」。
14. 在樹狀結構中，展開「chequesaccount\<Relations\BankChequeLayout」。
15. 在樹狀結構中，展開「chequesaccount\<Relations\BankChequeLayout\<Relations」。
16. 在樹狀結構中，展開「chequesaccount\<Relations\BankChequeLayout\<Relations\<Documents」。
17. 在樹狀結構中，選取「chequesaccount\<Relations\BankChequeLayout\<Relations\<Documents\getFileContentAsContainer()」。
18. 點選繫結。
19. 點選儲存。
20. 關閉頁面。
21. 關閉頁面。
22. 關閉頁面。
23. 關閉頁面。

## <a name="run-format-using-the-adjusted-model-mapping"></a>使用調整後的模型對應執行格式
1. 進入現金和銀行管理 > 銀行帳戶 > 銀行帳戶。
2. 使用快速篩選器尋找記錄。 例如，過濾器在銀行帳戶欄位上，具有「USMF OPER」的值。
3. 在動作窗格上，點選安裝。
4. 點選檢查。
5. 點選列印測試。
6. 點選確定。
    * 查看建立的輸出。 Document Management 附件中的影像顯示為授權人的簽名。  

## <a name="use-ms-word-document-as-a-template-in-the-imported-format"></a>使用 MS Word 文件作為匯入格式的範本
1. 關閉頁面。
2. 關閉頁面。
3. 進入組織管理 > 電子報表 > 設定。
4. 在樹狀結構中，展開「Model for cheques」。
5. 在樹狀結構中，選取「Model for cheques\Cheques printing format」。
6. 點選設計工具。
7. 點選附件。
8. 點選刪除。
9. 點選是。
10. 點選「新增」。
11. 點選檔案。
    * 點選瀏覽並選取預先下載的「Cheque template Word.docx」檔案。  
12. 關閉頁面。
13. 在範本欄位中，輸入或選取一個值。
14. 點選儲存。
15. 關閉頁面。
16. 點選編輯。
17. 在執行草稿欄位中選取是。
18. 關閉頁面。
19. 進入現金和銀行管理 > 銀行帳戶 > 銀行帳戶。
20. 使用快速篩選條件以篩選含有「DEMF OPER」值的銀行帳戶。
21. 點選檢查。
22. 點選列印測試。
23. 點選確定。
    * 查看建立的輸出。 輸出已產生為 Word 文件，其中嵌入了顯示公司標誌、授權人簽名和所選浮水印文字的影像。  



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]