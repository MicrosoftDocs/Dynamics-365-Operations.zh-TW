---
title: 準備要在 RCS 中使用的應用程式中繼資料
description: 本主題介紹如何建立包含應用程式中繼資料的新報表設定。
author: NickSelin
ms.date: 06/28/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-06-28
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 71a33a69796b31c456bfcc5abbb3b18bcb1064be65c1c58b36656a9cebfbf47d
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460428"
---
# <a name="prepare-application-metadata-to-be-used-in-rcs"></a>準備要在 RCS 中使用的應用程式中繼資料
[!include [banner](../../includes/banner.md)]

以下步驟說明了系統管理員或電子報表開發人員角色的使用者如何建立包含應用程式中繼資料的新電子報表 (ER) 設定，以便在 Regulatory Configuration Service (RCS) 中設計 ER 模型對應設定。 此設定將用於設計範例 ER 模型對應設定以存取外貿交易。 在此範例中，您將為樣本公司 Litware, Inc. 建立一個設定。這些步驟可以在任何公司中執行。 若要完成這些步驟，您首先必須完成本主題中的步驟，[建立設定廠商並將其標記為有效](er-configuration-provider-mark-it-active-2016-11.md)。

## <a name="prerequisites"></a>先決條件
1.    進入 **組織行政管理** > **工作區** > **電子報表**。 
2.    確保樣本公司 Litware, Inc. 的設定提供者可用並標記為 **作用中**。 如果您沒有看到此設定供應商，請完成程序中的步驟[建立設定供應商並將其標記為有效](er-configuration-provider-mark-it-active-2016-11.md)。 
3.    點選 **中繼資料設定**。 
4.    假設 RCS 將用於為財務和營運應用程式設計 ER 解決方案，該應用程式將產生包含來自外貿業務領域資訊的電子文件。 若要指定 ER 資料模型和所需資料來源之間的對應，在 RCS 中，我們需要存取財務和營運應用程式的中繼資料。 因此，作為設計 ER 解決方案的一部分，我們設定了一個新的 ER 中繼資料設定，其中包含目前為選定業務領域產生 ER 報表所需的所有中繼資料。 

## <a name="add-metadata-configuration"></a>新增中繼資料設定 
1.    點選 **建立設定** 即可打開下拉式對話方塊。 
2.    在 **名稱** 欄位，輸入「外貿中繼資料」。 
3.    點選 **建立設定**。 
4.    點選 **設計工具**。 
5.    選點 **新增**。 
  
> [!NOTE]
> 您可以選取整個應用程式或選定模型或選定模組的所有中繼資料。 請注意，在這種情況下，將自動新增以下中繼資料：記錄表、列舉和擴展資料類型。 當需要其他類型的中繼資料時，必須手動新增它們。 
 
透過手動選取中繼資料項，我們有一些與外貿交易相關的中繼資料。 
  
6.    點選 **新增資料來源**。 
7.    點選 **資料表記錄**。 
8.    使用快速篩選器篩選值為「Intrastat」的 **名稱** 欄位。 
9.    選取 **Intrastat** 資料表記錄。 
10.    點選 **確定**。
  
我們新增了有關 Intrastat 記錄表的中繼資料資訊。 
  
11.    在樹狀結構中，展開 **資料表記錄 Intrastat**\>**關係**。 
12.    在樹狀結構中，選取 **資料表記錄 Intrastat**\>**關係\IntrastatCommodity (資料表記錄 EcoResCategory)**。     
13.    點選 **新增中繼資料**。 
  
> [!NOTE]
> 必須手動新增有關所選記錄表所需關係的中繼資料。 
  
16.    點選 **新增資料來源**。 
17.    點選 **列舉**。 
18.    使用快速篩選器篩選值為「IntrastatDirection」的 **名稱** 欄位。 
19.    選取 **IntrastatDirection 列舉** 記錄。 
20.    點選 **確定**。 
21.    選取 **儲存**。  
22.    關閉頁面。 
  
## <a name="complete-the-draft-version-of-metadata-configuration"></a>完成中繼資料設定草稿版
1.    點選 **更改狀態**。 
2.    點選 **完成**。 
3.    點選 **確定**。 
4.    選取完成的版本 **1**。 
  
## <a name="export-the-completed-version-of-metadata-configuration-from-application-as-xml-file"></a>從應用程式中將中繼資料設定的完整版本匯出為 XML 檔案
1.    點選 **交換**。 
2.    點選 **匯出為 XML 檔案**。 
3.    點選 **確定**。 
    
建立的 ER 中繼資料設定已儲存為 XML 檔案，可匯入 RCS 並用作外貿業務域中繼資料的資訊來源。 基於此資訊，我們可以指定應用程式中繼資料和 ER 資料模型之間的對應。


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]