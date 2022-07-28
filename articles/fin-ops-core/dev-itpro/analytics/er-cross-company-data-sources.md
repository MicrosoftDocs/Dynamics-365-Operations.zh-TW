---
title: 電子報表 (ER) 中的跨公司資料來源
description: 本主題說明如何在電子報表 (ER) 中使用跨公司資料來源。
author: NickSelin
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERModelMappingDesigner, ERFormatMappingLegalEntityFilterTable
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.openlocfilehash: cfa6e61879618aede466bde3eafe582be36301e8a1609511b7e3bc3fe65ccfce
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460415"
---
# <a name="cross-company-data-sources-in-electronic-reporting-er"></a>電子報表 (ER) 中的跨公司資料來源

[!include[banner](../includes/banner.md)]

您可以設計電子報表 (ER) 格式以產生各種格式的傳出文件。 產生文件時，ER 格式會調用在相應 ER 模型對應中設定的資料來源。 若要設定對應用程式表的存取以進行記錄檢索，您可以使用 **資料表記錄** 類型的 ER 資料來源。 當存取表為共用表 (即儲存資料時不帶公司識別碼的資料表) 時，該資料來源回傳所有記錄。 當存取表是公司相關資料表 (即按公司儲存資料的資料表) 時，此資料來源僅回傳為現行公司儲存的記錄 (即 ER 格式的公司內容正在執行)。

模型對應中 **資料表記錄** 類型的每個資料來源現在都可以標記為跨公司資料來源。 因此，您可以使用 **資料表記錄** 類型的資料來源來存取應用表中的跨公司資料。

如果將資料來源標記為跨公司，則會發生以下行為：

- 對於參考除 CompanyInfo 之外的任何共用表的資料來源，該資料來源將回傳被參考表中存在的所有記錄。 
- 對於參考 CompanyInfo 表的資料來源，即使 CompanyInfo 是共用表，資料來源也會回傳包含定義範圍內公司識別碼的記錄。
- 對於任何與公司相關的表，資料來源會回傳參考表的記錄，這些記錄包含定義範圍內的公司識別碼。

在系統查詢對話方塊中，當為任何標記為跨公司的資料來源打開 **要求查詢** 選項時，您可以手動選取一個或多個公司以包括在 **公司範圍** 索引標籤上。

> [!IMPORTANT]
> 與其他過濾器一樣，當您執行 ER 格式時，公司過濾器作為查詢的最後使用值保留。 如果您更改資料來源的跨公司值，過濾器不會自動更改。 若要對另一個資料來源使用不同的跨公司值，請刪除相應的使用者特定選取。

對於標記為跨公司的每個資料來源，您可以使用 ER 運算式中的 **FILTER** 和 **WHERE** 函數選取所需的記錄。 **dataAreaID** 欄位也可以用作公司識別碼。 目前，使用 **FILTER** 函數時，**dataAreaID** 欄位僅限於以下幾種情況：

- 僅支援具有單個 **dataAreaID** 欄位比較的條件。
- 僅允許具有不依賴於記錄清單項的運算式的比較。

因此，下面的運算式是有效的。

```ER Expression
FILTER (MyTable, MyTable.dataAreaID = $StringUserInputParameter)
While shown below expressions will not pass the validation:
FILTER (MyTable, MyTable.dataAreaID = MyTable2RecordsList.MyField)
FILTER (MyTable, 
    OR(
        MyTable.dataAreaID = $StringUserInputParameter1,
        MyTable.dataAreaID = $StringUserInputParameter2
    )
)
```

在預設情況下，範圍包括現行應用程式的所有公司。 但是，它可以受到限制。 若要限制單個 ER 格式的跨公司資料存取範圍，請為該格式指派特定的組織階層。 為 ER 格式定義階層時，僅回傳指派的階層中顯示的法律實體的記錄，即使該格式調用跨公司資料來源也是如此。 當為 ER 格式定義對不再存在的階層的參考時，將應用預設範圍，並且該格式調用跨公司資料來源。 在這種情況下，將回傳所有申請公司的記錄。

請注意，當為指派給單個 ER 格式組織階層打開 **使用草稿** 選項時，該階層草稿版本中的法律實體將用於識別跨公司資料來源的範圍。 如果草稿版本不存在，則將使用此組織階層的最後發布版本中的法律實體。

請注意，當指派給單個 ER 格式組織階層的 **使用草稿** 選項關閉時，該組織階層的最後發布版本中的法律實體將用於識別跨公司資料來源的範圍。 ER 架構尚不支援組織階層的日期有效性。

可以將階層指派給特定頁面中的格式，該頁面可以從 ER 工作區或使用 **組織管理\>電子報表\>格式的法律實體過濾器** 選單項目存取。 若要存取該頁面，必須向使用者授予 **維護格式的法律實體過濾器** 權限 (ERMaintainFormatMappingLegalEntityFilters)。 除了使用者可以在系統查詢對話方塊中手動指定的限制之外，還應用了該格式的基於階層的法律實體的範圍限制。 執行格式時會使用這些限制的交集。

若要進一步了解此函數，請播放工作指南 **跨公司模式下公司依賴表的 ER 存取記錄**，它是 7.5.4.3 獲取/開發 IT 服務/解決方案組件 (10677) 業務流程的一部分，以及 可以從[Microsoft 下載中心](https://go.microsoft.com/fwlink/?linkid=874684)下載。 本工作指南將引導您完成設定 ER 模型對應和 ER 格式以在跨公司模式下存取應用程式表的過程。

下載以下檔案以完成工作指南：

- [ER 模型設定 - CrossCompanyDataAccessModel.xml](https://download.microsoft.com/download/4/2/5/4258f891-7054-4821-aedd-3721ba25fdd5/CrossCompanyDataAccessModel.xml)
- [ER 格式設定 - CrossCompanyDataAccessFormat.xml](https://download.microsoft.com/download/3/2/1/321deb75-3ba9-4323-99bf-207a52c60b5c/CrossCompanyDataAccessFormat.xml)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
