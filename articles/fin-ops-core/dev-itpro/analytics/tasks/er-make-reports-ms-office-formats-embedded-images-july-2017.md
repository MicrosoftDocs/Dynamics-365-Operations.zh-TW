---
title: 設計設定以產生具有內嵌影像的 Office 格式的報表
description: 本主題介紹如何設計在 Excel 和包含內嵌影像的 Word 格式中產生電子文件的設定。
author: NickSelin
ms.date: 04/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 03a514c5b616d761ef3eb6347e67e645b23eaa1794911775835e77cded4500ac
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460460"
---
# <a name="design-configurations-to-generate-reports-in-office-format-that-have-embedded-images"></a>設計設定以產生具有內嵌影像的 Office 格式的報表

[!include [banner](../../includes/banner.md)]

若要完成此過程中的步驟，要先完成過程「ER 建立設定提供者並將其標記為有效」。 此程序介紹如何設計電子報表 (ER) 設定以產生包含內嵌影像的 Microsoft Excel 或 Word 文件。 在此程序中，您將為範例公司 Litware, Inc 建立所需的 ER 設定。這些步驟可以使用 USMF 資料集完成。 此程序是為指派了系統管理員或電子報表開發人員角色的使用者建立的。 在開始之前，請下載並儲存以下檔案： 

| 描述                                          | 檔案名稱                   |
|------------------------------------------------------|-----------------------------|
| ER 資料模型設定                          | [支票.xml 的模型](https://download.microsoft.com/download/6/e/a/6ea166fd-1382-4fdb-8dcb-0f13379f9c8e/Modelforcheques.xml)       |
| ER 格式設定                              | [支票列印格式.xml](https://download.microsoft.com/download/1/7/c/17c301e3-c4ee-4886-ae75-440fcc002c8c/Chequesprintingformat.xml) |
| 公司標誌圖片                                   | [Company logo.png](https://download.microsoft.com/download/8/2/e/82e6bd81-caac-4e9a-bfce-1392ce7c8616/Companylogo.png)            |
| 簽名影像                                      | [簽名影像.png](https://download.microsoft.com/download/5/0/9/509151b3-06fc-4870-9408-7c9a43b72771/Signatureimage.png)         |
| 替代簽名影像                          | [簽名影像 2.png](https://download.microsoft.com/download/3/0/0/30045bf1-0ff6-4215-9162-b77c2f5dcc7c/Signatureimage2.png)       |
| 用於列印付款支票的 Microsoft Word 範本  | [支票範本 Word.docx](https://download.microsoft.com/download/4/4/d/44d9d255-9ad1-42fe-87db-23f319fd8e89/ChequetemplateWord.docx)   |

## <a name="verify-prerequisites"></a>驗證先決條件  
 1. 進入組織管理 > 工作區 > 電子報表。  
 2. 確保樣本公司 Litware, Inc. 的設定提供者可用並標記為有效。 如果您沒有看到此設定廠商，請完成「建立設定廠商並將其標記為有效」程序中的步驟。   
 3. 點選報表設定。  
 
## <a name="add-a-new-er-model-configuration"></a>新增新的 ER 模型配置  
 1. 您可以載入之前儲存的 ER 模型設定檔案 (Model for cheques.xml)，而不是建立新模型。 此檔案包含用於付款支票的樣本資料模型，以及資料模型的對應到 Dynamics 365 for Operations 應用程式的資料組件。   
 2. 在版本 FastTab 上，點選 Exchange。   
 3. 點選從 XML 檔案載入。  
 4. 點選瀏覽，然後選取 Model for cheques.xml。   
 5. 點選確定。  
 6. 載入的模型將用作資訊的資料來源，以在 Excel 和 Word 中產生包含影像的文件。  

## <a name="add-a-new-er-format-configuration"></a>新增新的 ER 格式設定  
 1. 您可以載入之前儲存的 ER 格式設定檔案 (Cheques printing format.xml)，而不是建立新格式。 此檔案包含使用預列印表格列印支票的格式的範例配置，以及此格式到「Model for cheques」資料模型的對應。   
 2. 點選 Exchange。  
 3. 點選從 XML 檔案載入。  
 4. 點選瀏覽並選取 Cheques printing format.xml 檔案。   
 5. 點選確定。  
 6. 在樹狀結構中，展開「Model for cheques」。  
 7. 在樹狀結構中，選取「Model for cheques\Cheques printing format」。  
 8. 載入的格式將用於產生包含 Excel 和 Word 中的影像的文件。   

## <a name="configure-er-user-parameters"></a>設定 ER 使用者參數  
 1. 在動作窗格上，點選設定。  
 2. 點選使用者參數。  
 3. 在執行設定欄位中選取是。  
  打開「執行草稿」標幟以啟動所選格式的草稿版本，而不是已完成的版本。  
 4. 點選確定。  

## <a name="configure-cash--bank-management-parameters"></a>設定現金和銀行管理參數  
 1. 進入現金和銀行管理 > 銀行帳戶 > 銀行帳戶。  
 2. 使用快速篩選條件以篩選含有「DEMF OPER」值的銀行帳戶。  
 3. 在動作窗格上，點選安裝。  
 4. 點選檢查。  
 5. 展開安裝區段。  
 6. 點選編輯。  
 7. 在公司標誌欄位中選取是。  
 8. 點選公司標誌。  
 9. 點選更改。  
 10. 點選瀏覽並選取您之前下載的檔案，Company logo.png。   
 11. 點選儲存。  
 12. 關閉頁面。  
 13. 展開簽章區段。  
 14. 在列印第一個簽章欄位中選取是。  
 15. 點選更改。  
 16. 點選瀏覽並選取您之前下載的檔案，Signature image.png。   
 17. 展開副本區段。  
 18. 在浮水印欄位中，選取一個選項。  
 19. 在常用電子匯出格式欄位中選取是。  
 20. 選取「支票列印表格」設定。  
 21. 現在所選的 ER 格式將用於列印支票。  
 22. 點選連結。  
 23. 點選新建。  
 24. 點選檔案。  
 25. 點選瀏覽並選取您之前下載的檔案，Signature image 2.png。   
 26. 關閉頁面。  
 27. 關閉頁面。  
 28. 關閉頁面。  
 29. 前往現金和銀行管理 > 安裝 > 現金和銀行管理參數。  
 30. 在允許在無效的銀行帳戶上建立預驗證：欄位中選取是。  
 31. 點選儲存。  
 32. 關閉頁面。  


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
