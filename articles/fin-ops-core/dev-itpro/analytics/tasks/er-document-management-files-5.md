---
title: ER 在格式輸出中使用文件管理檔案 (第 5 章節 - 修改和執行格式)
description: 本主題介紹如何設定電子報表 (ER) 格式以在 ER 輸出中使用文件管理檔案 (附件)。 (第 5 節)
author: NickSelin
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, EROperationDesigner, ERComponentTypeDropDialog, ERExpressionDesignerFormula, SysQueryForm
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 48175de4e58f9def15bf2bf8b10a1348036c88a1af284eb2a3e5f9fbefd649c1
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460259"
---
# <a name="er-use-document-management-files-in-format-outputs-part-5---modify-and-run-format"></a>ER 在格式輸出中使用文件管理檔案 (第 5 章節 - 修改和執行格式)

[!include [banner](../../includes/banner.md)]

以下步驟說明了指派給系統管理員或電子報表開發人員角色的使用者如何設定電子報表 (ER) 格式以使用 ER 輸出中的文件管理檔案 (附件)。 這些步驟可以在 DEMF 公司進行。

若要完成這些步驟，必須先填入「ER使用文件管理檔案以格式輸出 (第 4 章節：執行格式)」程序中的步驟。

此程序是 Dynamics 365 for Operations 版本 1611 中增加的函數。


## <a name="modify-the-format-to-populate-attachments-into-generating-messages-in-binary-format"></a>修改格式以填入附件以產生二進位格式的訊息
1. 進入組織管理 > 電子報表 > 設定。
2. 在樹狀結構中，展開「Customer invoice model」。
3. 在樹狀結構中，展開「Customer invoice model\Customer invoice model (custom)」。
4. 在樹狀結構中，選取「Customer invoice model\Customer invoice model (custom)\Electronic invoice sample message」。
5. 點選設計工具。
    * 您將使用 UNICODE 編碼將產生輸出中的發票訊息填入為 XML 檔案。  
6. 點選新增根以開啟下拉式對話方塊。
7. 在樹狀結構中，選取「Common\File」。
8. 在名稱欄位，輸入「Xml message」。
    * Xml 訊息  
9. 在編碼欄位，輸入「UTF-8」。
    * UTF-8  
10. 點選確定。
    * 將產生的輸出設定為壓縮檔案。  
11. 點選新增根以開啟下拉式對話方塊。
12. 在樹狀結構中，選取「Common\Folder」。
13. 在名稱欄位，輸入「Zip output」。
    * 壓縮輸出  
14. 點選確定。
15. 在樹狀結構中，選取「Zip output」。
    * 將附件作為具有原始名稱和副檔名的檔案新增到產生的壓縮檔案中。  
16. 點選新增以開啟下拉式對話方塊。
17. 在樹狀結構中，選取「Common\File」。
18. 在名稱欄位，輸入「Attached file」。
    * 附加檔案  
19. 點選確定。
20. 在樹狀結構中，選取「Zip output\Attached file」。
21. 點選新增以開啟下拉式對話方塊。
22. 在樹狀結構狀狀結構中，選取「Text\Base64」。
23. 點選確定。

## <a name="map-new-format-elements-to-data-model"></a>將新格式元素對應到資料模型
1. 點選對應索引標籤。
2. 在樹狀結構中，展開「模型」。
3. 在樹狀結構中，展開「model\Invoice attachments」。
4. 在樹狀結構中，選取「Zip output\Attached file\Base64」。
5. 在樹狀結構中，選取「model\Invoice attachments\File content」。
6. 點選繫結。
7. 在樹狀結構中，選取「Zip output\Attached file」。
8. 點選編輯檔案名稱。
9. 在樹狀結構中，展開「模型」。
10. 在樹狀結構中，展開「model\Invoice attachments」。
11. 在樹狀結構中，選取「model\Invoice attachments\File name」。
12. 點選新增資料來源。
13. 點選儲存。
14. 關閉頁面。
15. 在樹狀結構中，選取「model\Invoice attachments」。
16. 點選繫結。
17. 點選儲存。
18. 關閉頁面。

## <a name="run-the-designed-report-for-the-selected-invoice"></a>為選定的發票執行設計的報表
1. 點選執行。
2. 展開記錄以包含 () 區段。
3. 點選「篩選」。
4. 選取客戶發票日記帳資料列和銷售訂單欄位。
5. 在條件欄位中，在條件「銷售訂單」欄位中，輸入訂單號 000148。
    * 000148  
6. 點選確定。
7. 點選確定。
    * 查看產生的輸出。 請注意，除了 XML 格式的發票訊息外，還為每個附件建立了一個檔案。 附件檔案以二進位格式的壓縮輸出填入。  



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]