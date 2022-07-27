---
title: 使用 ER 設定存取應用程式中繼資料
description: 本主題描述 Regulatory Configuration Service 使用者如何使用中繼資料設計新的電子報表模型對應。
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
ms.openlocfilehash: 6ad175f81edcf6b21927d85927c42a3398a0286b4a766e06c88a61952384f75e
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460276"
---
# <a name="access-application-metadata-by-using-er-configuration"></a>使用 ER 設定存取應用程式中繼資料

[!include [banner](../../includes/banner.md)]

以下步驟說明了系統管理員或電子報表開發人員角色中的 Regulatory Configuration Service (RCS) 使用者如何使用應用程式中繼資料設計新的電子報表 (ER) 模型對應。 應用程式中繼資料將透過使用 ER 中繼資料設定來存取，該設定包含一組用於存取外貿交易的範例中繼資料。 若要完成這些步驟，您首先必須在 RCS 中完成本主題中的步驟，[建立設定供應商並將其標記為有效](er-configuration-provider-mark-it-active-2016-11.md)程序。 然後完成主題中的步驟，[準備要在 RCS 中使用的應用程式中繼資料](prepare-application-metadata-rcs.md)。

## <a name="prerequisites"></a>先決條件
1. 進入 **所有工作區** > **電子報表**。 
2. 確保樣本公司 Litware, Inc. 的設定提供者可用並標記為 **作用中**。 如果您沒有看到此設定供應商，請完成程序中的步驟[建立設定供應商並將其標記為有效](er-configuration-provider-mark-it-active-2016-11.md)。 

## <a name="import-metadata-configuration"></a>匯入中繼資料設定 
1. 點選 **中繼資料設定**。 
2. 匯入 ER 中繼資料設定，其中包含已設定為產生外貿業務電子文件的中繼資料。 此 ER 中繼資料設定已匯出成 XML 檔案，而[準備要在 RCS 中使用的應用程式中繼資料](prepare-application-metadata-rcs.md)程序中的步驟已完成。 
3. 點選 **Exchange**。 
4. 點選 **從 XML 文件載入**。 
5. 點選 **瀏覽** 並選取「外貿中繼資料.xml」檔案。 
6. 點選 **確定**。 
7. 關閉頁面。 

## <a name="create-data-model-configuration"></a>建立資料模型設定
1. 點選 **報表設定**。 
2. 點選 **建立設定** 即可打開下拉式對話方塊。 
3. 在 **名稱** 欄位，輸入「Foreign trade model」。 
4. 點選 **建立設定**。 
5. 點選 **設計工具**。 
6. 點選 **新增** 打開下拉式對話方塊。 
7. 在 **名稱** 欄位，輸入「Root」。 
8. 點選 **新增**。 
9. 點選 **新增** 打開下拉式對話方塊。 
10.    在 **名稱** 欄位，輸入「Transaction」。 
11.    在 **項目類型** 欄位中，選取 **記錄清單**。 
12.    點選 **新增**。 
13.    點選 **新增** 打開下拉式對話方塊。 
14.    在 **名稱** 欄位，輸入「Commodity code」。 
15.    在 **項目類型** 欄位中，選取 **字串**。 
16.    點選 **新增**。 
17.    點選 **新增** 打開下拉式對話方塊。 
18.    在 **名稱** 欄位，輸入「Invoiced amount」。 
19.    在 **項目類型** 欄位中，選取 **實數**。 
20.    點選 **新增**。 
21.    點選 **新增** 打開下拉式對話方塊。 
22.    在 **名稱** 欄位，輸入「Date」。 
23.    在 **項目** 類型欄位中，選取 **Date**。 
24.    點選 **新增**。 
25.    點選 **根參考**。 
26.    點選 **確定**。 
27.    點選 **儲存**。 
28.    關閉頁面。 
29.    點選 **更改狀態**。 
30.    點選 **完成**。 
31.    點選 **確定**。 

## <a name="create-model-mapping-configuration"></a>建立模型對應設定 
1. 點選 **建立設定** 即可打開下拉式對話方塊。 
2. 在 **新增** 欄位中，輸入「Model Mapping based on data model Foreign trade model」。 
3. 在 **名稱** 欄位，輸入「Foreign trade mapping」。 
4. 點選 **建立設定**。 
5. 展開 **先決條件** 區段。 
6. 點選 **編輯**。 
7. 點選 **新建**。 
8. 在清單中，標示選取的列。 
9. 在 **先決條件組件類型** 欄位，選取 **設定**。 
10.    選取 **外貿中繼資料** 設定。 
11.    點選 **儲存**。 
12.    我們對「外貿中繼資料」設定版本 1 新增了參考。 在設計此模型對應時，將提供此設定中的應用程式中繼資料。 
13.    關閉頁面。 
14.    點選 **設計工具**。 
15.    點選 **設計工具**。 
16.    在樹狀結構中，選取 **Dynamics 365 for Operations\資料表記錄**。 
17.    點選 **新增根**。 
18.    在 **名稱** 欄位，輸入「Intrastat」。 
19.    選取 **Intrastat** 表記錄。 
20.    點選 **確定**。 

> [!NOTE]
> 僅提供了 2 張表格，因為僅將 2 張表格新增到現行正在使用的中繼資料集中。 

21.    點選 **綁定**。 
22.    在樹狀結構中，展開 **Intrastat**。 
23.    在樹狀結構中，選取 **Intrastat\AmountMST**。 
24.    在樹狀結構中，展開 **交易 = Intrastat**。 
25.    在樹狀結構中，選取 **交易 = Intrastat\已開發票的金額**。 
26.    點選 **綁定**。 
27.    在樹狀結構中，選取 **Intrastat\TransDate**。 
28.    在樹狀結構中，選取 **交易 = Intrastat\日期**。 
29.    點選 **綁定**。 
30.    在樹狀結構中，展開 **Intrastat\>關聯**。 
31.    在樹狀結構中，展開 **Intrastat\>關聯\IntrastatCommodity**。 
32.    在樹狀結構中，選取 **Intrastat\>關聯\IntrastatCommodity\代碼**。 
33.    在樹狀結構中，選取 **交易 = Intrastat\商品代碼**。 
34.    點選 **綁定**。 
35.    點選 **驗證**。 

> [!NOTE]
> 我們已經成功地將資料模型的元素與資料來源項目綁定在一起，這些資料來源是透過使用參考 ER 中繼資料設定的應用程式中繼資料詳情來描述。 
36.    點選 **儲存**。 
37.    關閉頁面。 
38.    關閉頁面。 
39.    需要時，您可以展開現有的中繼資料集，然後匯出新完成的 ER 中繼資料設定版本。 然後，您可以將其匯入 RCS，並參考匯入的新版本中繼資料設定來更新已設定模型對應設定的先決條件。 

> [!NOTE]
> 這種獲取有關應用程式中繼資料資訊的方式是唯一提供內部部屬應用程式的方式 (當使用本地業務資料 (LBD) 或內部部屬模型時)。
        


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]