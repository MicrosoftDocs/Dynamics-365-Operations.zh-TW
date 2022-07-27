---
title: ER 在格式輸出中使用文件管理檔案 (第 3 節 - 建立格式)
description: 本主題介紹如何設定電子報表格式以在 ER 輸出中使用文件管理檔案。 (第 3 節)
author: NickSelin
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0cb052e2895cd0eb7f5c3bea9f33d988ef54dfb11e2e31c4212706b7fdaada79
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460262"
---
# <a name="er-use-document-management-files-in-format-outputs-part-3---create-format"></a>ER 在格式輸出中使用文件管理檔案 (第 3 節 - 建立格式)

[!include [banner](../../includes/banner.md)]

以下步驟說明了指派給系統管理員或電子報表開發人員角色的使用者如何設定電子報表 (ER) 格式以使用 ER 輸出中的文件管理檔案 (附件)。 這些步驟可以在任何公司進行。

若要完成這些步驟，必須先填入「ER使用文件管理檔案以格式輸出 (第2部分：擴展資料模型)」程序中的步驟。

此程序是 Dynamics 365 for Operations 版本 1611 中增加的函數。


## <a name="create-a-format-to-process-invoices"></a>建立處理發票的格式
1. 進入組織管理 > 工作區 > 電子報表。
2. 點選報表設定。
3. 在樹狀結構中，展開「Customer invoice model」。
4. 在樹狀結構中，選取「Customer invoice model\Customer invoice model (custom)」。
    * 您將建立一種格式來產生電子訊息，其中包含有關已附加到與電子處理發票相關的銷售訂單的任何檔案的資訊。  
5. 點選建立設定即可打開下拉式對話方塊。
6. 在新增欄位中，輸入「Format based on data model Customer invoice model (custom)」。
7. 在名稱欄位中，輸入「Electronic invoice sample message」。
    * 電子發票樣本訊息  
8. 在資料模型定義欄位中，輸入或選取一個值。
    * InvoiceCustomer  
9. 點選建立設定。

## <a name="design-a-format-to-populate-attachments-into-generating-a-message-in-mime-format"></a>設計一種格式來填入附件以產生 MIME 格式的訊息
1. 點選設計工具。
2. 點選新增根以開啟下拉式對話方塊。
3. 在樹狀結構中，選取「XML\元素」。
4. 在名稱欄位，輸入「Invoice」。
    * 發票  
5. 點選確定。
6. 點選新增以開啟下拉式對話方塊。
7. 在樹狀結構中，選取「XML\Attribute」。
8. 在名稱欄位，輸入「SalesOrder」。
    * SalesOrder  
9. 點選確定。
10. 點選新增屬性。
11. 在名稱欄位，輸入「InvoiceNumber」。
    * InvoiceNumber  
12. 點選確定。
13. 點選新增屬性。
14. 在名稱欄位，輸入「InvoiceAmount」。
    * InvoiceAmount  
15. 點選確定。
16. 點選新增以開啟下拉式對話方塊。
17. 在樹狀結構中，選取「XML\元素」。
18. 在名稱欄位，輸入「EnclosedDocs」。
    * EnclosedDocs  
19. 點選確定。
20. 在樹狀結構中，選取「Invoice\EnclosedDocs」。
21. 點選新增元素。
22. 在名稱欄位，輸入「Document」。
    * 文件  
23. 點選確定。
24. 在樹狀結構中，選取「Invoice\EnclosedDocs\Document」。
25. 點選新增以開啟下拉式對話方塊。
26. 在樹狀結構中，選取「XML\Attribute」。
27. 在名稱欄位，輸入「FileName」。
    * FileName  
28. 點選確定。
29. 點選新增以開啟下拉式對話方塊。
30. 在樹狀結構中，選取「XML\元素」。
31. 在名稱欄位，輸入「FileContent」。
    * FileContent  
32. 點選確定。
33. 在樹狀結構中，選取「Invoice\EnclosedDocs\Document\FileContent」。
34. 點選新增以開啟下拉式對話方塊。
35. 在樹狀結構狀狀結構中，選取「Text\Base64」。
36. 點選確定。

## <a name="map-format-elements-to-data-model-as-data-source"></a>將資料模型的對應格式元素作為資料來源
1. 在樹狀結構中，選取「Invoice\SalesOrder」。
2. 點選對應索引標籤。
3. 在樹狀結構中，展開「模型」。
4. 在樹狀結構中，選取「model\Sales order number(SalesId)」。
5. 點選繫結。
6. 在樹狀結構中，選取「Invoice\InvoiceNumber」。
7. 在樹狀結構中，展開「model\Base invoice(InvoiceBase)」。
8. 在樹狀結構中，選取「model\Base invoice(InvoiceBase)\Invoice number(Id)」。
9. 點選繫結。
10. 在樹狀結構中，選取「Invoice\InvoiceAmount」。
11. 在樹狀結構中，選取「model\Base invoice(InvoiceBase)\Invoice amount(Amount)」。
12. 點選繫結。
13. 在樹狀結構中，展開「model\Invoice attachments」。
14. 在樹狀結構中，選取「model\Invoice attachments\File content」。
15. 在樹狀結構中，選取「Invoice\EnclosedDocs\Document\FileContent\Base64」。
16. 點選繫結。
17. 在樹狀結構中，選取「model\Invoice attachments\File name」。
18. 在樹狀結構中，選取「Invoice\EnclosedDocs\Document\FileName」。
19. 點選繫結。
20. 在樹狀結構中，選取「model\Invoice attachments」。
21. 在樹狀結構中，選取「Invoice\EnclosedDocs\Document」。
22. 點選繫結。
23. 點選儲存。
24. 關閉頁面。



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]