---
title: ER 使用水平擴展範圍在 Excel 報表中動態新增資料欄 (第 2 章節 - 執行格式)
description: 本主題介紹如何設定電子報表 (ER) 格式以將報表產生為 OPENXML 工作表 (Excel) 檔案。 (第 2 章節)
author: NickSelin
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, SysQueryForm
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 22a7b2ce07aa172ab759d6e18d34afd7aa21609acc7fe5fc691244b66c4379a6
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460463"
---
# <a name="er-use-horizontally-expandable-ranges-to-dynamically-add-columns-in-excel-reports-part-2---run-format"></a>ER 使用水平擴展範圍在 Excel 報表中動態新增資料欄 (第 2 章節 - 執行格式)

[!include [banner](../../includes/banner.md)]

以下步驟說明指派給系統管理員或電子報表開發人員角色的使用者如何設定電子報表 (ER) 格式以將報表產生為 OPENXML 工作表 (Excel) 檔案，其中可以將所需資料欄動態建立為水平擴展範圍。 這些步驟可以在 DEMF 公司進行。

若要完成這些步驟，您必須先完成「ER 使用水平可擴展範圍在 Excel 報表中動態新增資料欄 (第 1 章節：設計格式)」程序中的步驟。

此程序是 Dynamics 365 for Operations 版本 1611 中增加的函數。


## <a name="find-created-format"></a>尋找已建立的格式
1. 進入組織管理 > 電子報表 > 設定。
2. 在樹狀結構中，展開「財務維度樣本模型」。
3. 在樹狀結構中，選取「財務維度範例模型\具有水平可擴展範圍的範例報表」。

## <a name="execute-format-to-create-excel-output"></a>執行格式以建立 Excel 輸出
1. 點選執行。
2. 在維度名稱欄位中，輸入「BusinessUnit;CostCenter;Department」。
    * 在維度名稱欄位中，輸入或選取一個值。  若要選取現行公司的所有維度，請輸入以下內容：BusinessUnit;CostCenter;Department;ItemGroup;MainAccount;Project  
3. 展開記錄以包含區段。
4. 點選「篩選」。
5. 選取分類帳日記帳表和日記帳批號欄位的資料列。
6. 在條件欄位中，輸入「00057..00058」。
    * 00057..00058  
7. 點選確定。
8. 點選確定。
    * 查看產生的輸出。 請注意，新建立的 Excel 檔案包含為財務維度選取的相同數量的資料欄。 這些資料欄中的報表標題代表財務維度的名稱。 這些資料欄中的交易明細代表財務維度。 執行此報表並選取不同的維度，以查看報表不依賴於所選維度的數量或為此實體設定的維度數量。  



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]