---
title: 建立格式時選取資料模型定義
description: 若要完成此過程中的步驟，您必須先完成該程序：ER 建立設定提供者並將其標記為有效。
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
ms.openlocfilehash: 34e6c8df735976ca0f7805fe3e06f141d38abf12faf02ff66195339147aa5405
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460325"
---
# <a name="select-data-model-definitions-when-you-create-formats"></a>建立格式時選取資料模型定義

[!include [banner](../../includes/banner.md)]

若要完成此過程中的步驟，您必須先完成該程序：ER 建立設定提供者並將其標記為有效。 

此程序顯示如何選取模型的根項目作為資料模型定義，以插入旨在產生電子文件的電子報表 (ER) 格式設定。 在此程序中，您將為範例公司 Litware, Inc. 新增新的 ER 格式設定。 

此程序適用於指派有系統管理員或電子報表開發人員角色的使用者。 可以使用任何資料集完成這些步驟。

1. 進入組織管理 > 工作區 > 電子報表。
    * 確保樣本公司 Litware, Inc. 的設定提供者可用並標記為有效。 如果您沒有看到此設定廠商，請完成「建立設定廠商並將其標記為有效」程序中的步驟。  
2. 點選報表設定。

## <a name="add-a-new-er-data-model-configuration"></a>新增新的 ER 資料模型設定
1. 點選建立設定即可打開下拉式對話方塊。
    * 我們新增了一個新的 ER 模型設定，其中包含一個資料模型，該模型旨在用作產生 ER 報表的資料來源。  
2. 在名稱欄位，輸入「付款模式 (虛構)」。
    * 付款模式 (虛構)  
3. 點選建立設定。
4. 點選設計工具。
    * 打開 ER 設計工具以指定此設定的資料模型的結構。  
    * 假設我們設計付款業務領域的資料模型以支援 2 種支付方式 - 貸記轉帳和直接借記。  
5. 按一下新增以開啟下拉式對話方塊。
6. 在名稱欄位，輸入「付款 - 貸記轉帳」。
    * 付款 - 貸記轉帳  
7. 選點新增。
8. 按一下新增以開啟下拉式對話方塊。
9. 在作為欄位的新節點中，輸入「Model root」。
10. 在名稱欄位，輸入「付款 - 直接借記」。
    * 付款 - 直接借記  
11. 選點新增。
12. 點選儲存。
13. 關閉頁面。
14. 點選更改狀態。
    * 完成模型的草稿版本，使其以新的模型對應和格式可供使用。  
15. 點選完成。
16. 點選確定。

## <a name="start-to-enter-a-new-er-format-configuration"></a>開始輸入新的 ER 格式設定
1. 點選建立設定即可打開下拉式對話方塊。
2. 在新增欄位中，輸入「基於資料模型的格式付款模型 (虛構)」。
3. 在資料模型定義欄位中，輸入或選取一個值。
    * 請注意，所選資料模型的所有根項目目前都可供選取作為資料模型定義。 您可以使用資料模型的任何必需根項目繼續設計您的格式。 所選根項目的遺失模型對應不會阻止您繼續。  
4. 關閉頁面。

## <a name="add-a-new-er-model-mapping-configuration"></a>新增新的 ER 模型對應設定
1. 點選建立設定即可打開下拉式對話方塊。
2. 在新增欄位中，輸入「基於資料模型的模型對應付款模型 (虛構)」。
3. 在名稱欄位，輸入「付款模型對應 (虛構)」。
    * 付款模式對應 (虛構)  
4. 在資料模型定義欄位中，輸入或選取一個值。
5. 點選建立設定。

## <a name="design-er-model-mappings"></a>設計 ER 模型對應
1. 點選設計工具。
    * 使用 ER 設計工具指定所需根項的模型對應。  
2. 點選設計工具。
    * 為選定模型的根項目模擬選定模型對應的設定。  
3. 在樹狀結構中，選取「Dynamics 365 for Operations\資料表記錄」。
4. 點選新增根。
5. 在名稱欄位，輸入「分類帳」。
6. 在資料表欄位，輸入「LedgerJournalTrans」。
    * LedgerJournalTrans  
7. 點選確定。
8. 點選儲存。
9. 關閉頁面。
10. 關閉頁面。

## <a name="start-to-enter-another-new-er-format-configuration"></a>開始輸入另一個新 ER 格式設定
1. 在樹狀結構中，選取「付款模型 (虛構)」。
2. 點選建立設定即可打開下拉式對話方塊。
3. 在新增欄位中，輸入「基於資料模型的格式付款模型 (虛構)」。
4. 在資料模型定義欄位中，輸入或選取一個值。
    * 請注意，現在只有一個根項目可用於對應到應用程式資料來源。 當引入至少一個模型對應時，只有對應到應用程式資料來源的模型根項才能被選為模型定義，同時新增 ER 格式。   
5. 關閉頁面。



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]