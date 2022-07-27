---
title: ER 在格式輸出中使用文件管理檔案 (第 2 章節 - 擴展資料模型)
description: 本主題介紹如何設定電子報表 (ER) 格式以在 ER 輸出中使用文件管理檔案 (附件)。 (第 2 部分)
author: NickSelin
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERDataModelDesigner, ERDataModelContentsItemCreationDialog, ERModelMappingTable, ERModelMappingDesigner, ERExpressionDesignerFormula
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d20738fbdfd85390870c935576d954d3050029f557fe8b5b690329f9e4a0aab4
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460261"
---
# <a name="er-use-document-management-files-in-format-outputs-part-2---extend-data-model"></a>ER 在格式輸出中使用文件管理檔案 (第 2 章節 - 擴展資料模型)

[!include [banner](../../includes/banner.md)]

以下步驟說明了指派給系統管理員或電子報告開發人員角色的使用者如何設定電子報告 (ER) 格式以使用 ER 輸出中的文件管理檔案 (附件)。 這些步驟可以在任何公司進行。

若要完成這些步驟，您必須先完成「使用格式輸出中的文件管理檔案 (第 1 章節：準備資料模型)」工作指南中的步驟。

此程序是 Dynamics 365 for Operations 版本 1611 中增加的函數。


## <a name="extend-data-model-to-present-the-document-management-files-in-it"></a>擴展資料模型以呈現其中的文件管理檔案
1. 進入組織管理 > 工作區 > 電子報表。
2. 點選報表設定。
3. 在樹狀結構中，展開「Customer invoice model」。
4. 在樹狀結構中，選取「Customer invoice model\Customer invoice model (custom)」。
5. 點選設計工具。
6. 在樹狀結構中，選取「Customer invoice(InvoiceCustomer)」。
    * 我們將擴展此資料模型以在其中公開已附加到與電子處理發票相關的銷售訂單的任何檔案。  
7. 按一下新增以開啟下拉式對話方塊。
8. 在名稱欄位，輸入「Invoice attachments」。
    * 發票附件  
9. 在項目類型欄位中，選取「記錄清單」。
10. 選點新增。
11. 按一下新增以開啟下拉式對話方塊。
12. 在名稱欄位，輸入「File content」。
    * 檔案內容  
13. 在項目類型欄位中，選取「Container」。
14. 選點新增。
15. 按一下新增以開啟下拉式對話方塊。
16. 在名稱欄位，輸入「File name」。
    * 檔案名稱  
17. 在項目類型欄位中，選取「字串」。
18. 選點新增。

## <a name="map-new-data-model-elements-to-data-sources"></a>將新資料模型元素對應到資料來源
1. 點選將模型對應到資料來源。
2. 使用快速過濾器在定義欄位上過濾具有「InvoiceCustomer」的值。
    * InvoiceCustomer  
    * 我們將將新的模型元素對應到適當的資料來源。  
3. 點選設計工具。
4. 在樹狀結構中，選取「Invoice attachments」。
5. 在樹狀結構中，展開「Invoice attachments」。
6. 在樹狀結構中，選取「Invoice attachments\File name」。
7. 點選編輯。
8. 在公式欄位中，輸入「CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'originalFileName()'」。
    * CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'originalFileName()'  
9. 點選儲存。
10. 關閉頁面。
11. 在樹狀結構中，選取「Invoice attachments\File content」。
12. 點選編輯。
13. 在公式欄位中，輸入「CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'getFileContentAsContainer()'」。
    * CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'getFileContentAsContainer()'  
14. 點選儲存。
15. 關閉頁面。
16. 在樹狀結構中，選取「Invoice attachments」。
17. 點選編輯。
18. 在公式欄位中，輸入「CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'」。
    * CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'  
19. 點選儲存。
20. 關閉頁面。
21. 點選儲存。
22. 關閉頁面。
23. 關閉頁面。
24. 關閉頁面。
25. 點選更改狀態。
26. 點選完成。
27. 點選確定。



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]