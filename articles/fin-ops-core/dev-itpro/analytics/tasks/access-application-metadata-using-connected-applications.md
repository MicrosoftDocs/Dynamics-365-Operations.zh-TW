---
title: 使用已連線的應用程式存取應用程式中繼資料
description: 本主題的步驟說明 Regulatory Configuration Service 使用者如何使用中繼資料設計新的電子報表模型對應。
author: NickSelin
ms.date: 06/29/2019
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
ms.openlocfilehash: 6d99ca41a9a24ef8ac0fe31e703cad79d41216fa726fa1d354ac19db90706954
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460275"
---
# <a name="access-application-metadata-by-using-connected-applications"></a>使用已連線的應用程式存取應用程式中繼資料

[!include [banner](../../includes/banner.md)]

以下步驟說明了系統管理員或電子報表開發人員角色中的 Regulatory Configuration Service (RCS) 使用者如何使用 Finance and Operations 中繼資料設計新的電子報表 (ER) 模型對應。 使用 RCS 離線的應用程式在線上存取應用程式中繼資料。 將樣本 ER 模型對應設定存取外貿交易。 若要完成這些步驟，您首先必須在 RCS 中完成本主題中的步驟，[建立設定供應商並將其標記為有效](er-configuration-provider-mark-it-active-2016-11.md)。 如果您尚未完成主題中的步驟，[使用 ER 設定存取應用程式中繼資料](access-application-metadata-er-configuration.md)，下載[電子報表範例](https://download.microsoft.com/download/0/4/e/04e13839-e423-442b-a6c2-dd35b1045c2d/Dynamics%20365%20for%20Finance%20and%20Operations%208.1%20Electronic%20reporting%20task%20guides.zip)並儲存以下 ER 設定：外貿中繼資料 .xml；外貿對應模型 .xml；外貿對應 .xml，以及完成程序中的步驟。

## <a name="prerequisites"></a>先決條件
1. 進入 **所有工作區** > **電子報表**。 
2. 確保樣本公司 Litware, Inc. 的設定提供者可用並標記為 **作用中**。 如果您沒有看到此設定供應商，請完成程序中的步驟[建立設定供應商並將其標記為有效](er-configuration-provider-mark-it-active-2016-11.md)。 

## <a name="get-required-er-configurations"></a>獲取所需的 ER 設定
1. 點選 **報表設定**。 
2. 如果您已經完成了[使用 ER 設定存取應用程式中繼資料](access-application-metadata-er-configuration.md)程序中的步驟，您已經在現行 RCS 執行個體中擁有所有必要的 ER 設定 (外貿中繼資料、模型和對應設定)。 您可以跳過此子任務的所有剩餘步驟。 
3. 點選 **Exchange**。 
4. 點選 **從 XML 文件載入**。 
5. 點選 **瀏覽** 並選取 **外貿中繼資料.xml** 檔案。 
6. 按一下 **確定**。 
7. 點選 **Exchange**。 
8. 點選 **從 XML 文件載入**。 
9. 點選 **瀏覽** 並選取 **外貿模型.xml** 檔案。 
10. 按一下 **確定**。 
11. 點選 **Exchange**。 
12. 點選 **從 XML 文件載入**。 
13. 點選 **瀏覽** 並選取 **外貿對應.xml** 檔案。 
14. 按一下 **確定**。 

## <a name="register-a-connected-application"></a>註冊連線的應用程式
1. 關閉頁面。 
2. 關閉頁面。 
3. 進入 **所有工作區** > **電子報表**。 
4. 點選 **已連線的應用程式**。 
5. 確保已設定的應用程式以 Azure 為主並且可供現行 RCS 使用者存取。 還要求現行的 RCS 使用者有權存取選定的應用程式並已註冊為該應用程式的使用者，扮演賦予他們存取應用程式中繼資料權限的角色。 
6. 按一下 **新建**。 
7. 在 **名稱** 欄位，輸入「MyConnectedApp」。 
8. 在 **應用程式** 欄位中，輸入「https:// mycompany.operations.dynamics.com」。 
9. 在 **租用戶** 欄位，輸入「mycompany.onmicrosoft.com」。 
10. 點選 **儲存**。 
11. 當您檢查與已設定的應用程式連線時，在 **連線到遠端應用程式** 頁面上點選 **點選此處連線到選定的遠端應用程式** 連結。 
12. 點選 **檢查連線**。 
13. 點選 **關閉**。 
14. 連線驗證成功後，將為現行格線中設定的應用程式更新版本和租用戶詳情。 

## <a name="review-existing-model-mapping-configuration"></a>查看現有模型對應設定
1. 關閉頁面。 
2. 點選 **報表設定**。 
3. 在樹狀結構中，展開 **外貿模型**。 
4. 在樹狀結構中，選取 **外貿模型\外貿對應**。 
5. 展開 **先決條件** 區段。 

    > [!NOTE]
    > 現行，此對應指的是中繼資料設定。 在設計此模型對應時，將提供此設定中的應用程式中繼資料。 

6. 點選 **設計工具**。 
7. 點選 **設計工具**。 
8. 在樹狀結構中，選取 **Dynamics 365 for Operations\資料表記錄**。 
9. 點選 **新增根**。 
10. 在 **資料表** 欄位中，輸入或選擇一個值。 

    > [!NOTE]
    > 現行，此對應指的是中繼資料設定。 在設計此模型對應時，將提供此設定中的應用程式中繼資料。 

11. 點選 **取消**。 
12. 關閉頁面。 
13. 關閉頁面。 

## <a name="assign-connected-application-to-model-mapping"></a>將連線的應用程式指派給模型對應 
1. 點選 **編輯**。 
2. 選取 **MyConnectedApp** 應用程式。 

    > [!NOTE]
    > 現行，此對應是指所選連線應用程式的中繼資料。 當相同對應同時指中繼資料設定和連線的應用程式時，將使用已連線的應用程式的中繼資料。 

3. 點選 **設計工具**。 
4. 點選 **設計工具**。 
5. 在樹狀結構中，選取 **Dynamics 365 for Operations\資料表記錄**。 
6. 點選 **新增根**。 
7. 在 **資料表** 欄位中，輸入或選擇一個值。 

    > [!NOTE]
    > 現在提供了兩個以上的應用程式表，因為此對應使用已為其指派的連線應用程式的所有中繼資料。 

8. 點選 **取消**。 
9. 點選 **驗證**。 

    > [!NOTE]
    > 我們已經成功地將資料模型的元素與資料來源項目綁定在一起，這些資料來源是透過使用已指派至此對應之連線應用程式的中繼資料詳情來描述。 

10. 關閉頁面。 
11. 關閉頁面。 

當您需要使用不同版本應用程式的中繼資料來評估此模型對應時，請註冊另一個連線的應用程式，將其指派給此模型對應並根據新中繼資料做驗證。


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
