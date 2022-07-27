---
title: ER 使用財務維度作為資料來源 (第 4 章節 - 執行報表)
description: 本主題介紹如何設定電子報表 (ER) 模型以使用財務維度作為 ER 報表的資料來源。 (第 4 章節)
author: NickSelin
ms.date: 05/27/2020
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
ms.openlocfilehash: f14be560ab014224e32169b4ac97682a669249b4
ms.sourcegitcommit: 25b3dd639e41d040c2714f56deadaa0906e4b493
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/06/2021
ms.locfileid: "8460439"
---
# <a name="er-use-financial-dimensions-as-a-data-source-part-4---run-the-report"></a>ER 使用財務維度作為資料來源 (第 4 章節 - 執行報表)

[!include [banner](../../includes/banner.md)]

以下步驟說明指派給系統管理員或電子報表開發人員角色的使用者如何設定電子報表 (ER) 模型以使用財務維度作為 ER 報表的資料來源。 這些步驟可以在 DEMF 公司進行。

若要完成這些步驟，您必須先完成「ER 使用財務維度作為資料來源 (第 3 章節：設計報表)」程序中的步驟。 您還必須在電子報表參數頁面上設定預設文件類型。 當您下載和匯入任何 ER 設定時，也會設定預設文件類型。 


## <a name="run-report"></a>執行報表
1. 進入組織管理 > 電子報表 > 設定。
2. 在樹狀結構中，展開「財務維度樣本模型」。
3. 在樹狀結構中，選取「財務維度樣本模型\分類帳日記帳報表」。
4. 點選執行。
![ER 設定頁面。](../media/er-financial-dimensions-guides-run1.png)
5. 在維度名稱欄位中，輸入或選取一個值。
    * 若要選取現行公司中的所有維度，請輸入以下信息：BusinessUnit;CostCenter;Department;ItemGroup;MainAccount;Project  
![電子報表參數滑出，維度名稱下拉式。](../media/er-financial-dimensions-guides-run2.png)
6. 展開記錄以包含區段。
7. 點選「篩選」。
8. 選取分類帳日記帳表和日記帳批號欄位的資料列。
9. 在條件欄位中，輸入「00057」。
10. 點選確定。
11. 點選確定。
![電子報表參數滑出，要加入區段的報表。](../media/er-financial-dimensions-guides-run3.png)
    * 查看產生的輸出。 對於所選批次的每筆交易，都會顯示相應維度集中的財務維度。 執行此報表並選取不同的維度，以查看報表不依賴於所選維度的數量或為此實體設定的維度數量。  
![ER 設定產生輸出。](../media/er-financial-dimensions-guides-run4.png)


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
