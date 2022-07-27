---
title: ER 設定格式以進行計數和求和 (第 1 章節 - 建立格式)
description: 本主題介紹如何設定電子報表格式以根據已產生的文字輸出的資料進行計數和求和。 (第 1 章節)
author: NickSelin
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERSolutionRepositoryTable, ERSolutionRepositoryCreateDropDialog, ERSolutionImport,  ERSolutionTable
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b0d1a90c0949e98b4c1e9ccb356d39de9c23b670c518ad14a99974ae2aed7301
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460438"
---
# <a name="er-configure-format-to-do-counting-and-summing-part-1---create-format"></a>ER 設定格式以進行計數和求和 (第 1 章節 - 建立格式)

[!include [banner](../../includes/banner.md)]

以下步驟說明指派給系統管理員或電子報表開發人員角色的使用者如何設定電子報表 (ER) 格式以根據已產生的文字輸出的資料進行計數和求和。 這些步驟可以在任何公司進行。

若要完成這些步驟，您必須先完成「建立設定提供者並將其標記為有效」程序中的步驟。

此程序是 Dynamics 365 for Operations 版本 1611 中增加的函數。


## <a name="get-access-to-the-list-of-configurations-provided-by-microsoft"></a>存取 Microsoft 提供的設定清單
1. 進入組織管理 > 工作區 > 電子報表。
    * 確保「Litware, Inc.」 提供者可供使用並標記為有效。  
2. 選取「Litware, Inc.」 提供者。
3. 點選存放庫。
    * 如果「營運資源」類型的存放庫已存在，則跳過現行子工作的剩餘步驟。  
4. 點選新增以開啟下拉式對話方塊。
5. 在設定存放庫類型欄位中，輸入「Operations resources」。
6. 點選建立存放庫。
7. 點選確定。

## <a name="get-the-intrastat-configurations-provided-by-microsoft"></a>取得 Microsoft 提供的 Intrastat 設定
1. 點選開啟。
2. 在樹狀結構中，選取「Intrastat model\Intrastat (DE)」。
3. 點選匯入。
    * 對於所選設定的 1.1 版，點選匯入。  
4. 點選是。
5. 關閉頁面。
6. 關閉頁面。
7. 點選報表設定。
8. 在樹狀結構中，展開「Intrastat model」。
9. 在樹狀結構中，選取「Intrastat model\Intrastat (DE)」。



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]