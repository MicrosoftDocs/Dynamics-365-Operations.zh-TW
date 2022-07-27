---
title: ER 設定目的地
description: 此程序示範如何為電子報表 (ER) 輸出組件 (例如資料夾或檔案) 設定和使用不同的目的地。
author: NickSelin
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERFormatDestinationTable, SysLookupPicklist, ERFormatDestinationSettings, ERFormatDestinationEmailSettings, ERExpressionDesignerFormula, SRSPrintDestinationTokens
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f1e679b52b28ff1ca117c5224fc7e2825feb26e5e5aea1c8b5bc3a88d1eaf235
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460264"
---
# <a name="er-configure-destinations"></a>ER 設定目的地

[!include [banner](../../includes/banner.md)]

此程序示範如何為電子報表 (ER) 輸出組件 (例如資料夾或檔案) 設定和使用不同的目的地。 建立此程序的示範資料公司為 DEMF。 德國是法律實體主要地址的國家\地區，但是您可以使用任何法律實體進行此程序。 

此範例中使用的格式是 ISO20022 貸記轉帳，但您可以使用已匯入的任何格式。 請注意，此過程是單個檔案和單個目的地安裝的範例。 可以在 Dynamics 365 Finance 說明中找到有關電子報表目的地管理的更多信息。

1. 進入組織管理 > 電子報表 > 電子報表目的地。
2. 點選新建為格式建立一組新的目的地。
3. 在參考欄位中，選取要為其設定目的地的格式。
    * 如果您沒有要選取的值，則表示您尚未匯入任何電子報表格式設定。 在設定目的地之前，您必須匯入格式設定。  
4. 點選新建即可建立新的檔案目的地。
    * 請注意，您可以為相同格式的每個輸出組件 (例如資料夾或檔案) 建立一個檔案目的地。 您將能夠在設定中分別啟用和停用目的地。  
5. 在名稱欄位中，輸入輸出組件的使用者自訂名稱。
    * 我們建議您使用有意義的名稱，例如「付款檔案」或「控制報表」。 這些名稱將在設定執行階段與目的地設定一起呈現給使用者。  
6. 在檔案名中，選取特定於該格式的檔案或資料夾。
7. 點選設定。
8. 在已啟用欄位中選取是。
    * 每個索引標籤上的啟用核取方塊分別啟用和停用每個目的地。 在此範例中，您將啟用在產生檔案時將輸出檔案發送給郵件收件者。  
9. 點選編輯以設定電子郵件收件者。
10. 選點新增。
11. 點選列印管理電子郵件。
12. 在電子郵件來源欄位中，選取一個選項。
    * 您可以選取不同的電子郵件來源類型，例如客戶或廠商類型。 這定義了電子郵件來源帳戶公式將回傳的引數類型。 電子郵件來源帳戶公式 (在以下步驟中描述) 是您繫結電子郵件來源的地方。 如果您的公式將回傳廠商帳戶，請選取廠商。 如果您使用 ISO 20022 Credit Transfer 設定範例，請使用廠商。  
13. 點選電子郵件來源繫結按鈕。
14. 在該公式中，輸入對您之前選取的參與方類型的特定文件參考。
    * 無需輸入，您可以找到代表方帳戶的資料來源節點，然後點選新增資料來源按鈕以更新公式。 例如，如果您使用 ISO 20022 Credit Transfer 設定，則代表廠商帳戶的節點是 '$PaymentsForCoveringLetter'.Creditor.Identification.SourceID。 否則，輸入任何字串值，例如「DE-001」，以儲存公式。  
15. 點選儲存。
16. 關閉頁面。
17. 點選編輯以設定該方的聯絡方式。
18. 在主要聯絡人欄位中選取是。
    * 您可以使用不同的選項來指示應使用哪種聯絡人類型作為此目的地的電子郵件地址。 在此範例中，我們使用主要聯絡人。  
19. 點選確定。
20. 點選確定。
21. 請在主旨欄位中輸入一值。
22. 點選確定。



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]