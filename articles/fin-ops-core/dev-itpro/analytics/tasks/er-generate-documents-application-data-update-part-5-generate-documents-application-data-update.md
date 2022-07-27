---
title: 產生具有應用程式資料的文件
description: 若要完成此程序中的步驟，您必須先完成程序「ER 產生具有應用程式資料更新的檔案 (第 4 章節 - 修改格式)」。
author: NickSelin
ms.date: 06/19/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0166e0afb542baea063f2d563e1eaeb0cdbfd6f62d77898fd9916afbeca90e48
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460430"
---
# <a name="generate-documents-that-have-application-data"></a>產生具有應用程式資料的文件

[!include [banner](../../includes/banner.md)]

若要完成此程序中的步驟，您必須先完成程序「ER 產生具有應用程式資料更新的檔案 (第 4 章節：修改格式)」。



此程序中的步驟說明如何設計電子報表 (ER) 設定以產生電子文件和更新應用程式資料。 在此程序中，您執行 ER 格式設定以產生 Intrastat 報表並更新應用程式資料以歸檔報表流程的詳情。



此程序是為指派了系統管理員或電子報表開發人員角色的使用者建立的。 這些步驟可以使用 DEMF 資料集完成。 在開始之前，請確保 DEMF 公司的國家/地區內容是 BEL (比利時)。


## <a name="set-up-foreign-trade-parameters"></a>設定外貿參數
1. 進入稅收 > 設定 > 外貿 > 外貿參數。
2. 點選編號序列索引標籤。

    歸檔 Intrastat 報表流程的詳情，我們需要識別我們建立的每個歸檔的記錄。 必須為此設定一個特殊的序列號。  

3. 選取「Intrastat 歸檔 ID」參考。
4. 在編號序列代碼欄位中，鍵入一個值。

    在「序列號代碼」欄位中，輸入或選取值「Fore_2」。  

5. ResolveChanges 序列號代碼。
6. 點選儲存。
7. 關閉頁面。

## <a name="run-modified-er-format"></a>執行修改好的 ER 格式
1. 進入組織管理 > 電子報表 > 設定。
2. 在樹狀結構中，展開「Intrastat (model)」。
3. 在樹狀結構中，選取「Intrastat (model)\Intrastat (format)」。
4. 點選執行。
5. 在輸入檔案名稱欄位，輸入「intrastat2.xml」。
6. 點選確定。

## <a name="review-er-format-executions-results"></a>查看 ER 格式執行的結果
查看產生的 XML 檔案。  
1. 關閉頁面。
2. 進入稅務 > 報表 > 外貿 > Intrastat。

    開啟此表單，其中包含已包含在產生的電子文件中的 Intrastat 交易。  

3. 點選 Intrastat 歸檔。

    由於執行的 ER 格式現在包含應用程式資料更新的設定，已完成 Intrastat 報表的詳情已存檔。 在此表單中，您可以看到建立的歸檔的標題記錄。  

4. 點選「詳細資料」。

    在此表單中，您可以查看已建立存檔的詳情。  

5. 關閉頁面。
6. 關閉頁面。
7. 關閉頁面。



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]