---
title: 設計設定以產生具有應用程式資料的文件
description: 本主題介紹如何設計電子報表 (ER) 設定以產生電子文件。 (第 1 章節 - 匯入設定)
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
ms.openlocfilehash: 3f335721ee97919af20e73fc9da6c9bf07dcae50aca8f8904d144d75c2f4d7b1
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460433"
---
# <a name="design-configurations-to-generate-documents-that-have-application-data"></a>設計設定以產生具有應用程式資料的文件

[!include [banner](../../includes/banner.md)]

若要完成此程序中的步驟，您必須先完成程序，ER 產生具有應用程式資料更新的檔案 (第 1 章節：匯入設定)。



此程序中的步驟說明如何設計電子報表 (ER) 設定以產生電子文件。 在此過程中，您運行為樣本公司 Litware, Inc. 建立的 ER 匯入格式設定以產生電子文件。



此程序是為指派了系統管理員或電子報表開發人員角色的使用者建立的。 這些步驟可以使用 DEMF 資料集完成。 



在開始之前，將 DEMF 公司的國家/地區內容從 DEU (德國) 更改為 BEL (比利時)。 點選組織管理 > 組織 > 法律實體以更新法律實體 DEMF 的主要地址中的國家/地區代碼。 重新啟動您的應用程式。


## <a name="run-imported-er-format"></a>執行已匯入好的 ER 格式
1. 進入組織管理 > 電子報表 > 設定。
2. 在樹狀結構中，展開「Intrastat (model)」。
3. 在樹狀結構中，選取「Intrastat (model)\Intrastat (format)」。
4. 點選執行。
    * 運行 ER 格式設定的草稿版本以產生 Intrastat 報表。  
5. 在輸入檔案名稱欄位，輸入「intrastat.xml」。
    * 指定檔案名稱  
6. 點選確定。
    * 查看產生的 XML 檔案。  
7. 關閉頁面。
8. 進入稅務 > 報表 > 外貿 > Intrastat。
    * 打開此表單以查看包含在產生的電子文件中的 Intrastat 交易。  
9. 點選 Intrastat 歸檔。
    * 由於執行的 ER 格式不包含任何應用程式資料更新設定，因此尚未存檔已完成的 Intrastat 報表的詳情。  
10. 關閉頁面。
11. 關閉頁面。



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]